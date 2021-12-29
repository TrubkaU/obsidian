#samsung
You can upload file to [[Samsung Store]] 

1. Do 
```
curl -i -X POST \  
  -H  "content-type: application/json" \  
  -H  "Authorization: Bearer 0BwTIery0ptJNjmJjc83V0pF" \  
  -H  "service-account-id: e5fd6869-923a-4dd4-9613-389ec9a304bd" \  
  "https://devapi.samsungapps.com/seller/createUploadSessionId"

```
return 
```json
{
	"url":"https://seller.samsungapps.com/galaxyapi/fileUpload.as",
	"sessionId":"52b7765b-19b3-4218-af68-d5d088eb3d07"
}
```
2. Do 
```
curl -v -i -X  POST \  
  -H "Content-Type:multipart/form-data" \  
  -H "Authorization: Bearer 0BwTIery0ptJNjmJjc83V0pF" \  
  -H "service-account-id: e5fd6869-923a-4dd4-9613-389ec9a304bd" \  
  -F "file=@headspace-production-release.apk" \  
  -F "sessionId=52b7765b-19b3-4218-af68-d5d088eb3d07" \  
  "https://seller.samsungapps.com/galaxyapi/fileUpload"
  ```
  return
  ```json
  {
  	"fileKey":"d61994c5-3e7a-411c-a720-512ae514e334",
	"fileName":"headspace-production-release.apk","errorCode":null,"errorMsg":null
  }
  ```
  