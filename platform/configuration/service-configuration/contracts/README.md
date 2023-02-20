# Contracts

## Add Module MDMS (Master Data Management Service) Configuration

When creating a Contracts module, the module needs to be enabled in `citymodule.json.`Add the Following details in [citymodule.json](https://github.com/egovernments/works-mdms-data/blob/DEV/data/pb/tenant/citymodule.json)

```json
{
    "tenantId": "pb",
    "moduleName": "tenant",
    "citymodule": [
        {
            "module": "Contracts",
            "code": "Contracts",
            "active": true,
            "order": 1,
            "tenants": [
                {
                    "code": "pb.jalandhar"
                },
                {
                    "code": "pb.nawanshahr"
                },
                {
                    "code": "pb.amritsar"
                }
            ]
        }
}
```
