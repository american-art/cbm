# LOD CBMAA Exhibitions.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/" + getValue("ObjectID")
```

#### _ExhibitionURI_
From column: _ExhibitionID_
``` python
return "exhibition/" + getValue("ExhibitionID")
```

#### _AppellationURI_
From column: _ExhibitionURI_
``` python
return getValue("ExhibitionURI") + "/appellation"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _ExhTitle_ | `rdf:value` | `crm:E41_Appellation1`|
| _ExhibitionURI_ | `uri` | `crm:E5_Event1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P12i_was_present_at` | `crm:E5_Event1`|
| `crm:E41_Appellation1` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404670`|
| `crm:E5_Event1` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
