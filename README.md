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
An assistive communication device built with Arduino UNO designed for mute, paralyzed, bedridden, or post-stroke patients who face difficulties expressing their daily needs verbally. By touching dedicated fingertip contacts against the thumb pad, the system audibly speaks out preset emergency and daily assistance messages through a speaker while simultaneously displaying them on a 16x2 LCD screen in dual languages (Odia & Hindi).
---
## 🎯 Objectives
- **Bridge the Communication Gap**: Enable mute, paralyzed, or speech-impaired patients to express essential daily needs independently without requiring spoken words.
- **Affordable & Accessible Assistive Tech**: Create an economical alternative to costly commercial AAC (Augmentative and Alternative Communication) devices using readily available electronics.
- **Multi-lingual Support**: Allow smooth toggling between regional languages (Odia & Hindi) to support diverse caregivers and family members.
- **Dual Visual & Audio Feedback**: Simultaneously play voice recordings through an amplified speaker and render textual information on an LCD screen.
- **Low-Effort Touch Triggers**: Provide reliable, lightweight, and gentle fingertip contact points suitable for patients with minimal physical strength.
---
## 🚀 Features
- **8 Core Emergency & Daily Needs Messages**: Pre-configured messages covering food, water, sanitation, ambient comfort, pain, and general aid.
- **Instant Language Switching**: Hardware switch to toggle between **Odia** and **Hindi** on the fly.
- **Non-Blocking Debounce Routine**: A 4-second hold period protects against duplicate voice triggering during speech playback.
- **I2C Protocol Implementation**: Minimizes pin usage for display communication, freeing up digital pins for touch sensors.
- **External Pull-Up Topology**: External 10kΩ resistors provide stable logic level transitions on input triggers.
---
## 🛠️ Components List

| Component | Quantity | Role / Description |
| :--- | :--- | :--- |
| **Arduino UNO** | 1 | Central processing microcontroller |
| **DFPlayer Mini** | 1 | MP3 audio decoder module |
| **16x2 LCD Display (with I2C)** | 1 | Real-time text display |
| **Metal Foil / Copper Pads** | 8 | Fingertip touch inputs |
| **Resistors (10kΩ)** | 8 | External pull-up resistors for touch lines |
| **Speaker (3W, 8Ω)** | 1 | Audio sound output |
| **Audio Amplifier Module (e.g. PAM8403)** | 1 | Audio signal amplification |
| **Toggle / Slide Switch** | 1 | Language selector (Odia / Hindi) |
| **5V Power Supply / Battery** | 1 | Regulated power source |
| **Breadboard & Jumper Wires** | — | Prototyping and wiring connections |

---
## 🔌 Circuit & Pin Mapping
### 1. Arduino UNO ↔ I2C LCD (16x2)

| LCD Pin | Arduino Pin | Description |
| :--- | :--- | :--- |
| **VCC** | `5V` | System 5V Power |
| **GND** | `GND` | Common Ground |
| **SDA** | `A4` | I2C Data Line |
| **SCL** | `A5` | I2C Clock Line |

### 2. Arduino UNO ↔ DFPlayer Mini

| DFPlayer Pin | Arduino Pin | Description |
| :--- | :--- | :--- |
| **VCC** | `5V` | Regulated 5V Input |
| **GND** | `GND` | Common Ground (Must be tied to Arduino GND) |
| **TX** | `D10` | Serial Data to Arduino |
| **RX** | `D11` | Serial Data from Arduino (Recommended with 1kΩ resistor) |
| **SPK2 / SPK1** | Speaker / Amp | Output to Amplifier / Speaker |

### 3. Touch Sensors (External Pull-Up)
Each input pin is tied to `+5V` via a `10kΩ` pull-up resistor. Touching the respective copper contact connects the pin to `GND`, driving it `LOW`:
- **Touch Pad 1** ➔ `D2` (`D2 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 2** ➔ `D3` (`D3 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 3** ➔ `D4` (`D4 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 4** ➔ `D5` (`D5 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 5** ➔ `D6` (`D6 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 6** ➔ `D7` (`D7 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 7** ➔ `D8` (`D8 -> 10kΩ -> +5V, pad -> finger -> GND`)
- **Touch Pad 8** ➔ `D9` (`D9 -> 10kΩ -> +5V, pad -> finger -> GND`)
### 4. Language Selector
- **Switch Pin** ➔ `D12` (Internal pull-up enabled; `HIGH` = Odia, `LOW` = Hindi)
---
## 📂 SD Card Audio Organization
Prepare a FAT32-formatted MicroSD card and place the audio files in a root directory named `mp3`:
```text
SD_CARD/
└── mp3/
    ├── 0001.mp3   <-- Hindi: Mujhe khana dijiye
    ├── 0002.mp3   <-- Hindi: Mujhe pani chahiye
    ├── 0003.mp3   <-- Hindi: Washroom jana he
    ├── 0004.mp3   <-- Hindi: TV dekhna he
    ├── 0005.mp3   <-- Hindi: Bahut garmi he
    ├── 0006.mp3   <-- Hindi: Thand lag rahi he
    ├── 0007.mp3   <-- Hindi: Dard ho raha he
    ├── 0008.mp3   <-- Hindi: Madad bulaiye
    ├── 0009.mp3   <-- Odia: Mote Bhoka Laguchi
    ├── 0010.mp3   <-- Odia: Mote Pani Dea
    ├── 0011.mp3   <-- Odia: Mu Washroom Jibi
    ├── 0012.mp3   <-- Odia: Mu Tv Dekhibi
    ├── 0013.mp3   <-- Odia: Mte Garam Laguchi
    ├── 0014.mp3   <-- Odia: Thanda Laguchi
    ├── 0015.mp3   <-- Odia: Mor Pain Hauchi
    └── 0016.mp3   <-- Odia: Mor Help Darkar
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <SoftwareSerial.h>
#include <DFRobotDFPlayerMini.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);
SoftwareSerial dfSerial(10, 11);
DFRobotDFPlayerMini dfplayer;

const byte pads[8] = {2, 3, 4, 5, 6, 7, 8, 9};
const byte langSwitch = 12;

unsigned long lastPlayTime = 0;
bool isPlaying = false;

const char* hiText[8] = {
  "Mujhe khana dijiye",
  "Mujhe pani chahiye",
  "Washroom jana he",
  "TV dekhna he",
  "Bahut garmi he",
  "Thand lag rahi he",
  "Dard ho raha he",
  "Madad bulaiye"
};

const char* enText[8] = {
  "Mote Bhoka Laguchi",
  "Mote Pani Dea",
  "Mu Washroom Jibi",
  "Mu Tv Dekhibi",
  "Mte Garam Laguchi",
  "Thanda Laguchi",
  "Mor Pain Hauchi",
  "Mor Help Darkar"
};

void setup() {
  lcd.init();
  lcd.backlight();
  lcd.setCursor(0, 0);
  lcd.print("Smart Voice Glove");
  delay(1500);
  lcd.clear();

  dfSerial.begin(9600);
  if (!dfplayer.begin(dfSerial)) {
    lcd.clear();
    lcd.print("DFPlayer error");
    while (1);
  }

  dfplayer.volume(25);

  for (byte i = 0; i < 8; i++) {
    pinMode(pads[i], INPUT_PULLUP);
  }
  pinMode(langSwitch, INPUT_PULLUP);

  showLanguageScreen();
}

void loop() {
  // ---------- If playing, wait non-blocking ----------
  if (isPlaying) {
    if (millis() - lastPlayTime >= 4000) { // 4 seconds hold time
      isPlaying = false;
      showLanguageScreen();
    }
    return;
  }

  // ---------- Check touch pads ----------
  for (byte i = 0; i < 8; i++) {
    if (digitalRead(pads[i]) == LOW) {
      playMsg(i + 1);
      isPlaying = true;
      lastPlayTime = millis();
      return;
    }
  }

  // ---------- Check Language Switch ----------
  static bool lastLang = digitalRead(langSwitch);
  bool currentLang = digitalRead(langSwitch);
  if (currentLang != lastLang) {
    lastLang = currentLang;
    showLanguageScreen();
  }
}

void playMsg(byte n) {
  bool english = digitalRead(langSwitch);
  byte track = english ? n + 8 : n;

  lcd.clear();
  lcd.print(english ? "Odia:" : "Hindi:");
  lcd.setCursor(0, 1);
  lcd.print(english ? enText[n - 1] : hiText[n - 1]);

  dfplayer.play(track);
}

void showLanguageScreen() {
  lcd.clear();
  if (digitalRead(langSwitch)) {
    lcd.print("Language: Odia");
  } else {
    lcd.print("Language: Hindi");
  }
  lcd.setCursor(0, 1);
  lcd.print("Touch to Play");
}
