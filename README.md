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
3. If you don't have 'git', enter ```sudo apt-get git``` depending on you specific Operating System.
4. Clone the repository:
```
git clone https://github.com/duggabe/gr-morse-code-gen.git
```

## Setting parameters

There are four variable boxes in the flowgraph: ```speed```, ```baud```, ```repeat```, and ```samp_rate```. ```baud``` and ```samp_rate``` are computed from the ```speed```. ```repeat``` is fixed at 1200.

* The ```speed``` variable in words per minute can be set to any of the following:
    * 2, 3, 4, 6, 8, 12, 16, or 24 (all factors of 48). 

* The Signal Source (sidetone) audio output frequency can be set between 300 and 20,000 hz.

* The Audio Sink Device Name is dependent on the Operating System and the desired output port. If in doubt, try 'default'. __NOTE__: All of the program timing is based on the audio sample rate being set to 48 kHz.

## Operation

1. Open a terminal window.
2. Go to the gr-morse-code-gen folder.
```
cd ~/gr-morse-code-gen
```
3. Execute Gnu Radio Companion.
```
gnuradio-companion
```
4. Open MorseCode.grc from the file menu.
5. Set the ```speed``` to the desired rate.
6. Click 'Run' and 'Execute' or press F6.
7. A new window titled "Morse Code Generator" will open showing an oscilloscope trace of the keying signal. One "dit" time equals 1 / baud. E.g. 10 baud => 100 ms.
8. Highlight the terminal screen.
9. Type a line of text to be sent and press 'Enter'. That line will be sent as Morse code.
10. Continue with additional text to be sent. Note that corrections can be made to the line of text before pressing 'Enter'. There is no need to stop execution of the program when switching from transmit to receive mode.
11. To Terminate the program, enter Control-C followed by 'Enter'.