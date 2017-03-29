# LOD PG Constituents.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404672`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404651`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404654`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404652`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
``` python
return "constituent/"+getValue("ConstituentID")
```

#### _NameLabel_
From column: _DisplayName_
``` python
return getValue("DisplayName")
```

#### _NameURI_
From column: _ConstituentURI_
``` python
return getValue("ConstituentURI")+"/name"
```

#### _SortNameURI_
From column: _NameLabel_
``` python
return getValue("ConstituentURI")+"/sort_name"
```

#### _NameCompositionURI_
From column: _NameTitle_
``` python
return getValue("ConstituentURI")+"/name"
```

#### _FirstNameURI_
From column: _NameCompositionURI_
``` python
if getValue("FirstName"):
    return getValue("NameCompositionURI")+"/first_name"
else:
    return ""
```

#### _MiddleNameURI_
From column: _FirstName_
``` python
if getValue("MiddleName"):
    return getValue("NameCompositionURI")+"/middle_name"
else:
    return ""
```

#### _LastNameURI_
From column: _MiddleName_
``` python
if getValue("LastName"):
    return getValue("NameCompositionURI")+"/last_name"
else:
    return ""
```

#### _FirstNameTypeURI_
From column: _NameCompositionURI_
``` python
return "thesauri/name_type/first_name"
```

#### _MiddleNameTypeURI_
From column: _FirstName_
``` python
return "thesauri/name_type/middle_name"
```

#### _LastNameTypeURI_
From column: _MiddleName_
``` python
return"thesauri/name_type/last_name"
```

#### _PrefIdURI_
From column: _ConstituentID_
``` python
return getValue("ConstituentURI")+"/pref_id"
```

#### _ID_Label_
From column: _ConstituentID_
``` python
return getValue("ConstituentID")
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AlphaSort_ | `rdf:value` | `crm:E82_Actor_Appellation2`|
| _ConstituentID_ | `rdf:value` | `crm:E42_Identifier1`|
| _ConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _DisplayName_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _FirstName_ | `rdf:value` | `crm:E82_Actor_Appellation4`|
| _FirstNameTypeURI_ | `uri` | `crm:E55_Type1`|
| _FirstNameURI_ | `uri` | `crm:E82_Actor_Appellation4`|
| _ID_Label_ | `rdfs:label` | `crm:E42_Identifier1`|
| _LastName_ | `rdf:value` | `crm:E82_Actor_Appellation6`|
| _LastNameTypeURI_ | `uri` | `crm:E55_Type3`|
| _LastNameURI_ | `uri` | `crm:E82_Actor_Appellation6`|
| _MiddleName_ | `rdf:value` | `crm:E82_Actor_Appellation5`|
| _MiddleNameTypeURI_ | `uri` | `crm:E55_Type2`|
| _MiddleNameURI_ | `uri` | `crm:E82_Actor_Appellation5`|
| _NameCompositionURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _NameLabel_ | `rdfs:label` | `crm:E39_Actor1`|
| _NameURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _PrefIdURI_ | `uri` | `crm:E42_Identifier1`|
| _SortNameURI_ | `uri` | `crm:E82_Actor_Appellation2`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E39_Actor1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation2`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation3`|
| `crm:E42_Identifier1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300404670`|
| `crm:E55_Type1` | `skos:broadMatch` | `http://vocab.getty.edu/aat/300404651`|
| `crm:E55_Type2` | `skos:broadMatch` | `http://vocab.getty.edu/aat/300404654`|
| `crm:E55_Type3` | `skos:broadMatch` | `http://vocab.getty.edu/aat/300404652`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300404670`|
| `crm:E82_Actor_Appellation2` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300404672`|
| `crm:E82_Actor_Appellation3` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation4`|
| `crm:E82_Actor_Appellation3` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation5`|
| `crm:E82_Actor_Appellation3` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation6`|
| `crm:E82_Actor_Appellation4` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E82_Actor_Appellation5` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E82_Actor_Appellation6` | `crm:P2_has_type` | `crm:E55_Type3`|
