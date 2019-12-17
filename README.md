# gr-morse-code-gen
Generates Morse code from keyboard input. It is based on gnuradio. The audio output can be fed to a Single Sideband (SSB) transmitter to generate a CW signal.

## Installation

See [What is GNU Radio?](https://wiki.gnuradio.org/index.php/What_is_GNU_Radio%3F) and [Installing GNU Radio](https://wiki.gnuradio.org/index.php/InstallingGR)

Note: These instructions are written for a Linux OS. Similar commands work for Mac and Windows.

1. Open a terminal window.
2. Change to the home directory.
```
cd ~/  
```
3. If you don't have 'git', enter<br> ```sudo apt install git``` depending on you specific Operating System.
4. Clone the repository:
```
git clone https://github.com/duggabe/gr-morse-code-gen.git
```

## Setting parameters

There are four variable boxes in the flowgraph: ```speed```, ```baud```, ```repeat```, and ```samp_rate```.  ```repeat``` is fixed at 1200.<br> ```baud``` and ```samp_rate``` are computed from the ```speed```.

* The ```speed``` variable in words per minute can be set to any of the following:
    * 2, 3, 4, 6, 8, 12, 16, or 24 (all are factors of 48). 

* The Signal Source (sidetone) audio output frequency can be set between 300 and 20,000 hz.

* The Audio Sink Device Name is dependent on the Operating System and the desired output port. If in doubt, try 'default' or 'hw:0'.

* __NOTE__: All of the program timing is based on the audio sample rate being set to 48 kHz.

## Operation

### Using gnuradio-companion

1. Open a terminal window.
2. Go to the gr-morse-code-gen folder.
```
cd ~/gr-morse-code-gen
```
3. Execute Gnu Radio Companion.
```
gnuradio-companion
```
4. Open MorseGen.grc from the file menu.
5. Set the ```speed``` to the desired rate.
6. Click 'Run' and 'Execute' or press F6.
7. A new window titled "Morse Code Generator" will open showing a tuning knob and a text input line.
8. Highlight the text input line.
9. Type a line of text to be sent and press 'Enter'. That line will be sent as Morse code.
10. Continue with additional text to be sent. Note that corrections can be made to the line of text before pressing 'Enter'. There is no need to stop execution of the program when switching from transmit to receive mode.
11. To Terminate the program, click the 'x' in the corner of the title line.

### Command line operation

If you don't need to change the speed, you can start the program as follows:

1. Open a terminal window.
2. Go to the gr-morse-code-gen folder.
```
cd ~/gr-morse-code-gen
```
3. Enter ```python3 MorseGen.py```
4. A new window titled "Morse Code Generator" will open showing a tuning knob and a text input line.
5. Highlight the text input line.
6. Type a line of text to be sent and press 'Enter'. That line will be sent as Morse code.
7. Continue with additional text to be sent. Note that corrections can be made to the line of text before pressing 'Enter'. There is no need to stop execution of the program when switching from transmit to receive mode.
8. To Terminate the program, click the 'x' in the corner of the title line.


## Credits

Thanks to Volker Schroer (dl1ksv) for the coding of the Message Edit block as the input device.