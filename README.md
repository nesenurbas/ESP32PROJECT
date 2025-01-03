# TinyML-Based Real-Time Image Classification Using ESP32-CAM

This README file provides a detailed explanation of the code used throughout the project, including the libraries utilized. The project involves capturing images with **ESP32-CAM** and performing real-time object detection using a **MobileNet** model trained on the **Edge Impulse** platform.

## 1. Project Overview
This project utilizes the ESP32-CAM module to perform the following key functions:

- **ESPSETUP.ino**: The initial setup code for configuring the ESP32-CAM and sending captured images to a Telegram bot.
- **esp32_camera.ino**: A script that integrates a **MobileNet** model trained on **Edge Impulse** to classify real-time images into four categories: female, male, cat, and dog.

## 2. Requirements and Libraries Used
### **Hardware Requirements**
- **ESP32-CAM** module
- **FTDI Programmer** (for programming ESP32-CAM)
- **5V power supply**
- **Wi-Fi connection**

### **Software Requirements**
- **Arduino IDE** (development environment for ESP32)
- **Edge Impulse Studio** (for model training)
- **ESP32 additional libraries** (for ESP32-CAM support)
- **Python (optional, for data processing and model training)**

### **Libraries Used in Arduino Code**
#### **For ESPSETUP.ino:**
```cpp
#include <WiFi.h>
#include <ESP32CAM.h>
#include <TelegramBot.h>
```
- `WiFi.h` - Manages Wi-Fi connection for ESP32.
- `ESP32CAM.h` - Controls the ESP32-CAM module.
- `TelegramBot.h` - Enables Telegram bot integration.

#### **For esp32_camera.ino:**
```cpp
#include <WiFi.h>
#include <esp_camera.h>
#include <EdgeImpulseSDK.h>
```
- `WiFi.h` - Enables Wi-Fi connectivity.
- `esp_camera.h` - Handles the ESP32-CAM camera module.
- `EdgeImpulseSDK.h` - Integrates the Edge Impulse model for object detection.

## 3. Connection Details

The project uses the following Wi-Fi and Telegram bot credentials:
```cpp
const char* ssid = "•NNB•";
const char* password = "12345678";

// Telegram BOT Details
String BOTtoken = "7386787547:AAGC9yt-mdJj9jf5nvMiCs71N7M5XGyFgJI";
String CHAT_ID = "7714361306";
```

## 4. Code Explanations and Execution

### **ESPSETUP.ino - Sending Images to Telegram**
This script captures images using ESP32-CAM and sends them to a **Telegram bot**.

#### **Setup Steps:**
1. **Open Arduino IDE and load** `ESPSETUP.ino`.
2. **Wi-Fi and bot credentials are provided in the previous section.**
3. **Upload the script to ESP32-CAM and verify the connection using the serial monitor.**
4. **Receive captured images via the Telegram bot.**

### **esp32_camera.ino - Real-Time Object Detection with Edge Impulse**
This script enables real-time object classification of **female, male, cat, and dog** images.

#### **Setup Steps:**
1. **Train the Model on Edge Impulse Studio:**
   - A **MobileNet** model was trained.
   - Data was collected for four categories: **female, male, cat, and dog**.
   - The trained model was downloaded in an ESP32-compatible format.

2. **Deploy the Model to ESP32-CAM:**
   - Open `esp32_camera.ino` in **Arduino IDE**.
   - Wi-Fi credentials and bot token are defined in the connection details section.
   - Integrate the **Edge Impulse model** into the code.
   - Upload the script to ESP32-CAM and test the model’s performance.

3. **Real-Time Classification:**
   - The ESP32-CAM captures images and classifies them using the Edge Impulse model.
   - Results can be displayed in the **serial monitor** or via an **HTTP server**.

## 5. Common Errors and Solutions
- **ESP32-CAM does not send images:**
  - Check Wi-Fi credentials.
  - Open the serial monitor and analyze error messages.
- **Edge Impulse model is not working properly:**
  - Ensure that the model was downloaded in a compatible format for ESP32.
  - Test the model with different input dimensions.
- **ESP32 does not boot:**
  - Verify that the FTDI programmer is connected correctly.
  - Double-check hardware connections.

## 6. Conclusion
This project successfully demonstrates the integration of **ESP32-CAM** with **Edge Impulse** to perform real-time object detection. The **ESPSETUP.ino** script facilitates image transmission via Telegram, while **esp32_camera.ino** enables live classification of **female, male, cat, and dog** objects. By leveraging **Edge Impulse Studio**, a robust **MobileNet-based** model was trained and optimized for deployment on ESP32-CAM. The implemented system effectively classifies images and delivers results via a serial monitor or HTTP server.

This project serves as a foundational step for more complex **embedded AI** applications, offering potential improvements such as increased model accuracy, enhanced dataset diversity, and alternative deployment approaches.

