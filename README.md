# CYD Video Player & Conversion Studio 🎬
Welcome to the ultimate Video Player and Conversion Studio ecosystem for the **Cheap Yellow Display (CYD)** (ESP32-2432S028R). This project offers a high-performance, lag-free MJPEG video player with synchronized I2S MP3 audio playback, touch controls, volume/brightness gestures, and seek support.

---
## ⚡ Quick Start & Installation
You can get the video player running on your CYD board in less than 2 minutes using our web tools.
### Option 1: Browser-Based Flashing (No Install)
Flash the software directly onto your Cheap Yellow Display from your web browser using WebSerial:
👉 **[Launch Web Flasher](https://quadever-launcher.onrender.com/flasher?app=1784397278763)**
### Option 2: Direct Binary Download
Download the compiled firmware `.bin` file to write using Espressif's Flash Download Tool:
👉 **[Download Firmware Binary (.bin)](https://quadever-launcher.onrender.com/apps/download/1784397278763)**
> [!WARNING]  
> **Touch Calibration Required Post-Flashing:**  
> Upon flashing the binary for the first time, immediately navigate to **Settings > Touch Cal** to calibrate your touch screen. Follow the crosshair prompts. This guarantees accurate gestures and button triggers.
---
## 📁 SD Card Folder Structure
The video player reads media files directly from a FAT32-formatted Micro SD Card inserted into the CYD board. Organize your card exactly as follows:
```
[SD Card Root]
 └── 📂 videos/
      ├── 🎬 movie1.mjpeg      (Video track)
      ├── 🎵 movie1.mp3        (Audio track - must match video filename)
      ├── 📄 movie1.idx        (Optional index file for instant scrubbing/seeking)
      ├── 🎬 holiday.mjpeg
      ├── 📄 holiday.idx
      └── 🎵 holiday.mp3
```
> [!NOTE]  
> **Matching Filenames:** The audio `.mp3` file must have the **exact same name** as the `.mjpeg` file in the `/videos` directory for the player to automatically synchronize them.
---
## 🎥 CYD Video Conversion Studio
To prepare your custom videos (MP4, MKV, AVI, etc.) for the Cheap Yellow Display, use the **CYD Video Conversion Studio** desktop application included in the release.
The studio is a fully standalone Windows application that **works 100% offline** (all converters and dependencies are embedded).
### How to use the Conversion Studio:
1. Open **[CYD Video Conversion Studio.exe](./CYD%20Video%20Conversion%20Studio.exe)**.
2. Select your **Board Preset** (e.g., `CYD 2.8" (Landscape)` for `320x240` resolution).
3. Browse and select your **Source Video** file.
4. Set your target FPS (30 FPS recommended) and JPEG Quality.
5. Click **Convert** to generate the outputs.
6. The tool will output:
   * A `.mjpeg` file (compressed video).
   * A `.mp3` file (optimized audio stream).
   * A `.idx` file (pre-calculated IDX).
7. Copy these three files into the `videos/` folder of your SD card.
---
## PCM5102A Wiring
* **Audio DAC**: PCM5102A (I2S configuration: BCK -> GPIO 4, LRCK -> GPIO 22, DIN -> GPIO 27)
*Note: Make sure to short the GND bridge pads on the PCM5102A board (SCK, FLT, DMP, FMT, BYP) to configure it for internal system clock operations.*
---
## 💬 Help & Support
If you run into issues, need custom builds, or want to explore matching hardware accessories:
* **Get Help & Issues**: [Report an Issue](https://github.com/samiralam5755/CYD-Video-Player/issues)
* **Official Support**: [Quadever Support](https://www.quadever.com/support)
* **Developer Coffee**: [Support Samir Alam on Ko-fi](https://ko-fi.com/samir_alam)
---
*Developed with ❤️ by Samir Alam | [Quadever](https://www.quadever.com)*
