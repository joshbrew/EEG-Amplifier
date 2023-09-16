## EEG Differential Amplifier

The main circuit here uses 4 low noise op amps to achieve EEG differential amplification. This should plug into any single ended ADC (or put your negative input to ground) to allow even as low as 10 bit EEG.

The reference design is for 1000x gain at 5v with a 2.5v voltage reference. All calculations are in the pdf for your needs. If using battery power a voltage divider should work for a reference. 

![amp](./amp.PNG)
![amp2](./ampSMT.PNG)

Design reference by Abishek Parikh.

EAGLE drawings by Josh Brewster. Works in free EAGLE or you can import them elsewhere usually.

TL08XH is the latest for this design.
