## EEG Differential Amplifier

The main circuit here uses 4 low noise op amps to achieve EEG differential amplification. This should plug into any single ended ADC (or put your negative input to ground) to allow even as low as 10 bit EEG.

The amps cost 10 cents from TI, not including the PCB which will vary.

The reference design is for 1000x gain at 5v with a 2.5v voltage reference. All calculations are in the pdf for your needs.

### Resources
- [Differential Amp BOM](https://docs.google.com/spreadsheets/d/1rzFOKtwm5F1gYTblCt51H4664hxHK5iFGmpR6K0Omsg/edit?usp=sharing)
- [Gain Amp BOM](https://docs.google.com/spreadsheets/d/1fu1xdZPcOAWwaKk6sFUOHw02OROvW1wCZvjth2xU8xA/edit?usp=sharing)
- [Design reference](https://github.com/joshbrew/EEG-Amplifier/blob/main/EEG_Active_electrode_design.pdf) by Abishek Parikh. 
Other info pulled from datasheets.

Note my previous OPA202 config was incorrect. And use this formula for calculating the bandpass: 
<table>
  <tr>
    <td>
      <img width="200px" src="https://github.com/user-attachments/assets/0b480666-d63d-422c-8c59-731e171d507b"><br/>
      In our config, + is our reference <br/> 
      (e.g. ear for EEG or opposite wrist for ECG)
    </td>
    <td>
      <img width="200px" src="https://github.com/user-attachments/assets/a81dac36-3ecf-41a9-b8cb-d12a59414333">
    </td>
    <td>
      Gain = R2 / R1
    </td>
  </tr>
</table>


### OPA4202ID/TL084CDR/TL084OD (or compatible SOIC14) SMT mount.
![amp2](./images/ampsmt.PNG)
OPA4202ID is more expensive but MUCH better quality, with better input impedance (3TΩ) and a 9nV/sqrt(Hz) noise density starting at 0.1Hz. The TL084's spectral noise doesn't bottom out until near 1kHz.

### 4mm Snap Button Electrode Mountholes
![amp2mount](./images/ampsmtmounthole.PNG)
![amp2mountCast](./images/ampsmtmountholecast.PNG)
Sized for Florida Instruments reusable plastic snap electrodes.

### TL084HCN (A,B,H, etc) Thruhole amp (for DIY)
![amp](./images/ampthroughole.PNG)

### OPA4202IPW or OPA4377 (or  compatible TSSOP14) SMT mount.
![amp3](./images/ampsmtOPA4377.PNG)

### Schematics
![schem](./images/schematic.PNG)
The BioAmp EXG Pill has a different layout you can check out. Same chipset.

### Noise vs Measured Bandwidth on OPA4202
![calcs](./images/noisecalc.PNG)
Note: Noise calcs are probably inaccurate. Lower frequencies have higher noise density. Adjust bandpass accordingly.

TL084 noise density:
![density](./images/tl084noisedensity.PNG)

OPA4202 noise density:
![density2](./images/opax202noisedensity.PNG)

OPA4202 or OPA4377 are about a dollar. I think the 4202 is better based on the noise.

## Also included in CAD/singular_amps

Single and Dual OPA202/OPA2202 gain amplifiers. E.g. for pre-amplification. Great low frequency noise density. 
![gain](./images/InvertingAmp.PNG)


### OPA202 (or pin compatible) VSSOP8 package (or pin compatible)
![smtgain](./images/singleamp_SMTr2.PNG)

### OPA202 VSSOP8 package with 4mm electrode mount
![smtgain2](./images/singleampSMTMountr2.PNG)

### OPA202 SOIC8 package and thruhole resistors/capacitors (easier to hand solder)
![smtgain3](./images/singleampThrur2.PNG)

### OPA202 SOIC8 package thruhole with 4mm electrode mount
![smtgain4](./images/singleampThruholeMountr2.PNG)

EAGLE drawings by Josh Brewster. Works in free EAGLE or you can import them elsewhere usually.

Best prices are on TI.com just FYI...

Free source! Definitely question my circuitry before you use it.
