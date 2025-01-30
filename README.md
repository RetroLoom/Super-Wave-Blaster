# Super Wave Blaster
The Super Wave Blaster is an adapter for converting digital audio from the Super Nintendo / Famicom to I2S Digital Audio protocol for use with the PCM5102 DAC module. It can be installed as a dedicated analog output by replacing the RF modulator or as a discrete mod tapping into the SNES audio mixing opamp for output through the AV multiport cable. 

 <img src='Images/kicad_3D.png' width=480>
<img src='Images/mounted/wave-blaster-2025-01-18-102557_005.jpeg' width=280>
<img src='Images/mounted/wave-blaster-2025-01-18-105353.jpeg' width=600>

## Audio Mixing Circuit
The original audio mixing circuit in the SNES can have a huge impact on the quality of the sound. For the earlier models, a LM324 opamp is used to combine the audio channels of the DSP, cartridge, and expansion port into one stereo / mono output for the AV multiport and RF module. However, the LM324 is a general purpose opamp and not designed for audio. In my testing this opamp can roll off much of the high frequencies of the audio, even affecting the original DAC. For this reason I recommend replacing the LM324 with a TI TLV2374IDR if using the Super Wave Blaster in the AV multiport circuit. This replacement is not a requirement for this mod, but I found most of the benefits of the Super Wave Blaster are negated when using the original LM324. This does not affect the sound if using the Super Wave Blaster dedicated audio output when replacing the RF modulator. 

The RGB and later revisions of the SNES replaced the LM324 with a proprietary IC called the S-Mix chip. This chip is not pin compatible with the LM324 so it cannot be swapped with the TLV2374IDR. Testing is still being done with this audio circuit to determine whether it should be replaced or not. For the purest sound on these later models it is recommended to use the dedicated audio jack of the Super Wave Blaster and replacing the RF modulator. Some external projects have already been built to replace the S-Mix with more off the shelf opamps, but this might benefit from adaption for the scope of this project. 

## Bill of Materials
Please refer to the BOM CSV file included in the release section for any main circuit board components. There are additional parts that need to be used depending on the integration method used. All links provided below are for example sources.

### GY-PCM5102
This module is required and contains the main audio DAC. 

https://www.aliexpress.us/item/3256806195735532.html?spm=a2g0o.order_list.order_list_main.11.6fde1802Z6ukMr&gatewayAdapt=glo2usa
https://www.amazon.com/dp/B07Q9K5MT8?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_1

### Texas Instruments TLV2374IDR 
Recommended for replacing the LM324 for higher fidelity audio in earlier revisions of the SNES. This might also improve the original DAC without the use of the Super Wave Blaster. This is not an option for replacing S-Mix chip in RGB+ revisions. 

https://www.mouser.com/ProductDetail/595-TLV2374IDR

### PJ-392 Audio Jack Variation
Required for mounting the Super Wave Blaster with RF modulator replacement integration. This jack conveniently solders to 3 pin headers and allows the module to be bolt mounted to the SNES shell. These can be found in packages from AliExpress and Amazon. 

https://www.aliexpress.us/item/3256806131431383.html?spm=a2g0o.order_list.order_list_main.131.4fbe1802ShfGCQ&gatewayAdapt=glo2usa

### M6 x 12 x 1 Washer
A washer is required to tightly mount the PJ-392 to the shell.

https://www.aliexpress.us/item/2255800098588607.html?spm=a2g0o.order_list.order_list_main.95.4fbe1802ShfGCQ&gatewayAdapt=glo2usa

### 4-pin 2.54mm Pitch Round Hole Pin Headers
For mounting to the RF modulator footprint, standard 2.54mm pin headers that are listed in the circuit BOM can be used but might require attention to the length of the pins when soldering. The header does not sit flush with the PCB when mounted correctly using the PJ-392. This works totally fine, but using 4 pole machined round hole pin headers with a socket may have been alignment and allows for easy removing and swapping of the module if needed. (Note: This is currently untested, but assumed as working. Will confirm once headers are received.)

Both male and female 4-pin sets are recommended.

https://www.amazon.com/dp/B07BS126FK?ref=ppx_yo2ov_dt_b_fed_asin_title
https://www.aliexpress.us/item/3256806486942369.html?spm=a2g0o.order_list.order_list_main.193.4fbe1802ShfGCQ&gatewayAdapt=glo2usa

### Other
Use your own preferred wiring for this project. I use dupont connectors and ribbon cables to make most of my connections with the board, but all wires can be soldered directly to the header pads if decided. For analog audio signals I recommend using thicker gauged and low resistance cables.

## Support the Developer
This project is brought to you free and open source, but it is not free to develop. If you like this project please consider supporting this and future developments. 

https://www.patreon.com/RetroLoom

## License
The hardware portions of this repository are licensed under the CERN OHL version 2, permissive.

https://ohwr.org/project/cernohl/-/wikis/uploads/819d71bea3458f71fba6cf4fb0f2de6b/cern_ohl_s_v2.txt





