# ok, this is fun :)

# Setting up WSJTX with (tr)uSDX

This is just my experience. YMMV.  

* Get a legit (tr)uSDX
    * https://dl2man.de/where-to-buy-trusdx/

* Do everything here
    * https://dl2man.de/4-trusdx-manual/
    * For extra fun, dont do it all at once, so a little of it, and then fight with USB control, then go back
* Flash the firmware (I had success with the beta firmware)
    * https://dl2man.de/3b-trusdx-firmware/
    * in avrdudess 2.16, the programmer I choose was "Arduino for bootloader using STK500 v1 protocol)
    * configure the settings
* Get a micro-USB cable
    * try about a hundred micro-USB cables that you can find where you live. Check every box you have.
    * Using each of the cables test cat control in WSJTX
     * watch CAT control fail a billion times as you test every combination of setting and cable
* Try the following settings
    * Kenwood TS-480; Serial Port COM8; Baud Rate 115200; Data Bits Default; Stop Bits Default; Handshake None; Force Control Lines DTR (blank) RTS (blank); PTT Method CAT; Transmit Audio Source Front/Mic; Mode USB; Split Operation None;
* add RF chokes to the USB Cable
    * continue to test CAT control; observe that more is better
    * When I got to about 6 of various sizes of these, it seemed more consistant
        * Im not certain, but it may still not work 100% of the time; still monitoring
        * https://a.co/d/i8q1TmA
* Wonder why there is no data showing in WSJTX for noise level
    * RTFM: https://wsjt.sourceforge.io/wsjtx-doc/wsjtx-main-2.6.1.html#TRANSCEIVER
    * Turn AGC off in the (tr)uSDX menu
    * Observe noise level in WSJTX
