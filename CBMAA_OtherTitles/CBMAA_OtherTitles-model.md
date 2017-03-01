# LOD CBMAA Titles.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404012`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/" + getValue("ObjectID")
```

#### _TitleVal_
From column: _Title_
``` python
return getValue("Title")
```

#### _TitleURI_
From column: _TitleVal_
``` python
return UM.uri_from_fields(getValue("ObjectURI")+"/alt_title/",getValue("TitleID"))
```

#### _TitleID_URI_
From column: _TitleID_
``` python
return getValue("TitleURI") + "/id"
```

#### _TitleTypeURI_
From column: _TitleType_
``` python
return UM.uri_from_fields("thesauri/name_type/",getValue("TitleType"))
```


## Selections
#### _DEFAULT_TEST_
From column: _TitleID_
<br>Operation: `Union`
``` python
return getValue("TitleType") == "Primary Title" or getValue("TitleType") == "(not entered)"
```


## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _TitleType_ | `skos:prefLabel` | `crm:E55_Type1`|
| _TitleTypeURI_ | `uri` | `crm:E55_Type1`|
| _TitleURI_ | `uri` | `crm:E35_Title1`|
| _TitleVal_ | `rdf:value` | `crm:E35_Title1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P102_has_title` | `crm:E35_Title1`|
| `crm:E35_Title1` | `crm:P2_has_type` | `crm:E55_Type1`|
