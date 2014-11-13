# Making a clone of Azure SQL DB  
Clone is created on the same or another (specified as [source_server_name]) Azure server, not downloaded to local PC.

#### Copy Azure DB to another server:
    CREATE DATABASE destination_database_name AS COPY OF [source_server_name].source_database_name

#### To view progress use this (operation can be considered done if this returns no results):
    SELECT * FROM sys.dm_database_copies
