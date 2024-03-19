# EX01 Developing a Simple Webserver
## Date:19/02/2024

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
<html>
      <head> 
            <title>Top Software Companies Revenue</title>
      </head>
      <body>
      <table border="4" cellspacing="5" width="40" heigth="50"
        <caption>REVENUE</caption>
        <tr>
             <th>S.NO</th>
             <th> Name of the company </th>
             <th>Period</th>
             <th>avg.sales</th>
        </tr>
        <tr>
             <td>1</td>
             <td>cognizant Tech</td>
             <td>2004-10</td>
             <td>50%</td>
        </tr>
        <tr>
             <td>2</td>
             <td>infosys</td>
             <td>2001-06</td>
             <td>50%</td>
        </tr>
        <tr>
             <td>3</td>
             <td>L&T Infotech</td>
             <td>2004-08</td>
             <td>46%</td>
        </tr>
        <tr>
             <td>4</td>
             <td>Mindtree</td>
             <td>2004-09</td>
             <td>54%</td>
        </tr>
        <tr>
             <td>5</td>
             <td>Oracle india</td>
             <td>2007-12</td>
             <td>25%</td>  
        </tr>
        </table>
        </body>
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
![alt text](<Screenshot 2024-03-19 105437.png>)


![alt text](<Screenshot 2024-03-19 105544.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
