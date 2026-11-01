<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/43/11/how-do-i-set-up-a-host-for-dynamic-dns/ | fetched: 2026-11-01T03:36:53Z -->

# How do I set up a Host for Dynamic DNS?

Before you start using Dynamic DNS on a particular host, you need to set up an A record for it. You can do it in the following way:

1. [Sign in](https://www.namecheap.com/myaccount/login.aspx) to your **Namecheap accoun**t.

2. Select **Domain List** from the left sidebar and click on the **Manage** button next to your [domain name](https://www.namecheap.com/):

3. Click on the **Advanced DNS** tab, then find the **Host records** section and click on the records for **@** and **www** to modify their values ([not able to edit Host Records?](https://www.namecheap.com/support/knowledgebase/article.aspx/323/46/why-can-not-email-domain-redirect-and-host-records-options-be-modified-in-my-namecheap-account)):

4. If you would like to have the IP address for your bare domain (*yourdomain.tld*) updated dynamically, select **A+Dynamic DNS Record** for **Type** and enter **@** symbol as a **Host**:

To have your IP address updated for *www.yourdomain.tld* or *test.yourdomain.tld* for example, enter **www** or **test** for **Host** accordingly:

In order to update your IP address for all non-existent subdomains, you will need to create a wildcard record. For that, enter \* for **Host**:

You may use any dummy IP address, like 127.0.0.1 for **Value**. Once your Dynamic DNS client is configured, this IP address will be updated automatically to your current one.

5. Once all details are inserted, save them using the **Save changes** green icon.

**NOTE**: It is possible to dynamically update IPv4 addresses (A records) at this time. Currently, IPv6 is not supported by our Dynamic DNS.

That's it!

If you have any questions, feel free to contact our [Support Team](https://www.namecheap.com//support/live-chat/domains.aspx).
