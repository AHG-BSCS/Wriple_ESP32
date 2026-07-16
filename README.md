# <img src="https://github.com/AHG-BSCS/Wriple_ESP32/blob/0cb059ab99261828a444cd10bde82d42706d2545/docs/icon.png" width="28" alt="Logo Thumbnail"> WRIPLE ESP32 ![wriple esp32 badge][wriple-esp32-badge]
The device-free wireless sensing (DFWS) firmware of the ESP32-WROOM-32U module for the WRIPLE system. This firmware serve as the controller of the ESP32 module during the real-time human presence detection. When the WRIPLE station and ESP32 are both is connected to the dedicated AP, WRIPLE station can control the ESP32 behavior to send Wi-Fi CSI and mmWave RDM in a controlled timing.
Find the WRIPLE application [here][wriple-system]. Email the developer for any questions and any development that this software has been used.

## Table of Contents
- [Features](#features)
- [Prototype](#Prototype)
- [Flashing](#Flashing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Features
- **Auto AP Association** - Automatically connect to dedicated AP using a fix SSID and password.
- **Auto Device Discovery** - Identify the WRIPLE station address by listening to broadcast messages.
- **Status LED** - Turn on the LED when the WRIPLE station and ESP32 is connected. Blink the LED when ESP32 is actively sending data.
- **Auto Connection Reset** - When the WRIPLE client is disconnected, the ESP32 will return to discovery mode to inform the WRIPLE client of the ESP32 presence.
- **Adaptive Transmit Timing** - Control the timing of data transmission of ESP32 based on the request frequency of the WRIPLE station.

## Prototype
### List of Components
# <img src="https://github.com/AHG-BSCS/Wriple_ESP32/blob/cbe37b5a8f4e9e60fa9dedafc3f33bb450269944/docs/prototype.jpg" width="700" alt="dfws prototype">

- ESP32-WROOM-32U DevKitC Module
- HLK-LD2420 mmWave Radar
- High Gain External Antenna (12 dBi)
- u.FL to RP-SMA Coaxial Pigtail Cable
- USB to USB Micro-B Cable
- Green LED
- Resistor (220 ohms)
- Aluminum Heat Sink (optional)
- Dupont Jumper Wires

### Schematic Diagram
# <img src="https://github.com/AHG-BSCS/Wriple_ESP32/blob/cbe37b5a8f4e9e60fa9dedafc3f33bb450269944/docs/schematic-diagram.png" width="500" alt="schematic diagram">

## Flashing
1. Clone the repository using [Git][git].
2. Open the source code folder using [VS Code][vs-code] IDE.
3. In the VS Code extension tab, search and install the [ESP-IDF][esp-idf-ext] by Espressif Systems.
4. Install any other necessary extension such as `C/C++` and `CMake Tools`.
5. After installation, the `ESP-IDF Explorer` tab will be added. Click the tab and a missing installation prompt will pop up. Click `Open ESP-IDF Installation Manager`. You can also open the installation window by clicking the `Open ESP-IDF Installation Manager` option in the ESP-IDF Explorer Advance section.
6. The ESP-IDF Installation Manager window will be open. Click Start Installation, then Start Easy Installation until you finish the installation.
7. From now on, the ESP-IDF Explorer tab will be utilize. Using the different selections from that tab, you have to set some configuration that will correctly communicate to the ESP32 WROOM 32U module. Ensure that the ESP32 DevKitC module is connected to the computer via USB. Set the following configuration: Flash Method = `UART`, Port = `COM3` (port may vary). If there is some error, ensure that the UART baud rate is set to `115200`.
8. In the ESP-IDF Explorer tab, click `Build Project`. This may take a while.
9. In the ESP32 DevKitC module, hold the boot button, then while holding click `Flash Device` option. Once the device is detected, boot button can be release.
10. Monitor the ESP32 output and status for debugging by clicking the `Monitor Device`.

## License
This project is licensed under the <licence-name> License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- **[ESP-IDF][esp-idf]**: For ESP32 framework and documentation.
- **[esp-csi][esp-csi]**: For sample usage of ESP-IDF.
- **[ESP32-CSI-Tool][esp32-csi-tool]**: For sample source code for capturing Wi-Fi CSI.
- **[ESP32 Pinout Reference][esp32-pinout]**: For ESP32-WROOM-32U DevKitC module pin reference.
- **[HMMD mmWave Sensor][mmwave-sensor]**: For HLK-LD2420 communication demo.

<!-- Reference -->
[wriple-esp32-badge]: https://img.shields.io/badge/Firmware-Device_Free_Wireless_Sensing-8B4513

[wriple-system]: https://github.com/AHG-BSCS/Wriple
[git]: https://git-scm.com/install/windows
[vs-code]: https://code.visualstudio.com/download
[esp-idf-ext]: https://marketplace.visualstudio.com/items?itemName=espressif.esp-idf-extension

[esp-idf]: https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-guides/wifi-driver/index.html
[esp-csi]: https://github.com/espressif/esp-csi
[esp32-csi-tool]: https://stevenmhernandez.github.io/ESP32-CSI-Tool/
[esp32-pinout]: https://lastminuteengineers.com/esp32-pinout-reference/
[mmwave-sensor]: https://www.waveshare.com/wiki/HMMD_mmWave_Sensor
