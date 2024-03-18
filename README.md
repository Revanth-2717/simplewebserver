# EX01 Developing a Simple Webserver
## Date: 18-03-24

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
</head>
<body>
<h1>Top Five Revenue Generating websites</h1>

<h1>1. AMAZON</h1>
<h1>2. META</h1>
<h1>3. NETFLIX</h1>
<h1>4. GOOGLE</h1>
<h1>5. X</h1>

</body>
</html>
"""

class HelloHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my web server")
server_address = ('', 80)
httpd = HTTPServer(server_address, HelloHandler)
httpd.serve_forever()

```

## OUTPUT:
![Screenshot 2024-03-18 194718](https://github.com/Revanth-2717/simplewebserver/assets/152462274/98e81ddd-e567-4038-86c0-573b09edaefd)


## RESULT:
The program for implementing simple webserver is executed successfully.
