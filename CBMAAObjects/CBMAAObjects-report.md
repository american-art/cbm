## LOD CBMAA Objects_formatted.csv

### PyTransforms
#### _ObjectURI_
From column: _ObjectID_
>``` python
return "object/" + getValue("ObjectID")
```

#### _MediumURI_
From column: _Medium_
>``` python
if getValue("Medium"):
    return getValue("ObjectURI")+"/medium"
```

#### _DimensionURI_
From column: _Dimensions_
>``` python
if getValue("Dimensions"):
    return getValue("ObjectURI")+"/dimensions"
```

#### _ClassificationURI_
From column: _Classification_
>``` python
if getValue("Classification"):
    return "thesauri/classification/"+getValue("Classification").replace(" ","-")
else:
    return ""
```

#### _ProductionURI_
From column: _ObjectURI_
>``` python
return getValue("ObjectURI")+"/production"
```

#### _ProductionDateURI_
From column: _ProductionURI_
>``` python
return getValue("ObjectURI")+"/production/date"
```

#### _DateBeginValid_
From column: _DateBegin_
>``` python
if getValue("DateBegin") == '0':
    return ""
else:
    return getValue("DateBegin")
```

#### _DateEndValid_
From column: _DateEnd_
>``` python
if getValue("DateEnd") == '0':
    return ""
else:
    return getValue("DateEnd")
```

#### _MarkingsURI_
From column: _Markings_
>``` python
if getValue("Markings") != "":
    return getValue("ObjectURI") + "/markings"
```

#### _ProvenanceURI_
From column: _Provenance_
>``` python
if getValue("Provenance"):
    return getValue("ObjectURI") + "/provenance"
```

#### _InscribedURI_
From column: _Inscribed_
>``` python
if getValue("Inscribed") != "":
    return getValue("ObjectURI") + "/inscribed"
```

#### _SignedURI_
From column: _Signed_
>``` python
if getValue("Signed") != "":
    return getValue("ObjectURI") + "/signed"
```

#### _BibliographyURI_
From column: _Bibliography_
>``` python
if getValue("Bibliography"):
    return getValue("ObjectURI") + "/bibliography"
```


### Semantic Types
| Column | Property | Class |
|  ----- | -------- | ----- |
| _Bibliography_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object2`|
| _BibliographyURI_ | `uri` | `E33_Linguistic_Object2`|
| _Classification_ | `rdfs:label` | `E55_Type1`|
| _ClassificationURI_ | `uri` | `E55_Type1`|
| _DateBeginValid_ | `http://www.cidoc-crm.org/cidoc-crm/P82a_begin_of_the_begin` | `E52_Time-Span1`|
| _DateEndValid_ | `http://www.cidoc-crm.org/cidoc-crm/P82b_end_of_the_end` | `E52_Time-Span1`|
| _Dated_ | `rdfs:label` | `E52_Time-Span1`|
| _DimensionURI_ | `uri` | `E54_Dimension1`|
| _Dimensions_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E54_Dimension1`|
| _Exhibitions_ | `rdfs:label` | `E41_Appellation1`|
| _Inscribed_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E34_Inscription1`|
| _InscribedURI_ | `uri` | `E34_Inscription1`|
| _Markings_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E37_Mark1`|
| _MarkingsURI_ | `uri` | `E37_Mark1`|
| _Medium_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E57_Material1`|
| _MediumURI_ | `uri` | `E57_Material1`|
| _ObjectURI_ | `uri` | `E22_Man-Made_Object1`|
| _ProductionDateURI_ | `uri` | `E52_Time-Span1`|
| _ProductionURI_ | `uri` | `E12_Production1`|
| _Provenance_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E33_Linguistic_Object1`|
| _ProvenanceURI_ | `uri` | `E33_Linguistic_Object1`|
| _Signed_ | `http://www.cidoc-crm.org/cidoc-crm/P3_has_note` | `E37_Mark3`|
| _SignedURI_ | `uri` | `E37_Mark3`|


### Links
| From | Property | To |
|  --- | -------- | ---|
| `E12_Production1` | `http://www.cidoc-crm.org/cidoc-crm/P4_has_time-span` | `E52_Time-Span1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P108i_was_produced_by` | `E12_Production1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P129i_is_subject_of` | `E33_Linguistic_Object1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P129i_is_subject_of` | `E33_Linguistic_Object2`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P12i_was_present_at` | `E7_Activity1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P2_has_type` | `E55_Type1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P43_has_dimension` | `E54_Dimension1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P45_consists_of` | `E57_Material1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P65_shows_visual_item` | `E34_Inscription1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P65_shows_visual_item` | `E37_Mark1`|
| `E22_Man-Made_Object1` | `http://www.cidoc-crm.org/cidoc-crm/P65_shows_visual_item` | `E37_Mark3`|
| `E7_Activity1` | `http://www.cidoc-crm.org/cidoc-crm/P1_is_identified_by` | `E41_Appellation1`|
