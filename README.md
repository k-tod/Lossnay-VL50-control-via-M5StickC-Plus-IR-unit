# M5Stack Temperature and Humidity Control of Lossnay-VL50

This Arduino sketch is designed for an M5Stack device with temperature and humidity sensors. It allows you to control a fan based on the temperature and humidity readings. 
When the humidity is above a certain threshold, it turns the fan on to a high setting, and when the humidity is below that threshold, it switches to a low setting. 
The code also uses infrared (IR) signals to control the fan and a feedback loop implemented to check if the IR command was succesfull, via a Airflow sensor(Renesas FS1015)

## Hardware Requirements

- M5Stack device (specifically M5StickC+)
- Temperature and humidity sensor (SHT3X)
- Pressure sensor (QMP6988)
- Infrared (IR) sender
- FS1015(Airflow) sensor

## Libraries Used

- [M5StickCPlus](https://github.com/m5stack/M5StickC-Plus)
- [HeatpumpIR](https://github.com/ToniA/arduino-heatpumpir)
- [CountDown](https://github.com/RobTillaart/CountDown)
- [FS3000](https://github.com/sparkfun/SparkFun_FS3000_Arduino_Library/tree/main)

## Usage

1. Connect the required hardware components to your M5Stack device.

2. Upload this Arduino sketch to your M5AtomS3 device.

3. Make sure the Lossnay-VL50 is turned off.

4. Power On the M5AtomS3.

5. From this point on, M5AtomS3 setup will monitor the temperature and humidity.
   - When the humidity exceeds a certain threshold (65% in this example), it will activate the fan on a high setting via IR command. Otherwise, it will run the fan on a low setting.
   - When the user is changing the fan state manually, via the original remote, the M5AtomS3 setup will suppress automatic control for 5 minutes
   - User can increase the original threshold by pressing the M5AtomS3 Display button in range +0 .. +15% to compensate for natural humidity depending on the season

7. The display will show temperature, humidity, Raw Airflow value and fan status.

8. Adjust the thresholds and timings in the code as needed for your specific application.

## License

This code is provided under the [MIT License](LICENSE.md).
