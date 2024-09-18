Postgtres - Bluepay Gateway 

##  Postgres High Availability 
- [pgBouncer](https://www.pgbouncer.org/)
- [Patroni](https://patroni.readthedocs.io/en/latest/)
- [HA Proxy](https://severalnines.com/resources/whitepapers/postgresql-load-balancing-haproxy/)
- Automatic Failover between DCs using - Cname automatic failover 
- We routinely fail over between DCs
##  DB & Performance 
- Transaction ID (XID)
- Vaccum maintenance 
- [pg_repack](https://www.tomica.net/blog/2019/06/postgresql-online-vacuum-with-pg_repack/)
- Performance metrics not enabled 
- Delete unused indexes / Table Bloat to prevent fragmentation (faster backups and recovery)
- Auto Vaccum is disabled 
## Backups 
- [pgBackRest](https://pgbackrest.org/) supports Parallel execution 
	- Faster compared to **pg_basebackup**
	-  *pg_basebackup* latest version supports incremental Backup
- process max - Parameter 
- Archive and Sync - *Default is no, we have to configure to Yes*
- Restore testing needs to be done
	>  Needs to test this for all DB types including mysql 
- Encryption of the backups 
## Access & Security
- Trust is not recommended (*solarwinds/telegraph*)
- Cluster DB Auditing - Downside of performance ? 
## Postgres Software 
- Version upgrade from 13 
- Postgres version 13 - EOL *13.7*
## Configuration 
- OS Huge pages
- Cluster Parameters 
- Public Schema uses (Default Schema and other users can modify. Latest version has added functionality to limit the public schema objects )
- Best Practice extensions to check Execution plans - Pg_profile (server statistics for performance ), pgBadger, Security 
- Logging and Parameter Optimization 
	- Log minimum duration - similar to Slow SQL log in mysql 
	- Replication monitoring using Nagios
	- Look into Percona PMM 
## DDL Changes and Optimization
- Standard Operating Procedure for applying DDL Changes 
- Document the processes 
- Patching / upgrade / DDL changes procedures - Documentation 



