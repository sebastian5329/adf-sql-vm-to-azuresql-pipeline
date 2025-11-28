This project contains an Azure Data Factory (ADF) pipeline that performs config-driven data movement from
SQL Server on an Azure Virtual Machine to Azure SQL Database.

The solution uses a configuration table (tblconfig) that stores source tables, sink tables, and an is_active flag.
Only tables marked as active (is_active = 1) are processed.

Pipeline Flow

	1.	Script Activity – Queries tblconfig to fetch only active tables.
	2.	ForEach Activity – Loops through each active table.
	3.	Copy Activity – Copies data from the SQL VM table to the corresponding Azure SQL table.

Key Features

	•	Configuration-driven table selection
	•	Dynamic table extraction and loading
	•	Integration between SQL Server on VM and Azure SQL
	•	Clean, scalable, and automated ETL pattern
