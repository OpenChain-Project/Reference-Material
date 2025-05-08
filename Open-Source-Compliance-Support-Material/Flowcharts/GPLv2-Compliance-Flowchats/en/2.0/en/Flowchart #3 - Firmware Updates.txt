## Flowchart #3 - Firmware Updates
```mermaid
flowchart TD
    A[Firmware co-located with source code?]
    A --> |yes| B[Is the Code Complete?] 
    A --> |no| C[Written Offer Supplied?]
    C --> |Yes| D[License Text Supplied?]
    C --> |No| F[Provide Written Offer]
    D --> |No| E[Provide License Text]
    B --> |No| H[Fix] --> B
    B --> I[Done!]
    D --> |Yes| B
    B --> E
    F --> D
```