## LOD PG Constituents.csv

### PyTransforms
#### _ConstituentURI_
From column: _ConstituentID_
>``` python
return "person-institution/" + getValue("ConstituentID")
```

#### _ActorAppellationURI_
From column: _ConstituentID_
>``` python
return "person-institution/" + getValue("ConstituentID") + "/appellation"
```

#### _DisplayPersonInstitutionName_
From column: _Institution_
>``` python
if getValue("DisplayName") == 'NULL':
    return getValue("Institution")
else:
    return getValue("DisplayName")
```

#### _FirstNameAppellationURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL':
    return ""
else:
    return getValue("ConstituentURI") + "/appellation/firstname"
```

#### _FirstNameURI_
From column: _FirstName_
>``` python
if getValue("FirstName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/firstname"
```

#### _MiddleNameAppellationURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL':
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/middlename"
```

#### _MiddleNameURI_
From column: _MiddleName_
>``` python
if getValue("MiddleName") == 'NULL':
    return ""
else:
    return "thesauri/nametype/middlename"
```

#### _LastNameAppellationURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL':
    return ""
else:
    return getValue("ConstituentURI")+"/appellation/lastname"
```

#### _LastNameURI_
From column: _LastName_
>``` python
if getValue("LastName") == 'NULL':
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


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _ActorAppellationURI_ | `uri` | `E82_Actor_Appellation1`|
| _ConstituentURI_ | `uri` | `E39_Actor1`|
| _DisplayPersonInstitutionName_ | `rdfs:label` | `E82_Actor_Appellation1`|
| _FirstName_ | `rdfs:label` | `E82_Actor_Appellation2`|
| _FirstNameAppellationURI_ | `uri` | `E82_Actor_Appellation2`|
| _FirstNameURI_ | `uri` | `E55_Type1`|
| _LastName_ | `rdfs:label` | `E82_Actor_Appellation4`|
| _LastNameAppellationURI_ | `uri` | `E82_Actor_Appellation4`|
| _LastNameURI_ | `uri` | `E55_Type3`|
| _MiddleName_ | `rdfs:label` | `E82_Actor_Appellation3`|
| _MiddleNameAppellationURI_ | `uri` | `E82_Actor_Appellation3`|
| _MiddleNameURI_ | `uri` | `E55_Type2`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionURI_ | `uri` | `E12_Production1`|
| _Role_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E12_Production1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P14_carried_out_by` | `E39_Actor1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
| `E39_Actor1` | `http://www.cidoc-crm.org/cidoc-crm/P131_is_identified_by` | `E82_Actor_Appellation1`|
| `E82_Actor_Appellation1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation2`|
| `E82_Actor_Appellation1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation3`|
| `E82_Actor_Appellation1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E82_Actor_Appellation4`|
| `E82_Actor_Appellation2` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type1`|
| `E82_Actor_Appellation3` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type2`|
| `E82_Actor_Appellation4` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type3`|
