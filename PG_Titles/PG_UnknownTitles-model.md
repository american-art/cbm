# LOD PG Titles.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/" + getValue("ObjectID")
```

#### _TitleURI_
From column: _Title_
``` python
return getValue("ObjectURI") + "/unknown_title_type"
```


## Selections
#### _DEFAULT_TEST_
From column: _TitleID_
<br>Operation: `Union`
``` python
return getValue("TitleType") != "(not entered)"
```


## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _Title_ | `rdf:value` | `crm:E35_Title1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
