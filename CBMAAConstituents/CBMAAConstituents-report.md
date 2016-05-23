## LOD CBMAA Constituents.csv

### PyTransforms
#### _ArtistConstituentURI_
From column: _ConstituentID_
>``` python
if getValue("Role") != "Depicted":
    return "person-institution/" + getValue("ConstituentID")
else:
    return ""
```

#### _ArtistActorAppellationURI_
From column: _ConstituentID_
>``` python
if getValue("Role") != "Depicted":
    return "person-institution/" + getValue("ConstituentID") + "/appellation"
else:
    return ""
```

#### _DisplayPersonInstitutionName_
From column: _Institution_
>``` python
if getValue("Role") == "Depicted":
    return ""
elif getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue("DisplayName")
```

#### _ArtistFirstNameAppellationURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ConstituentURI") + "/appellation/firstname"
```

#### _ArtistFirstNameURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL':
    return ""
elif getValue("Role") == "Depicted":
    return ""
else:
    return "thesauri/nametype/firstname"
```

#### _ArtistMiddleNameAppellationURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/middlename"
```

#### _ArtistMiddleNameURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return "thesauri/nametype/middlename"
```

#### _ArtistLastNameAppellationURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/lastname"
```

#### _ArtistLastNameURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL' or getValue("Role") == "Depicted":
    return ""
else:
    return "thesauri/name/lastname"
```

#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI") + "/production" 
```

#### _SitterFirstNameURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL':
    return ""
elif getValue("Role") != "Depicted":
    return ""
else:
    return "thesauri/nametype/firstname"
```

#### _SitterFirstNameAppellationURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return getValue("ConstituentURI") + "/appellation/firstname"
```

#### _SitterMiddleNameURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return "thesauri/nametype/middlename"
```

#### _SitterMiddleNameAppellationURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/middlename"
```

#### _SitterLastNameURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return "thesauri/name/lastname"
```

#### _SitterLastNameAppellationURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL' or getValue("Role") != "Depicted":
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/lastname"
```

#### _SitterDisplayPersonInstitutionName_
From column: _Institution_
>``` python
if getValue("Role") != "Depicted":
    return ""
elif getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue("DisplayName")
```

#### _SitterConstituentURI_
From column: _ArtistConstituentURI_
>``` python
if getValue("Role") == "Depicted":
    return "person-institution/" + getValue("ConstituentID")
else:
    return ""
```

#### _SitterPersonAppellationURI_
From column: _ArtistActorAppellationURI_
>``` python
if getValue("Role") == "Depicted":
    return "person-institution/" + getValue("ConstituentID") + "/appellation"
else:
    return ""
```

#### _SitterFirstName_
From column: _FirstName_
>``` python
if getValue("Role") == "Depicted":
    return getValue("FirstName")
else:
    return ""
```

#### _ArtistFirstName_
From column: _FirstName_
>``` python
if getValue("Role") != "Depicted":
    return getValue("FirstName")
else:
    return ""
```

#### _ArtistMiddleName_
From column: _MiddleName_
>``` python
if getValue("Role") != "Depicted":
    return getValue("MiddleName")
else:
    return ""
```

#### _SitterMiddleName_
From column: _MiddleName_
>``` python
if getValue("Role") == "Depicted":
    return getValue("MiddleName")
return ""
```

#### _ArtistLastName_
From column: _LastName_
>``` python
if getValue("Role") != "Depicted":
    return getValue("LastName")
else:
    return ""
```

#### _SitterLastName_
From column: _LastName_
>``` python
if getValue("Role") == "Depicted":
    return getValue("LastName")
else:
    return ""
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ActorAppellationURI_ | `uri` | `E82_Actor_Appellation1`|
| _ArtistFirstName_ | `rdfs:label` | `E82_Actor_Appellation2`|
| _ArtistFirstNameAppellationURI_ | `uri` | `E82_Actor_Appellation2`|
| _ArtistFirstNameURI_ | `uri` | `E55_Type1`|
| _ArtistLastName_ | `rdfs:label` | `E82_Actor_Appellation4`|
| _ArtistLastNameAppellationURI_ | `uri` | `E82_Actor_Appellation4`|
| _ArtistLastNameURI_ | `uri` | `E55_Type3`|
| _ArtistMiddleName_ | `rdfs:label` | `E82_Actor_Appellation3`|
| _ArtistMiddleNameAppellationURI_ | `uri` | `E82_Actor_Appellation3`|
| _ArtistMiddleNameURI_ | `uri` | `E55_Type2`|
| _ConstituentURI_ | `uri` | `E39_Actor1`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `E82_Actor_Appellation1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `E12_Production1`|
| _Role_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E12_Production1`|
| _SitterConstituentURI_ | `uri` | `E21_Person1`|
| _SitterDisplayPersonInstitutionName_ | `rdfs:label` | `E82_Actor_Appellation5`|
| _SitterFirstName_ | `rdfs:label` | `E82_Actor_Appellation6`|
| _SitterFirstNameAppellationURI_ | `uri` | `E82_Actor_Appellation6`|
| _SitterFirstNameURI_ | `uri` | `E55_Type4`|
| _SitterLastName_ | `rdfs:label` | `E82_Actor_Appellation8`|
| _SitterLastNameAppellationURI_ | `uri` | `E82_Actor_Appellation8`|
| _SitterLastNameURI_ | `uri` | `E55_Type6`|
| _SitterMiddleName_ | `rdfs:label` | `E82_Actor_Appellation7`|
| _SitterMiddleNameAppellationURI_ | `uri` | `E82_Actor_Appellation7`|
| _SitterMiddleNameURI_ | `uri` | `E55_Type5`|
| _SitterPersonAppellationURI_ | `uri` | `E82_Actor_Appellation5`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P14_carried_out_by` | `E39_Actor1`|
| `E21_Person1` | `http://www.cidoc-crm.org/cidoc-crm/P131_is_identified_by` | `E82_Actor_Appellation5`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P62_depicts` | `E21_Person1`|
| `E39_Actor1` | `http://www.cidoc-crm.org/cidoc-crm/P131_is_identified_by` | `E82_Actor_Appellation1`|
| `E82_Actor_Appellation1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation2`|
| `E82_Actor_Appellation1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation3`|
| `E82_Actor_Appellation1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation4`|
| `E82_Actor_Appellation2` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type1`|
| `E82_Actor_Appellation3` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type2`|
| `E82_Actor_Appellation4` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type3`|
| `E82_Actor_Appellation5` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation6`|
| `E82_Actor_Appellation5` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation7`|
| `E82_Actor_Appellation5` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation8`|
| `E82_Actor_Appellation6` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type4`|
| `E82_Actor_Appellation7` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type5`|
| `E82_Actor_Appellation8` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type6`|
