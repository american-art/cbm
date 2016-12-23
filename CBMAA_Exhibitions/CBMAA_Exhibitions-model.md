# LOD CBMAA Exhibitions.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300404670`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _VenueConstituentURI_
From column: _VenueConstituentID_
``` python
return "place/" + getValue("VenueConstituentID")
```

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

#### _ExhibitionDateURI_
From column: _ExhibitionURI_
``` python
return getValue("ExhibitionURI") + "/exhibition/date"
```

#### _PlaceAppellationURI_
From column: _VenueConstituentURI_
``` python
return getValue("VenueConstituentURI") + "/appellation"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _AppellationURI_ | `uri` | `crm:E41_Appellation1`|
| _ExhibitionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ExhibitionURI_ | `uri` | `crm:E5_Event1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _PlaceAppellationURI_ | `uri` | `crm:E44_Place_Appellation1`|
| _VenueConstituentURI_ | `uri` | `crm:E53_Place1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E22_Man-Made_Object1` | `crm:P12i_was_present_at` | `crm:E5_Event1`|
| `crm:E41_Appellation1` | `crm:P2_has_type` | `xsd:http://vocab.getty.edu/aat/300404670`|
| `crm:E53_Place1` | `crm:P1_is_identified_by` | `crm:E44_Place_Appellation1`|
| `crm:E5_Event1` | `crm:P1_is_identified_by` | `crm:E41_Appellation1`|
| `crm:E5_Event1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E5_Event1` | `crm:P7_took_place_at` | `crm:E53_Place1`|
