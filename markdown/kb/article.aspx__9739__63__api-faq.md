<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/9739/63/api-faq/ | fetched: 2026-11-01T03:34:55Z -->

# API

* [Do you charge any additional fee for using your API?](#a)
* [Can I use your API for drop catching?](#b)
* [I want to enable API for my account. Are there any specific requirements?](#c)
* [How can I start testing in Sandbox?](#t)
* [How accurate is the Sandbox?](#d)
* [Are all TLDs supported for the registration via API?](#e)
* [Where can I find documentation on API?](#f)
* [Is it possible to use port 80?](#g)
* [What are you API limits?](#z)
* [Can I use Namecheap coupon codes in Sandbox?](#h)
* [What prices should I set for my customers?](#i)
* [I have enabled API for my account and want to resell domains with you. Will I get a special reseller pricing?](#j)
* [Can Namecheap coupons be used with API?](#k)
* [How fast is Namecheap API?](#l)
* [Do you offer language platforms?](#m)
* [Can I add a free Whois Privacy Protection or promotional SSL to my order via API?](#n)
* [I’m using PremiumDNS/FreeDNS. How can I manage it via API?](#o)
* [How can I import a bind zone for my domains using API?](#p)
* [I want to register IDN domains. Shall I use native symbols or Punycode?](#q)
* [I want to delete domains registered in my Sandbox account](#r)
* [I want to sort my domains by categories using API](#s)
* [What are the payment methods accepted for API?](#u)

**Do you charge any additional fee for using your API?**
No, there is no additional fee for resellers using our API.

**Can I use your API for drop catching?**
Unfortunately, we do not allow drop catching using our API.

**I want to enable API for my account. Are there any specific requirements?**

We have certain requirements for activation to prevent system abuse. In order to have API enabled, your account should meet one of the following requirements:

- have at least 20 domains under your account;
- have at least $50 on your account balance;
- have at least $50 spent within the last 2 years.

Still, you are free to test our API through the Sandbox environment at <http://www.sandbox.namecheap.com>

**How can I start testing in Sandbox?**

To use the Sandbox environment, you should visit *http://www.sandbox.namecheap.com* and sign up for a Namecheap account (Sandbox and Namecheap accounts are not connected, thus the login details for Sandbox could be completely different from the ones you have in your Namecheap account.).

To enable access to Sandbox API, go to the **Profile** section, select **Tools** and choose the **Namecheap API Access** option for **Business & Dev Tools**.

You will get the **API key** almost immediately. Your **API username** is the same as your Sandbox account username.

Once API access is enabled, you should **whitelist at least one IP** before your API access begin to work. Please keep in mind that only IPv4 addresses can be used.

Whitelisted IPs are considered spam-free and safe for use.

The very same steps should be performed to enable API for actual Namecheap account. Your Namecheap account username will act as API username.

**How accurate is the Sandbox?**

The sandbox environment is separate and independent from the production one, thus, domain names registered in real will be shown as available in the Sandbox, unless you register them in the sandbox environment.

The same goes for nameservers. When nameservers are assigned to a domain, they need to be registered in the environment this is done in.

For example, if you would like to use ns1.nameserver.com on example.com, you'll need to register nameserver.com domain in the sandbox first, then register ns1.nameserver.com and only then you can change the DNS for example.com to ns1.nameserver.com.

**Are all TLDs supported for the registration via API?**

Yes, you can register all the TLDs listed on our [pricing page](https://www.namecheap.com/domains/). However, make sure you add the required extended attributes parameters for the API call. You can find the details [here](https://www.namecheap.com/support/api/extended-attributes/).

**Where can I find documentation on API?**

Our API documentation can be found [here](https://www.namecheap.com/support/api/intro/).

**Is it possible to use port 80?**

You can send API calls with http, however we recommend using https, since the calls contain sensitive details.

****What are your API limits?****

Our general API calls restriction is 50/min, 700/hour, and 8000/day across the whole key.

**Can I use Namecheap coupon codes in Sandbox?**

Unfortunately, no. Currently, we do not provide any coupon codes for testing in the sandbox environment.

**What prices should I set for my customers?**

You can resell the domains at your own prices. Your profit is the difference between your buying and selling prices.

**I have enabled API for my account and want to resell domains with you. Will I get a special reseller pricing?**
The prices are the same using API, however, you can use our monthly coupons for domain registrations. Alternatively, once you get 50+ domains in your account, we can set a special pricing for your account which will be working for renewals as well as new registrations.

**Can Namecheap coupons be used with API?**

Yes, you can use our coupons for purchases through API as well. [Click here](https://www.namecheap.com/support/api/methods/domains/create/) for the required parameters.

**How fast is Namecheap API?**

Domain registrations are real time through the API.

**Do you offer language platforms?**

Our API works in the background to perform all the operations (i.e., it’s a backend process). You can use any language on your website to sell domains. There is no need for us to offer a language platform as the backend process has got nothing to do with the language used on your website.

**Can I add a free Whois Privacy Protection or promotional SSL to my order via API?**

Yes, you can add a free Privacy Protection subscription to your domain name registration through API. Necessary parameters can be found [here](https://www.namecheap.com/support/api/methods/domains/create.aspx).

The promotional SSL from the Exclusive SSL Offer cannot be added when registering a domain via API.

**I’m using PremiumDNS/FreeDNS. How can I manage it via API?**

API can be used for the domains that are registered with us only. If the domain is using our PremiumDNS/FreeDNS, you will not be able to manage it via API.

**How can I import a bind zone for my domains using API?**

Unfortunately, this option is not supported. However, you can use [setHosts](https://www.namecheap.com/support/api/methods/domains-dns/set-hosts.aspx) command for creating records. Alternatively, if you have a bind zone, please contact our support team. We will be able to import it manually for your domains that are using our BasicDNS.

**I want to register IDN domains. Shall I use native symbols or Punycode?**

For now, API allows searching and registering IDN domains in Punycode only (ex.: xn--sdkhjsdhfkdh.com as mentioned [here](https://www.namecheap.com/support/api/methods/domains/create.aspx), as we do not support the native code).

**I want to delete domains registered in my Sandbox account**

Unfortunately, it is not possible to do that since the sandbox environment works just like the production one: it is linked to the registry testing environment.

In other words, the test domains actually exist in the testing environment on the registry side, too. So, it is not possible to register domain names that are already registered by another user or set nameservers that are not registered in a test environment.

Due to this, we cannot reset or cancel all test domain registrations for a specific user.

**I want to sort my domains by categories using API**

Unfortunately, at this time, our API does not allow categorizing domain names by client reference or any other parameter.

**What are the payment methods accepted for API?**

All billing operations through API can be performed using your Namecheap account balance only. You can [add funds](https://www.namecheap.com/support/knowledgebase/article.aspx/232/7/how-can-i-add-funds-to-my-namecheap-account) to it using your credit card (Visa, MasterCard, Discover or AmEx), PayPal, Bitcoin and Bitcoin Cash.

If you have any questions, feel free to contact our [Support Team](https://www.namecheap.com//support/live-chat/domains.aspx).
