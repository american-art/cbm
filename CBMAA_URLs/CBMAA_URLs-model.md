# LOD CBMAA Image URLs_with_header.csv

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
return getValue("Object_URL")
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Image_URL_ | `uri` | `crm:E38_Image1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ObjectUrlURI_ | `uri` | `foaf:Document1`|
| _Object_URL_ | `rdfs:label` | `foaf:Document1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P138i_has_representation` | `crm:E38_Image1`|
| `crm:E22_Man-Made_Object1` | `foaf:homepage` | `foaf:Document1`|
