
## Exports an Application from a desired environment

Commands
```
export-app
 
    Flags
      Required
        -n, --name string          Name of the Application to be exported
        -o, --owner string         Owner of the Application to be exported
        -e, --environment string   Environment to which the Application should be exported
      Optional
        -u, --username string      Username
        -p, --password string      Password
        
        -h, --help                 Help for export-app

        -k, --insecure             Allow connections to SSL endpoints without certs
            --verbose              Enable verbose mode
```
```
apimcli export-app (--name <name-of-the-application> --owner <owner-of-the-application> --environment <environment-from-which-the-app-should-be-exported>) [flags]

```

```
Examples:

        apimcli export-app -n SampleApp -o admin -e dev
        apimcli export-app -n SampleApp -o admin -e prod
        
```
```
Sample Response:
  
        Succesfully exported Application!
        Find the exported Application at /home/user/.wso2apimcli/exported/apps/dev/admin_sampleApp.zip

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
          -s, --skipSubscriptions    Skips subscriptions of the Application
          -o, --owner string         Name of the target Owner of the Application as desired by the Importer
          -r, --preserveOwner        Preserves app owner from the original Environment
          -u, --username string      Username
          -p, --password string      Password
          
          -h, --help                 Help for import-app
          

          -k, --insecure             Allow connections to SSL endpoints without certs
              --verbose              Enable verbose mode
```

```
apimcli import-app (--file <app-zip-file> --environment <environment-to-which-the-app-should-be-imported>) [flags]
```
```
Examples:

        apimcli import-app -f qa/sampleApp.zip -e dev
        apimcli Import App -f staging/sampleApp.zip -e prod -o testUser -u admin -p admin
        apimcli import-app -f qa/sampleApp.zip --preserveOwner --skipSubscriptions -e staging

```
```
Sample Response:

        ZipFilePath: /home/user/.wso2apimcli/exported/apps/staging/admin_sampleApp.zip
        Succesfully imported Application!

```
## Display a list of Applications in an environment specific to an owner

Commands
```
list apps

    Flags
        Required
            -e, --environment          Environment to be searched
            -o, --owner string         Owner of the Application
        Optional
            -u, --username             Username
            -p, --password             Password
            
            -h, --help                 Help for list apps

```
```
Examples:
    
        apimcli list apps -e dev -o admin 
        apimcli list apps -e staging -o sampleUser -u admin -p 123456
     
```
```
Sample Response:

        Environment: dev
        No. of Applications: 3
        +--------------------------------------+-----------+-------+----------+----------+
        |                  ID                  |   NAME    | OWNER |  STATUS  | GROUP-ID |
        +--------------------------------------+-----------+-------+----------+----------+
        | 0e09806c-65bb-4114-b483-3f7521e51a70 | adminApp1 | admin | APPROVED |          |
        | d2b2a966-97e6-40da-9f73-7202d6c2bf9b | sampleApp | admin | APPROVED |          |
        | 2817069d-ce62-410c-9f10-9f3910912bee | sharedApp | admin | APPROVED | testGrp  |
        +--------------------------------------+-----------+-------+----------+----------+



```


