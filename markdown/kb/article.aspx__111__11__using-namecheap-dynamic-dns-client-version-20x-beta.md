<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/111/11/using-namecheap-dynamic-dns-client-version-20x-beta/ | fetched: 2026-11-01T03:37:20Z -->

# Using Namecheap Dynamic DNS Client Version 2.0x (beta)

**The current version:**

Dynamic DNS Client V2.0 (2.0.0.8)

**System requirements:**

Windows 2000/XP/Vista/7/8/10, Internet Explorer, Microsoft .NET 2.0 Runtime

**Download File:**
Available under the Attachments section (see below).

Dynamic DNS client version 2.0x allows you to easily create and manage profiles for different hosts and domains that you wish to dynamically update. As an example, let assume that you wish to dynamically update the IP address of *http://www.exampledns.com* and *http://exampledns.com* .

The first thing we need to do is to enable Dynamic DNS for the domain *exampledns.com*.  The next step is to create an A record for the host *www* and *@*. Then, you need to launch the downloaded Dynamic DNS client version 2.0x on your computer and create a profile for each host.
 
To create a new profile for *exampledns.com*, click on the Manage Profiles tab in the Dynamic DNS client and "New". Enter the host as *@*, domain as *exampledns.com*, enter the Dynamic DNS password, select  the "Auto detect my IP address" option and choose how often to update the client. Click Save. To see the current status of this profile, select  the "Welcome!" tab.

 

In order to use Dynamic DNS for *www.exampledns.com*, you will need to create another profile by clicking on the "New" button one more time. Enter the host as *www*, domain as *exampledns.com*, enter the Dynamic DNS password, select the "Auto detect my IP address" option and choose how often to update the client and then click on Save.

**NOTE:** The values for the host name and domain in the URL must be of the same case (lowercase/uppercase) as in your account.

If the domain is shown as *E**xampleDns.com* in your Dashboard, enter it in the same way: *E**xampleDns.com*. If it shown in lowercase, like *exampledns.com*, add just *exampledns.com.*

 

If you wish to use Namecheap Dynamic DNS Client with any other subdomain, a new profile should be created for it same way as described above (the host field should be filled in with your subdomain only).

 

**NOTEs:**

1) Namecheap Dynamic DNS Client V2.0 (2.0.0.6) NEW Beta: Time interval problem fixed

2) Please ENSURE that you use the Dynamic DNS password in the client. Do not use your Namecheap user account’s password.

**Troubleshooting**

       

This application stores profiles in

C:\Users\<username>\AppData\Roaming\Dynamic DNS Client\Profiles.xml file. The profiles are automatically carried over when you download a new version.

Ensure that this file is not tampered or corrupted. In the event of this happening, kindly delete the whole file, the application will then create a fresh file to start with.

*MD5 (for ver. 2.0.0.8): B1C903D1AF35616709D20ED3314126A1*
