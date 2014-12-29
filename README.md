GoDaddy SSL on Nexcess Hosting
==========================================

Instructions for updating or adding a GoDaddy SSL certificate on Nexcess hosting. Originally written July 27, 2011. If there's been changes and you know about them, please file an issue or leave a pull request.

## Steps

1. Renew or set up the SSL on GoDaddy.
2. Once it is set up, log into the InterWorx Control Panel, and select the domain.
3. Go to Hosting Features > SSL Certificates.
4. Go into _Private Key_, _Certificate Signing Request (CSR)_, _SSL Certificate_, and _SSL Chain Certificate_ and click the Delete button.
5. Once you have deleted the Key, CSR, and both Certificates, go into _Private Key_ and click the Generate button.
6. Go back and to SSL Certificates and go into _Certificate Signing Request (CSR)_ and fill out the information needed, and click Generate.
7. Once the CSR is generated, you need to copy all of the text in the box, from `-----BEGIN CERTIFICATE-----` to `-----END CERTIFICATE-----` (including that text).
8. Go back to the GoDaddy account control panel and go to SSL Certificates. Click the _Manage Certificate_ button.
9. This will take you to the SSL Certificates Control Panel. Check the box next to the proper domain and click the Re-Key button above.
10. Paste the CSR data you copied from the dialog box and click the Re-Key button.
11. When finished, download the SSL as "Apache". Unzip the file and it will have two files in it:
  12. gd_bundle.crt
  13. domain-name.com.crt (Or whatever other domain it could be)
14. Open these files in a plain text editor.
15. Go back to the InterWorx Control Panel and go into _SSL Certificate_. Copy and paste the domain-name.com.crt text into the box and click Install.
16. Once successful, go back, and go into _SSL Chain Certificate_. Copy and paste the gd_bundle.crt text into the box and click Install.
17. You're done.

There is additional info on this page that helps somewhat, but not as much as the stuff I figured out above: http://docs.nexcess.net/ssl-tutorial
