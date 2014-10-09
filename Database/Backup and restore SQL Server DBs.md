# Backup and restore SQL Server databases

	BACKUP DATABASE AdventureWorks2012 TO DISK='d:\adw.bak'

	RESTORE DATABASE AdventureWorks2012 FROM DISK='d:\adw.bak'

Note: database restore will only be successful on PC with the same version of SQL server. If version differs, free One-Click SQL Restore application can be used:
http://sqlbackupandftp.com/restore/