# How The Web Works

## Overview

In this lesson we will learn the fundamentals of of the web. Covering web terminology, request and response cycle, DNS, Hosts, Domains, IP Addresses, and the role HTML, CSS, and JavaScript will play in the pages you build.

## Objectives

1. How our browsers connect to a server to retrieve web pages.
2. The role domains, IPs, DNS, and host servers play.
3. The headers and body of the request and response cycle.
4. Understand the relationship of front-end to back-end.

## Understanding The World Wide Web

<iframe width="640" height="480" src="//www.youtube.com/embed/ao532DhZWiY?rel=0" frameborder="0" allowfullscreen></iframe>

*Note: Slides for this lecture video are provided in the resources at the bottom of this lesson.*

### Domains, IPs, and DNS

Let's discuss the process of viewing a webpage in your browser. Imagine you're sitting in your favorite cafe, library, or at home. You eagerly type in your favorite site. Seemlingly, magically text and graphics zip across the world to your screen. Whats really happening under the hood? When you type in the domain name `www.facebook.com` your browser connects to a DNS (Domain Name Server). These servers are like the operators of the internet. They do not contain webpages per se, but instead they contain a list of IP addresses associated with domain names. IP addresses identify the unique location of a server anywhere on the internet. Each server has a unique static IP. Much in the same way the post office knows to deliver your mail based on your home address, IPs work simmiliarly in that they allow us to send communication across the web from one computer to another. The DNS server we first talk to looks up the domain we typed in "www.facebook.com" and associates it with the IP address "31.13.73.36" now that our computer knows the correct ip (thanks DNS), it will attempt to connect to that ip directly. One way we can see this process is from the Terminal. If you open the Terminal and type `ping www.facebook.com` it will respond with the following: 

```shell
PING star-mini.c10r.facebook.com (31.13.73.36): 56 data bytes
64 bytes from 31.13.73.36: icmp_seq=0 ttl=247 time=32.776 ms.....
```

You can press Ctrl+c to end this process. The IP address is revealed `(31.13.73.36)` in parenthesis. In fact you can even copy and paste this IP into your browser instead of the domain name and it will display Facebook's webpage. So you see, your browser allows you to use the more memorizable human label "facebook" so you do not need to remember a bunch of IP addresses to use the web. The DNS uses our domain name we give it to look up and respond with the appropriate IP. Now our browser starts a conversation directly with the server at that IP.

Just in the same way that Facebook has an IP you have one also so that the server knows where to send information back to. If you want to see your own IP address from terminal you can simply type: `curl ifconfig.me` and press return.

### Request and Response

Our browser connects to the host server 31.13.73.36 and asks for permission to access content. This is called a Request. The way our browser asks for content is to provide an HTTP header in the request. This header is text content that contains information about our browser among other things.

Let's look at a real request header. Open Chrome browser and bring up the developer tools by pressing **command+option+i** on mac or **ctrl+shift+i** on a pc. Then click the Network tab in the developer tools. In the url bar type in `www.facebook.com` and press return. Here you will see all the resources being loaded for the webpage you requested. Scroll to the top of the list and click the link at top left of the resource list labeled ***facebook.com***. This is the initial request to the server. This will reveal some tabs to the right. Under the Headers tab we can see under general the request url was http://facebook.com, the request method was GET, and a status code, in my case was 307 Internal Redirect. The HTTP protocol supports different request methods such as GET, PUT, PATCH, POST, and DELETE. In our case our browser made a GET request meaning we simply want to get back some content and we are not posting or providing any content ourselves. Servers use status codes defined as a three digit number. This number determines the state of the request and gives insight into the success or failure of your request. The most common code you see when browsing the web is 200 meaning your request was successful. For a list of the many other status codes you can refer to the link in the resources section at the bottom of the lesson. A bit further down from the General header information you will see Request Headers which includes our User-Agent details. This gives the server information about our operating system and our browser.

If the server accepts your request it will send back a response. The reponse comes in the form of another header and a body. The response header can be seen under the Network headers tab under the section labeled **Response headers**. The most interesting part of the response however is the response body. This can be seen under the tab labeled **Response**. This shows the HTML content that was sent back to our browser. The respose body comes in form of HTML, CSS, or JavaScript code. This content means nothing to the server and is merely seen as a string of text, however when this content is received by our browser, it begins to render the webpage content from this code.

### Local vs Remote

Local or client-side refers to your computer that is right in front of you and remote or server-side refers to a computer that is somewhere else in the world in the case of the web this is typically a web server.

### Front-End vs Back-End

Front-end development refers to writing the code that is interpreted by the browser locally (client-side). Examples of front-end languages are HTML, CSS, and JavaScript. Back-end development refers to any programing language running on the remote server. A few common programming languages that run server-side are: Ruby, PHP, Node, Python, Java, ASP.NET, as well as database query languages like SQL.

## Summary

- DNS servers associate a domain name with a particular IP address.
- IP addresses define the unique location of a computer on the internet.
- The communication between your browser and servers is done through the request and response cycle, which is made up of headers and a response body made up of HTML, CSS, or JavaScript.
- Local refers to your location, where as remote refers to location elsewhere.
- Front-end emcompases all HTML, CSS, JavaScript that is interpreted in your browser
- Back-end refers to languages running on a remote server.

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1eU-4wD5dsxV1t-3CA3T82gbv2K3pAs92pq30HlmXM_U/edit?usp=sharing)
- [How Stuff Works - The Internet](http://computer.howstuffworks.com/internet/basics/internet.htm)
- [Wikipedia - Status Codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-how-the-web-works' title='How The Web Works ~ 9min'>How The Web Works ~ 9min</a> on Learn.co and start learning to code for free.</p>
