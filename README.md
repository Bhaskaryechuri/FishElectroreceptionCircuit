_Author: [Bhaskar Yechuri](bhaskar.yechuri@gmail.com), Engineering Technician & Research Assistant at the [Leitch Lab](https://www.zoology.ubc.ca/person/duncan-leitch), University of British Columbia - Vancouver (Last Updated: June 2021)_

# Aquatic Electroreception Circuit - Summary

The circuit described here is based loosely on the circuit demonstrated in [this paper](https://journals.biologists.com/jeb/article/205/23/3609/9206/Electroreception-in-juvenile-scalloped-hammerhead), where a set input signal can be sent out through one of four electrode pairs positioned on the bottom of a fish tank. In our circuit, a rotary switch is used by the experimenter to vary the electrode pair being activated, and a pair of potentiometers (variable resistors) is used to vary amount of current (i.e. the strength of the signal being sent across the electrodes). 

While the main circuit is quite simple, there is an addition to it (also depicted in the schematic file) that extends its functionality by indicating which of the four electrode pairs is active at a given time, by lighting up one of four LEDs. This is done by sensing the peak voltage being sent out through the electrodes and using that signal to turn LEDs on and off using a BJT (biopolar junction transistor) as a switch. This secondary circuit is best powered from a DC power source, independent from the signal being sent through the electrodes

This repository contains the schematic file (.sch) which shows the various component types used in the circuit and the way they are connected. It also contains a [video](https://drive.google.com/file/d/17aoE4caPd3qhUQ_ESQ56myHzBBdYeZDZ/view?usp=sharing) of the circuit in action to demonstrate its operation.

# Note for future development

The first prototype of this circuit was created by soldering through-hole components onto a proto-board. While this is sufficient for a proof-of-concept/early prototype, I recommend moving the majority (or all) of the circuit onto a PCB to minimize turnaround time, device size/portability, and chances for shorts or open circuits at soldering joints.

# User-Facing Aspects of the Circuit

The main parts of the circuit to be familiarized to the user are:

1. **Input Signal Port**: This is where the positive and negative terminals of the input signal will be connected.
1. **Electrode Connector Ports**: This is where the four pairs of electrodes suspended in the tank are connected to the circuit.
1. **Battery Power Port**: This is where the positive and negative terminals of the battery will be connected. The battery powers the LEDs and nothing else.
1. **LED Connector Ports**: This is where the 4 pairs of wires connecting the circuit to the LEDs will be plugged in. _NOTE: Make sure to correctly orient the positive and negative terminals of the LEDs, otherwise the LEDs will not light up._
1. **Rotary Switch**: The dial turned by the user to cycle through the electrode pairs in the tank. The switch has 4 positions, one for each electrode pair.

# Using the Circuit

The circuit is simple to use, assuming you are familiar with the operation of the circuit as demonstrated in the linked paper. Once you have set up your tank and underwater electrode pairs appropriates, follow these steps:

1. Connect the 8 electrode wires to the Electrode Connector Ports and ensure they are connected end-to-end using the continuity test feature on a multimeter (looks like a sideways Wi-Fi symbol on the multimeter, and will emit a beeping sound when the probes are touched together)
1. Connect the 9V battery to the Battery Power Port
1. Connect your input signal to the Input Signal Port, with an ammeter in series in order to monitor the amount of current being fed into the circuit
1. Use the potentiometers to adjust the current flowing through the circuit to your requirements
1. Use the indicator LEDs and rotary switch to cycle through the four electrode positions to ensure all four positions are connected and functioning as expected.

# Notes on Troubleshooting

* Peak voltage/amplitude of the input signal needs to be at least 5-6V if the battery voltage is 9V, otherwise the LEDs will not be triggered into lighting up
* Ensure that LED wires have been connected with the correct polarity, otherwise they will not light up
* If the current displayed in the ammeter increases suddenly, you feel the circuit heating up abnormally, or you see/smell smoke, unhook the battery and the input signal to locate the source of the problem and fix the issue before using it again. (This has not occurred during testing and the high resistance in the circuit means that it is unlikely to happen in the first place, but this principle is good to know when dealing with hand-soldered electrical systems!)
