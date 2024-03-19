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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![image](https://github.com/Revanth-2717/simplewebserver/assets/152462274/b2d2f836-762b-47ec-a889-a5940511ef20)

![image](https://github.com/Revanth-2717/simplewebserver/assets/152462274/1459c13e-5087-41e0-8070-bd394a183a53)


## RESULT:
The program for implementing simple webserver is executed successfully.
