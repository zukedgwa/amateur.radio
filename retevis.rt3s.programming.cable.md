https://www.ebay.com/itm/184381660961 ; DMR Retevis RT3S Ham Radio DMR Dual Band TDMA Walkie Talkie 5W 2000mAh

I bought this months ago to play around with APRS.  I was never able to program this, so it sat there with me trying different things over a few months with no success.  It's summer road trip season, so i was hoping to play around with this on the road, so I really wanted to get this to work.

Ive had a terrible time trying different cables.  No matter what I did, I couldnt seem to get a "STM Device in DFU mode" in device manager.  I would always get "please check whether the USB is occupied or not connected" when I tried to connect via the software.  Argh!

Inspired by this, I started buying parts instead of premade cables.
https://www.miklor.com/COM/UV_ProgrCable.php

So basicaly we are trying to connect a Kenwood K1 type connector to USB
https://www.buytwowayradios.com/wp/wp-content/uploads/2/sites/2/images/K1-audio-connector.jpg

My first attempt at that was to use the USB CP2102 item there and a baofeng microphone cable.  That didnt work.  Continuity tester proves that the pins that were wired from the K1 connnector were just wrong for this usage.  TODO: Add actual

So the weird combo of 3.5mm and 2.5mm TRS jacks makes this a pain because there are so many options

So we have 3.5mm TRRS and 2.5mm TRRS
  * https://a.co/d/ig48xnW
    * T:1:Left:Red
    * R:2:Right:White
    * S:3:Ground:Black
  * https://a.co/d/89ZCiMB
    * T: PIN 1 - red wire is the left channel
    * R: PIN 2 - white wire is the right channel
    * R: PIN 3 - green wire is mic;
    * S: PIN 4 - black wire is ground

And on the USB side we have: 3v, TX, RX, GND, 5V for the connections.  There are only four that are part of the USB A side of the connection.
  * https://a.co/d/1qLUCxV
    * 1: 5V
    * 2:
    * 3:
    * 4:

So a ton of possible connections

The baofeng handset pinout was xxx and that didnt work at all, but of course I didnt know that until I hacked it all apart.  Very frustrating.  

So back to the basic cables.
 * https://github.com/radiodoc/uv-5r/blob/master/assets/images/kenwood-2pin-headset.svg

3.5MM TRRS. I think I only need TIP to USB to D+ (Pin 3)

2.5MM TRRS. 
* Tip to GND
* Ring to D- (Pin 2)

Still didnt work.

 Ok, so then i took a clue from some of the pictures and some of the things that Ive read.  The USB plug mentioned above creates a com port.  Usually something like 'Prolific PL-2303 USB to Serial adapter', but it depends on the chip in the USB to K1 adapter since most of them are a USB to Serial Port adapter that is then had the pinout for the radio and the K1 audio connector.  
 
 Thats not what we want. The RT3S chip actually just expects a USB connection.  We just want a USB data cable.  So i tried it out.  I cut the end off of a usb accessory that I wasnt using and stripped the end.

 I connected
 * 3.5mm Tip: Red: to USB 3: green
 * 2.5mm Sleeve: Black to USB 4: black
 * 2.5mm ring: white to USB 2: white

 And it worked!!!

 Using those connections I was able to use the Retevis software to program it.  

Using the same connections, I was able to follow the instructions to flash OpenGD77 and program that.  https://www.opengd77.com/viewtopic.php?t=2380

Once I knew what I was looking for I was able to find the following items that confirmed what I did.

https://dc2wk.schwab-intra.net/wp-content/uploads/2016/02/Tytera-MD380-USB-to-Cable-Pinout-Diagram-v2.pdf
http://www.radioamatoripeligni.it/i6ibe/rt3/cavo.jpg
    http://www.radioamatoripeligni.it/i6ibe/rt3/rt3.htm ; page in Italian
