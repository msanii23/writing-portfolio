## Hello LOVE
I love you, Misa! Here is what you asked for the other day!

{
  "resourceType": "Patient",
  "id": "123",
  "identifier": [
    {
      "system": "http://hospital.example.org/mrn",
      "value": "MRN001"
    }
  ],
  "name": [
    {
      "family": "Doe",
      "given": ["Jane"]
    }
  ],
  "telecom": [
    {
      "system": "phone",
      "value": "+1-555-555-5555",
      "use": "home"
    }
  ],
  "gender": "female",
  "birthDate": "1985-05-15"
}
```xml
<Patient xmlns="http://hl7.org/fhir">
  <id value="123"/>
  <identifier>
    <system value="http://hospital.example.org/mrn"/>
    <value value="MRN001"/>
  </identifier>
  <name>
    <family value="Doe"/>
    <given value="Jane"/>
  </name>
  <telecom>
    <system value="phone"/>
    <value value="+1-555-555-5555"/>
    <use value="home"/>
  </telecom>
  <gender value="female"/>
  <birthDate value="1985-05-15"/>
</Patient>
```

```http
GET /Patient/123
Accept: application/fhir+json
```

```yaml
resourceType: Patient
id: "123"
```

