# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```html
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. MERN Stack </h2>
<h2>4. ASP.NET core </h2>
<h2>5. Spring </h2>
</body>
</html>
'''
```

```py
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8079)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
### server output
![image](https://github.com/Mkumar262006/webserver/assets/147139472/96c59732-3c1a-4545-8788-51e5f76ba931)
### client output
![Screenshot from 2023-10-16 14-52-32](https://github.com/Mkumar262006/webserver/assets/147139472/a88fe21b-98db-4a8e-bf86-2af082ebf7f9)


## RESULT:
The program is executed succesfully
