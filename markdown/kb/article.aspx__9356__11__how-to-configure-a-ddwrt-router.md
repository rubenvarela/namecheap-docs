<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9356/11/how-to-configure-a-ddwrt-router/ | fetched: 2026-11-01T03:36:28Z -->

# How to configure a DD-WRT router

If you are using a router with DD-WRT firmware, you can make use of the built-in DDNS option to have A records for your domain automatically updated. Please follow the steps below:

1. Make sure Dynamic DNS is [enabled](article.aspx__595__11__how-do-i-enable-dynamic-dns-for-a-domain.md) for your domain.

2. Create an [A+Dynamic DNS record](article.aspx__43__11__how-do-i-set-up-a-host-for-dynamic-dns.md) with any IP address for the host name you would like to be updated. Because the IP address will be automatically updated by your router, it does not matter what IP address you specify when creating the record.

3. Set up DDNS on the router.

Log in to your router’s web interface and go to **Setup** > **DDNS**. You will need to fill out the following fields:

* **DDNS Service**: Custom
* **DYNDNS Server**: dynamicdns.park-your-domain.com - the name of the server should not be changed
* **Path**: */update?domain=yourdomain.tld&password=DynamicDNSPassword&host=*

**NOTE**: *"&host=*" parameter at the end of the Path must remain empty; otherwise, DD-WRT would report a successful update while the subdomain IP address in the zone file would remain unchanged.

* **Username**: yourdomain.tld - replace it with your domain name
* **Password**: Dynamic DNS password for your domain (**Domain List** >> click on the **Manage** button next to the domain >> the **Advanced DNS** tab >> **Dynamic DNS**)
* **Hostname**: Your subdomain (**@** for *yourdomain.tld*, **www** for *www.yourdomain.tld*, etc.)

      \*[yourdomain.tld and DynamicDNSPassword should be replaced with the relevant information]\*

Please don't forget that the "**Username**" field should be filled in with your actual domain name, "**Password**" - your Dynamic DNS password; "**Path**" - "*yourdomain.tld*" should be replaced with the domain, "*DynamicDNSPassword*" - with your Dynamic DNS password.

**Note**: If you would like to update **multiple host names**, use an ‘-a’ argument to separate them in the Hostname field. For instance:

**Hostname**: @ -a www -a mail

The configuration should look like this:

To finish the setup, please click "**Save**" and then "**Apply Settings**".

4. Set up the port forwarding (optional)

You will need to set up this feature if you are running a service (e.g., a web server) on an internal machine to make it accessible outside your local network. The feature is available in NAT / QoS > Port Forwarding in your router’s web interface:

It is required to fill out the the following fields to create a port forwarding rule:

* **Application**: descriptive name of the rule
* **Protocol**: protocol used by the service (TCP, UDP or both)
* **Source Net**: IP address allowed to access the service (you can leave it blank if you do not wish to restrict the access)
* **Port from**: port on your external IP address
* **IP Address**: IP address of the destination machine on your local network (you can check it in Status > LAN)
* **Port to**: port on your internal IP address (the same as Port from in most cases)

*Note*: Firmware version used in this article is DD-WRT v24-sp2 (03/29/14) std - build 23838

That's it!

If you have any questions, feel free to contact our [Support Team](https://www.namecheap.com//support/live-chat/domains.aspx).
