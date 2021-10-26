# Cloud SQL
- Relational Database
- fully managed
- default snapshot backup of 7 days
- Manual scaling
- RDBMS
    - MySQL
    - Postgres
- import and export databases using "mysqldump", or import and export CSV files

# Keywords
### Cloud SQL Instance
- corresponds to one VM
- the VM includes the database instance and accompanying software containers used to keep the database up and running

### Database Instance
- set of software files that run the database: MySQL, PostgreSQL, or SQL Server

### High Availability
- provides reliabilty by having two synchronized instances: primary and standby
- each synchronized instance has only one VM and each instance is in a different zone in the same exact region.

### Failover
- occurs when Cloud SQL switches from the primary synchronized instance to the standby sychronized instance

### Standby Instance
- used in High Availability to replace the primary synchronized instance when Failover happens
- does not appear in GCP console
connections to primary synchronized instance automatically transferred to standby synchronized instance when failover occurs

### Clone
- you create a new, independent instance that is an exact copy of the original source instance 
- any changes in the original source instance and the cloned instance are indepedent from each other
```bash
gcloud sql intances patch mysqldb

gcloud sql backups create --instance mysqldb

gcloud sql export sql mysqldb gs://mybucket/data.sql --database=mysql
gcloud sql export csv mysqldb gs://mybucket/data.csv --database=mysql

gcloud sql import sql mysqldb gs://mybucket/data.sql --database=mysql
```