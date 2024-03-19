-# EX01 Developing a Simple Webserver
## Date: 27-02-24

## AIM:
To develop a simple webserver to serve html pages.

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
```python
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
         <title>simplewebserver</title>
    </head>
    <body>
        <table align="center" border="2" cellspacing="12" cellpadding="12" height="25" width="50">
        <h1 align="center" >top 5 software companies with revenue</h1>
            <tr>
            
                <th>RANK</th>
                <th>COMPANY</th>
                <th>REVENUE</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Microsoft</td>
                <td>$86.8</td>
            </tr>
            <tr>
                <td>2</td>
                <td>oracle</td>
                <td>$37.1</td>
            </tr>
            <tr>
                <td>3</td>
                <td>SAP</td>
                <td>$20.9</td>
            </tr>
             <tr>
                <td>4</td>
                <td>symantec</td>
                <td>$6.8</td>
            </tr>
             <tr>
                <td>5</td>
                <td>VMware</td>
                <td>$5.2</td>
            </tr>
        </table>
    </body>
<html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```

## OUTPUT:
![Screenshot 2024-03-19 205430](https://github.com/Revanth-2717/simplewebserver/assets/152462274/eb3b708d-f841-4f51-923b-e3592f228bd3)
<br>
<br>
![Screenshot 2024-03-19 205046](https://github.com/Revanth-2717/simplewebserver/assets/152462274/87a79a9a-a88c-4527-89fa-71e9bb55dda4)



## RESULT:
The program for implementing simple webserver is executed successfully.
