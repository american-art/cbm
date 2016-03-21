## LOD PG Exhibitions.csv

### PyTransforms
#### _VenueConstituentURI_
From column: _VenueConstituentID_
>``` python
return "place/" + getValue("VenueConstituentID")
```

#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _ExhibitionURI_
From column: _ExhibitionID_
>``` python
return "exhibition/" + getValue("ExhibitionID")
```

#### _AppellationURI_
From column: _ExhibitionURI_
>``` python
return getValue("ExhibitionURI") + "/appellation"
```

#### _ExhibitionDateURI_
From column: _ExhibitionURI_
>``` python
return getValue("ExhibitionURI") + "/exhibition/date"
```

#### _PlaceAppellationURI_
From column: _VenueConstituentURI_
>``` python
return getValue("VenueConstituentURI") + "/appellation"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AppellationURI_ | `uri` | `E41_Appellation1`|
| _ExhTitle_ | `rdfs:label` | `E41_Appellation1`|
| _ExhibBeginISODate_ | `http://www.cidoc-crm.org/cidoc-crm/P82a_begin_of_the_begin` | `E52_Time-Span1`|
| _ExhibEndISODate_ | `http://www.cidoc-crm.org/cidoc-crm/P82b_end_of_the_end` | `E52_Time-Span1`|
| _ExhibitionDateURI_ | `uri` | `E52_Time-Span1`|
| _ExhibitionURI_ | `uri` | `E7_Activity1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _PlaceAppellationURI_ | `uri` | `E44_Place_Appellation1`|
| _VenueConstituentURI_ | `uri` | `E53_Place1`|
| _VenueDisplayName_ | `rdfs:label` | `E44_Place_Appellation1`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P12i_was_present_at` | `E7_Activity1`|
| `E53_Place1` | `http://www.cidoc-crm.org/cidoc-crm/P1_is_identified_by` | `E44_Place_Appellation1`|
| `E7_Activity1` | `http://www.cidoc-crm.org/cidoc-crm/P1_is_identified_by` | `E41_Appellation1`|
| `E7_Activity1` | `http://www.cidoc-crm.org/cidoc-crm/P4_has_time-span` | `E52_Time-Span1`|
| `E7_Activity1` | `http://www.cidoc-crm.org/cidoc-crm/P7_took_place_at` | `E53_Place1`|
