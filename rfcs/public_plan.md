### Flow diagram

```mermaid
sequenceDiagram
    actor  User
    participant Custom Web
    participant Formsflow
    participant Camunda
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


    end


```