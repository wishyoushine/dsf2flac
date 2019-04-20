# dsf2flac
Updated conversion tool for DSD files

This tool is a fork from https://code.google.com/archive/p/dsf2flac/

Support conversion from dsf or dff to wav files via DoP. DSD256 is also supported by converting source dsf or dff to a DoP stream encapsulated in a wav file 705600hz 24 bit (flac does not support sample rates above 655350).

# Compiling

download zip or clone. Make directory "build" under dsf2flac root dir then:

ds2flac/build # cmake ..

and:

ds2flac/build # make

# FFmpeg DSD256 ADI2 DAC pipe example:

dsf2flac -d -w -i "pathtofile" -o -  | ffmpeg -i - -c pcm_s32le -f alsa iec958:CARD=DAC57750571,DEV=0

Well tested up to DSD256 dsf to DoP wav conversion with rme ADI 2 DAC.
