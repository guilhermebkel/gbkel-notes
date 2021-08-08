# Adding Resource Limit to Captain Rover App

1. Just go into the App on the **App Configs**.

2. Add the following yml config on the **Service Update Override**:

```yml
TaskTemplate:
  Resources:
    Limits:
      MemoryBytes:  300000000
      NanoCPUs: 2000000000
```