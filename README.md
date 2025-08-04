```mermaid
graph TD
    subgraph "Customer Side"
        A[Start App] --> B[Registration Process<br>• Personal & Company Info<br>• Address (Pin on Google Maps)<br>• Verify with OTP]
        B --> C[Login]
        C --> D[Dashboard]
        D --> E[Click 'Order Fuel' Button]
        E --> F[Select Type, Quantity, Location, Date/Time]
        F --> G{Payment Method?}
        G -- "Cash/Credit" --> H[Submit Order]
        G -- "Bank Transfer" --> I[Upload Payment Slip]
        I --> H
        H --> J[Confirm Order]
        J --> K[Track Delivery Status]
        K --> L[Receive Fuel and Sign Confirmation]
        L --> M[End of Order]
    end

    subgraph "Admin Side"
        N[Receive New Order Notification] --> O{Review Order}
        O -- Approve --> P[Assign Driver]
        O -- Reject --> Q[Notify Customer/End]
        P --> R[Send Order to Driver]
        R --> S[Track Driver/Vehicle Status]
        S --> T[Receive Delivery Completion Report]
    end

    subgraph "Driver Side"
        U[Receive Delivery Job Notification] --> V{Accept Job?}
        V -- Accept --> W[Click 'Accept'/Status: 'Loading']
        V -- Decline --> X[Notify Admin/End]
        W --> Y[Drive to Customer Location]
        Y --> Z[Report Delivery]
        Z --> AA[Get Customer Signature]
        AA --> BB[Click 'Delivery Complete']
    end
    
    subgraph "Accounting Side"
        CC[New Invoice] --> DD{Check Payment Slip/Payment Status}
        DD -- Correct --> EE[Confirm Payment]
        DD -- Incorrect --> FF[Contact Customer]
    end
