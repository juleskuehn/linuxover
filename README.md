# linuxover
active crossover implementation with room(/speaker) correction

##purpose
passive crossovers make a lot of compromises.  with an active crossover, you amplify each speaker driver individually.  this means you can optimize the signal going into each speaker in both the analog and digital domains.

##my setup
i have a pair of infinity kappa 8 speakers from the late 1980's.  the hf drivers have been swapped out, so each speaker is composed of the following 4 drivers:
- infinity 12" cast-frame woofer
- infinity polygraph-k 5" mid-bass coupler --------------- their words, not mine
- dynaudio d52-af 2" soft-dome midrange
- hivi rt1c-a ribbon tweeter

respectively amplified by:
- tas5630 @ 300wpc
- tas5613 @ 150wpc
- tpa3116(x2) @ 100wpc
- tpa3116 @ 50wpc

##choosing a computer
this project was born out of desire to reuse computer parts i had lying around, while also fixing my speakers.  so i recommend you use whatever computer is available to you.

you CAN run this on a raspberry pi if you are willing to deal with having short FIR filters, high latency (~5ms), and low-bit depth (16).

with an intel core2duo (and hopefully on current arm boards) running linux-rt, i get ~1.5ms roundtrip latency.  192khz/32bit/64 samples buffer.  2 channels in, 8 channels out via ASUS Xonar HDMI/H6 pcie soundcard.

##how do you get sound in
- send (multichannel,lossless) audio over the network with zita-njbridge
- use analog inputs
- use sp/dif 2 channel inputs
- getting digital multichannel sound input is extremely difficult
