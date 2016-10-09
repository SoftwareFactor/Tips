# Windows Server 2012 Preparation Checklist

This involves quite a few steps, but if you do them in defined order, you should survive :)

### Enable RDP (if not enabled)
1. Go to "Control Panel\System and Security\System"
2. Click "Remote settings"
3. New Windows Opens. Choose "Remote Tab" and click "Allow remote connections to this computer"
4. Make sure this is checked "Allow connections only from computers running Remote Desktop with Network Level Authentication (recommended)" and click OK.

### Install Web Platform Installer
1. Download from https://www.microsoft.com/web/downloads/platform.aspx
2. Install

### Install IIS
1. Open "Server Manager"
2. Click "Add Roles and Features"
3. From "Server Roles" install "Web Server (IIS)"
4. To enable support of .NET applications, also install "Web Server (IIS) > Application Development". Check all there, except CGI, ASP (if no classic is used), and Server Side Includes.

### Install Web Deploy (for remote publishing from Visual Studio)
1. Open "Server Manager"
2. From "Server Roles" install "Web Server (IIS) > Management Tools > Management Service"
3. Close "Server Manager"
4. Install "Web Platform Installer" (if not yet exists)
5. Install "Web Deploy 3.6 without bundled SQL support" via "Web Platform Installer"
6. Open IIS
7. Click on the server (main) node on the left menu
8. Double click on "Management Service" icon
9. Check "Enable remote connections", apply changes and restart "Management Service"

### Install SQL Server Express (if needed)


### Configure and prepare IIS website for one click publishing from Visual Studio
1. Open IIS
2. Add new website
3. To make website load faster after inactivity period, set "Idle time-out (minutes)" to 0 in website's application pool's advanced settings.
4. To configure Publishing from Visual Studio, install Web Deploy (if not exists), then right click on website, choose "Deploy > Configure Web Deploy Publishing..."
5. Create a new user without admin privileges and assign it to web deploy
