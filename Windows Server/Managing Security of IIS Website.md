# Managing Security of IIS Website

In practice the preferred approach to securing a website (if the site gets its own application pool - which is the default for a new site in IIS7's MMC) is to run under Application Pool Identity. This means setting the site's Identity in its Application Pool's Advanced Settings to Application Pool Identity

![Alt text](https://raw.githubusercontent.com/SoftwareFactor/tips/master/img/6A759626-E7B9-4490-829F-95654330DCD9.png)

In the website you should then configure the Authentication feature

![Alt text](https://raw.githubusercontent.com/SoftwareFactor/tips/master/img/D5469C4B-B4A2-4B02-874B-A07C059B4830.png)

Right click and edit the Anonymous Authentication entry

![Alt text](https://raw.githubusercontent.com/SoftwareFactor/tips/master/img/73F9FF42-BE20-437E-A689-46EEB0580215.png)

Ensure that Application pool identity is selected

![Alt text](https://raw.githubusercontent.com/SoftwareFactor/tips/master/img/5F9F7B97-BA84-4BBF-903E-9799183E8825.png)

When you come to apply file and folder permissions you grant the Application Pool identity whatever rights are required. For example if you are granting the application pool identity for the ASP.NET v4.0 pool permissions, then you can either do this via Explorer
If pool is named RipplePool then user will be IIS AppPoolRipplePool

![Alt text](https://raw.githubusercontent.com/SoftwareFactor/tips/master/img/68813092-4452-407E-A302-0623F3DDFE7B.png)

Click the Check Names button

![Alt text](https://raw.githubusercontent.com/SoftwareFactor/tips/master/img/D9E00A29-91D7-48B4-8BA8-32152A597D26.png)