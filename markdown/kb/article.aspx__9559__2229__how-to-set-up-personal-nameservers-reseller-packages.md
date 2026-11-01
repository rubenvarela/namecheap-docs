<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9559/2229/how-to-set-up-personal-nameservers-reseller-packages/ | fetched: 2026-11-01T03:36:11Z -->

# How to set up personal nameservers (Reseller packages)

If you have a [Reseller](https://www.namecheap.com/hosting/reseller.aspx) account with us, you can register your own nameservers (ns1.yourdomain.tld and ns2.yourdomain.tld) to provide your clients with.

First of all, you need to obtain IP addresses to point your personal nameservers to. You can check them in an email from our Billing team or contact us via [HelpDesk](https://www.namecheap.com/support/live-chat/general.aspx) in order for our Hosting team to double-check them for you.

Once you have IPs at hand, you can go ahead and register the nameservers on the side of your domain registrar.

If your domain is registered with us, follow the guidelines [here](https://www.namecheap.com/support/knowledgebase/article.aspx/768/10/how-do-i-register-private-nameservers-for-my-domain). If your domain is registered with another company, get in touch with them for the nameservers setup assistance.

Lastly, when the nameservers are registered, you need to set them up on the server:

1. Log into your main cPanel and Navigate to the **Domains** section and click on the **Zone Editor** menu:

 2. Click **+A Record** next to your domain:

3. Create two A records for the two nameservers:

4. Now you need to log into **WHM** (yourdomain.tld/whm) and set the nameservers in the **WebHost Manager Setup** menu in order for them to be automatically applied to all new cPanel accounts you create:

Allow 24-72 hours to pass for the nameservers to propagate worldwide and feel free to use your new personal nameservers.

It is **not possible to use both PremiumDNS and private nameservers simultaneously**:

1. Once you points the domain to the new private nameservers, you will lose all the benefits of PremiumDNS;
2. If you would like to use PremiumDNS with your hosting, you should create corresponding  [Hosting Host records at the side of our PremiumDNS service](https://www.namecheap.com/support/knowledgebase/article.aspx/9764/2231/how-to-use-the-premiumdns-and-hosting-services-simultaneously/).

That's it!

              
                      Need any help? Contact our [HelpDesk](https://www.namecheap.com/help-center/)
