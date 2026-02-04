# Sorting tables
## Install Python Environment
https://learn.microsoft.com/en-us/power-bi/connect-data/service-python-packages-support

* Python 3.11
* Pandas: 2.2.2
* Seaborn:  0.13.2
* matplotlib: 3.8.4

```
conda create --name <env-name>
```

### Creation of environment with Anaconda

#### Environment set with python version and libraries set from the beggining
To add packages while creating an environment, specify them after the environment name:

```
conda create --name envpython311 python==3.11 pandas==2.2.2 seaborn==0.13.2 matplotlib==3.8.4
```


#### Create environment and then install libraries

**Environment**
```cmd
conda create -n envpython311 python==3.11 
```
or
```cmd
conda create --name envpython311 python==3.11 
```

**Libraries+

```cmd
pip install pandas==2.2.2 
pip install seaborn==0.13.2 
pip install matplotlib==3.8.4
```



## Freeze rows

https://community.fabric.microsoft.com/t5/Desktop/How-to-freeze-rows-in-a-Matrix-visual-in-Power-BI/td-p/4763705



## Sort by columns

https://community.fabric.microsoft.com/t5/Desktop/how-to-order-the-rows-in-table-on-power-bi/m-p/4233380



## Custom sorting options

* https://zebrabi.com/how-to-sort-columns-in-matrix-power-bi/
* https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-sort-by-column
* https://www.thebricks.com/resources/guide-how-to-manually-sort-columns-in-power-bi

* Custom SORT ORDER with sort by COLUMN in Power BI: https://youtu.be/NAKZVquuY6E
  * Data View
  * Select column
  * Go to "Column tools" tab
  * Select "Sort by column", and select the column in the dropdow



# How to Reorder Rows

https://www.thebricks.com/resources/guide-how-to-reorder-rows-in-power-bi-table



```BASH
Apple1 Rank = 
VAR CountRowApple1 = 
    CALCULATE(
        'prod_data'[Apple1],
        FILTER('prod_data', 'prod_data'[Quality Index] = "Count")
    )
RETURN
    RANKX(
        FILTER(
            'prod_data',
            'prod_data'[Quality Index] = EARLIER('prod_data'[Quality Index]) &&
            ('prod_data'[Apple1] > 0 || 'prod_data'[Apple2] > 0 || 
             'prod_data'[Apple3] > 0 || 'prod_data'[Apple4] > 0 ||
             'prod_data'[Apple5] > 0 || 'prod_data'[Apple6] > 0 ||
             'prod_data'[Apple7] > 0)
        ),
        CountRowApple1,
        ,
        ASC
    )
    
    Apple1 Rank = 
VAR CountRowApple1 = 
    CALCULATE(
        FILTER('prod_data', 'prod_data'[Quality Index] == "Count")
    )
RETURN
    RANKX(
        FILTER(
            'prod_data'[Apple1] > 0 || 'prod_data'[Apple2] > 0 || 
             'prod_data'[Apple3] > 0 || 'prod_data'[Apple4] > 0 ||
             'prod_data'[Apple5] > 0 || 'prod_data'[Apple6] > 0 ||
             'prod_data'[Apple7] > 0)
        ),
        CountRowApple1,
        ,
        ASC
    )
    
```





```bash
Ranked Apples Table = EVALUATE
VAR CountRow = 
    CALCULATE(
        SELECTCOLUMNS(
            'prod_data',
            "Apple1", 'prod_data'[Apple1],
            "Apple2", 'prod_data'[Apple2],
            "Apple3", 'prod_data'[Apple3],
            "Apple4", 'prod_data'[Apple4],
            "Apple5", 'prod_data'[Apple5],
            "Apple6", 'prod_data'[Apple6],
            "Apple7", 'prod_data'[Apple7]
        ),
        'prod_data'[Quality Index] = "Count"
    )
RETURN
    TOPN(7, CountRow, [Apple1], ASC)
```

cuenta powe bi microsoft - talvez con la escuela unadm

mcpi powe bi



# MCP



* AI-POWERED POWER BI DEVELOPMENT IS HERE! - Power BI MCP Server Step by Step Walkthrough: https://youtu.be/3fFoUcj1tWc
