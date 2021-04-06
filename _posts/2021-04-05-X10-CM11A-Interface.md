---
categories:
  - Electronics
---
My old X10 [CM11A](http://kbase.x10.com/wiki/CM11A) is back up and working! This is the story:
I had an old male-RS232 to something adapter with the other end cut off. I striped the outer insulator off and discovered an outer shield, presumably ground, and one brown and one black wire.
I also had [these notes](https://lh3.googleusercontent.com/3Ly2EBkKP3Ju0IRfNoA2Kt7q1PeDDjdCyUuiW7rhq6Z-pa_PgI56-2UU-aceeE4Jx5Dxj4kav0BhXIQ8Ga6fEh0h1K7K_uVQ8RWITrmCw5HXZRBelM10NY4nTiPEZXlQVsfYaQS_0o4Dg0yJVPULJnD_F_tvzyl8AOYlX1W-5jYI-aT6fs3bykgWZsXW6ovnb-XvqCZYyykRYnCmdxxObTKTo7ZQo2lgZgDiSw0F_LArXrPK5fmgHIkkHzet4lxkKxt9n58brQuRdKjUqhretgE4-mM87PL80NRfRdvYU9z-ekmSiEKVNPKgiUqcTUCW-Ps5Q0n8M44FglneT4VntZJfy9doj-gSQj4BCnMMa8wnFwjmR5qZjrYmsDsIjlYPvc6pJK8khMRtWw-YLR3EzABI_BX1dfR_6KWDQbfhUlY39js6oYMBWOcn2oJIU3oh3EcPwXsaCbDA_vgRWkNIncmEQMKxMU1fOmM8hEDF3DQUBeZQDn-Vbjoh23rYHCHh7WMlj5T7BXdBUGM37B6V3Pru-FalTfav-YBhvEa7sO2w6r0HQVrksvvORbrsd4xp2USMAIrRcFIlRRARZnhB93yhNB-Biyk3hpmQiSY-cTXOwRYStKhcE905BjS7IqLnQdTKsGbUB5Cxyciovr86g8xJCdT94q6mpqm1Y1uCAdFHhIqVdoCY5Dn03K9hZof1WiVgc-4XL5oGrXfnug2bEGtl2g=w1000-no-tmp.jpg), and verified that the ground did indeed connect to pin 5, and that the brown and black wires connected to pins 2 and 3 respectively. Deciphering my earlier notes, the brown wire then should be SIN, the output of the X10 interface.
I had also learned previously that the CM11A would generated a stream of "A5"s after line power is reestablish. I put 2 NiMH batteries in the CM11A and plugged it into line power. My oscilloscope showed the following:
![enter image description here](https://lh3.googleusercontent.com/5br0kafRTKbU-8XO9YBxnvFDl4j7mJcvWef0xYdj4dGSR-LUyWKLoc0dfAG5o6GSv12TEFiglZN_MgsXB7UIvikHeWcy1B3t5dul-jxkHRtcCJyqwLjjA-ZbHnzkvmKkqAkavqR0SusR0pu75bIqgBhTWjcdMDD-5b_mWhDNP0eOQpN2SOEDJjYxVVhSEusT0thThEH2lmfGEb4VtVMYM1xsgnvhKdFJDtkJ3P-TJs9NrK7HoeupeXnqPxkq5YYLrGHfnPoMiD1ohns4Jp75J7iN3rSbIjl3Cld7OzFqsybK8qPKrxUH2J36nAAGM1sioZKMt2bZVBEgY_lhmmeT1Vs6YjQ4T5dYZiuY_qaIFaKMpHd7TIJ0uq_b-NG4rX6g8qAkpZSzz1DrwMhAqunIqdJoYiURZmqCxWfboE1alqkQxfCdL56z1yqLkHshUutrHFOxyQfOpoP6MEdxFMQqGcn9qmoF732LBds0pUyV_kVsH7RDvgo5VNZ2zV5zeAz5Enr9zfAuOvI6Mg2nuXU3riCOcYawRicq0Fs912Q0iNIl6n8CmMVrXza-ycnMlHkfWbk6sPeOsIoc0HgSyo26hMrazceUOuvmnQWELVv5EaAC9YF-LY0S6J4sLAYGupQgJS8M9k5IgV0OM3ewoIMTFmuaP_ZFkfM23bNtI9YVDaLSSKgGdIhXNZA4rng9haOAQgVKx4G98ACWvD5uAC_ps88OEA=w800-no-tmp.jpg)
It was alive, but why was the waveform only from 0 to 6 volts? RS232 should be from -12 to 12 or similar.
Then I remember that the CM11A probably used the negative voltage on its input pin to generate the negative voltage on its output.
It is an USB to RS232 interface using a MSP430G2553 Launchpad development board and a level converter module. I'm using it to interface to and program an old [CM11A](http://kbase.x10.com/wiki/CM11A) (X10 interface.)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MDEyMjczNSwxOTE1MTMxNDAzLDkzNz
AwNjEzOSw5NDAyNTcxMzJdfQ==
-->