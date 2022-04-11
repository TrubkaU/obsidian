There is a way to automate delivery to [[00 Huawei store]] by the [[00 Fastlane]]

First, keep the 

Get Bearer token: [Huawei API](https://developer.huawei.com/consumer/en/doc/development/AppGallery-connect-References/agcapi-obtain_token-0000001158365043)
``` bash
curl -i -X POST \ -H "Host: connect-api.cloud.huawei.com" \ -H "Content-Type: application/json" \ -d '{ "grant_type":"client_credentials", "client_id":"821872928160239488", "client_secret":"8BE3C1826ADC162218FE15FDF21C65F10AE47DA141E32E9B78A867F3F9EC4DE6" }'\ "https://connect-api.cloud.huawei.com/api/oauth2/v1/token"
```
