### Flow diagram

```mermaid
sequenceDiagram
    actor  User
    participant Custom Web
    participant Formsflow
    participant Camunda
    participant Custom API
    participant ELSTER
    participant Keycloak
    participant LDAP
    participant ePayBL

    par Authenticate with ELSTER
        User ->> Custom Web : Landing UI
        Custom Web ->> ELSTER : Authenticate business
        ELSTER ->> Custom Web : Authentication token
        Custom Web ->> Custom API : ELSTER Token
        Custom API ->> Custom API : Save business details and create a JWT for UI
        Custom Web ->> Formsflow : Authenticate use using cutom jwt
    par Authenticate with AD
        User ->> Formsflow : Authenticate request
        Formsflow ->> Keycloak : 
        Keycloak ->> AD : Delegate authentication
        Keycloak ->> Keycloak : Map AD groups
        Keycloak ->> Formsflow : Authenticated JWT
    par Payment with ePayBL
        User ->> Custom Web : Payment details page
        Custom Web ->> Custom API : Initiate pay request
        Custom API ->> ePayBL : Initiate pay request
        Custom Web ->> ePayBL : Pay redirect for online payment
        Custom Web ->> Custom API : Validate payment result

    end


```