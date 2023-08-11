## {{page-title}}

### Background
The following coded values are used to describe administrative and clinical concepts within the FHIR elements to meet structural requirements of both the data model profiles and user interfaces.

Whenever possible, value sets and code systems were taken from the [US Core Terminology](https://hl7.org/fhir/us/core/terminology.html) and/or [FHIR Core Terminology](http://hl7.org/fhir/terminologies-valuesets.html) that were associated with the resources for interoperability.

#### Notes
- ValueSet resources in Signal's IG have been ["expanded"](https://www.hl7.org/fhir/valueset.html#expansion) utilizing the `ValueSet.expansion` element backbone. This is because Azure FHIR Service lacks a terminology server, so any value set that is not [extensional](https://www.hl7.org/fhir/valueset.html#int-ext), and UI developers require an enumerated lists of all values for display.
   - Expanded value sets retain their original Canonical URL if they are otherwise unmodified
   - Any changes to the original value set including adding or removing a code system, defining additional values, or removing values from the `.compose` element is considered a custom value set and will be noted below
- **\* (Asterisk) Denotes that these code systems an/or value sets have been modified or created for Signal.** 
   - An attempt was made to use a standards-based system whenever possible; e.g. ICD-10, LOINC< SNOMED, CPT, etc. to retain interoperability
   - Any custom values will be defined in a CodeSystem resource in addition to the ValueSet


### Value sets defined by this implementation guide

|Value Set|Description|Profile(s)|Binding Strength|
|---|---|---|---|
| [AddressType](https://www.hl7.org/fhir/valueset-address-type.html) | The type of an address (physical / postal). | [**Organization** - Organization.address.type](Structure-Definition--Organization-Profile) <br /> [**Organization** - Organization.contact.address.type](Structure-Definition--Organization-Profile) <br /> [**Patient** - Patient.address.type](Structure-Definition--Patient-Profile) <br /> [**Practitioner** - Practitioner.address.type](Structure-Definition--Practitioner-Profile) <br /> [**Location** - Location.address.type](Structure-Definition--Location-Profile)| [Required](https://www.hl7.org/fhir/terminologies.html#required) |
| [AddressUse](http://hl7.org/fhir/ValueSet/address-use) | The use of an address | [**Organization** - Organization.address.use](Structure-Definition--Organization-Profile) <br /> [**Organization** - Organization.contact.address.use](Structure-Definition--Organization-Profile) <br /> [**Patient** - Patient.address.use](Structure-Definition--Patient-Profile) <br /> [**Practitioner** - Practitioner.address.use](Structure-Definition--Practitioner-Profile) <br /> [**Location** - Location.address.use](Structure-Definition--Location-Profile) | [Required](https://www.hl7.org/fhir/terminologies.html#required) |
| [ContactPointSystem](https://hl7.org/fhir/valueset-contact-point-use.html) | Telecommunications form for contact point | [**Organization** - Organization.telecom.system](Structure-Definition--Organization-Profile) <br/> [**Organization** - Organization.contact.telecom.system](Structure-Definition--Organization-Profile) <br/> [**Practitioner** - Practitioner.telecom.system](Structure-Definition--Practitioner-Profile) <br/> [**PractitionerRole** - PractitionerRole.telecom.system](Structure-Definition--PractitionerRole-Profile) <br/> [**HealthcareService** - HealthcareService.telecom.system](Structure-Definition--HealthcareService-Profile) <br/> [**Location** - Location.telecom.system](Structure-Definition--Location-Profile) <br/> [**OrganizationAffiliation** - OrganizationAffiliation.telecom.system](Structure-Definition--OrganizationAffiliation-Profile)| [Required](https://www.hl7.org/fhir/terminologies.html#required) |
| [ContactPointUse](http://hl7.org/fhir/ValueSet/contact-point-use.html) | Use of contact point | [**Organization** - Organization.telecom.use](Structure-Definition--Organization-Profile) <br/> [**Organization** - Organization.contact.telecom.use](Structure-Definition--Organization-Profile)<br/> [**Practitioner** - Practitioner.telecom.use](Structure-Definition--Practitioner-Profile) <br/> [**PractitionerRole** - PractitionerRole.telecom.use](Structure-Definition--PractitionerRole-Profile) <br/> [**HealthcareService** - HealthcareService.telecom.use](Structure-Definition--HealthcareService-Profile) <br/> [**Location** - Location.telecom.use](Structure-Definition--Location-Profile) <br/> [**OrganizationAffiliation** - OrganizationAffiliation.telecom.use](Structure-Definition--OrganizationAffiliation-Profile)| [Required](https://www.hl7.org/fhir/terminologies.html#required)|
| [OrganizationType](https://hl7.org/fhir/valueset-organization-type.html) | Kind of organization | [**Organization** - Organization.type](Structure-Definition--Organization-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
| [ContactEntityType](http://hl7.org/fhir/ValueSet/contactentity-type) | The type of contact | [**Organization** - Organization.contact.purpose](Structure-Definition--Organization-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
| [UspsTwoLetterAlphabeticCodes](http://hl7.org/fhir/us/core/ValueSet/us-core-usps-state) | Sub-unit of country | [**Organization** - Organization.address.state](Structure-Definition--Organization-Profile) <br/> [**Practitioner** - Practitioner.address.state](Structure-Definition--Practitioner-Profile) <br/> [**Location** - Location.address.state](Structure-Definition--Location-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
| [NameUse](http://hl7.org/fhir/ValueSet/name-use) | The use of a human name | [**Organization** - Organization.contact.name.use](Structure-Definition--Organization-Profile) <br/> [**Organization** - Organization.contact.name.use](Structure-Definition--Organization-Profile) <br/> [**Practitioner** - Practitioner.name.use](Structure-Definition--Practitioner-Profile)| [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [AdministrativeGender](http://hl7.org/fhir/ValueSet/administrative-gender) | The gender of a person used for administrative purposes | [**Patient** - Patient.gender](Structure-Definition--Patient-Profile) <br/> [**Practitioner** - Practitioner.gender](Structure-Definition--Practitioner-Profile)| [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [OmbRaceCategories](http://hl7.org/fhir/us/core/ValueSet/omb-race-category) | Omb Race categories | [**Patient** - Patient.extension:race:ombCategory](Structure-Definition--Patient-Profile) | [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [DetailedRace](http://hl7.org/fhir/us/core/ValueSet/detailed-race) | Detailed Race | [**Patient** - Patient.extension:race:detailed](Structure-Definition--Patient-Profile) | [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [OmbEthinicityCategories](http://hl7.org/fhir/us/core/ValueSet/omb-ethnicity-category) | Omb Ethnicity Categories | [**Patient** - Patient.extension:ethnicity:ombCategory.value[x]](Structure-Definition--Patient-Profile) | [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [DetailedEthnicity](http://hl7.org/fhir/us/core/ValueSet/detailed-ethnicity) | Detailed Ethnicity | [**Patient** - Patient.extension:ethnicity:detailed.value[x]](Structure-Definition--Patient-Profile) | [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [BirthSex](http://hl7.org/fhir/us/core/ValueSet/birthsex) | Sex at birth | [**Patient** - Patient.extension:birthsex.value[x]](Structure-Definition--Patient-Profile) | [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [GenderIdentity](http://hl7.org/fhir/ValueSet/gender-identity) | This example value set defines a set of codes that can be used to indicate a patient's gender identity | [**Patient** - Patient.extension:genderIdentity.value[x]](Structure-Definition--Patient-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
 | [IdentifierUse](http://hl7.org/fhir/ValueSet/identifier-use) | Identifies the purpose for this identifier, if known | [**Patient** - Patient.identifier.use](Structure-Definition--Patient-Profile) <br/> [**Encounter** -Encounter.identifier.use](Structure-Definition--Encounter-Profile) <br/> [**Organization** -Organization.Identifier.use](Structure-Definition--Organization-Profile) <br/> [**Practitioner** -Practitioner.Identifier.use](Structure-Definition--Practitioner-Profile) <br/> [**Practitioner** -Practitioner.identifier:NPI.use](Structure-Definition--Practitioner-Profile) <br/> [**PractitionerRole** -PractionerRole.Identifier.use](Structure-Definition--PractitionerRole-Profile) <br/> [**Procedure** -Procedure.identifier.use](Structure-Definition--Procedure-Profile) <br/> [**Location** -Location.Identifier.use](Structure-Definition--Location-Profile) <br/> [**Observation** -Observation.identifier.use](Structure-Definition--Observation-Profile) <br/> [**Condition** -Condition.Identifier.use](Structure-Definition--Condition-Profile) <br/> [**QuestionnaireResponse** -QuestionnaireResponse.Identifier.use](Structure-Definition--QuestionnaireResponse-Profile) <br/> [**EpisodeOfCare** -EpisodeOfCare.Identifier.use](Structure-Definition--EpisodeOfCare-Profile) <br/> [**OrganizationAffiliation** -OrganizationAffiliation.Identifier.use](Structure-Definition--OrganizationAffiliation-Profile) <br/> [**HealthcareService** -HealthcareService.Identifier.use](Structure-Definition--HealthcareService-Profile) <br/> [**ServiceRequest** -ServiceRequest.identifier.use](Structure-Definition--ServiceRequest-Profile) <br/> [**ServiceRequest** -ServiceRequest.requisition.use](Structure-Definition--ServiceRequest-Profile) <br/> [**Coverage** -Coverage.identifier.use](Structure-Definition--Coverage-Profile) <br/> [**Contract** -Contract.identifier.use](Structure-Definition--Contract-Profile) <br/> [**Contract** -Contract.term.identifier.use](Structure-Definition--Contract-Profile) <br/> [**Account** -Account.identifier.use](Structure-Definition--Account-Profile) <br/> [**Invoice** -Invoice.identifier.use](Structure-Definition--Invoice-Profile)| [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [IdentifierType](http://hl7.org/fhir/ValueSet/identifier-type) | A coded type for an identifier that can be used to determine which identifier to use for a specific purpose | [**Patient** - Patient.identifier.type](Structure-Definition--Patient-Profile) <br/> [**Encounter** -Encounter.dentifier.type](Structure-Definition--Encounter-Profile) <br/> [**Organization** -Organization.Identifier.type](Structure-Definition--Organization-Profile) <br/> [**Practitioner** -Practitioner.Identifier.type](Structure-Definition--Practitioner-Profile) <br/> [**Practitioner** -Practitioner.identifier:NPI.type](Structure-Definition--Practitioner-Profile) <br/> [**PractitionerRole** -PractionerRole.Identifier.type](Structure-Definition--PractitionerRole-Profile) <br/> [**Procedure** -Procedure.dentifier.type](Structure-Definition--Procedure-Profile) <br/> [**Location** -Location.Identifier.type](Structure-Definition--Location-Profile) <br/> [**Observation** -Observation.identifier.type](Structure-Definition--Observation-Profile) <br/> [**Condition** -Condition.Identifier.type](Structure-Definition--Condition-Profile) <br/> [**QuestionnaireResponse** -QuestionnaireResponse.Identifier.type](Structure-Definition--QuestionnaireResponse-Profile) <br/> [**EpisodeOfCare** -EpisodeOfCare.Identifier.type](Structure-Definition--EpisodeOfCare-Profile) <br/> [**OrganizationAffiliation** -OrganizationAffiliation.Identifier.type](Structure-Definition--OrganizationAffiliation-Profile) <br/> [**HealthcareService** -HealthcareService.Identifier.type](Structure-Definition--HealthcareService-Profile) <br/> [**ServiceRequest** -ServiceRequest.identifier.type](Structure-Definition--ServiceRequest-Profile) <br/> [**ServiceRequest** -ServiceRequest.requisition.type](Structure-Definition--ServiceRequest-Profile) <br/> [**Coverage** -Coverage.identifier.type](Structure-Definition--Coverage-Profile) <br/> [**Contract** -Contract.identifier.type](Structure-Definition--Contract-Profile) <br/> [**Contract** -Contract.term.identifier.type](Structure-Definition--Contract-Profile) <br/> [**Account** -Account.identifier.type](Structure-Definition--Account-Profile) <br/> [**Invoice** -Invoice.identifier.type](Structure-Definition--Invoice-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
 | [EncounterStatus](http://hl7.org/fhir/encounter-status) | Current state of the encounter | [**Encounter** - Encounter.status](Structure-Definition--Encounter-Profile) <br/> [**Encounter** - Encounter.statusHistory.status](Structure-Definition--Encounter-Profile)| [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [EncounterClass](http://terminology.hl7.org/ValueSet/encounter-class) | Classification of patient encounter | [**Encounter** - Encounter.class](Structure-Definition--Encounter-Profile) <br/> [**Encounter** - Encounter.classHistory.class](Structure-Definition--Encounter-Profile)| [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
 | [USCoreEncounterType](http://hl7.org/fhir/us/core/ValueSet/us-core-encounter-type) | Specific type of encounter | [**Encounter** - Encounter.type](Structure-Definition--Encounter-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
  | [ServiceType ](http://hl7.org/fhir/ValueSet/service-type) | Specific type of service | [**Encounter** - Encounter.serviceType](Structure-Definition--Encounter-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [v3-ActPriority](http://terminology.hl7.org/CodeSystem/v3-ActPriority) | Indicates the urgency of the encounter | [**Encounter** - Encounter.priority](Structure-Definition--Encounter-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [ParticipantType](http://hl7.org/fhir/ValueSet/encounter-participant-type) | Role of participant in encounter | [**Encounter** - Encounter.participant.type](Structure-Definition--Encounter-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
 | [DiagnosisRole](http://hl7.org/fhir/ValueSet/diagnosis-role) | Role that this diagnosis has within the encounter (e.g. admission, billing, discharge …) | [**Encounter** - Encounter.diagnosis.use](Structure-Definition--Encounter-Profile) | [ Preferred](https://www.hl7.org/fhir/terminologies.html#preferred) | 
 | [AdmitSource](http://hl7.org/fhir/ValueSet/encounter-admit-source) | From where patient was admitted (physician referral, transfer) | [**Encounter** - Encounter.hospitalization.admitSource](Structure-Definition--Encounter-Profile) | [ Preferred](https://www.hl7.org/fhir/terminologies.html#preferred) | 
 | [ReAdmissionIndicator](http://terminology.hl7.org/ValueSet/v2-0092) | The type of hospital re-admission that has occurred (if any). If the value is absent, then this is not identified as a readmission | [**Encounter** - Encounter.hospitalization.reAdmission](Structure-Definition--Encounter-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [EncounterDiet](http://hl7.org/fhir/ValueSet/encounter-diet) | Diet preferences reported by the patient | [**Encounter** - Encounter.hospitalization.dietPreference](Structure-Definition--Encounter-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [EncounterSpecialCourtesy](http://terminology.hl7.org/ValueSet/v3-EncounterSpecialCourtesy) | Special courtesies (VIP, board member) | [**Encounter** - Encounter.hospitalization.specialCourtesy](Structure-Definition--Encounter-Profile) | [ Preferred](https://www.hl7.org/fhir/terminologies.html#preferred) | 
 | [SpecialArrangements](http://hl7.org/fhir/ValueSet/encounter-special-arrangements) | This defines a set of codes that can be used to indicate the kinds of special arrangements in place for a patients visit. | [**Encounter** - Encounter.hospitalization.specialArrangement](Structure-Definition--Encounter-Profile) | [ Preferred](https://www.hl7.org/fhir/terminologies.html#preferred) | 
 | [EncounterLocationStatus](http://hl7.org/fhir/encounter-location-status) | The status of the location | [**Encounter** - Encounter.location.status](Structure-Definition--Encounter-Profile) | [ Required](https://www.hl7.org/fhir/terminologies.html#required) | 
 | [LocationType](http://terminology.hl7.org/ValueSet/location-physical-type) | The physical type of the location (usually the level in the location hierachy - bed room ward etc.) | [**Encounter** - Encounter.location.physicalType](Structure-Definition--Encounter-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
| [CommonLanguages](http://hl7.org/fhir/ValueSet/languages) | Human language of the content | [**Practitioner** - Practitioner.photo.Language](Structure-Definition--Practitioner-Profile) <br/> [**Practitioner** - Practitioner.communication](Structure-Definition--Practitioner-Profile) <br/> [**HealthcareService** - HealthcareService.photo.Language](Structure-Definition--HealthcareService-Profile) <br/> [**HealthcareService** - HealthcareService.communication](Structure-Definition--HealthcareService-Profile) | [ Preferred](https://www.hl7.org/fhir/terminologies.html#preferred) | 
| [DegreeLicenseCertificate](http://terminology.hl7.org/ValueSet/v2-0360) | Specific qualification the practitioner has to provide a service | [**Practitioner** - Practitioner.qualification.code](Structure-Definition--Practitioner-Profile) | [ Example](https://www.hl7.org/fhir/terminologies.html#required) | 
| [PractitionerRole](http://hl7.org/fhir/ValueSet/practitioner-role) | Roles which this practitioner may perform | [**PractitionerRole** - PractitionerRole.code](Structure-Definition--PractitionerRole-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 
| [PractitionerSpecialty](http://hl7.org/fhir/ValueSet/practitioner-specialty) | Specific specialty of the practitioner | [**PractitionerRole** - PractitionerRole.specialty](Structure-Definition--PractitionerRole-Profile) | [ Extensible](https://www.hl7.org/fhir/terminologies.html#extensible) | 


 



### Other value set notes
[Procedure ValueSet](https://hl7.org/fhir/us/core/ValueSet-us-core-procedure-code.html) will include code systems from ICD, HCPCS, CPT, LOINC, Snomed.