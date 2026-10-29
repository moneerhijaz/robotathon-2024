# IEEE RAS Robotathon 2024

Historical ESP32 competition robot code using Arduino components inside ESP-IDF, Bluepad32 controller input, QTR line sensing, Sharp IR, and APDS9960 color sensing.

Moneer Hijaz participated in the team; this repository is retained as learning history rather than promoted as the latest robot platform. See the [experience write-up](https://hijaz.dev/experience/robotathon-2024/) and [2025 successor](https://github.com/moneerhijaz/robotathon-2025).

## Source and reproduction

- `main/arduino_main.cpp`: controller callbacks, motor helpers, calibration, and line-following logic.
- `Sensor codes/`: separate sensor experiments.
- `components/`: vendored Arduino, Bluepad32, and Bluetooth dependencies; retain their notices.
- `sdkconfig`: original project configuration; do not replace it with another robot's settings.

The [original setup guide](docs/original-setup.md) specifies **ESP-IDF 4.4.8**. From an installed/exported IDF 4.4.8 shell, in this repository:

```bash
idf.py --version
idf.py -B build build
# Only after wiring/power checks on the intended board:
idf.py -B build -p /dev/ttyUSB0 flash monitor
```

Build and hardware validation were not run here because the ESP-IDF toolchain and robot are absent. Historical commit messages describe ongoing controller and direction debugging, not a complete validation report. Secure wheels off the ground and keep a motor-power cutoff available; verify direction, neutral behavior, sensor calibration, and disconnect behavior before any course run.

No photos or competition measurements are invented. Existing backups and sensor experiments remain in place. [Licensing](LICENSE) covers multiple components rather than one blanket project license; retain upstream credit and confirm team contributions before reusing hardware assets.
