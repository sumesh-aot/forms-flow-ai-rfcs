### Flow diagram

```mermaid
sequenceDiagram
    actor  User
    actor  Admin
    participant Formsflow
    participant Camunda
    participant Custom Web
    participant Custom API
    participant ELSTER
    participant ePayBL

    par Authenticate with ELSTER
        User ->> Custom Web : Landing UI
        Custom Web ->> ELSTER : Authenticate business
        ELSTER ->> Custom Web : Authentication Success
        Custom Web ->> Custom API : ELSTER Token
        Custom API ->> Custom API : Save business details and create a JWT for UI
        Custom Web ->> Formsflow Web : Authenticate use using cutom jwt

    <!-- and Manage Users
        Tenant Admin ->> Admin Web : User and tenant maintainance
        Admin Web ->> Tenants API :  Manage users, roles, supported IDPs
        Tenants API ->> Keycloak :  Create Users, client role mappings
    
    and par Tenant login
        Tenant User ->> Formsflow Web : Public landing page
        Formsflow Web ->> Tenants API : Get Tenant keycloak mapping
        Formsflow Web ->> Keycloak : Authenticate using IDP hint and tenant client
        Keycloak ->> Formsflow Web : Receive token with tenant claim -->
    end


```