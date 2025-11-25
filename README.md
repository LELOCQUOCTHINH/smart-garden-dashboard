# BK Smart Garden – Public Web Dashboard

This repository hosts the source code for the public Web Dashboard of the BK Smart Garden project. This website serves as the central remote control and monitoring hub for the intelligent plant care system, connecting to the ESP32 device via the MQTT protocol (HiveMQ Cloud).

| ![Auto Mode UI](https://github.com/user-attachments/assets/c3a6e9ab-5b5e-440c-9b7e-567cd8ebce28) | ![Manual Mode UI](https://github.com/user-attachments/assets/f2897967-65c1-441a-a818-57658c0b810c) |
|:--:|:--:|
| **Auto Mode Control UI**<br>| **Manual Mode Control UI**<br>|

| ![Setting Mode UI](https://github.com/user-attachments/assets/fe69b9a7-4bbe-4272-92e1-fa670d9b1979) | ![Manual Mode UI](https://github.com/user-attachments/assets/27e76134-4d9c-4624-b631-da43d4cf2199) |
|:--:|:--:|
| **Setting Mode UI**<br>| **User Manual UI**<br>|

## Directory Structure

```
.
├── index.html          # Main file containing HTML, CSS, and JavaScript for the Dashboard
├── images/             # Directory containing image resources
│   ├── favicon_32x32.png  # Website favicon
│   └── logoBK.png         # Ho Chi Minh City University of Technology Logo
└── README.md           # This documentation file
```

## Key Features

- **User Interface (UI)**: Modern, user-friendly flat design, optimized for both desktop and mobile devices.
- **Real-time Monitoring**: Displays real-time data for air temperature, air humidity, soil moisture, and pump status updated instantly from the ESP32.
- **Remote Control**:
  - Flexible switching between Auto (Automatic) and Manual modes.
  - Direct Pump ON/OFF control in Manual mode.
- **System Configuration**: Allows users to set trigger thresholds for Auto mode (e.g., Temperature > 30°C, Soil Moisture < 40%) and synchronize them to the device.
- **Security**: Requires login with MQTT credentials (Username/Password) to ensure only authorized users can access and control the system.

## Technologies Used

- **HTML5 / CSS3**: Builds the structure and styling of the webpage.
- **JavaScript (ES6+)**: Handles logic, user interactions, and dynamic interface updates.
- **Paho MQTT Client (JS)**: The mqttws31.min.js library enables direct connection from the web browser to the MQTT Broker via WebSockets (WSS).

## Deployment Guide

Since this is a static website, it can be easily deployed for free on various platforms:

### 1. GitHub Pages (Recommended)

1. Push the source code to a GitHub repository.
2. Go to Settings → Pages.
3. Under Source, select the main (or master) branch and the /root folder.
4. Click Save. The website will be available at https://<your-username>.github.io/<repo-name>/.

### 2. Netlify / Vercel

1. Connect your GitHub account to Netlify or Vercel.
2. Select this repository.
3. Click Deploy. The system will automatically build and provide a domain URL.

### 3. Traditional Hosting

1. Upload all files (index.html and the images folder) to the public_html directory of your hosting provider.
2. Access via your domain name.

## User Guide

1. Access the deployed website URL.
2. Enter the MQTT Username and Password (configured on HiveMQ Cloud and the ESP32).
3. Click Connect System.
4. Upon successful connection, you can view data and control the device.

## Important Notes

- **MQTT Configuration**: Ensure that the MQTT Broker information (Host, Port, Topic) in the index.html file matches the configuration on the ESP32 device.
  - Host: your-cluster-url.s1.eu.hivemq.cloud
  - Port: 8884 (Note: WebSockets typically use port 8884, while the ESP32 uses port 8883 for TCP).
  - Protocol: WSS (WebSockets Secure).

## Contact

This project was developed by Le Loc Quoc Thinh – Student at Ho Chi Minh City University of Technology.  
For any questions or contributions, please contact: thinhle.hardware@gmail.com
