# Super Wave Blaster
The Super Wave Blaster is an mod for converting digital audio from the Super Nintendo / Famicom to I2S Digital Audio protocol for use with the PCM5102 DAC module. 

<img src='Images/kicad_3D.png' width=480>

The Super Nintendo uses the UPD6376 audio DAC in an EIAJ CD-350 digital audio format. This EIAJ standard uses 3 serial data lines which is similar to the modern digital audio standard called I2S. The main function of the the Super Wave Blaster module is to convert the EIAJ standard to I2S using a sequence of inverters and bit shifters to realign the digital data. 

The original design of this conversion circuit was inspired by this forum thread - https://www.diyaudio.com/community/threads/eiaj-to-i2s-converter-and-vice-versa.58564/. 

## Audio Mixing Circuit
It is recommended that the entire audio signal chain is upgraded. This includes the mixing opamps, transistors, and capacitors. This may even have a larger impact on the quality of the sound than replacing the DAC. Different revisions of the SNES may need different components and methods. 

### Mixing Opamp
An ideal drop in replacement opamp would be the OPA1652AID and OPA1654AIDR, or similar audiophile grade type opamp. The SHVC revisions with the module uses two dual-opamp LM2904's, and the GPM revisions uses a quad-opamp LM324. The later RGB revisions use the S-Mix chip which is not drop in compatible with the OPA16xx style opamps. A circuit board is being designed to replace the S-Mix chip with the OPA16xx footprint (coming soon). Replacing the opamp can result in lower noise and distortion, especially in the high frequency details. 

### Audio Transistors
After the mixing opamp, the audio passes through two C2412 transistors on Q16 / Q17 (not on S-Mix versions). These can be replaced by MMBT5088LT1G transistors which will provide a strong drive with cleaner high frequency detail. However, if using a OPA16xx opamp these transistors can be bypassed entirely for a more accurate and cleaner sound from the DAC. The transistors add a lot of coloration to the sound which can be used if preferred. It is likely these transistors were originally used to boost the current and drive when using the LM324 or equivalent mixing opamp. The OPA16xx series opamps should have enough drive for standard line level audio, but keep the transistors if lower impedance outputs are used like headphones or passive speakers. 

### Output Coupling Capacitors
Before the audio connects to the multiout AV connector it passes through 10uF electrolytic capacitors. I would recommend upgrading these to low ESR polymer caps. I used the Wurth Elektronik 875105240001 which are 10uF, 45 mOhms ESR, 4mm diameter. Pay attention to the cap size on your SNES revision as it may defer. 

## Bill of Materials
Mouser: https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=aabb15e1e3

## License
The hardware portions of this repository are licensed under the CERN OHL version 2, permissive.

https://ohwr.org/project/cernohl/-/wikis/uploads/819d71bea3458f71fba6cf4fb0f2de6b/cern_ohl_s_v2.txt





