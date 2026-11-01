<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/596/11/using-dynamic-dns-client-version-001/ | fetched: 2026-11-01T03:37:15Z -->

# Using Dynamic DNS Client – Version 0.01

**System requirements:**
Windows 2000/XP/Vista/7, Internet Explorer, Visual Basic Runtime, .NET Framwork2.0/3.0/4.0 **Download File:**
Available under the Attachments section (see below).
Dynamic DNS client version 0.01 can be used to dynamically update the IP address of *one domain* and *one hostname*. As an example, let assume that you wish to dynamically update the IP address for *www.exampledns.com*.

The first thing you need to do is to enable Dynamic DNS for this domain.  The next step is to create an A record for the host **www**.

You then need to launch the downloaded Dynamic DNS client version 0.01 on your computer and enter the host as "www", domain name as "
exampledns.com", Dynamic DNS password, select how often you wish to update the client, enter any IP address and click on the **Start** button:

 To dynamically update the IP address for *http://exampledns.com,*  you need to create an A record for the host **@**.

To update the IP address for *subdomain.exampledns.com*, you need to create an A record for the host **subdomain**.

**NOTE:** Please make sure you're using the Dynamic DNS password in the client and not your Namecheap's account one.

That's it!

If you have any questions, feel free to contact our [Support Team](https://www.namecheap.com//support/live-chat/domains.aspx).
