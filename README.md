# EX01 Developing a Simple Webserver

# Date: 13.09.2024

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
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content="""
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>System Specifications</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f9;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        table {
            width: 100%;
            max-width: 600px;
            margin: 20px auto;
            border-collapse: collapse;
            background-color: #fff;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }
        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        th {
            background-color: #f2f2f2;
            font-weight: bold;
        }
        td {
            color: #555;
        }
        .section-title {
            font-size: 1.2em;
            margin-top: 20px;
            color: #444;
        }
    </style>
</head>
<body>

    <h1>System Specifications</h1>
    
    <table>
        <tr>
            <th>Device Name</th>
            <td>DESKTOP-MOHHBTU</td>
        </tr>
        <tr>
            <th>Processor</th>
            <td>13th Gen Intel(R) Core(TM) i5-1335U @ 1.30 GHz</td>
        </tr>
        <tr>
            <th>Installed RAM</th>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <th>Device ID</th>
            <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
        </tr>
        <tr>
            <th>Product ID</th>
            <td>00342-42709-07179-AAOEM</td>
        </tr>
        <tr>
            <th>System Type</th>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <th>Pen and Touch</th>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
    
    <div class="section-title">Additional Information</div>
    <p>The system is equipped with a 13th Gen Intel Core i5 processor, providing a solid balance of power and efficiency for everyday tasks. The 16 GB of RAM ensures smooth multitasking performance, while the 64-bit architecture supports modern applications and games.</p>

</body>
</html>
"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=('',8000)
httpd= HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
# OUTPUT:

![Screenshot (83)](https://github.com/user-attachments/assets/b35a9cc2-866e-4ac4-b38f-f86d3141aa41)

![Screenshot (84)](https://github.com/user-attachments/assets/8e7c7d0d-1d11-4399-a6bc-c83a28f74925)


# RESULT:
The program for implementing simple webserver is executed successfully.
