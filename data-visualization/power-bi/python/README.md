# Python in Power BI 

https://learn.microsoft.com/en-us/power-bi/connect-data/service-python-packages-support

* Python 3.11
* Pandas: 2.2.2
* Seaborn:  0.13.2
* matplotlib: 3.8.4

## Install python and pip

### Windows

```cmd
python get-pip.py
python -m pip --version
py -m ensurepip --default-pip

python -m pip install

[notice] A new release of pip is available: 23.2.1 -> 25.3
[notice] To update, run: C:\Users\rosal\AppData\Local\Programs\Python\Python312\python.exe -m pip install --upgrade pip

```



````cmd
python -m pip install --upgrade pip
python -m pip --version
````

👉 If this works, you can install packages like this forever:

```
python -m pip install requests
```

### Linux

````bash
python3 -m ensurepip --default-pip
````



## Python environment

### Windows

```cmd
py -m venv venv
```



### Linux

````bash
python3 -m venv venv
source venv/bin/activate
````

