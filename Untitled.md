

```python
import numpy as np # linear algebra
import pandas as pd
```


```python
data=pd.read_csv("C:/Documents/Microeconometrics/Assignments2/videogamesales/vgsales.csv")
data.info
```




    <bound method DataFrame.info of         Rank                                               Name Platform  \
    0          1                                         Wii Sports      Wii   
    1          2                                  Super Mario Bros.      NES   
    2          3                                     Mario Kart Wii      Wii   
    3          4                                  Wii Sports Resort      Wii   
    4          5                           Pokemon Red/Pokemon Blue       GB   
    5          6                                             Tetris       GB   
    6          7                              New Super Mario Bros.       DS   
    7          8                                           Wii Play      Wii   
    8          9                          New Super Mario Bros. Wii      Wii   
    9         10                                          Duck Hunt      NES   
    10        11                                         Nintendogs       DS   
    11        12                                      Mario Kart DS       DS   
    12        13                        Pokemon Gold/Pokemon Silver       GB   
    13        14                                            Wii Fit      Wii   
    14        15                                       Wii Fit Plus      Wii   
    15        16                                 Kinect Adventures!     X360   
    16        17                                 Grand Theft Auto V      PS3   
    17        18                      Grand Theft Auto: San Andreas      PS2   
    18        19                                  Super Mario World     SNES   
    19        20       Brain Age: Train Your Brain in Minutes a Day       DS   
    20        21                      Pokemon Diamond/Pokemon Pearl       DS   
    21        22                                   Super Mario Land       GB   
    22        23                                Super Mario Bros. 3      NES   
    23        24                                 Grand Theft Auto V     X360   
    24        25                        Grand Theft Auto: Vice City      PS2   
    25        26                      Pokemon Ruby/Pokemon Sapphire      GBA   
    26        27                        Pokemon Black/Pokemon White       DS   
    27        28        Brain Age 2: More Training in Minutes a Day       DS   
    28        29                             Gran Turismo 3: A-Spec      PS2   
    29        30                     Call of Duty: Modern Warfare 3     X360   
    ...      ...                                                ...      ...   
    16568  16571                                        XI Coliseum      PSP   
    16569  16572                                 Resident Evil 4 HD     XOne   
    16570  16573                      Farming 2017 - The Simulation      PS4   
    16571  16574         Grisaia no Kajitsu: La Fruit de la Grisaia      PSP   
    16572  16575                   Scarlett: Nichijou no Kyoukaisen      PS2   
    16573  16576                                Mini Desktop Racing      Wii   
    16574  16577  Yattaman Wii: BikkuriDokkiri Machine de Mou Ra...      Wii   
    16575  16578                              Neo Angelique Special      PSP   
    16576  16579                                  Rugby Challenge 3     XOne   
    16577  16580                                          Damnation       PC   
    16578  16581                      Outdoors Unleashed: Africa 3D      3DS   
    16579  16582                                  PGA European Tour      N64   
    16580  16583                                          Real Rode      PS2   
    16581  16584                                          Fit & Fun      Wii   
    16582  16585                                    Planet Monsters      GBA   
    16583  16586                                     Carmageddon 64      N64   
    16584  16587                                   Bust-A-Move 3000       GC   
    16585  16588                                             Breach       PC   
    16586  16589                     Secret Files 2: Puritas Cordis       DS   
    16587  16590                           Mezase!! Tsuri Master DS       DS   
    16588  16591                                   Mega Brain Boost       DS   
    16589  16592  Chou Ezaru wa Akai Hana: Koi wa Tsuki ni Shiru...      PSV   
    16590  16593  Eiyuu Densetsu: Sora no Kiseki Material Collec...      PSP   
    16591  16594                                Myst IV: Revelation       PC   
    16592  16595                                           Plushees       DS   
    16593  16596                 Woody Woodpecker in Crazy Castle 5      GBA   
    16594  16597                      Men in Black II: Alien Escape       GC   
    16595  16598   SCORE International Baja 1000: The Official Game      PS2   
    16596  16599                                         Know How 2       DS   
    16597  16600                                   Spirits & Spells      GBA   
    
             Year         Genre                    Publisher  NA_Sales  EU_Sales  \
    0      2006.0        Sports                     Nintendo     41.49     29.02   
    1      1985.0      Platform                     Nintendo     29.08      3.58   
    2      2008.0        Racing                     Nintendo     15.85     12.88   
    3      2009.0        Sports                     Nintendo     15.75     11.01   
    4      1996.0  Role-Playing                     Nintendo     11.27      8.89   
    5      1989.0        Puzzle                     Nintendo     23.20      2.26   
    6      2006.0      Platform                     Nintendo     11.38      9.23   
    7      2006.0          Misc                     Nintendo     14.03      9.20   
    8      2009.0      Platform                     Nintendo     14.59      7.06   
    9      1984.0       Shooter                     Nintendo     26.93      0.63   
    10     2005.0    Simulation                     Nintendo      9.07     11.00   
    11     2005.0        Racing                     Nintendo      9.81      7.57   
    12     1999.0  Role-Playing                     Nintendo      9.00      6.18   
    13     2007.0        Sports                     Nintendo      8.94      8.03   
    14     2009.0        Sports                     Nintendo      9.09      8.59   
    15     2010.0          Misc       Microsoft Game Studios     14.97      4.94   
    16     2013.0        Action         Take-Two Interactive      7.01      9.27   
    17     2004.0        Action         Take-Two Interactive      9.43      0.40   
    18     1990.0      Platform                     Nintendo     12.78      3.75   
    19     2005.0          Misc                     Nintendo      4.75      9.26   
    20     2006.0  Role-Playing                     Nintendo      6.42      4.52   
    21     1989.0      Platform                     Nintendo     10.83      2.71   
    22     1988.0      Platform                     Nintendo      9.54      3.44   
    23     2013.0        Action         Take-Two Interactive      9.63      5.31   
    24     2002.0        Action         Take-Two Interactive      8.41      5.49   
    25     2002.0  Role-Playing                     Nintendo      6.06      3.90   
    26     2010.0  Role-Playing                     Nintendo      5.57      3.28   
    27     2005.0        Puzzle                     Nintendo      3.44      5.36   
    28     2001.0        Racing  Sony Computer Entertainment      6.85      5.09   
    29     2011.0       Shooter                   Activision      9.03      4.28   
    ...       ...           ...                          ...       ...       ...   
    16568  2006.0        Puzzle  Sony Computer Entertainment      0.00      0.00   
    16569  2016.0       Shooter                       Capcom      0.01      0.00   
    16570  2016.0    Simulation            UIG Entertainment      0.00      0.01   
    16571  2013.0     Adventure                    Prototype      0.00      0.00   
    16572  2008.0     Adventure              Kadokawa Shoten      0.00      0.00   
    16573  2007.0        Racing               Popcorn Arcade      0.01      0.00   
    16574  2008.0        Racing                  Takara Tomy      0.00      0.00   
    16575  2008.0     Adventure                   Tecmo Koei      0.00      0.00   
    16576  2016.0        Sports         Alternative Software      0.00      0.01   
    16577  2009.0       Shooter                  Codemasters      0.00      0.01   
    16578  2011.0        Sports                      Mastiff      0.01      0.00   
    16579  2000.0        Sports                   Infogrames      0.01      0.00   
    16580  2008.0     Adventure              Kadokawa Shoten      0.00      0.00   
    16581  2011.0        Sports                      Unknown      0.00      0.01   
    16582  2001.0        Action                        Titus      0.01      0.00   
    16583  1999.0        Action           Virgin Interactive      0.01      0.00   
    16584  2003.0        Puzzle                      Ubisoft      0.01      0.00   
    16585  2011.0       Shooter                    Destineer      0.01      0.00   
    16586  2009.0     Adventure                  Deep Silver      0.00      0.01   
    16587  2009.0        Sports                  Hudson Soft      0.00      0.00   
    16588  2008.0        Puzzle        Majesco Entertainment      0.01      0.00   
    16589  2016.0        Action              dramatic create      0.00      0.00   
    16590  2007.0  Role-Playing           Falcom Corporation      0.00      0.00   
    16591  2004.0     Adventure                      Ubisoft      0.01      0.00   
    16592  2008.0    Simulation                    Destineer      0.01      0.00   
    16593  2002.0      Platform                        Kemco      0.01      0.00   
    16594  2003.0       Shooter                   Infogrames      0.01      0.00   
    16595  2008.0        Racing                   Activision      0.00      0.00   
    16596  2010.0        Puzzle                     7G//AMES      0.00      0.01   
    16597  2003.0      Platform                      Wanadoo      0.01      0.00   
    
           JP_Sales  Other_Sales  Global_Sales  
    0          3.77         8.46         82.74  
    1          6.81         0.77         40.24  
    2          3.79         3.31         35.82  
    3          3.28         2.96         33.00  
    4         10.22         1.00         31.37  
    5          4.22         0.58         30.26  
    6          6.50         2.90         30.01  
    7          2.93         2.85         29.02  
    8          4.70         2.26         28.62  
    9          0.28         0.47         28.31  
    10         1.93         2.75         24.76  
    11         4.13         1.92         23.42  
    12         7.20         0.71         23.10  
    13         3.60         2.15         22.72  
    14         2.53         1.79         22.00  
    15         0.24         1.67         21.82  
    16         0.97         4.14         21.40  
    17         0.41        10.57         20.81  
    18         3.54         0.55         20.61  
    19         4.16         2.05         20.22  
    20         6.04         1.37         18.36  
    21         4.18         0.42         18.14  
    22         3.84         0.46         17.28  
    23         0.06         1.38         16.38  
    24         0.47         1.78         16.15  
    25         5.38         0.50         15.85  
    26         5.65         0.82         15.32  
    27         5.32         1.18         15.30  
    28         1.87         1.16         14.98  
    29         0.13         1.32         14.76  
    ...         ...          ...           ...  
    16568      0.01         0.00          0.01  
    16569      0.00         0.00          0.01  
    16570      0.00         0.00          0.01  
    16571      0.01         0.00          0.01  
    16572      0.01         0.00          0.01  
    16573      0.00         0.00          0.01  
    16574      0.01         0.00          0.01  
    16575      0.01         0.00          0.01  
    16576      0.00         0.00          0.01  
    16577      0.00         0.00          0.01  
    16578      0.00         0.00          0.01  
    16579      0.00         0.00          0.01  
    16580      0.01         0.00          0.01  
    16581      0.00         0.00          0.01  
    16582      0.00         0.00          0.01  
    16583      0.00         0.00          0.01  
    16584      0.00         0.00          0.01  
    16585      0.00         0.00          0.01  
    16586      0.00         0.00          0.01  
    16587      0.01         0.00          0.01  
    16588      0.00         0.00          0.01  
    16589      0.01         0.00          0.01  
    16590      0.01         0.00          0.01  
    16591      0.00         0.00          0.01  
    16592      0.00         0.00          0.01  
    16593      0.00         0.00          0.01  
    16594      0.00         0.00          0.01  
    16595      0.00         0.00          0.01  
    16596      0.00         0.00          0.01  
    16597      0.00         0.00          0.01  
    
    [16598 rows x 11 columns]>




```python
data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>Name</th>
      <th>Platform</th>
      <th>Year</th>
      <th>Genre</th>
      <th>Publisher</th>
      <th>NA_Sales</th>
      <th>EU_Sales</th>
      <th>JP_Sales</th>
      <th>Other_Sales</th>
      <th>Global_Sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Wii Sports</td>
      <td>Wii</td>
      <td>2006.0</td>
      <td>Sports</td>
      <td>Nintendo</td>
      <td>41.49</td>
      <td>29.02</td>
      <td>3.77</td>
      <td>8.46</td>
      <td>82.74</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Super Mario Bros.</td>
      <td>NES</td>
      <td>1985.0</td>
      <td>Platform</td>
      <td>Nintendo</td>
      <td>29.08</td>
      <td>3.58</td>
      <td>6.81</td>
      <td>0.77</td>
      <td>40.24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Mario Kart Wii</td>
      <td>Wii</td>
      <td>2008.0</td>
      <td>Racing</td>
      <td>Nintendo</td>
      <td>15.85</td>
      <td>12.88</td>
      <td>3.79</td>
      <td>3.31</td>
      <td>35.82</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Wii Sports Resort</td>
      <td>Wii</td>
      <td>2009.0</td>
      <td>Sports</td>
      <td>Nintendo</td>
      <td>15.75</td>
      <td>11.01</td>
      <td>3.28</td>
      <td>2.96</td>
      <td>33.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Pokemon Red/Pokemon Blue</td>
      <td>GB</td>
      <td>1996.0</td>
      <td>Role-Playing</td>
      <td>Nintendo</td>
      <td>11.27</td>
      <td>8.89</td>
      <td>10.22</td>
      <td>1.00</td>
      <td>31.37</td>
    </tr>
  </tbody>
</table>
</div>




```python
data.dropna(how="any",inplace=True)
```


```python
data.info
```




    <bound method DataFrame.info of         Rank                                               Name Platform  \
    0          1                                         Wii Sports      Wii   
    1          2                                  Super Mario Bros.      NES   
    2          3                                     Mario Kart Wii      Wii   
    3          4                                  Wii Sports Resort      Wii   
    4          5                           Pokemon Red/Pokemon Blue       GB   
    5          6                                             Tetris       GB   
    6          7                              New Super Mario Bros.       DS   
    7          8                                           Wii Play      Wii   
    8          9                          New Super Mario Bros. Wii      Wii   
    9         10                                          Duck Hunt      NES   
    10        11                                         Nintendogs       DS   
    11        12                                      Mario Kart DS       DS   
    12        13                        Pokemon Gold/Pokemon Silver       GB   
    13        14                                            Wii Fit      Wii   
    14        15                                       Wii Fit Plus      Wii   
    15        16                                 Kinect Adventures!     X360   
    16        17                                 Grand Theft Auto V      PS3   
    17        18                      Grand Theft Auto: San Andreas      PS2   
    18        19                                  Super Mario World     SNES   
    19        20       Brain Age: Train Your Brain in Minutes a Day       DS   
    20        21                      Pokemon Diamond/Pokemon Pearl       DS   
    21        22                                   Super Mario Land       GB   
    22        23                                Super Mario Bros. 3      NES   
    23        24                                 Grand Theft Auto V     X360   
    24        25                        Grand Theft Auto: Vice City      PS2   
    25        26                      Pokemon Ruby/Pokemon Sapphire      GBA   
    26        27                        Pokemon Black/Pokemon White       DS   
    27        28        Brain Age 2: More Training in Minutes a Day       DS   
    28        29                             Gran Turismo 3: A-Spec      PS2   
    29        30                     Call of Duty: Modern Warfare 3     X360   
    ...      ...                                                ...      ...   
    16568  16571                                        XI Coliseum      PSP   
    16569  16572                                 Resident Evil 4 HD     XOne   
    16570  16573                      Farming 2017 - The Simulation      PS4   
    16571  16574         Grisaia no Kajitsu: La Fruit de la Grisaia      PSP   
    16572  16575                   Scarlett: Nichijou no Kyoukaisen      PS2   
    16573  16576                                Mini Desktop Racing      Wii   
    16574  16577  Yattaman Wii: BikkuriDokkiri Machine de Mou Ra...      Wii   
    16575  16578                              Neo Angelique Special      PSP   
    16576  16579                                  Rugby Challenge 3     XOne   
    16577  16580                                          Damnation       PC   
    16578  16581                      Outdoors Unleashed: Africa 3D      3DS   
    16579  16582                                  PGA European Tour      N64   
    16580  16583                                          Real Rode      PS2   
    16581  16584                                          Fit & Fun      Wii   
    16582  16585                                    Planet Monsters      GBA   
    16583  16586                                     Carmageddon 64      N64   
    16584  16587                                   Bust-A-Move 3000       GC   
    16585  16588                                             Breach       PC   
    16586  16589                     Secret Files 2: Puritas Cordis       DS   
    16587  16590                           Mezase!! Tsuri Master DS       DS   
    16588  16591                                   Mega Brain Boost       DS   
    16589  16592  Chou Ezaru wa Akai Hana: Koi wa Tsuki ni Shiru...      PSV   
    16590  16593  Eiyuu Densetsu: Sora no Kiseki Material Collec...      PSP   
    16591  16594                                Myst IV: Revelation       PC   
    16592  16595                                           Plushees       DS   
    16593  16596                 Woody Woodpecker in Crazy Castle 5      GBA   
    16594  16597                      Men in Black II: Alien Escape       GC   
    16595  16598   SCORE International Baja 1000: The Official Game      PS2   
    16596  16599                                         Know How 2       DS   
    16597  16600                                   Spirits & Spells      GBA   
    
             Year         Genre                    Publisher  NA_Sales  EU_Sales  \
    0      2006.0        Sports                     Nintendo     41.49     29.02   
    1      1985.0      Platform                     Nintendo     29.08      3.58   
    2      2008.0        Racing                     Nintendo     15.85     12.88   
    3      2009.0        Sports                     Nintendo     15.75     11.01   
    4      1996.0  Role-Playing                     Nintendo     11.27      8.89   
    5      1989.0        Puzzle                     Nintendo     23.20      2.26   
    6      2006.0      Platform                     Nintendo     11.38      9.23   
    7      2006.0          Misc                     Nintendo     14.03      9.20   
    8      2009.0      Platform                     Nintendo     14.59      7.06   
    9      1984.0       Shooter                     Nintendo     26.93      0.63   
    10     2005.0    Simulation                     Nintendo      9.07     11.00   
    11     2005.0        Racing                     Nintendo      9.81      7.57   
    12     1999.0  Role-Playing                     Nintendo      9.00      6.18   
    13     2007.0        Sports                     Nintendo      8.94      8.03   
    14     2009.0        Sports                     Nintendo      9.09      8.59   
    15     2010.0          Misc       Microsoft Game Studios     14.97      4.94   
    16     2013.0        Action         Take-Two Interactive      7.01      9.27   
    17     2004.0        Action         Take-Two Interactive      9.43      0.40   
    18     1990.0      Platform                     Nintendo     12.78      3.75   
    19     2005.0          Misc                     Nintendo      4.75      9.26   
    20     2006.0  Role-Playing                     Nintendo      6.42      4.52   
    21     1989.0      Platform                     Nintendo     10.83      2.71   
    22     1988.0      Platform                     Nintendo      9.54      3.44   
    23     2013.0        Action         Take-Two Interactive      9.63      5.31   
    24     2002.0        Action         Take-Two Interactive      8.41      5.49   
    25     2002.0  Role-Playing                     Nintendo      6.06      3.90   
    26     2010.0  Role-Playing                     Nintendo      5.57      3.28   
    27     2005.0        Puzzle                     Nintendo      3.44      5.36   
    28     2001.0        Racing  Sony Computer Entertainment      6.85      5.09   
    29     2011.0       Shooter                   Activision      9.03      4.28   
    ...       ...           ...                          ...       ...       ...   
    16568  2006.0        Puzzle  Sony Computer Entertainment      0.00      0.00   
    16569  2016.0       Shooter                       Capcom      0.01      0.00   
    16570  2016.0    Simulation            UIG Entertainment      0.00      0.01   
    16571  2013.0     Adventure                    Prototype      0.00      0.00   
    16572  2008.0     Adventure              Kadokawa Shoten      0.00      0.00   
    16573  2007.0        Racing               Popcorn Arcade      0.01      0.00   
    16574  2008.0        Racing                  Takara Tomy      0.00      0.00   
    16575  2008.0     Adventure                   Tecmo Koei      0.00      0.00   
    16576  2016.0        Sports         Alternative Software      0.00      0.01   
    16577  2009.0       Shooter                  Codemasters      0.00      0.01   
    16578  2011.0        Sports                      Mastiff      0.01      0.00   
    16579  2000.0        Sports                   Infogrames      0.01      0.00   
    16580  2008.0     Adventure              Kadokawa Shoten      0.00      0.00   
    16581  2011.0        Sports                      Unknown      0.00      0.01   
    16582  2001.0        Action                        Titus      0.01      0.00   
    16583  1999.0        Action           Virgin Interactive      0.01      0.00   
    16584  2003.0        Puzzle                      Ubisoft      0.01      0.00   
    16585  2011.0       Shooter                    Destineer      0.01      0.00   
    16586  2009.0     Adventure                  Deep Silver      0.00      0.01   
    16587  2009.0        Sports                  Hudson Soft      0.00      0.00   
    16588  2008.0        Puzzle        Majesco Entertainment      0.01      0.00   
    16589  2016.0        Action              dramatic create      0.00      0.00   
    16590  2007.0  Role-Playing           Falcom Corporation      0.00      0.00   
    16591  2004.0     Adventure                      Ubisoft      0.01      0.00   
    16592  2008.0    Simulation                    Destineer      0.01      0.00   
    16593  2002.0      Platform                        Kemco      0.01      0.00   
    16594  2003.0       Shooter                   Infogrames      0.01      0.00   
    16595  2008.0        Racing                   Activision      0.00      0.00   
    16596  2010.0        Puzzle                     7G//AMES      0.00      0.01   
    16597  2003.0      Platform                      Wanadoo      0.01      0.00   
    
           JP_Sales  Other_Sales  Global_Sales  
    0          3.77         8.46         82.74  
    1          6.81         0.77         40.24  
    2          3.79         3.31         35.82  
    3          3.28         2.96         33.00  
    4         10.22         1.00         31.37  
    5          4.22         0.58         30.26  
    6          6.50         2.90         30.01  
    7          2.93         2.85         29.02  
    8          4.70         2.26         28.62  
    9          0.28         0.47         28.31  
    10         1.93         2.75         24.76  
    11         4.13         1.92         23.42  
    12         7.20         0.71         23.10  
    13         3.60         2.15         22.72  
    14         2.53         1.79         22.00  
    15         0.24         1.67         21.82  
    16         0.97         4.14         21.40  
    17         0.41        10.57         20.81  
    18         3.54         0.55         20.61  
    19         4.16         2.05         20.22  
    20         6.04         1.37         18.36  
    21         4.18         0.42         18.14  
    22         3.84         0.46         17.28  
    23         0.06         1.38         16.38  
    24         0.47         1.78         16.15  
    25         5.38         0.50         15.85  
    26         5.65         0.82         15.32  
    27         5.32         1.18         15.30  
    28         1.87         1.16         14.98  
    29         0.13         1.32         14.76  
    ...         ...          ...           ...  
    16568      0.01         0.00          0.01  
    16569      0.00         0.00          0.01  
    16570      0.00         0.00          0.01  
    16571      0.01         0.00          0.01  
    16572      0.01         0.00          0.01  
    16573      0.00         0.00          0.01  
    16574      0.01         0.00          0.01  
    16575      0.01         0.00          0.01  
    16576      0.00         0.00          0.01  
    16577      0.00         0.00          0.01  
    16578      0.00         0.00          0.01  
    16579      0.00         0.00          0.01  
    16580      0.01         0.00          0.01  
    16581      0.00         0.00          0.01  
    16582      0.00         0.00          0.01  
    16583      0.00         0.00          0.01  
    16584      0.00         0.00          0.01  
    16585      0.00         0.00          0.01  
    16586      0.00         0.00          0.01  
    16587      0.01         0.00          0.01  
    16588      0.00         0.00          0.01  
    16589      0.01         0.00          0.01  
    16590      0.01         0.00          0.01  
    16591      0.00         0.00          0.01  
    16592      0.00         0.00          0.01  
    16593      0.00         0.00          0.01  
    16594      0.00         0.00          0.01  
    16595      0.00         0.00          0.01  
    16596      0.00         0.00          0.01  
    16597      0.00         0.00          0.01  
    
    [16291 rows x 11 columns]>




```python
from bokeh.io import output_file,show,output_notebook,push_notebook
from bokeh.plotting import figure
from bokeh.models import ColumnDataSource,HoverTool,CategoricalColorMapper
from bokeh.layouts import row,column,gridplot
from bokeh.models.widgets import Tabs,Panel
output_notebook()
```



    <div class="bk-root">
        <a href="https://bokeh.pydata.org" target="_blank" class="bk-logo bk-logo-small bk-logo-notebook"></a>
        <span id="1001">Loading BokehJS ...</span>
    </div>





```python
source = ColumnDataSource(data)
plot = figure()
plot.circle(x="Year",y="Global_Sales",source = source)
show(plot)
```








  <div class="bk-root" id="28493f99-e82d-40af-93ae-d688d137c304"></div>






```python
import statsmodels.api as sm
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
from patsy import dmatrix
```


```python

year=df.Year
sale=df.Global_Sales
year_grid=np.arange(year.min(),year.max())
```


```python
fit=np.polyfit(year,sale,4)
model=np.poly1d(fit)
print(model)
```

               4          3         2
    -1.84e-05 x + 0.1473 x - 441.9 x + 5.893e+05 x - 2.947e+08
    


```python
pred = model(year_grid)

plt.figure(figsize=(10,8))
plt.scatter(year, sale, facecolor='None', edgecolor='k', alpha=0.1, label='')
plt.plot(year_grid, pred, color='darkblue', label='Degree-4 Polynomial')
plt.legend()
plt.xlabel('year')
plt.ylabel('sale')

```




    Text(0, 0.5, 'sale')




![png](Untitled_files/Untitled_10_1.png)



```python
data[data['Global_Sales']>=40]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>Name</th>
      <th>Platform</th>
      <th>Year</th>
      <th>Genre</th>
      <th>Publisher</th>
      <th>NA_Sales</th>
      <th>EU_Sales</th>
      <th>JP_Sales</th>
      <th>Other_Sales</th>
      <th>Global_Sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Wii Sports</td>
      <td>Wii</td>
      <td>2006.0</td>
      <td>Sports</td>
      <td>Nintendo</td>
      <td>41.49</td>
      <td>29.02</td>
      <td>3.77</td>
      <td>8.46</td>
      <td>82.74</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Super Mario Bros.</td>
      <td>NES</td>
      <td>1985.0</td>
      <td>Platform</td>
      <td>Nintendo</td>
      <td>29.08</td>
      <td>3.58</td>
      <td>6.81</td>
      <td>0.77</td>
      <td>40.24</td>
    </tr>
  </tbody>
</table>
</div>




```python
data.info
```




    <bound method DataFrame.info of         Rank                                               Name Platform  \
    0          1                                         Wii Sports      Wii   
    1          2                                  Super Mario Bros.      NES   
    2          3                                     Mario Kart Wii      Wii   
    3          4                                  Wii Sports Resort      Wii   
    4          5                           Pokemon Red/Pokemon Blue       GB   
    5          6                                             Tetris       GB   
    6          7                              New Super Mario Bros.       DS   
    7          8                                           Wii Play      Wii   
    8          9                          New Super Mario Bros. Wii      Wii   
    9         10                                          Duck Hunt      NES   
    10        11                                         Nintendogs       DS   
    11        12                                      Mario Kart DS       DS   
    12        13                        Pokemon Gold/Pokemon Silver       GB   
    13        14                                            Wii Fit      Wii   
    14        15                                       Wii Fit Plus      Wii   
    15        16                                 Kinect Adventures!     X360   
    16        17                                 Grand Theft Auto V      PS3   
    17        18                      Grand Theft Auto: San Andreas      PS2   
    18        19                                  Super Mario World     SNES   
    19        20       Brain Age: Train Your Brain in Minutes a Day       DS   
    20        21                      Pokemon Diamond/Pokemon Pearl       DS   
    21        22                                   Super Mario Land       GB   
    22        23                                Super Mario Bros. 3      NES   
    23        24                                 Grand Theft Auto V     X360   
    24        25                        Grand Theft Auto: Vice City      PS2   
    25        26                      Pokemon Ruby/Pokemon Sapphire      GBA   
    26        27                        Pokemon Black/Pokemon White       DS   
    27        28        Brain Age 2: More Training in Minutes a Day       DS   
    28        29                             Gran Turismo 3: A-Spec      PS2   
    29        30                     Call of Duty: Modern Warfare 3     X360   
    ...      ...                                                ...      ...   
    16568  16571                                        XI Coliseum      PSP   
    16569  16572                                 Resident Evil 4 HD     XOne   
    16570  16573                      Farming 2017 - The Simulation      PS4   
    16571  16574         Grisaia no Kajitsu: La Fruit de la Grisaia      PSP   
    16572  16575                   Scarlett: Nichijou no Kyoukaisen      PS2   
    16573  16576                                Mini Desktop Racing      Wii   
    16574  16577  Yattaman Wii: BikkuriDokkiri Machine de Mou Ra...      Wii   
    16575  16578                              Neo Angelique Special      PSP   
    16576  16579                                  Rugby Challenge 3     XOne   
    16577  16580                                          Damnation       PC   
    16578  16581                      Outdoors Unleashed: Africa 3D      3DS   
    16579  16582                                  PGA European Tour      N64   
    16580  16583                                          Real Rode      PS2   
    16581  16584                                          Fit & Fun      Wii   
    16582  16585                                    Planet Monsters      GBA   
    16583  16586                                     Carmageddon 64      N64   
    16584  16587                                   Bust-A-Move 3000       GC   
    16585  16588                                             Breach       PC   
    16586  16589                     Secret Files 2: Puritas Cordis       DS   
    16587  16590                           Mezase!! Tsuri Master DS       DS   
    16588  16591                                   Mega Brain Boost       DS   
    16589  16592  Chou Ezaru wa Akai Hana: Koi wa Tsuki ni Shiru...      PSV   
    16590  16593  Eiyuu Densetsu: Sora no Kiseki Material Collec...      PSP   
    16591  16594                                Myst IV: Revelation       PC   
    16592  16595                                           Plushees       DS   
    16593  16596                 Woody Woodpecker in Crazy Castle 5      GBA   
    16594  16597                      Men in Black II: Alien Escape       GC   
    16595  16598   SCORE International Baja 1000: The Official Game      PS2   
    16596  16599                                         Know How 2       DS   
    16597  16600                                   Spirits & Spells      GBA   
    
             Year         Genre                    Publisher  NA_Sales  EU_Sales  \
    0      2006.0        Sports                     Nintendo     41.49     29.02   
    1      1985.0      Platform                     Nintendo     29.08      3.58   
    2      2008.0        Racing                     Nintendo     15.85     12.88   
    3      2009.0        Sports                     Nintendo     15.75     11.01   
    4      1996.0  Role-Playing                     Nintendo     11.27      8.89   
    5      1989.0        Puzzle                     Nintendo     23.20      2.26   
    6      2006.0      Platform                     Nintendo     11.38      9.23   
    7      2006.0          Misc                     Nintendo     14.03      9.20   
    8      2009.0      Platform                     Nintendo     14.59      7.06   
    9      1984.0       Shooter                     Nintendo     26.93      0.63   
    10     2005.0    Simulation                     Nintendo      9.07     11.00   
    11     2005.0        Racing                     Nintendo      9.81      7.57   
    12     1999.0  Role-Playing                     Nintendo      9.00      6.18   
    13     2007.0        Sports                     Nintendo      8.94      8.03   
    14     2009.0        Sports                     Nintendo      9.09      8.59   
    15     2010.0          Misc       Microsoft Game Studios     14.97      4.94   
    16     2013.0        Action         Take-Two Interactive      7.01      9.27   
    17     2004.0        Action         Take-Two Interactive      9.43      0.40   
    18     1990.0      Platform                     Nintendo     12.78      3.75   
    19     2005.0          Misc                     Nintendo      4.75      9.26   
    20     2006.0  Role-Playing                     Nintendo      6.42      4.52   
    21     1989.0      Platform                     Nintendo     10.83      2.71   
    22     1988.0      Platform                     Nintendo      9.54      3.44   
    23     2013.0        Action         Take-Two Interactive      9.63      5.31   
    24     2002.0        Action         Take-Two Interactive      8.41      5.49   
    25     2002.0  Role-Playing                     Nintendo      6.06      3.90   
    26     2010.0  Role-Playing                     Nintendo      5.57      3.28   
    27     2005.0        Puzzle                     Nintendo      3.44      5.36   
    28     2001.0        Racing  Sony Computer Entertainment      6.85      5.09   
    29     2011.0       Shooter                   Activision      9.03      4.28   
    ...       ...           ...                          ...       ...       ...   
    16568  2006.0        Puzzle  Sony Computer Entertainment      0.00      0.00   
    16569  2016.0       Shooter                       Capcom      0.01      0.00   
    16570  2016.0    Simulation            UIG Entertainment      0.00      0.01   
    16571  2013.0     Adventure                    Prototype      0.00      0.00   
    16572  2008.0     Adventure              Kadokawa Shoten      0.00      0.00   
    16573  2007.0        Racing               Popcorn Arcade      0.01      0.00   
    16574  2008.0        Racing                  Takara Tomy      0.00      0.00   
    16575  2008.0     Adventure                   Tecmo Koei      0.00      0.00   
    16576  2016.0        Sports         Alternative Software      0.00      0.01   
    16577  2009.0       Shooter                  Codemasters      0.00      0.01   
    16578  2011.0        Sports                      Mastiff      0.01      0.00   
    16579  2000.0        Sports                   Infogrames      0.01      0.00   
    16580  2008.0     Adventure              Kadokawa Shoten      0.00      0.00   
    16581  2011.0        Sports                      Unknown      0.00      0.01   
    16582  2001.0        Action                        Titus      0.01      0.00   
    16583  1999.0        Action           Virgin Interactive      0.01      0.00   
    16584  2003.0        Puzzle                      Ubisoft      0.01      0.00   
    16585  2011.0       Shooter                    Destineer      0.01      0.00   
    16586  2009.0     Adventure                  Deep Silver      0.00      0.01   
    16587  2009.0        Sports                  Hudson Soft      0.00      0.00   
    16588  2008.0        Puzzle        Majesco Entertainment      0.01      0.00   
    16589  2016.0        Action              dramatic create      0.00      0.00   
    16590  2007.0  Role-Playing           Falcom Corporation      0.00      0.00   
    16591  2004.0     Adventure                      Ubisoft      0.01      0.00   
    16592  2008.0    Simulation                    Destineer      0.01      0.00   
    16593  2002.0      Platform                        Kemco      0.01      0.00   
    16594  2003.0       Shooter                   Infogrames      0.01      0.00   
    16595  2008.0        Racing                   Activision      0.00      0.00   
    16596  2010.0        Puzzle                     7G//AMES      0.00      0.01   
    16597  2003.0      Platform                      Wanadoo      0.01      0.00   
    
           JP_Sales  Other_Sales  Global_Sales  
    0          3.77         8.46         82.74  
    1          6.81         0.77         40.24  
    2          3.79         3.31         35.82  
    3          3.28         2.96         33.00  
    4         10.22         1.00         31.37  
    5          4.22         0.58         30.26  
    6          6.50         2.90         30.01  
    7          2.93         2.85         29.02  
    8          4.70         2.26         28.62  
    9          0.28         0.47         28.31  
    10         1.93         2.75         24.76  
    11         4.13         1.92         23.42  
    12         7.20         0.71         23.10  
    13         3.60         2.15         22.72  
    14         2.53         1.79         22.00  
    15         0.24         1.67         21.82  
    16         0.97         4.14         21.40  
    17         0.41        10.57         20.81  
    18         3.54         0.55         20.61  
    19         4.16         2.05         20.22  
    20         6.04         1.37         18.36  
    21         4.18         0.42         18.14  
    22         3.84         0.46         17.28  
    23         0.06         1.38         16.38  
    24         0.47         1.78         16.15  
    25         5.38         0.50         15.85  
    26         5.65         0.82         15.32  
    27         5.32         1.18         15.30  
    28         1.87         1.16         14.98  
    29         0.13         1.32         14.76  
    ...         ...          ...           ...  
    16568      0.01         0.00          0.01  
    16569      0.00         0.00          0.01  
    16570      0.00         0.00          0.01  
    16571      0.01         0.00          0.01  
    16572      0.01         0.00          0.01  
    16573      0.00         0.00          0.01  
    16574      0.01         0.00          0.01  
    16575      0.01         0.00          0.01  
    16576      0.00         0.00          0.01  
    16577      0.00         0.00          0.01  
    16578      0.00         0.00          0.01  
    16579      0.00         0.00          0.01  
    16580      0.01         0.00          0.01  
    16581      0.00         0.00          0.01  
    16582      0.00         0.00          0.01  
    16583      0.00         0.00          0.01  
    16584      0.00         0.00          0.01  
    16585      0.00         0.00          0.01  
    16586      0.00         0.00          0.01  
    16587      0.01         0.00          0.01  
    16588      0.00         0.00          0.01  
    16589      0.01         0.00          0.01  
    16590      0.01         0.00          0.01  
    16591      0.00         0.00          0.01  
    16592      0.00         0.00          0.01  
    16593      0.00         0.00          0.01  
    16594      0.00         0.00          0.01  
    16595      0.00         0.00          0.01  
    16596      0.00         0.00          0.01  
    16597      0.00         0.00          0.01  
    
    [16291 rows x 11 columns]>




```python
df=data[data['Global_Sales']<=10]
```


```python
df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>Name</th>
      <th>Platform</th>
      <th>Year</th>
      <th>Genre</th>
      <th>Publisher</th>
      <th>NA_Sales</th>
      <th>EU_Sales</th>
      <th>JP_Sales</th>
      <th>Other_Sales</th>
      <th>Global_Sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>62</th>
      <td>63</td>
      <td>Halo: Reach</td>
      <td>X360</td>
      <td>2010.0</td>
      <td>Shooter</td>
      <td>Microsoft Game Studios</td>
      <td>7.03</td>
      <td>1.98</td>
      <td>0.08</td>
      <td>0.78</td>
      <td>9.88</td>
    </tr>
    <tr>
      <th>63</th>
      <td>64</td>
      <td>Mario Kart 64</td>
      <td>N64</td>
      <td>1996.0</td>
      <td>Racing</td>
      <td>Nintendo</td>
      <td>5.55</td>
      <td>1.94</td>
      <td>2.23</td>
      <td>0.15</td>
      <td>9.87</td>
    </tr>
    <tr>
      <th>64</th>
      <td>65</td>
      <td>New Super Mario Bros. 2</td>
      <td>3DS</td>
      <td>2012.0</td>
      <td>Platform</td>
      <td>Nintendo</td>
      <td>3.66</td>
      <td>3.07</td>
      <td>2.47</td>
      <td>0.63</td>
      <td>9.82</td>
    </tr>
    <tr>
      <th>65</th>
      <td>66</td>
      <td>Halo 4</td>
      <td>X360</td>
      <td>2012.0</td>
      <td>Shooter</td>
      <td>Microsoft Game Studios</td>
      <td>6.63</td>
      <td>2.36</td>
      <td>0.04</td>
      <td>0.73</td>
      <td>9.76</td>
    </tr>
    <tr>
      <th>66</th>
      <td>67</td>
      <td>Final Fantasy VII</td>
      <td>PS</td>
      <td>1997.0</td>
      <td>Role-Playing</td>
      <td>Sony Computer Entertainment</td>
      <td>3.01</td>
      <td>2.47</td>
      <td>3.28</td>
      <td>0.96</td>
      <td>9.72</td>
    </tr>
    <tr>
      <th>67</th>
      <td>68</td>
      <td>Call of Duty: Ghosts</td>
      <td>PS3</td>
      <td>2013.0</td>
      <td>Shooter</td>
      <td>Activision</td>
      <td>4.09</td>
      <td>3.73</td>
      <td>0.38</td>
      <td>1.38</td>
      <td>9.59</td>
    </tr>
    <tr>
      <th>68</th>
      <td>69</td>
      <td>Just Dance 2</td>
      <td>Wii</td>
      <td>2010.0</td>
      <td>Misc</td>
      <td>Ubisoft</td>
      <td>5.84</td>
      <td>2.89</td>
      <td>0.01</td>
      <td>0.78</td>
      <td>9.52</td>
    </tr>
    <tr>
      <th>69</th>
      <td>70</td>
      <td>Gran Turismo 2</td>
      <td>PS</td>
      <td>1999.0</td>
      <td>Racing</td>
      <td>Sony Computer Entertainment</td>
      <td>3.88</td>
      <td>3.42</td>
      <td>1.69</td>
      <td>0.50</td>
      <td>9.49</td>
    </tr>
    <tr>
      <th>70</th>
      <td>71</td>
      <td>Call of Duty 4: Modern Warfare</td>
      <td>X360</td>
      <td>2007.0</td>
      <td>Shooter</td>
      <td>Activision</td>
      <td>5.91</td>
      <td>2.38</td>
      <td>0.13</td>
      <td>0.90</td>
      <td>9.32</td>
    </tr>
    <tr>
      <th>71</th>
      <td>72</td>
      <td>Donkey Kong Country</td>
      <td>SNES</td>
      <td>1994.0</td>
      <td>Platform</td>
      <td>Nintendo</td>
      <td>4.36</td>
      <td>1.71</td>
      <td>3.00</td>
      <td>0.23</td>
      <td>9.30</td>
    </tr>
    <tr>
      <th>72</th>
      <td>73</td>
      <td>Minecraft</td>
      <td>X360</td>
      <td>2013.0</td>
      <td>Misc</td>
      <td>Microsoft Game Studios</td>
      <td>5.58</td>
      <td>2.83</td>
      <td>0.02</td>
      <td>0.77</td>
      <td>9.20</td>
    </tr>
    <tr>
      <th>73</th>
      <td>74</td>
      <td>Animal Crossing: New Leaf</td>
      <td>3DS</td>
      <td>2012.0</td>
      <td>Simulation</td>
      <td>Nintendo</td>
      <td>2.01</td>
      <td>2.32</td>
      <td>4.36</td>
      <td>0.41</td>
      <td>9.09</td>
    </tr>
    <tr>
      <th>74</th>
      <td>75</td>
      <td>Mario Party DS</td>
      <td>DS</td>
      <td>2007.0</td>
      <td>Misc</td>
      <td>Nintendo</td>
      <td>4.46</td>
      <td>1.88</td>
      <td>1.98</td>
      <td>0.70</td>
      <td>9.02</td>
    </tr>
    <tr>
      <th>75</th>
      <td>76</td>
      <td>The Elder Scrolls V: Skyrim</td>
      <td>X360</td>
      <td>2011.0</td>
      <td>Role-Playing</td>
      <td>Bethesda Softworks</td>
      <td>5.03</td>
      <td>2.86</td>
      <td>0.10</td>
      <td>0.85</td>
      <td>8.84</td>
    </tr>
    <tr>
      <th>76</th>
      <td>77</td>
      <td>Super Mario Kart</td>
      <td>SNES</td>
      <td>1992.0</td>
      <td>Racing</td>
      <td>Nintendo</td>
      <td>3.54</td>
      <td>1.24</td>
      <td>3.81</td>
      <td>0.18</td>
      <td>8.76</td>
    </tr>
    <tr>
      <th>77</th>
      <td>78</td>
      <td>FIFA 16</td>
      <td>PS4</td>
      <td>2015.0</td>
      <td>Sports</td>
      <td>Electronic Arts</td>
      <td>1.11</td>
      <td>6.06</td>
      <td>0.06</td>
      <td>1.26</td>
      <td>8.49</td>
    </tr>
    <tr>
      <th>78</th>
      <td>79</td>
      <td>Wii Party</td>
      <td>Wii</td>
      <td>2010.0</td>
      <td>Misc</td>
      <td>Nintendo</td>
      <td>1.79</td>
      <td>3.53</td>
      <td>2.49</td>
      <td>0.68</td>
      <td>8.49</td>
    </tr>
    <tr>
      <th>79</th>
      <td>80</td>
      <td>Halo 2</td>
      <td>XB</td>
      <td>2004.0</td>
      <td>Shooter</td>
      <td>Microsoft Game Studios</td>
      <td>6.82</td>
      <td>1.53</td>
      <td>0.05</td>
      <td>0.08</td>
      <td>8.49</td>
    </tr>
    <tr>
      <th>80</th>
      <td>81</td>
      <td>Mario Party 8</td>
      <td>Wii</td>
      <td>2007.0</td>
      <td>Misc</td>
      <td>Nintendo</td>
      <td>3.81</td>
      <td>2.30</td>
      <td>1.58</td>
      <td>0.73</td>
      <td>8.42</td>
    </tr>
    <tr>
      <th>81</th>
      <td>82</td>
      <td>Pokemon Black 2/Pokemon White 2</td>
      <td>DS</td>
      <td>2012.0</td>
      <td>Role-Playing</td>
      <td>Nintendo</td>
      <td>2.91</td>
      <td>1.86</td>
      <td>3.14</td>
      <td>0.43</td>
      <td>8.33</td>
    </tr>
    <tr>
      <th>82</th>
      <td>83</td>
      <td>FIFA Soccer 13</td>
      <td>PS3</td>
      <td>2012.0</td>
      <td>Action</td>
      <td>Electronic Arts</td>
      <td>1.06</td>
      <td>5.05</td>
      <td>0.13</td>
      <td>2.01</td>
      <td>8.24</td>
    </tr>
    <tr>
      <th>83</th>
      <td>84</td>
      <td>The Sims 3</td>
      <td>PC</td>
      <td>2009.0</td>
      <td>Simulation</td>
      <td>Electronic Arts</td>
      <td>0.98</td>
      <td>6.42</td>
      <td>0.00</td>
      <td>0.71</td>
      <td>8.11</td>
    </tr>
    <tr>
      <th>84</th>
      <td>85</td>
      <td>GoldenEye 007</td>
      <td>N64</td>
      <td>1997.0</td>
      <td>Shooter</td>
      <td>Nintendo</td>
      <td>5.80</td>
      <td>2.01</td>
      <td>0.13</td>
      <td>0.15</td>
      <td>8.09</td>
    </tr>
    <tr>
      <th>85</th>
      <td>86</td>
      <td>Mario &amp; Sonic at the Olympic Games</td>
      <td>Wii</td>
      <td>2007.0</td>
      <td>Sports</td>
      <td>Sega</td>
      <td>2.58</td>
      <td>3.90</td>
      <td>0.66</td>
      <td>0.91</td>
      <td>8.06</td>
    </tr>
    <tr>
      <th>86</th>
      <td>87</td>
      <td>Final Fantasy X</td>
      <td>PS2</td>
      <td>2001.0</td>
      <td>Role-Playing</td>
      <td>Sony Computer Entertainment</td>
      <td>2.91</td>
      <td>2.07</td>
      <td>2.73</td>
      <td>0.33</td>
      <td>8.05</td>
    </tr>
    <tr>
      <th>87</th>
      <td>88</td>
      <td>Final Fantasy VIII</td>
      <td>PS</td>
      <td>1999.0</td>
      <td>Role-Playing</td>
      <td>SquareSoft</td>
      <td>2.28</td>
      <td>1.72</td>
      <td>3.63</td>
      <td>0.23</td>
      <td>7.86</td>
    </tr>
    <tr>
      <th>88</th>
      <td>89</td>
      <td>Pokémon Platinum Version</td>
      <td>DS</td>
      <td>2008.0</td>
      <td>Role-Playing</td>
      <td>Nintendo</td>
      <td>2.82</td>
      <td>1.78</td>
      <td>2.69</td>
      <td>0.55</td>
      <td>7.84</td>
    </tr>
    <tr>
      <th>89</th>
      <td>90</td>
      <td>Pac-Man</td>
      <td>2600</td>
      <td>1982.0</td>
      <td>Puzzle</td>
      <td>Atari</td>
      <td>7.28</td>
      <td>0.45</td>
      <td>0.00</td>
      <td>0.08</td>
      <td>7.81</td>
    </tr>
    <tr>
      <th>90</th>
      <td>91</td>
      <td>Grand Theft Auto: Liberty City Stories</td>
      <td>PSP</td>
      <td>2005.0</td>
      <td>Action</td>
      <td>Take-Two Interactive</td>
      <td>2.90</td>
      <td>2.83</td>
      <td>0.24</td>
      <td>1.75</td>
      <td>7.72</td>
    </tr>
    <tr>
      <th>91</th>
      <td>92</td>
      <td>Super Mario Galaxy 2</td>
      <td>Wii</td>
      <td>2010.0</td>
      <td>Platform</td>
      <td>Nintendo</td>
      <td>3.66</td>
      <td>2.42</td>
      <td>0.98</td>
      <td>0.64</td>
      <td>7.69</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>16568</th>
      <td>16571</td>
      <td>XI Coliseum</td>
      <td>PSP</td>
      <td>2006.0</td>
      <td>Puzzle</td>
      <td>Sony Computer Entertainment</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16569</th>
      <td>16572</td>
      <td>Resident Evil 4 HD</td>
      <td>XOne</td>
      <td>2016.0</td>
      <td>Shooter</td>
      <td>Capcom</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16570</th>
      <td>16573</td>
      <td>Farming 2017 - The Simulation</td>
      <td>PS4</td>
      <td>2016.0</td>
      <td>Simulation</td>
      <td>UIG Entertainment</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16571</th>
      <td>16574</td>
      <td>Grisaia no Kajitsu: La Fruit de la Grisaia</td>
      <td>PSP</td>
      <td>2013.0</td>
      <td>Adventure</td>
      <td>Prototype</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16572</th>
      <td>16575</td>
      <td>Scarlett: Nichijou no Kyoukaisen</td>
      <td>PS2</td>
      <td>2008.0</td>
      <td>Adventure</td>
      <td>Kadokawa Shoten</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16573</th>
      <td>16576</td>
      <td>Mini Desktop Racing</td>
      <td>Wii</td>
      <td>2007.0</td>
      <td>Racing</td>
      <td>Popcorn Arcade</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16574</th>
      <td>16577</td>
      <td>Yattaman Wii: BikkuriDokkiri Machine de Mou Ra...</td>
      <td>Wii</td>
      <td>2008.0</td>
      <td>Racing</td>
      <td>Takara Tomy</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16575</th>
      <td>16578</td>
      <td>Neo Angelique Special</td>
      <td>PSP</td>
      <td>2008.0</td>
      <td>Adventure</td>
      <td>Tecmo Koei</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16576</th>
      <td>16579</td>
      <td>Rugby Challenge 3</td>
      <td>XOne</td>
      <td>2016.0</td>
      <td>Sports</td>
      <td>Alternative Software</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16577</th>
      <td>16580</td>
      <td>Damnation</td>
      <td>PC</td>
      <td>2009.0</td>
      <td>Shooter</td>
      <td>Codemasters</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16578</th>
      <td>16581</td>
      <td>Outdoors Unleashed: Africa 3D</td>
      <td>3DS</td>
      <td>2011.0</td>
      <td>Sports</td>
      <td>Mastiff</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16579</th>
      <td>16582</td>
      <td>PGA European Tour</td>
      <td>N64</td>
      <td>2000.0</td>
      <td>Sports</td>
      <td>Infogrames</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16580</th>
      <td>16583</td>
      <td>Real Rode</td>
      <td>PS2</td>
      <td>2008.0</td>
      <td>Adventure</td>
      <td>Kadokawa Shoten</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16581</th>
      <td>16584</td>
      <td>Fit &amp; Fun</td>
      <td>Wii</td>
      <td>2011.0</td>
      <td>Sports</td>
      <td>Unknown</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16582</th>
      <td>16585</td>
      <td>Planet Monsters</td>
      <td>GBA</td>
      <td>2001.0</td>
      <td>Action</td>
      <td>Titus</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16583</th>
      <td>16586</td>
      <td>Carmageddon 64</td>
      <td>N64</td>
      <td>1999.0</td>
      <td>Action</td>
      <td>Virgin Interactive</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16584</th>
      <td>16587</td>
      <td>Bust-A-Move 3000</td>
      <td>GC</td>
      <td>2003.0</td>
      <td>Puzzle</td>
      <td>Ubisoft</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16585</th>
      <td>16588</td>
      <td>Breach</td>
      <td>PC</td>
      <td>2011.0</td>
      <td>Shooter</td>
      <td>Destineer</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16586</th>
      <td>16589</td>
      <td>Secret Files 2: Puritas Cordis</td>
      <td>DS</td>
      <td>2009.0</td>
      <td>Adventure</td>
      <td>Deep Silver</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16587</th>
      <td>16590</td>
      <td>Mezase!! Tsuri Master DS</td>
      <td>DS</td>
      <td>2009.0</td>
      <td>Sports</td>
      <td>Hudson Soft</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16588</th>
      <td>16591</td>
      <td>Mega Brain Boost</td>
      <td>DS</td>
      <td>2008.0</td>
      <td>Puzzle</td>
      <td>Majesco Entertainment</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16589</th>
      <td>16592</td>
      <td>Chou Ezaru wa Akai Hana: Koi wa Tsuki ni Shiru...</td>
      <td>PSV</td>
      <td>2016.0</td>
      <td>Action</td>
      <td>dramatic create</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16590</th>
      <td>16593</td>
      <td>Eiyuu Densetsu: Sora no Kiseki Material Collec...</td>
      <td>PSP</td>
      <td>2007.0</td>
      <td>Role-Playing</td>
      <td>Falcom Corporation</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16591</th>
      <td>16594</td>
      <td>Myst IV: Revelation</td>
      <td>PC</td>
      <td>2004.0</td>
      <td>Adventure</td>
      <td>Ubisoft</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16592</th>
      <td>16595</td>
      <td>Plushees</td>
      <td>DS</td>
      <td>2008.0</td>
      <td>Simulation</td>
      <td>Destineer</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16593</th>
      <td>16596</td>
      <td>Woody Woodpecker in Crazy Castle 5</td>
      <td>GBA</td>
      <td>2002.0</td>
      <td>Platform</td>
      <td>Kemco</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16594</th>
      <td>16597</td>
      <td>Men in Black II: Alien Escape</td>
      <td>GC</td>
      <td>2003.0</td>
      <td>Shooter</td>
      <td>Infogrames</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16595</th>
      <td>16598</td>
      <td>SCORE International Baja 1000: The Official Game</td>
      <td>PS2</td>
      <td>2008.0</td>
      <td>Racing</td>
      <td>Activision</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16596</th>
      <td>16599</td>
      <td>Know How 2</td>
      <td>DS</td>
      <td>2010.0</td>
      <td>Puzzle</td>
      <td>7G//AMES</td>
      <td>0.00</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>16597</th>
      <td>16600</td>
      <td>Spirits &amp; Spells</td>
      <td>GBA</td>
      <td>2003.0</td>
      <td>Platform</td>
      <td>Wanadoo</td>
      <td>0.01</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.01</td>
    </tr>
  </tbody>
</table>
<p>16229 rows × 11 columns</p>
</div>




```python
pred1 = fit1.predict(dmatrix("bs(year_grid, knots=(1990,2000,2010), include_intercept=False)", {"year_grid": year_grid}, return_type='dataframe'))
pred2 = fit2.predict(dmatrix("cr(year_grid, knots=(1990,2000,2010))", {"year_grid": year_grid}, return_type='dataframe'))

plt.figure(figsize=(10,8))
plt.scatter(year, sale, facecolor='None', edgecolor='k', alpha=0.1, label='')
plt.plot(year_grid, pred1, color='cornflowerblue', label='Cubic Spline')
plt.plot(year_grid, pred2, color='darkorange', label='Natural Cubic Spline')
plt.legend()
plt.xlabel('year')
plt.ylabel('sale')
```




    Text(0, 0.5, 'sale')




![png](Untitled_files/Untitled_15_1.png)



```python
year_cs = dmatrix("bs(year, knots=(1990,2000,2010), degree=3, include_intercept=False)",{"year": year},return_type='dataframe')
fit1 = sm.GLM(sale, year_cs).fit()
fit1.params
```




    Intercept                                                                   0.261886
    bs(year, knots=(1990, 2000, 2010), degree=3, include_intercept=False)[0]    2.009827
    bs(year, knots=(1990, 2000, 2010), degree=3, include_intercept=False)[1]    0.376798
    bs(year, knots=(1990, 2000, 2010), degree=3, include_intercept=False)[2]    0.380793
    bs(year, knots=(1990, 2000, 2010), degree=3, include_intercept=False)[3]   -0.097022
    bs(year, knots=(1990, 2000, 2010), degree=3, include_intercept=False)[4]    0.638847
    bs(year, knots=(1990, 2000, 2010), degree=3, include_intercept=False)[5]   -1.688605
    dtype: float64




```python
year_ncs = dmatrix("cr(year, knots=(1990,2000,2010))",{"year": year},return_type='dataframe')
fit2 = sm.GLM(sale, year_ncs).fit()
fit2.params
```




    Intercept                                0.569717
    cr(year, knots=(1990, 2000, 2010))[0]    0.492952
    cr(year, knots=(1990, 2000, 2010))[1]    0.428666
    cr(year, knots=(1990, 2000, 2010))[2]   -0.047500
    cr(year, knots=(1990, 2000, 2010))[3]   -0.137080
    cr(year, knots=(1990, 2000, 2010))[4]   -0.167321
    dtype: float64




```python

```
