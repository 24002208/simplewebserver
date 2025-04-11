# EX01 Developing a Simple Webserver
## Date:09.04.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler 
content="""
<html>
<title>TCP/IP PROTOCOL</title>
<body>
<table border="2" cellspacing="15" cellpadding="6" bgcolor="pink">
<tr bgcolor="lightblue">
<th>S.No</th><th>LAYER</th><th>PROTOCOLS</th>
</tr> 
<tr>
<td>1</td><td>Application Layer</td><td>HTTP,FTP,DNS,Telnet,SSH</td>
</tr>
<tr>
<td>2</td><td>Transport Layer</td><td>TCP,UDP</td>
</tr>
<tr>
<td>3</td><td>Internet Layer</td><td>IPv4/IPv6</td>
</tr>
<tr>
<td>4</td><td>Network Access Layer</td><td>MAC/Ethernet</td>
</tr>
</table>
</body>
</html>
"""
class myhandler (BaseHTTPRequestHandler):
     def do_GET(self):
        print("request received") 
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![alt text](<web exp1 (2).png>)

![alt text](web.png)

## RESULT:
The program for implementing simple webserver is executed successfully.
