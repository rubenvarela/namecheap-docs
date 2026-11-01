<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/29/11/how-to-dynamically-update-the-hosts-ip-with-an-https-request/ | fetched: 2026-11-01T03:36:43Z -->

# How to dynamically update the host's IP with an HTTPS request?

The **Dynamic DNS** feature is available only for the domains pointed to our [BasicDNS](https://www.namecheap.com/support/knowledgebase/article.aspx/782/10/how-do-i-set-my-domain-to-use-namecheaps-default-dns-servers), [PremiumDNS](https://www.namecheap.com/security/premiumdns/) or [FreeDNS](https://www.namecheap.com/support/knowledgebase/article.aspx/531/51/what-is-freedns).

Please substitute these with appropriate values for host, domain,
password and IP:

https://dynamicdns.park-your-domain.com/update?host=**[host]**&domain=**[domain\_name]**&password=**[ddns\_password]**&ip=**[your\_ip]**
Fields that **are to be changed** in the URL are: [host], [domain\_name], [ddns\_password] and [your\_ip].Here is an example for IP address update for a bare domain (e.g., *yourdomain.tld*):

**Host** = @ **Domain Name** = yourdomain.tld **Dynamic DNS Password** = Domain List >> click **Manage** next to the domain >>**Advanced DNS** tab >> **Dynamic DNS**. If it is not enabled, enable it to check the password. **IP Address** = optional value. If you don't specify any IP, the IP from which you are accessing this URL will be set for the domain.

**NOTE:** The values for the host name and domain in the URL must be of the same case (lowercase/uppercase) as in your account.

If the domain is shown as *YourDomain.tld* in your Dashboard, enter it in the same way: https://dynamicdns.park-your-domain.com/update?host=**@**&domain=**YourDomain.tld**&password=**e747d77054a844409c486973cb**&ip=**127.0.0.1**

If it shown in lowercase, like *yourdomain.tld*, add just *yourdomain.tld*. The URL will have the following format in this case: https://dynamicdns.park-your-domain.com/update?host=**@**&domain=**yourdomain.tld**&password=**e747d77054a844409c486973cb**&ip=**127.0.0.1**

Please make sure you are using your **Dynamic DNS password** and not the
Namecheap account's one.

To dynamically update the IP address for a **subdomain** (*test.yourdomain.tld*), use **test** for **Host** (host=**test**). To dynamically update it for *www.**yourdomain.tld*, use **www** for **Host**: host=www.

To have the **wildcard** subdomain updated dynamically, just make sure that you insert an asterisk (\*) as **Host** in the URL.

Please take into account that if you process such updates not through
the browser, but through the terminal, for example, then only the GET
method for such requests should be used, the POST method does not work.

**TIP:** If you don't want to use any DNS client, you can just bookmark the URL (after inputting proper values there) and access it whenever you need to update your IP.

**NOTE**: It is only possible to dynamically update IPv4 addresses (A records) at this time. Currently, IPv6 is not supported by our Dynamic DNS.

That's it!

If you have any questions, feel free to contact our [Support Team](https://www.namecheap.com//support/live-chat/domains.aspx).
