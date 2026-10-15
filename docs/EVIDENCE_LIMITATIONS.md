# Evidence and security limitations

## What is supported by the Word report

Assignment 3 pages 23–33 document an Ubuntu VM running the EpicBook application with Nginx and PM2, an Azure VNet and NSGs, a MySQL Flexible Server, database connection troubleshooting, and a working storefront screenshot.

## Conflicts in the supplied evidence

1. **MySQL private access is not established:** Task 4 describes private VNet integration; the page 31 screenshot visibly shows **Public access (allowed IP addresses)** and **Virtual network: Not configured**. An additional subnet's existence does not prove the managed DB is attached to it.
2. **NSG rule versus association:** The `NSG-Private` screenshot shows rules, but **0 subnet associations and 0 network-interface associations**. Traffic enforcement on the intended subnet is not proven by that capture.
3. **SQL import and transactions:** The report says database import, cart actions and orders worked; available screenshots do not show a completed import or recorded order.
4. **Frontend wording:** The report mentions a React frontend build. The available Assignment 3 pictures do not independently prove a separate React build. This project remains labeled the **EpicBook monolithic app**.
5. **TLS verification:** A `rejectUnauthorized: false` setting is described in the report. This disables database certificate validation; it is not evidence of secure production TLS.
6. **Unproven production properties:** No evidence for HTTPS on the public site, a load balancer, autoscaling, guaranteed high availability, deployment automation, proactive monitoring, or current availability.

## Photo sourcing

Nine screenshots in `screenshots/` were extracted from the **embedded Word images** associated with Assignment 3, not from PDF page screenshots. The original images are **1958 × 951 px**. Limited browser/header trimming and identifier masking were applied for privacy. This does not add or alter Azure configuration claims.

**For a future portfolio update:** provide current Azure database networking settings, explicit applied NSG associations, a verified SQL query, and a screenshot after testing a completed order if you wish to claim these as demonstrated.
