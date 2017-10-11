# PG Images_with_header.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/"+getValue("ObjectID")
```

#### _ObjectUrlURI_
From column: _Object_URL_
``` python
if getValue("Object_URL"):
    return "http://"+getValue("Object_URL")
else:
    return ""
```

#### _ObjectURL_clean_
From column: _Object_URL_
``` python
if getValue("Object_URL"):
    return "http://"+getValue("Object_URL")
else:
    return ""
```

#### _ImageURL_clean_
From column: _Image_URL_
``` python
if getValue("Image_URL"):
    return getValue("Image_URL")
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ImageURL_clean_ | `uri` | `crm:E38_Image1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectURL_clean_ | `rdfs:label` | `foaf:Document1`|
| _ObjectUrlURI_ | `uri` | `foaf:Document1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P138i_has_representation` | `crm:E38_Image1`|
| `crm:E22_Man-Made_Object1` | `foaf:homepage` | `foaf:Document1`|
