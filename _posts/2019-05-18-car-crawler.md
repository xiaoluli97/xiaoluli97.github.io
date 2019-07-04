---
layout:     post
title:      车辆信息爬取
subtitle:   爬虫说明
date:       2019-05-18
author:     Xiaolu
header-img: img/post-bg-car.jpg
catalog: true
tags:
    - Python - 爬虫
---
## 简介

这是一个用于[《道路机动车辆生产企业及产品公告》新产品公示](http://www.miit.gov.cn/datainfo/resultSearch?searchType=advancedSearch&categoryTreeId=1128)信息爬取的爬虫程序。


```python
import pandas as pd
import requests
from bs4 import BeautifulSoup
import re 
import random
import time
import datetime
import math
```

## 定义Header

这一步的目的在于将程序伪装成浏览器，从而防止被网站识别进而阻挡爬取。


```python
def get_headers():
    '''
    随机获取一个headers
    '''
    user_agents =  ['Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1','Mozilla/5.0 (Windows; U; Windows NT 6.1; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50','Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11']
    headers = {'User-Agent':random.choice(user_agents)}
    return headers
```

## 抓取每个车辆信息的ID

在每一个车辆具体信息页面中，我们可以观察到其唯一的ID。我们将每个页面的ID数字爬取下来便可以访问所有车辆信息页面。


```python
def getID():
    print('<<<<<<<<<<<<<<<<<<<< Scraping Starts! >>>>>>>>>>>>>>>>>>>>')
    url='http://www.miit.gov.cn/datainfo/resultSearch?searchType=advancedSearch&categoryTreeId=1128&pagenow={}'
    res=requests.get(url.format(1),headers=get_headers())
    res.encoding='utf-8'
    soup=BeautifulSoup(res.text,'html.parser')
    num=soup.find_all('a',attrs={"href":"javascript:void(0);"})[0].text
    info_num=int(re.findall("\d+",num)[0])
    page_num=math.ceil(info_num/30)
    last_page_num=info_num%30

    code=[]
    key="纯电动|插电式|燃料电池"
    for page in range(1,page_num+1):
        if page==page_num:
            page_url=url.format(page)
            res=requests.get(page_url,headers=get_headers())
            res.encoding='utf-8'
            soup=BeautifulSoup(res.text,'html.parser')
            each_page=soup.find_all('table',attrs={"class":"table table-bordered table-responsive"})[0].find_all('td')
            print('Page'+str(page)+' is completed')
            for i in range(3,last_page_num*5,5):    #最后一页
                if re.findall(key,each_page[i].text.strip())!=[]:
                    code.append(each_page[i].find_all('a')[0]['href'].lstrip('/datainfo/viewCar?carId='))
        else:
            page_url=url.format(page)
            while True:
                try:
                    res=requests.get(page_url,headers=get_headers())
                except requests.exceptions.ConnectionError:    #连接异常处理，保证程序持续运行
                    print('ConnectionError -- please wait 3 seconds')
                    time.sleep(3)
                else:
                    res.encoding='utf-8'
                    soup=BeautifulSoup(res.text,'html.parser')
                    each_page=soup.find_all('table',attrs={"class":"table table-bordered table-responsive"})[0].find_all('td')
                    print('Page'+str(page)+' is completed')
                    for i in range(3,150,5):
                    	if re.findall(key,each_page[i].text.strip())!=[]:
                    		code.append(each_page[i].find_all('a')[0]['href'].lstrip('/datainfo/viewCar?carId='))
                    break
    print('There are in total '+str(len(code))+' vehicles')
    return code
```


## 定义车辆信息页面抓取函数

通过对页面结构进行分析，我们定义一个函数将需要的信息抓取下来，并储存到`result`之中。


```python
def getPage(url):
    result={}
    car_url=url
    r=requests.get(car_url,headers=get_headers())
    r.encoding='utf-8'
    soup_car=BeautifulSoup(r.text,'html.parser')
    total=soup_car.select('td')
    result['产品商标']=total[0].text
    result['产品型号']=total[1].text
    result['产品名称']=total[2].text
    result['企业名称']=total[3].text
    result['注册地址']=total[4].text
    result['生产地址']=total[6].text
    result['外形尺寸']=total[8].text
    result['燃料种类']=total[11].text
    result['最高车速']=total[12].text
    result['整备质量kg']=total[17].text
    result['轴距mm']=total[20].text
    result['其他']=total[35].text
    result['发动机企业']=total[44].text
    result['排量ml']=total[45].text
    result['功率kw']=total[46].text
    return result
```

## 定义爬取函数

之前我们获得了每辆车的页面ID，通过循环调用ID可以进入到每辆车的信息页面之中，然后再调用以上定义的页面抓取函数便可以把所有页面的信息抓取下来。


```python
def vehicle_scraping(path):    
    url='http://www.miit.gov.cn/datainfo/viewCar?carId={}'
    all_car=[]
    code=getID()
    print('<<<<<<<<<<<<<<<<<<<< Scraping Vehicle Information >>>>>>>>>>>>>>>>>>>>')
    for i in range(0,len(code)):
        each_car_url=url.format(code[i])
        while True:    #不断尝试直到成功访问
                try:
                    each_car=getPage(each_car_url)
                except requests.exceptions.ConnectionError:    #连接异常处理，保证程序持续运行
                    print('ConnectionError -- please wait 3 seconds')
                    time.sleep(3)
                else:
                    all_car.append(each_car)
                    if i%100==0 or i==len(code)-1:
                        print('Scraped '+str(len(all_car))) 
                        print(datetime.datetime.now())
                    else:
                        time.sleep(random.randint(0,2))  #防止访问速度过快
                    break
    df=pd.DataFrame(all_car)
    df.to_csv(path,index=False,header=True,encoding='utf_8_sig')
    print('<<<<<<<<<<<<<<<<<<<< Scraping Ends! >>>>>>>>>>>>>>>>>>>>')
```

## 执行爬取程序

最后执行爬取程序，并将结果存储到所选择的本地路径。

```python
if __name__ == '__main__':
    print('请选择文件储存路径 例如：C:/Documents/all_vehicle.csv')
    root = tk.Tk()    # 创建一个Tkinter.Tk()实例
    root.withdraw()       # 将Tkinter.Tk()实例隐藏
    path=tk.filedialog.asksaveasfilename(title=u'保存文件', filetypes=[("CSV", ".csv")])
    vehicle_scraping(path)
    print('程序将于10秒后关闭')
    time.sleep(10)
```
