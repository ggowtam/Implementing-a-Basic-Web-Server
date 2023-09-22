# Implementing-a-Basic-Web-Server!
] Identify where in RFC 2616 you found the rules for correctly responding to a correctly formatted GET request for the root directory

[image](https://github.com/ggowtam/Implementing-a-Basic-Web-Server/assets/108767096/459a2a3b-9c03-4953-8406-674b53872850)
Wireshark capture of the GET request packet sent to your server and the server response
![image](https://github.com/ggowtam/Implementing-a-Basic-Web-Server/assets/108767096/d11961bb-1ed3-43ef-a10b-9961ce77fec7)
RFC 2616 you found the rules for correctly responding to a correctly formatted GET request for a nonexistent file
![image](https://github.com/ggowtam/Implementing-a-Basic-Web-Server/assets/108767096/00c425a3-108e-464f-acb2-2a032edb4167)
Wireshark capture of the GET request for nonexistent file packet sent to your server and the server response
![image](https://github.com/ggowtam/Implementing-a-Basic-Web-Server/assets/108767096/cca6bf31-c277-4cbd-be3d-4ce62ca10999)
HTTP/1.1 200 OK
Date: Tue, 16 Feb 2010 19:21:24 GMT
(More HTTP headers...)
Content-Type: text/html; charset=utf-8

<html><head>
<title>Yahoo!</title>
(More HTML follows)
As a basic test of functionality, try requesting a page using telnet:
telnet localhost <port>
Trying 127.0.0.1...
Connected to localhost.localdomain (127.0.0.1).
Escape character is '^]'.
GET http://127.0.0.1/path_to_html_file HTTP/1.1
When your proxy starts, the first thing that it will need to do is establish a socket connection that it can use to listen for incoming connections. Your proxy should listen on the port specified from the command line and wait for incoming client connections. 
Once a client has connected, the proxy should read data from the client and then check for a properly-formatted HTTP request -- but don't worry, we have provided you with libraries that parse the HTTP request lines and headers. Specifically, you will need to ensure that the server receives a request that contains a valid request line:
<METHOD> <URL> <HTTP VERSION>
All other headers just need to be properly formatted:
<HEADER NAME>: <HEADER VALUE>
In this assignment, client requests to the proxy must be in their absolute URI form.
GET http://www.cs.princeton.edu/index.html HTTP/1.1
Your browser will send absolute URI if properly configured to explicitly use a proxy (as opposed to a transparent on-path proxies that some ISPs deploy, unbeknownst to their users). On the other form, your proxy should issue requests to the webserver properly specifying relative URLs, e.g.,
GET /index.html HTTP/1.1
Testing Proxy Correctness
To test the correctness of your program, start by running your Web server with the following command (assuming a Pythonic implementation):

python [YOUR_NAU_ID]_web_server_ec3.py port

As a basic test of functionality, try requesting a page using telnet:

telnet localhost <port>
Trying 127.0.0.1...
Connected to localhost.localdomain (127.0.0.1).
Escape character is '^]'.
GET http://www.google.com/ HTTP/1.1


