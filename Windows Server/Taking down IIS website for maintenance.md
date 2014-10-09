# Taking down IIS website for maintenance
Our goal is to prevent any errors that might arise due to visitors browsing our web applications during the deployment process. This can be solved by putting a file named **App_offline.htm** in the root of your website. While this file exists in the directory, website will not work.

Hint: you should put some takedown notice in **App_offline.htm** as it will be served to all visitors during downtime.