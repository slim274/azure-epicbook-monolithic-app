# Troubleshooting — Week 8 EpicBook (Assignment 3)

The items below come from **Tasks 2–5, report pages 25–32**; they are not newly tested fixes.

| Recorded symptom | Reported action | Evidence boundary |
|---|---|---|
| `Access denied for user 'root'@'localhost'` | Created dedicated `epicbookadmin` MySQL user and updated the connection settings. | Actual grant and connection success output not shown. |
| MySQL VM connection denied / import failed | Updated credentials, network settings and SSL options; tested with MySQL client. | MySQL screenshot shows public access, not private integration; SQL import result not pictured. |
| Nginx pointed to the wrong frontend directory | Corrected Nginx site config and reloaded the service. | No Nginx configuration screenshot in this section. |
| PM2 ignored modified environment variables | Ran `pm2 restart epicbook-app --update-env`. | PM2 process status shown on the page 29 image. |
| Some frontend elements did not render | Corrected DB configuration and refreshed PM2 environment values. | Homepage appears in page 33 image; root cause is reported. |

**Security warning:** The report's `rejectUnauthorized: false` database TLS option bypasses certificate verification. It is not a production-grade solution. Secrets from `config/config.json`, `.env`, or MySQL dumps should not be uploaded to a public repository.
