# EX01 Developing a Simple Webserver
## Date:25/08/2025

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
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''(=)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
            <table align="center" border="5" bgcolor="rgb(0,0,0)"cellpadding="30">
        <caption>list of Protcols in TCP/IP Practical_Suite.</caption>
        <tr><th>S.No.</th><th>Name of the layer</th><th>Name of the Protocol</th></tr>
        <tr><td>1</td><td >Application Layer</td><td>HTTP,FTP,DNS,Telnet& SHH</td></tr>
        <tr><td>2</td><td >Transport Layer</td><td>TCP/UDP</td></tr>
        <tr><td>3</td><td >Network Layer</td><td>IPV4/IPV6</td></tr>
        <tr><td>4</td><td >Link Layer</td><td>Ethernet</td></tr>
    </table>
</body>
</html>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
<img width="1507" height="945" alt="image" src="https://github.com/user-attachments/assets/156ef892-3bd7-4bab-9da8-53f59b962fa1" />


## RESULT:
The program for implementing simple webserver is executed successfully.
