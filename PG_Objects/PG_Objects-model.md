# LOD PG Objects_formatted.csv

## Add Column

## Add Node/Literal
#### Literal Node: `http://vocab.getty.edu/aat/300264237`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300266036`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300026687`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300404621`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `http://vocab.getty.edu/aat/300179869`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`

#### Literal Node: `The collection of Crystal Bridges Museum of American Art`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `false`

#### Literal Node: `http://data.crystalbridges.org`
Literal Type: ``
<br/>Language: ``
<br/>isUri: `true`


## PyTransforms
#### _ObjectURI_
From column: _ObjectID_
``` python
return "object/" + getValue("ObjectID")
```

#### _MediumURI_
From column: _Medium_
``` python
if getValue("Medium"):
    return getValue("ObjectURI")+"/medium"
```

#### _DimensionURI_
From column: _Dimensions_
``` python
if getValue("Dimensions"):
    return getValue("ObjectURI")+"/dimensions"
```

#### _ClassificationURI_
From column: _Classification_
``` python
if getValue("Classification"):
    return AATTerm.get_aat_uri("cbm",getValue("Classification"))
else:
    return ""
```

#### _ProductionURI_
From column: _ObjectURI_
``` python
return getValue("ObjectURI")+"/production"
```

#### _ProductionDateURI_
From column: _ProductionURI_
``` python
return getValue("ObjectURI")+"/production/date"
```

#### _DateBeginValid_
From column: _DateBegin_
``` python
if getValue("DateBegin") == '0':
    return ""
else:
    return getValue("DateBegin")+"-01-01"
```

#### _DateEndValid_
From column: _DateEnd_
``` python
if getValue("DateEnd") == '0':
    return ""
else:
    return getValue("DateEnd")+"-12-31"
```

#### _MarkingsURI_
From column: _Markings_
``` python
if getValue("Markings") != "":
    return getValue("ObjectURI") + "/markings"
```

#### _InscribedURI_
From column: _Inscribed_
``` python
if getValue("Inscribed") != "":
    return getValue("ObjectURI") + "/inscribed"
```

#### _SignedURI_
From column: _Signed_
``` python
if getValue("Signed") != "":
    return getValue("ObjectURI") + "/signed"
```

#### _BibilographyURI_
From column: _Bibilography_
``` python
if getValue("Bibilography"):
    return getValue("ObjectURI") + "/Bibilography"
```

#### _CreditLineURI_
From column: _CreditLine_
``` python
if getValue("CreditLine"):
    return getValue("ObjectURI")+"/credit_line"
```

#### _ObjectLabel_
From column: _ObjectID_
``` python
return getValue("ObjectID")
```

#### _ObjectID_URI_
From column: _ObjectLabel_
``` python
return "object/id/" + getValue("ObjectID")
```

#### _TypeAssignmentURI_
From column: _ClassificationURI_
``` python
return getValue("ObjectURI") + "/type_assigned"
```

#### _ExhibitionEventURI_
From column: _Exhibitions_
``` python
return getValue("ObjectURI") + "/exhibition_event"
```

#### _ExhibitionEventAppellationURI_
From column: _ExhibitionEventURI_
``` python
return getValue("ObjectURI") + "/exhibition_event/appellation"
```

#### _DateLabel_
From column: _Dated_
``` python
return getValue("DateBeginValid") + " to " + getValue("DateEndValid")
```

#### _OwnerURI_
From column: _ObjectURI_
``` python
return "http://data.crystalbridges.org/collection"
```


## Selections

## Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Classification_ | `rdfs:label` | `crm:E55_Type1`|
| _ClassificationURI_ | `uri` | `crm:E55_Type1`|
| _CreditLine_ | `rdf:value` | `crm:E33_Linguistic_Object5`|
| _CreditLineURI_ | `uri` | `crm:E33_Linguistic_Object5`|
| _DateBeginValid_ | `crm:P82a_begin_of_the_begin` | `crm:E52_Time-Span1`|
| _DateEndValid_ | `crm:P82b_end_of_the_end` | `crm:E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `crm:E52_Time-Span1`|
| _DimensionURI_ | `uri` | `crm:E33_Linguistic_Object4`|
| _Dimensions_ | `rdf:value` | `crm:E33_Linguistic_Object4`|
| _Medium_ | `rdf:value` | `crm:E33_Linguistic_Object3`|
| _MediumURI_ | `uri` | `crm:E33_Linguistic_Object3`|
| _ObjectID_ | `rdf:value` | `crm:E42_Identifier1`|
| _ObjectID_URI_ | `uri` | `crm:E42_Identifier1`|
| _ObjectURI_ | `uri` | `crm:E22_Man-Made_Object1`|
| _OwnerURI_ | `uri` | `crm:E78_Collection1`|
| _ProductionDateURI_ | `uri` | `crm:E52_Time-Span1`|
| _ProductionURI_ | `uri` | `crm:E12_Production1`|
| _TypeAssignmentURI_ | `uri` | `crm:E17_Type_Assignment1`|


## Links
| From | Property | To |
|  --- | -------- | ---|
| `crm:E12_Production1` | `crm:P4_has_time-span` | `crm:E52_Time-Span1`|
| `crm:E17_Type_Assignment1` | `crm:P42_assigned` | `crm:E55_Type1`|
| `crm:E17_Type_Assignment1` | `crm:P21_had_general_purpose` | `http://vocab.getty.edu/aat/300179869`|
| `crm:E22_Man-Made_Object1` | `crm:P108i_was_produced_by` | `crm:E12_Production1`|
| `crm:E22_Man-Made_Object1` | `crm:P41i_was_classified_by` | `crm:E17_Type_Assignment1`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object3`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object4`|
| `crm:E22_Man-Made_Object1` | `crm:P67i_is_referred_to_by` | `crm:E33_Linguistic_Object5`|
| `crm:E22_Man-Made_Object1` | `crm:P1_is_identified_by` | `crm:E42_Identifier1`|
| `crm:E22_Man-Made_Object1` | `crm:P46i_forms_part_of` | `crm:E78_Collection1`|
| `crm:E22_Man-Made_Object1` | `crm:P2_has_type` | `crm:E55_Type1`|
| `crm:E33_Linguistic_Object3` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300264237`|
| `crm:E33_Linguistic_Object4` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300266036`|
| `crm:E33_Linguistic_Object5` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300026687`|
| `crm:E42_Identifier1` | `crm:P2_has_type` | `http://vocab.getty.edu/aat/300404621`|
| `crm:E78_Collection1` | `crm:P109_has_current_or_former_curator` | `http://data.crystalbridges.org`|
| `crm:E78_Collection1` | `rdfs:label` | `The collection of Crystal Bridges Museum of American Art`|
