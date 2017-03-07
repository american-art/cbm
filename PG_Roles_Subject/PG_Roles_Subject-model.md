# LOD PG Constituents.csv

## Add Column

## Add Node/Literal

## PyTransforms
#### _ArtistURI_
From column: _ConstituentID_
``` python
if getValue("Role") in ["Artist", "Author", "Maker"]:
    return "constituent/"+getValue("ConstituentID")
else:
    return ""
```

#### _SubjectURI_
From column: _ArtistURI_
``` python
if getValue("Role") == "Depicted":
    return "constituent/"+getValue("ConstituentID")
else:
    return ""
```

#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/"+getValue("ObjectID")
```

#### _ProductionURI_
From column: _ConstituentID_
``` python
return getValue("ObjectURI")+"/production"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _SubjectURI_ | `uri` | `crm:E39_Actor2`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P62_depicts` | `crm:E39_Actor2`|
