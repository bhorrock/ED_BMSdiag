# ED BMSdiag
Retrieve battery diagnostic data from your smart electric drive EV.

 <p align="center">
 <img  src="https://raw.githubusercontent.com/MyLab-odyssey/ED_BMSdiag/master/pictures/ED_BMSdiag_example_data.png" />
 <p/>

## You need
An Arduino with CAN bus shield to connect to the diagnostics port (OBDII-connector) of your car. Get the hardware and use an appropriate cable for the physical connection. See the schematics for making your own cable.

<p align="center">
<img  src="https://raw.githubusercontent.com/MyLab-odyssey/ED_BMSdiag/master/pictures/Arduino%26CANbusShield.jpg" width="640"/>
<p/>

## Get started
* Download the repo-ZIP, then copy the files to your Arduino folder. The folder structure should look like this:
<p align="left">
<img  src="https://github.com/MyLab-odyssey/ED_BMSdiag/raw/master/pictures/Arduino_folder_structure.png" /><p/>

* Open the ED_BMSdiag.ino file and compile / upload it to the Arduino board.

Please see the [wiki](https://github.com/MyLab-odyssey/ED_BMSdiag/wiki) for further information.

## Usage (on your own risk!)
Connect the CAN shield to the OBDII-connector and power up the car.

This simple version will display the diagnostics via a serial USB connection. You need to open the serial monitor of the Arduino-IDE. Verify that the baud rate is set to 115200. **The readout will be started by entering a serial command / keystroke in the top input line.** You will get an text output of the current battery status.
<p align="center">
<img  src="https://raw.githubusercontent.com/MyLab-odyssey/ED_BMSdiag/master/pictures/Arduino%20-IDE_serial_monitor.png" />
<p/>

## Version history
version  | comment
-------- | --------
v0.38    | New readings and stability improvements
         | ... read HV-Battery voltage even with contactors open
         | ... get HV-DC-Isolation in kOhm (reliable with contactors closed)
         | ... get info about hardware- / software-revision of battery
v0.35a   | Bugfix to continue reading messages if one was skipped
         | ... show 0.00kW power instead of -300.00kW
v0.35    | Added new readouts
         | ... realSOC, current, power, time from BC
         | ... EXPERIMENTAL: initial capacity & loss
         | Changed data formatting and code cleanup
v0.31    | Fixed overflow in ODO calc.
         | ... no special ASCII-characters for int. support
v0.30    | Added more readout data and reformatted the output
         | ... ODO, 12V battery, HV-unit production date
         | ... temperatures of battery modules
         | ... # of cell at min, max (in individual cell data)
v0.24    | Overall improvements
         | ... added Doxygen compatible comments
         | ... added standard deviation calc.
         | ... changed formatting
         | Average.h (**please reload library**)
         | ... corrected vice versa cell mapping
         | ... overflow corrected
v0.21    | Waiting for serial init
         | Showing status of OBD port (CAN-Bus)
v0.2     | Initial Commit
         | Tested with Arduino R3 and Sparkfun CAN-Bus shield
