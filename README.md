# Super Wave Blaster
The Super Wave Blaster is a backpack adapter for converting the digital audio signals from the Super Nintendo DSP chip to standardized I2S protocol for use with the PCM5102 DAC module available from places like Amazon and Aliexpress. It can be installed as a dedicated analog output by replacing the RF modulator or as a discrete mod tapping into the SNES audio mixing opamp for output through the AV multiport cable. 

## Digital to Analog Conversion
The SNES DSP generates audio at 32k / 16bit so why upgrade with a DAC that is compatible with 192k / 24bit? A lot of the difference can be found in the analog circuitry of the DAC along with tigher sample rate clocking. Since the PCM5102 is capable of 192k / 24bit operation the analog circuitry is designed for much lower noise and more harmonic accuracy. This along with modern clocking results in less harmonic distortion which cannot be measured by frequency charts alone. This means that conversion even at 32 k / 16bit sounds better as it is a more accurate representation of the source sound. 

It can be difficult to summarize the differences in words, but in my experience the upgraded DAC is more detailed and heightens the stereo field / depth of the sound. Sound and music is more 3D with greater clarity of the bass and high frequency perception. 

## Audio Mixing Circuit
The original audio mixing circuit in the SNES can have a huge impact on the quality of the sound. For the earlier models, a LM324 opamp is used to combine the audio channels of the DSP, cartridge, and expansion port into one stereo / mono output for the AV multiport and RF module. However, the LM324 is a general purpose opamp and not designed for audio. In my testing this opamp can roll off much of the high frequencies of the audio, even affecting the original DAC. For this reason I recommend replacing the LM324 with a TI TLV2374IDR if using the Super Wave Blaster in the AV multiport circuit. This replacement is not a requirement for this mod, but I found most of the benefits of the Super Wave Blaster are negated when using the original LM324. This does not affect the sound if using the Super Wave Blaster dedicated audio output when replacing the RF modulator. 

The RGB and later revisions of the SNES replaced the LM324 with a proprietary IC called the S-Mix chip. This chip is not pin compatible with the LM324 so it cannot be swapped with the TLV2374IDR. Testing is still being done with this audio circuit to determine whether it should be replaced or not. For the purest sound on these later models it is recommended to use the dedicated audio jack of the Super Wave Blaster and replacing the RF modulator. Some external projects have already been built to replace the S-Mix with more off the shelf opamps, but these might benefit from adaption for the scope of this project. 






