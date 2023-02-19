
# How DNS works? Everything you need to know.

For every one of us, understanding behind the scenes of DNS has been a tough ride. In this article, we are going to simplify DNS and understand what happens when we type a URL.

![](https://miro.medium.com/max/688/1*_CJrPxWtoAeCSFUfkiCEVA.jpeg)

Computers and other devices communicate using  **IP addresses**  to identify each other on the internet. But humans can’t remember IP addresses, so they use words.  
The domain name system (DNS) brings the two together and gets you to your destination. DNS is a system that translates domain names (e.g.  [www.google.com](http://www.google.com/)) into IP addresses (e.g. 74.125.204.147) that computers can understand and use to access websites and other internet resources.

Wait! What? Just plain text to this complex address located on the web anywhere, How does that happen?

**Here’s how it happens… 🧾**

1.  A user types a URL into their browser.
2.  The browser first checks its cache to see if it has recently looked up the IP address for that domain name.
3.  If it does not have the IP address saved previously, this is the right time to annoy OS. The OS will search in its cache as well and return an IP address if found.
4.  Now sends a request to a local  **DNS resolver**  to translate the domain name into an IP address.

**Who is this resolver guy?**

The resolver server is usually your  **ISP (Internet Service Provider)**. All resolvers must know one thing: where to locate the root server.

**5.**  If the DNS resolver does not have the required IP, It is time to reach out to the  **Root**  nameserver.

**Who is this Root guy? 😯**

The administration of the DNS is structured in a hierarchy using different managed areas or “zones”, with the root zone at the very top of that hierarchy. Root servers are DNS nameservers that operate in the root zone. These servers can directly answer queries for records stored or cached within the root zone, and they can also refer other requests to the appropriate  **Top Level Domain**  (TLD) server.

**Note:** _A common misconception is that there are only 13 root servers in the world. In reality, there are many more, but still, only 13 IP addresses are used to query the different root server networks. In the early days, there was only one server for each of the 13 IP addresses, most of which were located in the USA. The Internet Corporation for Assigned Names and Numbers (_**_ICANN_**_) operates servers  
Today each of the 13 IP addresses has several servers, which use_ **_Anycast routing_** _to distribute requests based on load and proximity. Right now there are over_ **_600_** _different DNS root servers distributed across every populated continent._

**…. a few milliseconds later …. ⏳**

**6.**  The root nameservers respond with the IP addresses of the TLD nameservers.

**Who is this TLD guy?**

A TLD nameserver maintains information for all the domain names that share a common domain extension, such as .com, . net, or whatever comes after the last dot in a URL.

![](https://miro.medium.com/max/700/1*k6uf_GinBdgYhdA1RH4RxA.png)

Parts of URL

**7.** The TLD domain servers return the IP address of the  **Authoritative DNS**  servers to the Resolver.

**Note:** _When a domain is purchased, the_ **_domain registrar_** _reserves the name and communicates to the TLD registry the authoritative name servers._

**Who is this Authoritative server guy?**

The authoritative DNS server is the final holder of the IP of the domain you are looking for. It has been configured from the original source for the specific zones, which makes them very efficient and fast.

-   **_No cached values. Not asking someone else. Only the real deal._** 🎯

**8.**  The resolver finally got the answer he was looking for! Hurray for the Authoritative name server! 🤩

**9.**  Now it will be cached by the resolver and returned to the browser. The browser uses the IP address to connect to the website's server and retrieve the website's content.

**Summary**  —

A summary of the article can be seen in the below image as well as you can refer to this awesome  [comic](https://howdns.works/).