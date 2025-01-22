# Super Wave Blaster
The Super Wave Blaster is an mod for converting digital audio from the Super Nintendo / Famicom to I2S Digital Audio protocol for use with the PCM5102 DAC module. 

<img src='Images/kicad_3D.png' width=480>

The Super Nintendo uses the UPD6376 audio DAC in an EIAJ CD-350 digital audio format. This EIAJ standard uses 3 serial data lines which is similar to the modern digital audio standard called I2S. The main function of the the Super Wave Blaster module is to convert the EIAJ standard to I2S using a sequence of inverters and bit shifters to realign the digital data. 

The original design of this conversion circuit was inspired by this forum thread - https://www.diyaudio.com/community/threads/eiaj-to-i2s-converter-and-vice-versa.58564/. 

## Audio Mixing Circuit
It is recommended that the entire audio signal chain is upgraded. This includes the mixing opamps, transistors, and capacitors. This may even have a larger impact on the quality of the sound than replacing the DAC. Different revisions of the SNES may need different components and methods. 

### Mixing Opamp
An ideal drop in replacement opamp would be the OPA1652AIDR and OPA1654AIDR, or similar audiophile grade type opamp. The SHVC revisions with the module uses two dual-opamp LM2904's, and the GPM revisions uses a quad-opamp LM324. The later RGB revisions use the S-Mix chip which is not drop in compatible with the OPA16xx style opamps. A circuit board is being designed to replace the S-Mix chip with the OPA16xx footprint (coming soon). Replacing the opamp can result in lower noise and distortion, especially in the high frequency details. 

### Audio Transistors
After the mixing opamp, the audio passes through two C2412 transistors on Q16 / Q17 (not on S-Mix versions). These can be replaced by MMBT5088LT1G transistors which will provide a strong drive with cleaner high frequency detail. However, if using a OPA16xx opamp these transistors can be bypassed entirely for a more accurate and cleaner sound from the DAC. The transistors add a lot of coloration to the sound which can be used if preferred. It is likely these transistors were originally used to boost the current and drive when using the LM324 or equivalent mixing opamp. The OPA16xx series opamps should have enough drive for standard line level audio, but keep the transistors if lower impedance outputs are used like headphones or passive speakers. 

### Output Coupling Capacitors
Before the audio connects to the multiout AV connector it passes through 10uF electrolytic capacitors. I would recommend upgrading these to low ESR polymer caps. I used the Wurth Elektronik 875105240001 which are 10uF, 45 mOhms ESR, 4mm diameter. Pay attention to the cap size on your SNES revision as it may defer. 

## LM324 / S-Mix - DAC Output Configuration
Depending on the opamp used, the DAC module will require different configurations. These can also be adjusted to taste. 

LM324 / OPA16xx - Keep JP1 and JP2 open, and do not populate the 10k resistors on R3 and R4. The gain is controlled by R7 and R8 and the feedback resistors on the opamp. Populating 24k resistors on R7 and R8 should create unity gain from the PCM5102A DAC. 

S-Mix - Close JP1 and JP2, populate 10k resistors on R3 and R4. Substitute a 470pf on C15 and C16, and do not populate R5 and R6. You can also use a 0ohm resistor on R7 and R8 if slightly less impedance is desired. The S-Mix has it's own gain network so the voltage divider on the output of the DAC module is required to avoid clipping and the audio signal being too hot. 

## Bill of Materials
Note that the mouser project will include components related to multiple revisions. Check and edit and change your cart accordingly. It may not include the correct components for your particular revisions. 

For the 0.1uF output coupling capacitors on the DAC module, use C0G (NP0) type over X5R / X7R for optimal quality. 

Mouser: https://www.mouser.com/Tools/Project/Details?projectGUID=576ace13-fcfc-4374-9011-b2b0ae4ebff9

## License
The hardware portions of this repository are licensed under the CERN OHL version 2 - Strongly Reciprocal.

https://ohwr.org/project/cernohl/-/wikis/uploads/819d71bea3458f71fba6cf4fb0f2de6b/cern_ohl_s_v2.txt





