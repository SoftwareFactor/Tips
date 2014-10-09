# Installing SSL certificate to IIS

Easiest to use tool that I have found is DigiCert Certificate Utility for Windows. It's free.

1. In DigiCert utility click Create CSR
2. Upload CSR to SSL provider's system
3. Download certificate from SSL provider's system
4. Import it to DigiCert Certificate Utility via Import function
5. a) If you will be using it in IIS: go to IIS to configure the certificate  
b) If you will be using it in Azure: export it to *.pfx and upload to Azure