<h1>EOS26/EOS34 Host Board Instructions:</h1>

Follow these instructions in order. In order to prevent damage to the chips, you must make sure the voltages are set prior to installing a chip board.

<h2>Adjustments Before Installing Chip Board</h2>

Solder a 90-degree 0.1" Molex connector with locking tab in position P1. Note that this connector should be installed upside-down to provide good clearance to the SMA connectors on the chip board and match the polarity of the FPGA control board:

![](doc/PCBA_molex_90deg_connector_installed.jpg)

Install a power cable between host board and control board. A 5V external power supply may also be used (Note: J1 and J2 are connected in parallel with P1, allowing pin-type test leads to be used instead of a Molex connector):

![](doc/PCBA_molex_power_cable_installed.jpg)

Probe between TP17 ("HVDD") and TP29 ("GND"). Adjust potentiometer R8 (nearest one to the HVDD test point) to set the desired heater voltage. 1.35V is the maximum safe voltage for EOS34 source ring heaters. 1.90V is the maximum tested voltage for EOS34 filter ring heaters. Note that heater currents will also depend on VDD since this rail drives the gates of the low-side choppers.

![](doc/PCBA_measure_adjust_HVDD.jpg)

Probe between TP14 ("DVDD") and TP29 ("GND"). Adjust potentiometer R7 (nearest one to the DVDD test point) to set DVDD to 1.80V.

Probe between TP12 ("VDD") and TP29 ("GND"). Adjust potentiometer R6 (nearest one to VDD test point) to set VDD to 1.00V (VDD can range from 0.90V to 1.20V, higher VDD leads to higher heater currents).

Probe between TP10 ("AVDD") and TP29 ("GND"). Adjust potentiometer R5 (nearest one to AVDD test point) to set AVDD to 1.20V.

Probe between TP5 ("VPD") and TP29 ("GND"). Adjust potentiometer R2 (also labeled "VPD") to set VPD to the desired cathode voltage on the photodetector rings. Higher voltage leads to greater responsivity, but increased dark current.

Probe between TP20 ("VREF0") and TP29 ("GND"). Adjust potentiometer R12 (also labeled "VREF0") to set VREF0 to 0.30V. This sets an interval voltage reference in the source ring tuning controller ADC.

Probe between TP21 ("VREF1") and TP29 ("GND"). Adjust potentiometer R11 (also labeled "VREF1") to set VREF1 to 0.60V. This sets an interval voltage reference in the source ring tuning controller ADC.

Probe between TP25 ("VREF2") and TP29 ("GND"). Adjust potentiometer R10 (also labeled "VREF2") to set VREF2 to 0.90V. This sets an interval voltage reference in the source ring tuning controller ADC.

Install jumpers onto the top positions of J5 ("HVDD"), J4 ("VDD"), and J3 ("AVDD/OVDD"). This routes power to EOS34 circuits (as opposed to EOS26):

![](doc/PCBA_install_jumpers_for_eos34.jpg)


<h2>Adjustments After Installing Chip Board</h2>