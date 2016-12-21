## LOD PG Titles.csv

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _TitleURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI") + "/title/displayOrder/" + getValue("TitleType")
```

#### _PreferredLabel_
From column: _Title_
>``` python
if getValue("DisplayOrder") == '1':
    return getValue("Title")
```

#### _AltLabel_
From column: _PreferredLabel_
>``` python
if getValue("DisplayOrder") != '1':
    return getValue("Title")
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AltLabel_ | `skos:altLabel` | `E22_Man-Made_Object1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _PreferredLabel_ | `skos:prefLabel` | `E22_Man-Made_Object1`|
| _Title_ | `rdfs:label` | `E35_Title1`|
| _TitleURI_ | `uri` | `E35_Title1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P102_has_title` | `E35_Title1`|
