
## Exports an Application from a desired environment

Commands
```
export-app
 
    Flags
      Required
        -n, --name string          Name of the Application to be exported
        -i, --uuid string          UUID of the Application to be exported
        -e, --environment string   Environment to which the Application should be exported
      Optional
        -p, --password string      Password
        -u, --username string      Username

        -k, --insecure             Allow connections to SSL endpoints without certs
            --verbose              Enable verbose mode
```
```
apimcli export-app (--name <name-of-the-application> --uuid <uuid-of-the-application> --environment <environment-from-which-the-app-should-be-exported>) [flags]
```

```
Examples:

        apimcli export-app -n SampleApp 9f6affe2-4c97-4817-bded-717f8b01eee8 -e dev
        apimcli export-app -n SampleApp 7bc2b94e-c6d2-4d4f-beb1-cdccb08cd87f -e prod

```
## Imports an Application to a desired environment

Commands
```
import-app

    Flags
        Required
          -f, --file string          Name of the Application to be imported
          -e, --environment string   Environment from the which the Application should be imported (default "default")
        Optional
          -s, --addSubscriptions     Adds subscriptions of the Application
          -o, --perserveOwner        Preserves app owner from the original Environment
          -p, --password string      Password
          -u, --username string      Username

          -k, --insecure             Allow connections to SSL endpoints without certs
              --verbose              Enable verbose mode
```

```
apimcli import-app (--file <app-zip-file> --environment <environment-to-which-the-app-should-be-imported>) [flags]
```
```
Examples:

        apimcli import-app -f qa/sampleApp.zip -e dev
        apimcli import-app -f staging/sampleApp.zip -e prod -u admin -p admin
        apimcli import-app -f qa/sampleApp.zip --preserveOwner --addSubscriptions -e prod

```
## Lists the Applications available for a certain user

Commands
```
list apps

    Flags
        Required
            -e, --environment
        Optional
            -u, --username 
            -p, --password 

```
```
Examples:
    
        wso2apim list apps -e dev
        wso2ppim list apps -e staging 
        wso2ppim list apps -e staging -u admin -p 123456
        wso2ppim list apps -e staging -u admin
        wso2ppim list apps -e staging -p 123456
```



