<!-- source: https://www.namecheap.com/support/knowledgebase/article.aspx/583/11/how-do-i-configure-ddclient/ | fetched: 2026-11-01T03:37:25Z -->

# How do I configure DDClient?

 The following is the format of the DDClient configuration:

**use**=web, **web**=dynamicdns.park-your-domain.com/getip
**protocol**=namecheap
**server**=dynamicdns.park-your-domain.com
**login**=yourdomain.tld
**password**=your [dynamic dns password](article.aspx__595__11__how-do-i-enable-dynamic-dns-for-a-domain.md)
**yourhost**

Here is the example of its usage. If you would like to set up Dynamic DNS for *yourdomain.tld* (without www), check its configuration:

If you need to dynamically update a subdomain, substitute the host only:

**use**=web, **web**=dynamicdns.park-your-domain.com/getip
**protocol**=namecheap
**server**=dynamicdns.park-your-domain.com
**login**=yourdomain.tld
**password**=a9438540ba8a449fb0ed09c3737b9e32
**www**

Only **login**, **password** and ****yourhost**** parameters should be changed for a domain.

Should you need to configure the DDClient installed on Fedora OS, feel free to refer to [this guide](https://mgw.dumatics.com/ddclient-on-fedora-2/).
