# EX01 Developing a Simple Webserver
## Date:
15/3/24
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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
    <table>
        <tr>
 /           <th>Rank</th>
            <th>Company</th>
            <th>Revenue</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Microsoft</td>
            <td>$86.8</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Oracle</td>
            <td>$37.1</td>
        </tr>
        <tr>
            <td>3</td>
            <td>SAP</td>
            <td>$20.9</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Symantec</td>
            <td>$6.8</td>
        </tr>
        <tr>
            <td>5</td>
            <td>VMware</td>
            <td>$5.2</td>
        </tr>
    </table>
</html>
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
![image](https://github.com/thamizh610/simplewebserver/assets/150418511/8a1f5cd9-ac8b-48d6-923c-3a404c8417f3)
![image](https://github.com/thamizh610/simplewebserver/assets/150418511/d268c33c-06a2-4060-bba8-13d69d0b05a3)


## RESULT:
The program for implementing simple webserver is executed successfully.
