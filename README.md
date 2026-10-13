<h1 align="center">Hi 👋, I'm Rajat kumar nayak</h1>
<h3 align="center">A passionate frontend developer from India</h3>

- 🔭 I’m currently working on **Smart talking gloves**

- 👯 I’m looking to collaborate on **Smart talking gloves**

- 🤝 I’m looking for help with **Smart talking gloves**

<h3 align="left">Connect with me:</h3>
<p align="left">
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://www.arduino.cc/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/arduino-1.svg" alt="arduino" width="40" height="40"/> </a> </p>
# Smart Talking Glove for Mute & Paralyzed Patients
An Arduino-based assistive device designed for speech-impaired, bedridden, or paralyzed patients to communicate their essential needs effectively. By simply touching fingertips with copper contact pads, the glove speaks predefined messages via an audio speaker and displays them on an LCD screen in dual languages (Odia & Hindi).
---
## Features
- **Dual-Language Support**: Switch easily between **Odia** and **Hindi** with a toggle switch.
- **8 Pre-Recorded Messages**: Covers primary daily needs (Food, Water, Washroom, Assistance, Pain, etc.).
- **Visual Display**: 16x2 I2C LCD screen displays the spoken sentence in real-time.
- **Clear Voice Output**: High-clarity audio powered by DFPlayer Mini module and an amplified speaker.
- **Simple Touch Mechanism**: Low-effort fingertip touch pads designed for patients with limited mobility.
---
## Components List

| Component | Quantity | Description / Role |
| :--- | :--- | :--- |
| **Arduino UNO** | 1 | Main microcontroller unit |
| **DFPlayer Mini** | 1 | MP3 voice playback module |
| **16x2 LCD (with I2C)** | 1 | Visual message display |
| **Copper Foil / Touch Pads** | 8 | Fingertip trigger inputs |
| **Resistors (10kΩ)** | 8 | External pull-up resistors for touch triggers |
| **Resistor (1kΩ)** | 1 | Current limiting for DFPlayer RX line |
| **PAM8403 / Audio Amp Module** | 1 | Speaker audio amplification |
| **Speaker (3W, 8Ω)** | 1 | Voice output |
| **Toggle Switch** | 1 | Language selector (Odia / Hindi) |
| **Power Supply** | 5V | Common power source |
| **Breadboard & Wires** | — | Prototyping and connections |

---
## Circuit & Pin Connections
### 1. I2C LCD (16x2) to Arduino
- **VCC** ➔ `5V`
- **GND** ➔ `GND`
- **SDA** ➔ `A4`
- **SCL** ➔ `A5`
### 2. DFPlayer Mini to Arduino
- **VCC** ➔ `5V`
- **GND** ➔ `GND` (Must share common ground with Arduino)
- **TX** ➔ `D10` (Arduino RX)
- **RX** ➔ `D11` (Arduino TX via 1kΩ resistor)
- **SPK_1 / SPK_2** ➔ Audio Amplifier / Speaker
### 3. Touch Points (External Pull-Up)
Each touch pad is pulled up to +5V through a 10kΩ resistor and connects to GND upon contact:
- **Touch 1** ➔ `D2`
- **Touch 2** ➔ `D3`
- **Touch 3** ➔ `D4`
- **Touch 4** ➔ `D5`
- **Touch 5** ➔ `D6`
- **Touch 6** ➔ `D7`
- **Touch 7** ➔ `D8`
- **Touch 8** ➔ `D9`
### 4. Language Selector Switch
- **Switch Pin** ➔ `D12` (Uses internal pull-up; switches between Odia and Hindi)
---
## Message Mapping

| Pad No. | Hindi Audio (`0001.mp3` - `0008.mp3`) | Odia Audio (`0009.mp3` - `0016.mp3`) |
| :--- | :--- | :--- |
| **1** | Mujhe khana dijiye | Mote Bhoka Laguchi |
| **2** | Mujhe pani chahiye | Mote Pani Dea |
| **3** | Washroom jana he | Mu Washroom Jibi |
| **4** | TV dekhna he | Mu Tv Dekhibi |
| **5** | Bahut garmi he | Mte Garam Laguchi |
| **6** | Thand lag rahi he | Thanda Laguchi |
| **7** | Dard ho raha he | Mor Pain Hauchi |
| **8** | Madad bulaiye | Mor Help Darkar |

---
## SD Card Folder Structure
Store the 16 audio files inside an `mp3` folder on your FAT32 formatted MicroSD card:
```text
SD_CARD/
└── mp3/
    ├── 0001.mp3   <-- Hindi: Mujhe khana dijiye
    ├── 0002.mp3   <-- Hindi: Mujhe pani chahiye
    ├── ...
    ├── 0008.mp3   <-- Hindi: Madad bulaiye
    ├── 0009.mp3   <-- Odia: Mote Bhoka Laguchi
    ├── ...
    └── 0016.mp3   <-- Odia: Mor Help Darkar
