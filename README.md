# EMG Monitor
A wearable EMG monitoring sensor project.

EMGv1 will come soon:
![EMGv1](https://github.com/xit057/EMGMonitor/blob/master/hardware/circuit/img/EMGv1.png?raw=true)
## EMG measurement
Here are the Arduino code and GUI code for the real-time EMG measurement.
To run the codes:
1. Unzip the attached file and upload the ''v010219.ino'' to Arduino Nano 33 BLE Sense board.
2. Connect the  Arduino Nano 33 BLE Sense board to the laptop via USB and check the COM port number.
3. Make sure that there is a folder called ''rawdata'' in the same path as the ''arduinoGUI.py.''
4. Run the  ''arduinoGUI.py.'' and input your COM port number to the terminal like ''COM 6''.
5. Then you will see the real-time curve about raw-data and four features.

Note: 
1. This program will try to record every second's raw data to the ''rawdata'' folder as a .bin file.
2. When the program starts, it will clear all the old .bin files in the ''rawdata'' folder.
3. If you want to load the .bin data to python to do the offline process, you may need numpy.fromfile().


## Offline data processing
The 'readbin.py' in readdata folder can process the .bin datas in 'rawdata' folder and convert the results to .csv file.
The processing part include 4 feature detection model: AVR, RMS, MEF, MDF.
The FFT window length is 1s.

