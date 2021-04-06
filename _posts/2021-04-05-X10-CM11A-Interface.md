---
categories:
  - Electronics
---
My old X10 [CM11A](http://kbase.x10.com/wiki/CM11A) is back up and working! This is the story:

I had an old male-RS232 to something adapter with the end cut off. I stripped off the outer insulator and discovered an outer shield, presumably ground, and one brown and one black wire.
I also had [these notes](https://lh3.googleusercontent.com/3Ly2EBkKP3Ju0IRfNoA2Kt7q1PeDDjdCyUuiW7rhq6Z-pa_PgI56-2UU-aceeE4Jx5Dxj4kav0BhXIQ8Ga6fEh0h1K7K_uVQ8RWITrmCw5HXZRBelM10NY4nTiPEZXlQVsfYaQS_0o4Dg0yJVPULJnD_F_tvzyl8AOYlX1W-5jYI-aT6fs3bykgWZsXW6ovnb-XvqCZYyykRYnCmdxxObTKTo7ZQo2lgZgDiSw0F_LArXrPK5fmgHIkkHzet4lxkKxt9n58brQuRdKjUqhretgE4-mM87PL80NRfRdvYU9z-ekmSiEKVNPKgiUqcTUCW-Ps5Q0n8M44FglneT4VntZJfy9doj-gSQj4BCnMMa8wnFwjmR5qZjrYmsDsIjlYPvc6pJK8khMRtWw-YLR3EzABI_BX1dfR_6KWDQbfhUlY39js6oYMBWOcn2oJIU3oh3EcPwXsaCbDA_vgRWkNIncmEQMKxMU1fOmM8hEDF3DQUBeZQDn-Vbjoh23rYHCHh7WMlj5T7BXdBUGM37B6V3Pru-FalTfav-YBhvEa7sO2w6r0HQVrksvvORbrsd4xp2USMAIrRcFIlRRARZnhB93yhNB-Biyk3hpmQiSY-cTXOwRYStKhcE905BjS7IqLnQdTKsGbUB5Cxyciovr86g8xJCdT94q6mpqm1Y1uCAdFHhIqVdoCY5Dn03K9hZof1WiVgc-4XL5oGrXfnug2bEGtl2g=w1000-no-tmp.jpg) from before, and then verified (with a continuity tester) that the ground shield did indeed connect to pin 5, and that the brown and black wires connected to pins 2 and 3 respectively. Deciphering my earlier notes, the brown wire then should be SIN (serial in to host), the output of the X10 interface.

I had also learned previously that the CM11A would generated a stream of "A5"s after line power is reestablish. I put 2 NiMH batteries in the CM11A and plugged it into line power. My oscilloscope showed the following:
![enter image description here](https://lh3.googleusercontent.com/5br0kafRTKbU-8XO9YBxnvFDl4j7mJcvWef0xYdj4dGSR-LUyWKLoc0dfAG5o6GSv12TEFiglZN_MgsXB7UIvikHeWcy1B3t5dul-jxkHRtcCJyqwLjjA-ZbHnzkvmKkqAkavqR0SusR0pu75bIqgBhTWjcdMDD-5b_mWhDNP0eOQpN2SOEDJjYxVVhSEusT0thThEH2lmfGEb4VtVMYM1xsgnvhKdFJDtkJ3P-TJs9NrK7HoeupeXnqPxkq5YYLrGHfnPoMiD1ohns4Jp75J7iN3rSbIjl3Cld7OzFqsybK8qPKrxUH2J36nAAGM1sioZKMt2bZVBEgY_lhmmeT1Vs6YjQ4T5dYZiuY_qaIFaKMpHd7TIJ0uq_b-NG4rX6g8qAkpZSzz1DrwMhAqunIqdJoYiURZmqCxWfboE1alqkQxfCdL56z1yqLkHshUutrHFOxyQfOpoP6MEdxFMQqGcn9qmoF732LBds0pUyV_kVsH7RDvgo5VNZ2zV5zeAz5Enr9zfAuOvI6Mg2nuXU3riCOcYawRicq0Fs912Q0iNIl6n8CmMVrXza-ycnMlHkfWbk6sPeOsIoc0HgSyo26hMrazceUOuvmnQWELVv5EaAC9YF-LY0S6J4sLAYGupQgJS8M9k5IgV0OM3ewoIMTFmuaP_ZFkfM23bNtI9YVDaLSSKgGdIhXNZA4rng9haOAQgVKx4G98ACWvD5uAC_ps88OEA=w800-no-tmp.jpg)
It was alive! But why was the waveform only from 0 to 6 volts? RS232 should be from -12 to 12 or similar.

I sort of remembered that the CM11A used the negative voltage on its input pin to generate the negative voltage on its output. To test this, I fished out a new RS232 converter chip and [this note](https://lh3.googleusercontent.com/pw/ACtC-3fRqbOwYhAg9EuXhRdoCVjb2EJmCpPHutMtDdMWLWyNa1VRXgIfi36sf8gFG6BCd1bTIGDKEF8LYRiDyi6YF4W0c3WUOEtCWI0_XlX-CQzkQp6XZbo0eFmnTHI8xZwWo6cj2S0WA1Ighu5rPdga6uZPbA=w800-no-tmp.jpg). I connected +3.3V and Gnd to the RS232 converter module and connected the black wire to its RS232 output. Sure enough, now the A5 voltage levels on the brown wire reached rail-to-rail as desired:
![enter image description here](https://lh3.googleusercontent.com/DrAZ7TgaGMjGE7KgsVW6KGusOXwxWWByrj08KE7MKCIXcUhGCrHM05vVzQBRTk7VHzDQYbQoaqNMlB-usoLx06HXlegTTaCORGsd_hvDAyBUEQe5QhjjkvSP77BqJ1DRoJ4L5WamANIBkKHSSXqe7ZgXOVai3ktI80AU3gMr5eYJt8FcNuzft-FnU7y-DnVoJse2bHKXOkEPbGbZt1QI6uS8S1yAoGQgbMnSwO5Zw7S-saIB5OCPEmHEMuQlYCUWGDRjDfNW-F_JUA8TRAIjOa1T8j1MYSTI8Ee1wIc6_-SYrhKprBVVdzbQjqsm3EJWDWeAD7h23s3Zut--mEUWaQLTsTwraZUe4LFTrNlKhGiq3OSwXMIp0JAiAijMocAFpvIit10gg2JLtQ1AIsxulCd7MkHzkP72Dkhf-ghnGiGyTOjoB6z0wDkNLpMxuRXQxqyMsm4I2rmfm8bEKcEpzA534HGAWaXuQWRyDvLbPn9yG49EmACWXH_pBMpCeJ9kQPtC7D9qYST9ZgnTh1tKX6mgnL5tuxaH0M0WttQMu_4ZGsaKWI_pzihzql8BxRjh3iW6esMqAvRpLqGMK4_vWCfuwSOpGFtMTEgXTYb16nJuALw4WKLE6DVgJtalPP2TjpECTfXqJeDAD6TsY68ef2wN7194KHCO5PkFrZTpGU9ezYjQgf829AhI4Hr3m27_2RGyU9tMWNRDvxfqwUR4N4l9qQ=w800-no-tmp.jpg)

Next I soldered the brown wire to the RS232 side, and a green wire to the TTL-level output and verified that the "A5" was now inverted and level-shifted back to 3.3V.  This is so-called TTL-Serial.
![enter image description here](https://lh3.googleusercontent.com/pw/ACtC-3c0ff9Z0erJZt9l2oNy0rlKE9DrUwXVcbZ-70Rq9CQytdJZwNOgXTOL1Xv4hm-JbR_LyutD6TgWFTNUAtaanCt5wZj-E3w4GK9Vbfpk6U5coo9Og5lCeRoTPTch-_eVZTCXqzzDnREKAl-_dwpeJ_4Chw=w800-no-tmp.jpg)

Finally, I connected the MSP430G2553 Launchpad development board, with all the jumpers removed, and the RS232 module as shown, and tested that I could send data as well (with Putty).
![enter image description here](https://lh3.googleusercontent.com/pw/ACtC-3cwr0lRRSqNvyGN-tyxWq7NBPd8LqP3KT8Hmw1Rx7vZlUnERC_dM4UYFwzVRoZ4CBpJi3vtJEyWk0oBNbh2iy3zq-CUsEpR7veyRSPdmRB-qXQs1HlWYwJqQ6gfuwKcUzJ3Pfh8xv57sruhuq0vjYssUQ=w800-no-tmp.jpg)

Removing the jumpers isolates the development board's USB to serial emulator from the chip under development. Connecting serial in and serial out is a bit odd - the green jumper, receiving data for the host, is on the second row of pins. Putty must be set to connect on /dev/ttyACM0 at 4800.

Now I had to hope I could find some software that worked. I knew "Heyu" would work on Linux, but I never figured out how to use it to program macros. Instead, I tried another program more like the original, Active Home Vista.
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTI3NDczMjAyLC0xMDE1MjYzNjYyLC03OD
EzMzAwMDIsLTE5MDI5OTY4MywxOTAyMzY3MzQ3LDE5MTUxMzE0
MDMsOTM3MDA2MTM5LDk0MDI1NzEzMl19
-->