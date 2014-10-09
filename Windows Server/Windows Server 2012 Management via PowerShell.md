# Windows Server 2012 Management via PowerShell

#### Server Manager
* Add features:

		Add-WindowsFeature [-Name] string[] [-IncludeAllSubFeature] [-logPath string] [-WhatIf] [-Restart] [-Concurrent] [CommonParameters]
* List features:

		Get-WindowsFeature [[-Name] string[]] [-logPath string] [CommonParameters]
* Remove features:

		Remove-WindowsFeature [-Name] string[] [-logPath string] [-WhatIf] [-Restart] [-Concurrent] [CommonParameters]



#### Server Preparation via PowerShell
1. Install IIS:

		Add-WindowsFeature Web-Server
2. Enable ASP.NET:

		Add-WindowsFeature Web-Asp-Net45
3. Add management service:

		Add-WindowsFeature Web-Mgmt-Service
4. Enable remote management:

		Set-ItemProperty -Path HKLMSOFTWAREMicrosoftWebManagementServer -Name EnableRemoteManagement -Value 1
5. Restart Web-Mgmt-Service for changes to take effect:

		Net Stop WMSVC
		Net Start WMSVC
6. Allow Web Management Service incoming connections in firewall:

		netsh advfirewall firewall add rule name=”Allow Web Management” dir=in action=allow service=”WMSVC”
7. Install IIS Management Console and then IIS Manager for Remote Administration on computer from which the server will be managed
9. Also add firewall exception for SQL server remote management:

		netsh advfirewall firewall add rule name=”Allow SQL Server Expresss” dir=in action=allow service=”MSSQL$SQLEXPRESS”