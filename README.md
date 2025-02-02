# Room Temperature Controller

This project demonstrates a simple room temperature controller using an Arduino microcontroller. 

**Functionality:**

* **Temperature Sensing:** Reads temperature data from an analog temperature sensor connected to analog pin A0.
* **Temperature Conversion:** Converts the analog reading to a voltage value and then to Celsius.
* **Temperature Control:** 
    * If the temperature exceeds a set threshold (25°C in this example), an alarm is triggered (tone on pin 11) and a relay (connected to pin 13) is activated to control a cooling device (e.g., fan).
    * If the temperature is below the threshold, the alarm is deactivated and the relay is turned off.

**Hardware Components:**

* Arduino board (any compatible model)
* Temperature sensor (e.g., LM35)
* Relay module
* Piezo buzzer or speaker (for alarm)
* Jumper wires
* Breadboard (optional)

**Connections:**

* **Temperature Sensor:**
    - VCC to 5V 
    - GND to GND
    - Output to analog pin A0
* **Relay Module:**
    - IN to digital pin 13
    - VCC to 5V
    - GND to GND
* **Buzzer/Speaker:**
    - Positive to digital pin 11
    - Negative to GND

**Code Explanation:**

* **`setup()`:**
    * Initializes the serial communication for debugging.
    * Sets the pin modes for the analog input (A0), relay output (13), and buzzer output (11).

* **`loop()`:**
    * Reads the analog temperature sensor value.
    * Converts the analog reading to voltage and then to Celsius.
    * Checks if the temperature exceeds the threshold (25°C).
        * If true:
            * Activates the buzzer (tone) to sound an alarm.
            * Turns on the relay to activate the cooling device.
        * If false:
            * Deactivates the buzzer.
            * Turns off the relay.

**Note:**

* This can be further enhanced. 
* Consider adding features like:
    * Hysteresis to prevent frequent on/off cycles of the cooling device.
    * User-defined temperature thresholds.
    * Display the temperature on a serial monitor or an LCD.
    * Implement more sophisticated control algorithms (e.g., PID control).
