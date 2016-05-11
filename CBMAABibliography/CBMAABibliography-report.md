## LOD CBMAA Bibliography.csv

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _ReferenceURI_
From column: _ReferenceID_
>``` python
return "reference/" + getValue("ReferenceID")
```

#### _PlaceURI_
From column: _PlacePublished_
>``` python
if getValue("ReferenceURI") != "":
    return getValue("ReferenceURI") + "/place"
```

#### _PlaceAppellationURI_
From column: _PlacePublished_
>``` python
return getValue("PlaceURI") + "/appellation"
```

#### _ConstituentURI_
From column: _ConstituentID_
>``` python
if getValue("ConstituentID") != "":
    return "constituent/" + getValue("ConstituentID")
```

#### _RoleTypeURI_
From column: _RoleTypeID_
>``` python
if getValue("RoleTypeID") != "":
    return "roleType/" + getValue("RoleTypeID")
```

#### _RoleURI_
From column: _RoleID_
>``` python
if getValue("RoleID") != "":
    return "role/" + getValue("RoleID")
```

#### _ConstituentAppellationURI_
From column: _DisplayName_
>``` python
if getValue("ConstituentURI") != "":
    return getValue("ConstituentURI") + "/appellation"
```

#### _PageNumberURI_
From column: _PageNumber_
>``` python
if getValue("PageNumber") != "":
    return "page/" + getValue("PageNumber").replace(", ","_")
```

#### _CatalogueNumberURI_
From column: _Catalogue Number_
>``` python
if getValue("Catalogue Number") != "":
    return "catalogue/" + getValue("Catalogue Number")
```

#### _PublicationYearURI_
From column: _YearPublished_
>``` python
if getValue("YearPublished") != "":
    return getValue("ReferenceURI") + "/publication/date"
```

#### _PublicationDateBeginValid_
From column: _YearPublished_
>``` python
return getValue("YearPublished") + "-01-01"
```

#### _PublicationDateEndValid_
From column: _YearPublished_
>``` python
return getValue("YearPublished") + "-12-31"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _CatalogueNumberURI_ | `uri` | `E31_Document2`|
| _ConstituentAppellationURI_ | `uri` | `E82_Actor_Appellation1`|
| _ConstituentURI_ | `uri` | `E39_Actor1`|
| _DisplayName_ | `rdfs:label` | `E82_Actor_Appellation1`|
| _Format_ | `rdfs:label` | `E55_Type1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _PageNumberURI_ | `uri` | `E73_Information_Object1`|
| _PlaceAppellationURI_ | `uri` | `E44_Place_Appellation1`|
| _PlacePublished_ | `rdfs:label` | `E44_Place_Appellation1`|
| _PlaceURI_ | `uri` | `E53_Place1`|
| _PublicationDateBeginValid_ | `http://www.cidoc-crm.org/cidoc-crm/P82a_begin_of_the_begin` | `E52_Time-Span1`|
| _PublicationDateEndValid_ | `http://www.cidoc-crm.org/cidoc-crm/P82b_end_of_the_end` | `E52_Time-Span1`|
| _PublicationYearURI_ | `uri` | `E52_Time-Span1`|
| _ReferenceURI_ | `uri` | `E31_Document1`|
| _Role_ | `rdfs:label` | `E55_Type3`|
| _RoleType_ | `rdfs:label` | `E55_Type2`|
| _RoleTypeURI_ | `uri` | `E55_Type2`|
| _RoleURI_ | `uri` | `E55_Type3`|
| _Title_ | `rdfs:label` | `E42_Identifier1`|
| _YearPublished_ | `rdfs:label` | `E52_Time-Span1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P70i_is_documented_in` | `E31_Document1`|
| `E31_Document1` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E73_Information_Object1`|
| `E31_Document1` | `http://www.cidoc-crm.org/cidoc-crm/P1_is_identified_by` | `E42_Identifier1`|
| `E31_Document1` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type1`|
| `E31_Document2` | `http://www.cidoc-crm.org/cidoc-crm/P106_is_composed_of` | `E31_Document1`|
| `E39_Actor1` | `http://www.cidoc-crm.org/cidoc-crm/P1_is_identified_by` | `E82_Actor_Appellation1`|
| `E39_Actor1` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type3`|
| `E53_Place1` | `http://www.cidoc-crm.org/cidoc-crm/P87_is_identified_by` | `E44_Place_Appellation1`|
| `E55_Type3` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type2`|
| `E65_Creation1` | `http://www.cidoc-crm.org/cidoc-crm/P14_carried_out_by` | `E39_Actor1`|
| `E65_Creation1` | `http://www.cidoc-crm.org/cidoc-crm/P4_has_time-span` | `E52_Time-Span1`|
| `E65_Creation1` | `http://www.cidoc-crm.org/cidoc-crm/P7_took_place_at` | `E53_Place1`|
| `E65_Creation1` | `http://www.cidoc-crm.org/cidoc-crm/P94_has_created` | `E31_Document1`|
