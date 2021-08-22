# Adding Resource Limit to Captain Rover App

1. Just go into the App on the **App Configs**.

2. Add the following script config on the **Pre-Deploy Script**:

```js
var preDeployFunction = function (captainAppObj, dockerUpdateObject) {
    return Promise.resolve()
        .then(function(){
            dockerUpdateObject.TaskTemplate.Resources = {Limits: {MemoryBytes: 300000000}};
            return dockerUpdateObject;
        });
};
```