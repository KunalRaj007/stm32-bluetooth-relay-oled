# 🔌 Smart Bluetooth-Controlled Light System with OLED Display (STM32)

Control a relay (e.g. room light) wirelessly using Bluetooth from your smartphone, and view the ON/OFF status in real-time on an SSD1306 OLED display. Built with STM32 and HAL libraries.



---

## 📦 Components Used

| Component         | Description                        |
|------------------|------------------------------------|
| STM32F4 (e.g. F401RE) | ARM Cortex-M4 Microcontroller     |
| HC-05 Bluetooth   | Wireless serial communication     |
| SSD1306 OLED      | I2C Display Module (128x64)       |
| Relay Module      | Controls AC Load (Light/Fan etc.) |
| Smartphone App    | Bluetooth Terminal App (Android)  |

---

## 🛠️ Features

- ✅ Turn light ON/OFF using Bluetooth commands (`1` or `0`)
- ✅ Display current status (`Light: ON/OFF`) on OLED screen
- ✅ UART interrupt-based command handling
- ✅ Non-blocking code using HAL drivers

---

## 🧠 How It Works

1. Smartphone sends `1` or `0` via HC-05 Bluetooth.
2. STM32 receives it over `USART1` (with interrupt).
3. On `1`: PA5 set HIGH → Relay ON → OLED shows **Light: ON**
4. On `0`: PA5 set LOW → Relay OFF → OLED shows **Light: OFF**

---

## 📲 Wiring Diagram

> Connect as per below:

| STM32 Pin | Module         | Notes             |
|-----------|----------------|-------------------|
| PA5       | Relay IN       | Digital output    |
| PB8       | OLED SCL       | I2C Clock         |
| PB9       | OLED SDA       | I2C Data          |
| PA9       | HC-05 TX       | UART RX (STM32)   |
| PA10      | HC-05 RX       | UART TX (STM32)   |
| 3.3V      | HC-05 VCC      | Power             |
| 5V        | Relay VCC      | Power             |
| GND       | All GND        | Common Ground     |

---

## 🧪 Testing Steps

1. Flash firmware using STM32CubeIDE.
2. Open Bluetooth Terminal App on Android (e.g. **Serial Bluetooth Terminal**).
3. Send `'1'` → Light ON, OLED shows **Light: ON**
4. Send `'0'` → Light OFF, OLED shows **Light: OFF**

---
## 📷 Demo Preview

> *(Add image or video/GIF of the working prototype here)*
![off_hc-05](https://github.com/user-attachments/assets/5741caab-242f-4d79-a054-c1692de862b4)
> ![on_hc-05](https://github.com/user-attachments/assets/05ce30fe-e355-4e80-85d4-77353f6f5b62)


---
## 📜 License

This project is open-source and available under the **MIT License**.

---

## 👤 Author

**Kunal Raj**  
Embedded Systems Developer | IoT Enthusiast  
GitHub: [https://github.com/KunalRaj007](https://github.com/KunalRaj007)  
Email: Kunalraj1699@gmail.com


