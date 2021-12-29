#samsung
[[Samsung Store]] provides API
So, what I know for current moment:

1. For getting the list of content. 
It allow to provide the 
 ``` 
 curl -v -X GET \
  -H  "content-type: application/json" \  
  -H  "Authorization: Bearer 0BwTIery0ptJNjmJjc83V0pF" \  
  -H  "service-account-id: e5fd6869-923a-4dd4-9613-389ec9a304bd" \  
  "https://devapi.samsungapps.com/seller/contentList"
  ```
  the resoponse look like:
  ```json
[{
    "contentName": "Headspace: Meditation & Mindfulness",
    "contentId": "000003746860",
    "contentStatus": "REGISTERING",
    "standardPrice": "0",
    "paid": "N",
    "modifyDate": "2021-07-02 09:17:38.0"
  },
  {
    "contentName": "Headspace: Meditation & Mindfulness",
    "contentId": "000003746860",
    "contentStatus": "FOR_SALE",
    "standardPrice": "0",
    "paid": "N",
    "modifyDate": "2021-07-02 09:17:38.0"
  }]
```

2. The detailed info about app you should call:
```
curl -i -X GET \  
  -H "Authorization: Bearer 0BwTIery0ptJNjmJjc83V0pF" \  
  -H "service-account-id: e5fd6869-923a-4dd4-9613-389ec9a304bd" \  
  "https://devapi.samsungapps.com/seller/contentInfo?contentId=000003746860"
  ```
  It will return the detailed info