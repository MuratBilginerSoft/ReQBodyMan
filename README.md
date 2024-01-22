![BrainyTechLogo](https://brainytech.net/wp-content/uploads/2023/11/brainy-tech-site.png)

## Project Description

ReQBodyMan is a package that you can use to manage the validations of body data coming with Request more effectively.

## Installation

### 1 Install to Package

For Windows

```
pip install ReQBodyMan
```

For Linux/MacOs

```
pip3 install ReQBodyMan
``` 

### 2 Dependencies Package

`flask`

## Usage

### 1 Import The Package

```py
from ReQBodyMan.ReQBodyMan import ReQBodyMan
```
### 2 ReQBodyMan Create Object

```py
ReQBodyMans = ReQBodyMan()
```

### 2 Get Form Data

If the data comes from the request with a form, you can get the data as follows.

```py

Data : string, int, float, boolean, list, dict,  
Parameters : contextName, variableType, booleanType=NoneRequired
booleanType default = "int"
Return: data

data = ReQBodyMans.form("data_name", "str")
data = ReQBodyMans.form("data_name", "int")
data = ReQBodyMans.form("data_name", "float")
data = ReQBodyMans.form("data_name", "bool", booleanType="bool")
data = ReQBodyMans.form("data_name", "bool", booleanType="int" )
data = ReQBodyMans.form("data_name", "list")
data = ReQBodyMans.form("data_name", "dict")
```

If Variable Type is sent outside the specified format, return None.

### 3 Get Json Data

```py

Data : string, int, float, boolean, list, dict,  
Parameters : contextName, variableType, booleanType=NoneRequired
booleanType default = "int"
Return : Data

data = ReQBodyMans.json("data_name", "str")
data = ReQBodyMans.json("data_name", "int")
data = ReQBodyMans.json("data_name", "float")
data = ReQBodyMans.json("data_name", "bool", booleanType="bool")
data = ReQBodyMans.json("data_name", "bool", booleanType="int")
data = ReQBodyMans.json("data_name", "list")
data = ReQBodyMans.json("data_name", "dict")
```

If Variable Type is sent outside the specified format, return None.

### 4 Get File

```py
Data : file
Parameters : fileName
Return: file

file = ReQBodyMans.file("fileName")
```
If FileName is not in request.file, the value "The {fileName} is not in request.files" is returned.

### 5 Get Params

```py
Data : string, int, float, boolean, list,  
Parameters : variableName, variableType, booleanType=NoneRequired
booleanType default = "int"
Return : data

data = ReQBodyMans.params("data_name", "str")
data = ReQBodyMans.params("data_name", "int")
data = ReQBodyMans.params("data_name", "float")
data = ReQBodyMans.params("data_name", "bool", booleanType="bool")
data = ReQBodyMans.params("data_name", "bool", booleanType="int")
data = ReQBodyMans.params("data_name", "list")
```

### 6 GetAllData Function

```py
Data : string, int, float, boolean, list, file,  
Parameters : bodyJson
variableName : Variable name in body data 
bodyType :  form, json, params, file
booleanType: int, bool
Return : allVariablesJson

bodyJson = {

    "variableName" : ["bodyType", "variableType", "booleanType"]
}

# BodyType Json

bodyJson = {
    
    "password"  : ["json", "str"],
    "email"     : ["json", "str"]
}

# Boolean Type Usage 

bodyJson = {
    
    "password"  : ["json", "str"],
    "email"     : ["json", "str"],
    "status"    : ["json", "str", "int"]
    "status2"   : ["json", "str", "bool"]
}

# BodyType Form

bodyJson = {
    
    "password"  : ["form", "str"],
    "email"     : ["form", "str"],
    "status"    : ["form", "str", "int"]
    "status2"   : ["form", "str", "bool"]
    "fileName"  : ["file"] 
}

# BodyForm Params

bodyJson = {
    
    "password"  : ["params", "str"],
    "email"     : ["params", "str"],
    "status"    : ["params", "str", "int"]
    "status2"   : ["params", "str", "bool"] 
}

data = ReQBodyMans.getAllData(bodyJson)

Return data content 

{
    "email" : "test@test.com",
    "password":"test2",
    "status" : "1" or "0",
    "status2" : True or False,
    "fileName" : file
}

```

If Variable Type is sent outside the specified format, return None.

# Release Note

## v1.2.0

1. getAllData Function Added 
      - Allows you to send all the data at once and receive the data as a dictionary

## v.1.1.0

1. Added dict property to Params.
2. Added dict property to Json
3. The return value for bool type has been added to return int or bool type according to the value to be given with booleanType.
4. Code refactor.

## v.1.0.1

1. ReadMe file updated

## v.1.0.0

1. Project published.


**ReQBodyMan is a BrainyTech Product.**

**Developer : Murat Bilginer**