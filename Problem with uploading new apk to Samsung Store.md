#samsung 

The are issue for updating the apk on the [[Samsung Store]]
After running [[Upload file to Samsung Store]] I'm trying to:
```
curl -i -X POST \  
  -H "Content-Type: application/json" \  
  -H "Authorization: Bearer 0BwTIery0ptJNjmJjc83V0pF" \  
  -H "service-account-id: e5fd6869-923a-4dd4-9613-389ec9a304bd" \  
  -d '{"contentId": "000007654321", "binaryList":[{"fileName": "headspace-production-release.apk","binarySeq": "61","versionCode": "3","versionName": "3","packageName": "com.getsomeheadspace.android","nativePlatforms": null,"apiminSdkVersion": "21","apimaxSdkVersion": null,"iapSdk": "N","gms": "Y","filekey": "49153fdc-10e1-400c-b65a-83bae78d9d2f"}]}'\  
  "https://devapi.samsungapps.com/seller/contentUpdate"
  ```
  I got the 
  ```json
  {	"from":"seller",
  	"body":{
	"ctntId":"000007654321",		   
	"contentStatus":null,
	"httpStatus":"BAD_REQUEST",
	"errorCode":"4128",
	"errorMsg":"You must have an app in service that is already registered on the Seller Portal. The Developer API does not support new app registration."
	}
}
```
So, it's confused why it impossible to add the binary file, or I should add like testing track?

The questions:
I should move the app to Register. How I can do that?