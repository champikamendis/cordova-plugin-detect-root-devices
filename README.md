# cordova-plugin-detect-root-devices
This is cordova plugin for android to detect whether our device is not rooted. Here uses the google Safetynet Attestation Api for root detection

You can use following line to call the plugin <br></br>
```
detectRoot.attest(API_KEY, onSuccessCallback, onErrorCallback);
```

You can access the callbacks like following code. <br></br>
```
function onSuccessCallback(response) {
    const responseJson = JSON.parse(response.data);
    console.log("This is success callback", responseJson);
    //  In here you can access the json object of the response
    //  when ctsProfileMatch=true that means your device is not rooted
    if(responseJson.ctsProfileMatch) {
        console.log("This device is not rooted");
    } else {
        console.log("This device is rooted");
    }
}

function onErrorCallback(response) {
//  In errorCallback it will give String as the response
    console.log("This is failure callback", response);
}
```
