# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
## mywebserver.py
```
from http.server import HTTPServer,BaseHTTPRequestHandler

Content="""
<!doctype html>
<html lang="en">
<head>
<title>my webserver</title>
</head>
<body>
<h1>MULTIPLICATION TABLES OF 8</h1>
8×0=0<br>
8×1=8<br>
8×2=16<br>
8×3=24<br>
8×4=32<br>
8×5=40<br>
8×6=48<br>
8×7=56<br>
8×8=64<br>
8×9=72<br>
8x10=80<br>
<br>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recived")

        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')             
        self.end_headers()

     #to send the responce
        self.wfile.write(Content.encode())

 #to create server address     
server_address=('',80)

#to listen at the specified port
httpd = HTTPServer(server_address,myhandler)
print("MY WEBSERVER IS RUNNING...")
httpd.serve_forever()
```

## OUTPUT:

![output](./static/img/o.png)

![output](./static/img/r.png)

## RESULT:
Thus, a webserver is designed to display multiplication table and is hosted in the URL
http://prasanna.student.saveetha.in/