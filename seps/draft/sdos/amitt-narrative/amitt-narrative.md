
# SEP Name
Narrative

## SEP Identifier
`amitt-narrative`

## SEP Version
1

## SEP Description
TODO

## SEP Use Cases
* TODO

## SEP Sponsors
Org                  | Primary Contact
-------------------- | ---------------
CogSec Collaboration | Sara-Jane Terp
CogSec Collaboration | Pablo Breuer
CogSec Collaboration | Roger Johnston
CogSec Collaboration | Eric Duval

## POC Implementations
TODO

Org | GitHub Repository
--- | -----------------
TDB | TDB
TBD | TBD

## SEP Definition

### Properties

#### Required Common Properties
**type, spec_version, id, created, modified**

#### Optional Common Properties
**created_by_ref, revoked, labels, confidence, lang, external_references, object_marking_refs, granular_markings**

#### Not Applicable Common Properties
**defanged, extensions**

#### Narrative Specific Properties

Property Name                       | Type                     | Description
----------------------------------- | ------------------------ | ------------------------
**type** (required)                 | `string`                 | The value of this property **MUST** be narrative.
**name** (optional)                 | `string`                 | A name used to identify the narrative instance or family, as specified by the producer of the SDO. For a narrative family the name **MUST** be defined.
**aliases** (optional)              | `list` of type `string`  | Alternative names used to identify this narrative or narrative family.
**is_family** (required)            | `boolean`                | Whether the object represents a narrative family (if `true`) or a narrative instance (if `false`).
**description** (optional)          | `string`                 | A description that provides more details and context about the narrative instance or family, potentially including its purpose and its key characteristics.
**kill_chain_phases** (optional)    | `list` of type `kill-chain-phase` | The list of Kill Chain Phases for which this narrative can be used.
**first_seen** (optional)           | `timestamp`              | The time that the narrative instance or family was first seen. This property is a summary property of data from sightings and other data that may or may not be available in STIX. If new sightings are received that are earlier than the first seen timestamp, the object may be updated to account for the new data.
**last_seen** (optional)            | `timestamp`              | The time that the narrative family or narrative instance was last seen. This property is a summary property of data from sightings and other data that may or may not be available in STIX. If new sightings are received that are later than the **last_seen** timestamp, the object may be updated to account for the new data. This **MUST** be greater than or equal to the timestamp in the **first_seen** property.
**languages** (optional)            | `list` of type `string`  | Specifies the languages used by the narrative. The value of each list member **MUST** be an ISO 639-2 language code [ISO639-2].
**narrative_types** (optional)      | `list` of type `open-vocab`| A set of categorizations for the narrative being described. The values for this property **SHOULD** come from the `narrative-type-ov` open vocabulary.
**narrative_techniques** (optional) | `list` of type `open-vocab`| A set of techniques for the narrative being described. The values for this property **SHOULD** come from the `narrative-technique-ov` open vocabulary.
**topics** (optional)               | `list` of type `open-vocab`| A set of topics for the narrative being described. The values for this property **SHOULD** come from the `topic-ov` open vocabulary.


## Relationships

### Embedded Relationships
Property Name                       | Type                     
----------------------------------- | ------------------------
**created_by_ref**                  | `identifier` (of type `identity`)
**object_marking_refs**             | `list` of type `identifier` (of type `marking-definition`)


### Common Relationships
`duplicate-of`, `derived-from`, `related-to`

Source                    | Relationship Type                   | Target                    | Description
------------------------- | ----------------------------------- | ------------------------  | ----------------------
TODO                      | TODO                                | TODO                      | TODO


## Vocabularies


### Narrative Type
**Vocabulary Name: `narrative-type-ov`**

Vocabulary Value	                         | Description
------------------------------------------ | ----------------------------------------------------
conspiracy                                 | Conspiracy narratives appeal to the human desire for explanatory order, by invoking the participation of powerful (often sinister) actors in pursuit of their own political goals. These narratives are especially appealing when an audience is low-information, marginalized or otherwise inclined to reject the prevailing explanation. Conspiracy narratives are an important component of the "firehose of falsehoods model.
competing                                  | Suppressing or discouraging narratives already spreading requires an alternative. The most simple set of narrative techniques in response would be the construction and promotion of contradictory alternatives centered on denial, deflection, dismissal, counter-charges, excessive standards of proof, bias in prohibition or enforcement, and so on.

### Narrative Technique
**Vocabulary Name: `narrative-technique-ov`**

Vocabulary Value	        | Description
------------------------- | -------------------------------
constructive-activate     | Bandwagon, pander, ignite. e.g., “If you love Mr. Trump, RT this.”
constructive-astroturf    | Artificial consensus-building, inflation, or amplification. Also called a “Potemkin Village.” e.g., “The \#1 trending hashtag can’t be wrong.”
destructive-suppress      | Harass, intimidate, exhaust. Often targets influential individuals.
destructive-discredit     | Libel, leak, tarnish. Often targets government, political parties, elections, or other institutions.
oblique-troll             | Confusion by way of discourse infiltration and targeted distraction. Conscious efforts by disinformants to derail political movements through tailored engagement.
oblique-flood             | Confusion by way of hashtag invasion and mass noise generation. The hijacking of an online political movement through appropriation of an existing hashtag and addition of large quantity of unrelated material.

### Topic
**Vocabulary Name: `topic-ov`**

Vocabulary Value	                         | Description
------------------------------------------ | ----------------------------------------------------
Government                                 | TODO (Includes international governing bodies)
Military                                   | TODO
Political Party                            | TODO
Elections                                  | TODO
Non-State Political Actor                  | TODO
Business                                   | TODO
Influential Individuals                    | TODO
Racial, Ethnic, Religious, or Sexual Identity Group | TODO
Terrorism                                  | TODO
Immigration                                | TODO
Economic Issue                             | TODO
Other                                      | TODO


### Examples

#### A standalone Narrative
TODO

```json
{
    "TODO": "TODO"
}
```
