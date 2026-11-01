
<a name="top"></a>
<h1>LAMP Stack CRM Deployment</h1>

### 📋 Tickets Covered in This Repository

- 🖥️ [**Ticket #78** — Install a LAMP Stack Application](#ticket-78)


<br />
<br />

<p align="right"><a href="https://github.com/RexQuaye">🏠 Back to home page</a></p>
<br />


---
<br />


<a name="ticket-78"></a>
<h1>Ticket #78 — Install a LAMP Stack Application</h1>

<h2>Languages and Utilities Used</h2>
- <b>Bash</b>
- <b>PHP</b>
- <b>SQL</b>
- <b>MariaDB (mysql_secure_installation)</b>
- <b>Apache httpd</b>
- <b>phpMyAdmin</b>
- <b>Git (GitLab)</b>
- <b>dnf / yum</b>
- <b>systemctl</b>
- <b>firewall-cmd</b>
- <b>vi</b>

<h2>Environments Used</h2>
- <b>CentOS Stream 9 (stage-web-rexq3)</b>
- <b>Web browser (phpMyAdmin and the CRM application)</b>
<br />
<h2>Project walk-through:</h2>

**Task:** The development team released a new application, and I was assigned to deploy it and configure its database.

**Objective:** Strengthen Linux system administrator skills through server deployments using a LAMP stack.

**Requirements:**
- VM: stage-web (stage-web-rexq3)
- Application: Small CRM Project using PHP and MySQL
- LAMP stack: Apache, PHP, phpMyAdmin and a MySQL-compatible database

**Instructions:**
1. Download the project zip file from the Git repository.
2. Extract it on the VM and copy the `crm` folder to `/var/www/html`.
3. Open phpMyAdmin and create a database named `crm`.
4. Import `crm.sql` (from the SQL File folder in the zip package).
5. Edit `/var/www/html/crm/dbconnection.php` and `/var/www/html/crm/admin/dbconnection.php` to add the database password.
6. Open the admin panel at `/crm/admin`.
7. Open the frontend at `/crm` and create a regular user through Sign Up.
8. Test that the new user can access the application.

**Note on redactions:** The database password in the dbconnection.php screenshot, and the email and password in the browser's save-password prompt on the Sign Up screenshot, are redacted. Each affected image says so under its caption.

<br />
<br />
<br />
<p align="center">
<b>stage-web-rexq3 — Creating info.php with phpinfo() to test PHP:</b>
<br/>
<img width="609" height="213" alt="image" src="https://github.com/user-attachments/assets/5ade2c18-9291-44f2-896f-ca9dc845bbcc" />


</p>

<br />
<br />
<br />
<p align="center">
<b>stage-web-rexq3 — PHP 8.0.30 information page served by Apache:</b>
<br/>
<img width="963" height="946" alt="image" src="https://github.com/user-attachments/assets/9b3874c2-7fb6-4b13-9db5-273ed1ff5fc1" />


</p>

<br />
<br />
<br />
<p align="center">
<b>stage-web-rexq3 — Editing the phpMyAdmin Apache configuration (Require all granted added to the Directory block):</b>
<br/>
<img width="770" height="447" alt="image" src="https://github.com/user-attachments/assets/be3e2a67-edbb-475f-b6ac-0c54d3f8c05d" />


</p>

<br />
<br />
<br />
<p align="center">
<b>phpMyAdmin — Home page confirming MariaDB 10.5.29, Apache 2.4.62 and PHP 8.0.30:</b>
<br/>
<img width="1034" height="950" alt="image" src="https://github.com/user-attachments/assets/8099553a-1d9a-4cd5-8dfe-1bda82d96963" />


</p>

<br />
<br />
<br />
<p align="center">
<b>phpMyAdmin — Creating the crm database:</b>
<br/>
<img width="1033" height="332" alt="image" src="https://github.com/user-attachments/assets/3d126afe-ef79-469a-94e5-844b4d7d3ed1" />


</p>

<br />
<br />
<br />
<p align="center">
<b>phpMyAdmin — Importing crm.sql (32 queries executed, five tables created):</b>
<br/>
<img width="1033" height="922" alt="image" src="https://github.com/user-attachments/assets/074ea95d-53b2-4b7b-9326-e522ca974fb3" />


</p>

<br />
<br />
<br />
<p align="center">
<b>stage-web-rexq3 — dbconnection.php with the database password added:</b>
<br/>
<b>Redaction: the database password is hidden.</b>
<br/><img width="570" height="190" alt="image" src="https://github.com/user-attachments/assets/f34f37cc-58f9-4f8b-80a0-c71ce3365234" />


</p>

<br />
<br />
<br />
<p align="center">
<b>CRM — Admin panel loads with live data:</b>
<br/>
<img width="1043" height="606" alt="image" src="https://github.com/user-attachments/assets/df360b34-1b56-4e03-bc96-b35d954ddbb7" />


</p>

<br />
<br />
<br />
<p align="center">
<b>CRM — Frontend sign-in page:</b>
<br/>
<img width="652" height="363" alt="image" src="https://github.com/user-attachments/assets/8f5fbd1a-dc70-4e19-a2ea-8a8fd0f3ba1e" />


</p>

<br />
<br />
<br />
<p align="center">
<b>CRM — Creating a regular user through Sign Up ("Successfully register with us"):</b>
<br/>
<b>Redaction: the email and password in the browser's save-password prompt are hidden.</b>
<br/>
<img width="1047" height="537" alt="image" src="https://github.com/user-attachments/assets/101344ef-d515-4584-8538-984ce5789fd1" />


</p>

<br />
<br />
<br />
<p align="center">
<b>CRM — Logged in as the new regular user:</b>
<br/>
<img width="725" height="798" alt="image" src="https://github.com/user-attachments/assets/52390233-890c-4412-b566-c38da9f08ba6" />


</p>

<br />
<br />
<br />

<b><u>Solution:</u></b> I deployed the development team's Small CRM application (PHP and MySQL) on stage-web-rexq3 by building a full LAMP stack. I installed and secured MariaDB (root password set, anonymous users and the test database removed, remote root login disabled), then installed Apache, enabled it and opened the firewall for HTTP and HTTPS. I installed PHP and confirmed it with a phpinfo() page, then installed phpMyAdmin and edited its Apache configuration so it could be reached in the browser. I cloned the CRM repository from GitLab into <code>/opt/crm-deployment</code>, unzipped the project and copied the <code>crm</code> folder into <code>/var/www/html</code>. In phpMyAdmin I created the <code>crm</code> database and imported <code>crm.sql</code>, which ran 32 queries and created the admin, prequest, ticket, user and usercheck tables. I then added the database password to both <code>dbconnection.php</code> files so the application could connect. Testing showed the admin panel loading with live data, and a new regular user created through Sign Up and logged in on the frontend.

<br />
<br />

<p align="right"><a href="#top">⬆ Back to top</a></p>

<br />
<br />
