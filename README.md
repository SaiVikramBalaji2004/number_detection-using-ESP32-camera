# 🚘 ESP32-CAM Based Number Plate Recognition

**Published on:** January 31, 2025  
**Author:** Jonahan

This project demonstrates how to use the **ESP32-CAM** to capture vehicle number plates and send them to a **cloud API** for recognition. All machine learning tasks are offloaded to the **Circuit Digest Cloud Server**, making this project lightweight and compatible with other microcontrollers that have internet and camera capabilities.

---

## 📷 How It Works

1. ESP32-CAM captures an image when a button is pressed.
2. The image is sent via WiFi to the **Circuit Digest Number Plate Recognition API**.
3. The server processes the image using OCR and sends back the recognized number plate.
4. The result is displayed on a **0.96" OLED Display** and via **Serial Monitor**.

---

## 🧰 Components Required

| Component               | Quantity |
|------------------------|----------|
| ESP32-CAM              | 1        |
| 0.96” OLED Display     | 1        |
| Push Button            | 1        |
| 10KΩ Resistor          | 1        |
| USB to UART Converter  | 1        |
| Breadboard             | 1        |
| Jumper Wires           | As needed |

---

## 📡 Circuit Diagram

The connection between ESP32-CAM, OLED, push button, and UART converter is simple and uses only essential pins. 
 ![image alt](https://github.com/SaiVikramBalaji2004/Image-processing-on-fire-detetion/blob/b1e9149b1eee7b5795b7c34898d234945ee787ca/image.png)


---

## 💻 Programming the ESP32-CAM

### 1. **Generate an API Key**

To use the number plate recognition feature, you'll need an API Key.


### 2. **Code Structure**

The code is divided into three parts:

#### 📁 Part 1: Setup & Configuration
- Includes libraries for **WiFi**, **Camera**, **OLED**, and **HTTPS**.
- Configure WiFi credentials and API Key.
- Initialize GPIOs (I2C_SDA, I2C_SCL, Flash, Button).

#### 📁 Part 2: Initialization & Custom Functions
- Custom function `extractJsonStringValue()` to parse server response.
- OLED print functions for real-time feedback.
- `setup()` initializes WiFi, camera, OLED, and disables brownout detector.

#### 📁 Part 3: Main Loop
- `loop()` monitors the trigger button.
- When pressed, it calls `sendPhoto()`:
  - Turns on flash
  - Captures image
  - Sends image to API server
  - Receives JSON response
  - Displays number plate on OLED
 
    
     ![image alt](https://github.com/SaiVikramBalaji2004/Image-processing-on-fire-detetion/blob/9e23f8b3fc52b95172fbbe8d7005ca0a9ca4c754/ESP32-CAM%20real.jpg)


---

## 🚀 Running the Project

1. Connect all hardware components as per the diagram.
2. Open the code in **Arduino IDE**.
3. Add your **WiFi SSID**, **Password**, and **API Key**.
4. Select the board as `AI Thinker ESP32-CAM` in Arduino IDE.
5. Upload the code using a USB to UART Converter.
6. Open Serial Monitor at `115200 baud`.
7. Press the trigger button to capture and process the number plate.

---

## ⚠️ Tips for Better Accuracy

- Ensure the camera is **focused properly** on the number plate.
- **Improve lighting** conditions or use the built-in flash.
- Reduce image resolution (if needed) to improve upload speed.
- Clean and readable number plates = higher OCR accuracy.

---



