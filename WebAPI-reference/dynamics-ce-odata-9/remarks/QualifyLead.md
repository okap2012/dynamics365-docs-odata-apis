
QualifyLead Action qualifies a lead record and creates account, contact, and opportunity records that are linked to the originating lead record.

## Example

**Request**

```HTTP
POST [Organization URI]/api/data/v9.0/leads(f282fa8b-3bcf-e711-80f3-00155d889a3b)/Microsoft.Dynamics.CRM.QualifyLead HTTP/1.1
If-None-Match: null
OData-Version: 4.0
Content-Type: application/json
Accept: application/json
OData-MaxVersion: 4.0
Prefer: return=representation

{
  	"CreateAccount":true,
  	"CreateContact":true,
  	"CreateOpportunity":true,
  	"Status":3,
    "OpportunityCurrencyId":{'@odata.type':'Microsoft.Dynamics.CRM.transactioncurrency','transactioncurrencyid':'874ca79f-b2ce-e711-80ee-00155d889a3b'},
    "OpportunityCustomerId":{'@odata.type':'Microsoft.Dynamics.CRM.contact','contactid':'720dd88f-fece-e711-80f3-00155d889a3b'},
    "SourceCampaignId":{'@odata.type':'Microsoft.Dynamics.CRM.campaign','campaignid':'260dd88f-fece-e711-80f3-00155d889a3b'}
}
```
**Response**
```JSON
{
      "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#Collection(Microsoft.Dynamics.CRM.crmbaseentity)",
      "value": [
  		<JSON data of created Account, Contact and Opportunity records omitted for brevity>
  	     ]
}
  ```
