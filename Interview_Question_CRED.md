
# Interview Question: What happens when you hit a URL on the browser?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676721302596/ff4ba263-2083-4dd4-8f1e-f4c7d4f21983.jpeg?auto=compress,format&format=webp)

This was the question asked in a **CRED SDE interview** in the initial rounds.  
Let us deep dive and we are going to frame the answer as it should be told in the interview.

**The question itself covers a lot of topics from DNS, Networks, etc.**

1.  When you hit a URL on the browser, the first step is for the browser to resolve the domain name in the URL to an IP address. This process is called DNS resolution, and it involves the browser sending a DNS query to a DNS server to get the IP address associated with the domain name.
    
    (_I have already written a detailed article about_  [DNS resolution](https://pranavtripathi.hashnode.dev/how-dns-works-everything-you-need-to-know)  👈)
    
2.  If the DNS server has a record of the domain name, it returns the IP address to the browser. If it doesn't, it forwards the query to other DNS servers until one of them can provide the IP address.
    
3.  Once the browser has the  **IP address**, it establishes a TCP (Transmission Control Protocol) connection to the web server located at that IP address. This involves a  **three-way handshake**  between the browser and the server, where they exchange packets to establish the connection.
    
4.  Now that the  **TCP connection**  is established, the browser sends an HTTP request to the web server, specifying the URL and any other parameters needed to retrieve the webpage. The web server receives the request and sends back an HTTP response, containing the HTML code for the webpage along with any other resources needed to display the page.
    
5.  If the website is secured with  **SSL/TLS**  encryption, the browser and server perform a handshake to establish a secure connection using HTTPS instead of HTTP. This involves the exchange of  **digital certificates**  to verify the identity of the server and encrypt the data being transmitted between the browser and server.
    
6.  The browser then interprets the HTML code and displays the webpage on your screen, using the assets provided by the server to render the page correctly. If the webpage contains any additional resources, such as videos or audio files, the browser will send additional requests to the server to retrieve those resources and display them on the page.
    

This was a brief explanation about how we get the information displayed on the browser.

> Note: Now that we have discussed other terms (**marked in bold**) of the computer networks in the answer, the interviewer might ask follow-up questions on that so we need to be well prepared.*

**Thanks for reading!**

### [](https://pranavtripathi.hashnode.dev/interview-question-what-happens-when-you-hit-a-url-on-the-browser#heading-call-for-action "Permalink")Call for action :

-   If the article was helpful star the repo and follow me @[theGrowingKid's Blog](https://hashnode.com/@theGrowingKid)


.