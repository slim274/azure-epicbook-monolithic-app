# Azure EpicBook deployment — documented steps

**Scope:** Week 8, Assignment 3 (pp. 23–33), *as reported*. This is a historical record, not confirmation that Azure services are still active and not a guarantee that any code snippet will operate unchanged today.

## 1. Virtual network and controls — Task 1

- VNet CIDR: `10.0.0.0/16`.
- VM subnet: `10.0.1.0/24`.
- Additional subnet: `10.0.2.0/24`, described as MySQL private subnet in the write-up.
- NSG rules reported: HTTP `80`, SSH `22`, and MySQL `3306` from VM subnet.
- Attached public IP to VM through a network interface.

**Evidence qualification:** Private NSG has no attached subnet/NIC in the source screenshot; MySQL server screenshot does not demonstrate private VNet integration.

## 2. Prepare Ubuntu VM — Task 2

- `epickbookvm` running Ubuntu Server 22.04 LTS.
- Reported installed utilities: Node.js, npm, Nginx, Git, MySQL client.
- Process supervisor: PM2. The screenshots show PM2 online at capture time.

## 3. Deploy monolithic application — Task 3

- Reused the third-party EpicBook application from [theepicbook](https://github.com/pravinmishraaws/theepicbook).
- Installed packages with `npm install`.
- Adjusted Nginx frontend/reverse-proxy location and backend database settings.
- Used PM2 to keep the Node.js service running. A recorded refresh command was:

```bash
pm2 restart epicbook-app --update-env
```

The Word report mentions a React build step; no separately verifiable React build output is included in the Assignment 3 evidence. Do not invent a specific frontend build command.

## 4. MySQL Flexible Server — Task 4

The report names database `bookstore`, user `epicbookadmin`, and SQL data import using:

```bash
mysql -h <mysql-server-hostname> -u epicbookadmin -p bookstore < dump.sql
```

`<mysql-server-hostname>` is the report's placeholder, not a real credential. Its screenshot shows **public-access networking**, contrary to its written private integration statement. Do not publish real passwords in application configuration or screenshots.

## 5. Application validation — Task 5

The report lists an HTTP public VM endpoint and describes book display, cart, and order tests. The included photo visibly establishes only that the EpicBook webpage and book listings were displayed. The IP address is historical and is **not claimed to be online**.

## Recommended future evidence (not shown in the assignment)

For a future redeployment, capture an Nginx configuration test, `pm2 status`, an actual MySQL query result, a confirmed private MySQL networking screen (if private access is configured), and successful cart/order test evidence. Use trusted TLS certificates rather than disabling verification.
