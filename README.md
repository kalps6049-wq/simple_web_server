# EX01 Developing a Simple Webserver

# Date: 18.09.2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
'''
from http.server import HTTPServer,BaseHTTPRequestHandler

content= '''< !DOCTYPE html>
<html lang="en">

   <head>
        <title>
            LAPTOP SPECIFICATION
        </title>
        <h1 align="center">LAPTOP SPECIFICATION</h1>
        <h3> REGISTER NUMBER = 25014380</h3>
        <h3> NAME            = KALPANA M </h3>
        <br>
        <br>
    </head>
    
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f7fb;
      padding: 20px;
    }
    table {
      border-collapse: collapse;
      width: 70%;
      margin: 0 auto;
      background: #fff;
      box-shadow: 0 3px 8px rgba(0,0,0,0.1);
    }
    th, td {
      border: 1px solid #ccc;
      padding: 12px;
      text-align: left;
    }
    th {
      width: 30%;
      background: #eaeaea;
    }
    caption {
      font-size: 22px;
      font-weight: bold;
      margin-bottom: 10px;
      color: #2c3e50;
    }
  </style>
</head>
<body>
  <table>
    <caption>HP Laptop Specification</caption>
    <tr>
      <th>Brand</th>
      <td>HP</td>
    </tr>
    <tr>
      <th>Model</th>
      <td>HP Pavilion 15</td>
    </tr>
    <tr>
      <th>Processor</th>
      <td>Intel Core i5 12th Gen</td>
    </tr>
    <tr>
      <th>RAM</th>
      <td>16 GB DDR4</td>
    </tr>
    <tr>
      <th>Storage</th>
      <td>512 GB SSD</td>
    </tr>
    <tr>
      <th>Graphics</th>
      <td>NVIDIA GeForce MX450</td>
    </tr>
    <tr>
      <th>Display</th>
      <td>15.6" Full HD (1920x1080)</td>
    </tr>
    <tr>
      <th>Operating System</th>
      <td>Windows 11 Home</td>
    </tr>
    <tr>
      <th>Battery</th>
      <td>3-cell, 41 Wh Li-ion, up to 7 hours</td>
    </tr>
    <tr>
      <th>Weight</th>
      <td>1.75 kg</td>
    </tr>
    <tr>
      <th>Special Features</th>
      <td>Backlit Keyboard, Wi-Fi 6, Bluetooth 5.2</td>
    </tr>
  </table>
</body>
</html>
'''
        

    
    
        
    

    
        


class Myserver(BaseHTTPRequestHandler):
   def do_GET(self):
       print("Get request received...")
       self.send_response(200)
       self.send_header("content-type", "text/html")
       self.end_headers()
       self.wfile.write(content.encode())
print("This is my webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,Myserver)
httpd.serve_forever()



# OUTPUT:
![alt text](<Screenshot (1).png>)

![alt text](<Screenshot (2).png>)


# RESULT:
The program for implementing simple webserver is executed successfully.
