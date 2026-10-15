# Week 8 Assignment 3 — Report-based deployment record

**Sole source:** `IBRAHIM AHMED ABIODUN_Week8_GROUP2.docx`, **pages 23–33**, from **Assignment 3: Deploy EpicBook Web App on Azure Virtual Machine with Azure Database for MySQL**. No material from Assignment 1, 2, or 4 is included.

This document records **what the assignment says**. Where a screenshot supports less than the written account, that distinction is made explicitly.

## Task 1 — Network (pp. 23–25)

**Reported:** Created VNet `10.0.0.0/16`, VM subnet `10.0.1.0/24`, private MySQL subnet `10.0.2.0/24`, public NSG rules for HTTP `80` and SSH `22`, and a private NSG rule allowing MySQL `3306` from the VM subnet. Assigned the VM a public IP. The report describes initially missing a restrictive DB rule, then correcting it.

**Visual evidence:** [VNet](../screenshots/01-azure-vnet.png), [subnets](../screenshots/02-azure-subnets.png), [public NSG](../screenshots/03-public-nsg.png), [private NSG](../screenshots/04-private-nsg.png), [public IP](../screenshots/05-vm-public-ip.png). The private NSG screenshot has **0 associated subnets / NICs**; a configured rule is not the same as an enforced attachment.

## Task 2 — Ubuntu VM / tools (pp. 25–26)

**Reported:** Provisioned an Ubuntu 22.04 LTS VM named `epickbookvm`, updated packages, installed Node.js, npm, Nginx, Git and MySQL client, deployed code with `npm install`, and managed the app with PM2. Encountered `root@localhost` access denied and stale PM2 environment values; used a dedicated database account and refreshed PM2's environment.

**Visual evidence:** [VM resource](../screenshots/06-epicbook-ubuntu-vm.png), [PM2 output](../screenshots/07-pm2-terminal.png). Screenshots do not individually prove every package version or VM bootstrap command.

## Task 3 — Deploy EpicBook (pp. 27–28)

**Reported:** Forked and cloned the EpicBook source, installed application dependencies, configured Nginx to serve the frontend and route requests to Node.js/Express, connected the backend to `bookstore`, and ran it with PM2. The written assignment also says "built the React frontend"; this screenshot set contains **no distinct React-build proof**, so the portfolio presents EpicBook as the monolithic application in this assignment rather than claiming a separately verified React deployment.

**Recorded corrections:** Nginx directory configuration, database credentials / SSL settings, and `pm2 restart epicbook-app --update-env`.

## Task 4 — Azure MySQL (pp. 29–30)

**Reported:** Created MySQL Flexible Server and database `bookstore` with database user `epicbookadmin`, imported the SQL dump with a MySQL client from the VM, and set connection access. The report describes **private VNet integration**.

**Screenshot limitation:** [MySQL resource overview](../screenshots/08-azure-mysql-flexible-server.png) shows **Public access (allowed IP addresses)** and **Virtual network: Not configured**. A [terminal screenshot](../screenshots/07-pm2-terminal.png) shows PM2 processes, **not** database import output. Consequently private network integration and completed SQL import cannot be independently verified from the pictures.

**Security note:** The report includes the Sequelize setting `rejectUnauthorized: false` as a connection workaround. It turns off database certificate verification; do not describe that setting as production-secure.

## Task 5 — Application check (pp. 31–32)

**Reported:** Opened `http://20.200.113.164`, verified the EpicBook home page, viewed database-backed book listings, added items to a cart and submitted orders. It also documents correcting credentials and restarting PM2 after frontend rendering errors.

**Visible:** [EpicBook homepage](../screenshots/09-epicbook-application.png) shows the site's bookstore interface and books. Separate transaction screenshots or SQL query results are **not provided**.

## Task 6 — LinkedIn submission (p. 33)

The report contains a public LinkedIn submission URL. The portfolio uses infrastructure screenshots as its primary technical evidence instead of confusing the LinkedIn post with proof of live system health.

## Attribution

Original application: https://github.com/pravinmishraaws/theepicbook. This report documents **the user's deployment and operational work**, not their original authorship of EpicBook.
