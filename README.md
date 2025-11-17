QR Code Generator
Project Overview
This project is a QR Code Generator application created using Node.js, HTML, and CSS. It includes:

A Node.js command-line tool that generates QR codes from user-entered URLs.
A simple web interface containing forms for login and sign-in.
A landing page with buttons for QR generation and downloading.
This project demonstrates the usage of Node.js modules, user input handling, file creation, and basic web UI design.

Features
Node.js QR Generator
Takes user input using Inquirer.js
Uses qr-image module to convert URLs into QR images
Saves the generated QR code as qr_img.png
Writes the original URL to a text file URL.txt
Web UI
Simple HTML page for QR Generator UI
Sign-in and Login pages
Clean form layout using inline CSS
Project Structure
qr-generator index.js (Node.js QR generator logic) package.json (Dependencies + metadata) URL.txt (Generated file storing user URL) qr_img.png (Generated QR image) index.html (Main frontend page) login.html (Login page) sign.html (Sign-in page)

How the Node.js QR Generator Works
Takes user input
Using Inquirer: js inquirer.prompt([{ message: "Type in your URL:", name: "URL" }])

Generates QR Image
js var qr_svg = qr.image(url); qr_svg.pipe(fs.createWriteStream("qr_img.png")); This saves a PNG QR image based on provided URL.

Stores URL in a text file
js fs.writeFile("URL.txt", url, (err) => {...});

A text file is created containing the same URL for record-keeping.

Dependencies
Installed using npm: json { "dependencies": { "fs": "^0.0.1-security", "inquirer": "^9.2.16", "qr-image": "^3.2.0" } }

inquirer
Used for interactive input.

qr-image
Creates QR codes in PNG/SVG form.

fs module
Used to save files.

How to Run the Project
1. Install Node.js
Download from https://nodejs.org/

2. Install Dependencies
npm install

3. Run the program
node index.js You will be prompted: Type in your URL:

4. After entering URL:
A file qr_img.png will be generated.
A URL.txt file will be created.
Conclusion
This QR Code Generator project shows how to:

Use Node.js modules
Accept user input through CLI
Generate QR codes automatically
Create simple frontend interfaces
