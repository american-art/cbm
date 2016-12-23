# LOD PG Constituents.csv

## Add Column

## Add Node/Literal
#### Literal Node: `First Name`
Literal Type: `xsd:string`
<br/>Language: ``
<br/>isUri: `false`

#### Literal Node: `http://vocab.getty.edu/aat/300404651`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `Middle Name`
Literal Type: `xsd:string`
<br/>Language: ``
<br/>isUri: `false`

#### Literal Node: `http://vocab.getty.edu/aat/300404654`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `Last Name`
Literal Type: `xsd:string`
<br/>Language: ``
<br/>isUri: `false`

#### Literal Node: `http://vocab.getty.edu/aat/300404652`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404672`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ArtistConstituentURI_
From column: _ConstituentID_
``` python
if getValue("Role") != "Depicted":
    return "person-institution/" + getValue("ConstituentID")
else:
    return ""
```

#### _ArtistActorAppellationURI_
From column: _ConstituentID_
``` python
if getValue("Role") != "Depicted":
    return "person-institution/" + getValue("ConstituentID") + "/appellation"
else:
    return ""
```

#### _DisplayPersonInstitutionName_
From column: _Institution_
``` python
if getValue("Role") == "Depicted":
    return ""
elif getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue("DisplayName")
```

#### _ArtistFirstNameAppellationURI_
From column: _FirstName_
``` python
if getValue("FirstName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ArtistActorAppellationURI") + "/firstname"
```

#### _ArtistFirstNameURI_
From column: _FirstName_
``` python
if getValue("FirstName") == 'NULL':
    return ""
elif getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ArtistActorAppellationURI") + "/name_type/firstname"



```

#### _ArtistMiddleNameAppellationURI_
From column: _MiddleName_
``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ArtistActorAppellationURI") + "/middlename"
```

#### _ArtistMiddleNameURI_
From column: _MiddleName_
``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ArtistActorAppellationURI") + "/nametype/middlename"
```

#### _ArtistLastNameAppellationURI_
From column: _LastName_
``` python
if getValue("LastName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ArtistActorAppellationURI") + "/lastname"
```

#### _ArtistLastNameURI_
From column: _LastName_
``` python
if getValue("LastName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ArtistActorAppellationURI") + "/nametype/lastname"
```

#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/" + getValue("ObjectID")
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI") + "/production" 
```

#### _SitterFirstNameURI_
From column: _FirstName_
``` python
if getValue("FirstName") == 'NULL':
    return ""
elif getValue("Role") != "Depicted":
    return ""
else:
    return "thesauri/nametype/firstname"
```

#### _SitterFirstNameAppellationURI_
From column: _FirstName_
``` python
if getValue("FirstName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return getValue("ConstituentURI") + "/appellation/firstname"
```

#### _SitterMiddleNameURI_
From column: _MiddleName_
``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return "thesauri/nametype/middlename"
```

#### _SitterMiddleNameAppellationURI_
From column: _MiddleName_
``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/middlename"
```

#### _SitterLastNameURI_
From column: _LastName_
``` python
if getValue("LastName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return "thesauri/name/lastname"
```

#### _SitterLastNameAppellationURI_
From column: _LastName_
``` python
if getValue("LastName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/lastname"
```

#### _SitterDisplayPersonInstitutionName_
From column: _Institution_
``` python
if getValue("Role") != "Depicted":
    return ""
elif getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue("DisplayName")
```

#### _SitterConstituentURI_
From column: _ArtistConstituentURI_
``` python
if getValue("Role") == "Depicted":
    return "person-institution/" + getValue("ConstituentID")
else:
    return ""
```

#### _SitterPersonAppellationURI_
From column: _ArtistActorAppellationURI_
``` python
if getValue("Role") == "Depicted":
    return "person-institution/" + getValue("ConstituentID") + "/appellation"
else:
    return ""
```

#### _SitterFirstName_
From column: _FirstName_
``` python
if getValue("Role") == "Depicted":
    return getValue("FirstName")
else:
    return ""
```

#### _ArtistFirstName_
From column: _FirstName_
``` python
if getValue("Role") != "Depicted":
    return getValue("FirstName")
else:
    return ""
```

#### _ArtistMiddleName_
From column: _MiddleName_
``` python
if getValue("Role") != "Depicted":
    return getValue("MiddleName")
else:
    return ""
```

#### _SitterMiddleName_
From column: _MiddleName_
``` python
if getValue("Role") == "Depicted":
    return getValue("MiddleName")
return ""
```

#### _ArtistLastName_
From column: _LastName_
``` python
if getValue("Role") != "Depicted":
    return getValue("LastName")
else:
    return ""
```

#### _SitterLastName_
From column: _LastName_
``` python
if getValue("Role") == "Depicted":
    return getValue("LastName")
else:
    return ""
```

#### _ArtistAlphaSort_
From column: _Institution_
``` python
if getValue("Role") != "Depicted":
    return getValue("AlphaSort")
else:
    return ""
```

#### _ArtistDisplayName_
From column: _Institution_
``` python
if getValue("Role") != "Depicted":
    return getValue("DisplayName")
else:
    return ""
```

#### _ArtistAlphaSortURI_
From column: _ArtistAlphaSort_
``` python
if getValue("Role") != "Depicted":
    return "person-institution/" + getValue("ConstituentID") + "/appellation_alpha_sort"
else:
    return ""
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ArtistActorAppellationURI_ | `uri` | `crm:E82_Actor_Appellation1`|
| _ArtistAlphaSort_ | `rdf:value` | `crm:E82_Actor_Appellation9`|
| _ArtistAlphaSortURI_ | `uri` | `crm:E82_Actor_Appellation9`|
| _ArtistConstituentURI_ | `uri` | `crm:E39_Actor1`|
| _ArtistDisplayName_ | `rdfs:label` | `crm:E39_Actor1`|
| _ArtistFirstName_ | `rdf:value` | `crm:E82_Actor_Appellation2`|
| _ArtistFirstNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation2`|
| _ArtistFirstNameURI_ | `uri` | `crm:E55_Type1`|
| _ArtistLastName_ | `rdfs:label` | `crm:E82_Actor_Appellation4`|
| _ArtistLastNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation4`|
| _ArtistLastNameURI_ | `uri` | `crm:E55_Type3`|
| _ArtistMiddleName_ | `rdf:value` | `crm:E82_Actor_Appellation3`|
| _ArtistMiddleNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation3`|
| _ArtistMiddleNameURI_ | `uri` | `crm:E55_Type2`|
| _DisplayPersonInstitutionName_ | `rdf:value` | `crm:E82_Actor_Appellation1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _SitterConstituentURI_ | `uri` | `crm:E21_Person1`|
| _SitterDisplayPersonInstitutionName_ | `rdfs:label` | `crm:E82_Actor_Appellation5`|
| _SitterFirstName_ | `rdfs:label` | `crm:E82_Actor_Appellation6`|
| _SitterFirstNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation6`|
| _SitterFirstNameURI_ | `uri` | `crm:E55_Type4`|
| _SitterLastName_ | `rdfs:label` | `crm:E82_Actor_Appellation8`|
| _SitterLastNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation8`|
| _SitterLastNameURI_ | `uri` | `crm:E55_Type6`|
| _SitterMiddleName_ | `rdfs:label` | `crm:E82_Actor_Appellation7`|
| _SitterMiddleNameAppellationURI_ | `uri` | `crm:E82_Actor_Appellation7`|
| _SitterMiddleNameURI_ | `uri` | `crm:E55_Type5`|
| _SitterPersonAppellationURI_ | `uri` | `crm:E82_Actor_Appellation5`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P14_carried_out_by` | `crm:E39_Actor1`|
| `crm:E21_Person1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation5`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P62_depicts` | `crm:E21_Person1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation1`|
| `crm:E39_Actor1` | `crm:P131_is_identified_by` | `crm:E82_Actor_Appellation9`|
| `crm:E55_Type1` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404651`|
| `crm:E55_Type1` | `skos:prefLabel` | `xsd:First Name`|
| `crm:E55_Type2` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404654`|
| `crm:E55_Type2` | `skos:prefLabel` | `xsd:Middle Name`|
| `crm:E55_Type3` | `skos:broadMatch` | `xsd:http://vocab.getty.edu/aat/300404652`|
| `crm:E55_Type3` | `skos:prefLabel` | `xsd:Last Name`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation2`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation3`|
| `crm:E82_Actor_Appellation1` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation4`|
| `crm:E82_Actor_Appellation1` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404670`|
| `crm:E82_Actor_Appellation2` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E82_Actor_Appellation3` | `crm:P2_has_type` | `crm:E55_Type2`|
| `crm:E82_Actor_Appellation4` | `crm:P2_has_type` | `crm:E55_Type3`|
| `crm:E82_Actor_Appellation5` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation6`|
| `crm:E82_Actor_Appellation5` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation7`|
| `crm:E82_Actor_Appellation5` | `crm:P106_is_composed_of` | `crm:E82_Actor_Appellation8`|
| `crm:E82_Actor_Appellation6` | `crm:P2_has_type` | `crm:E55_Type4`|
| `crm:E82_Actor_Appellation7` | `crm:P2_has_type` | `crm:E55_Type5`|
| `crm:E82_Actor_Appellation8` | `crm:P2_has_type` | `crm:E55_Type6`|
| `crm:E82_Actor_Appellation9` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404672`|
