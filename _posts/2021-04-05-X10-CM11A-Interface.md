---
categories:
  - Electronics
---
My old X10 [CM11A](http://kbase.x10.com/wiki/CM11A) is back up and working! This is the story:
I had an old male-RS232 to something adapter with the other end cut off. I striped the outer insulator off and discovered an outer shield, presumably ground, and one brown and one black wire.
I also had [these notes](https://lh3.googleusercontent.com/3Ly2EBkKP3Ju0IRfNoA2Kt7q1PeDDjdCyUuiW7rhq6Z-pa_PgI56-2UU-aceeE4Jx5Dxj4kav0BhXIQ8Ga6fEh0h1K7K_uVQ8RWITrmCw5HXZRBelM10NY4nTiPEZXlQVsfYaQS_0o4Dg0yJVPULJnD_F_tvzyl8AOYlX1W-5jYI-aT6fs3bykgWZsXW6ovnb-XvqCZYyykRYnCmdxxObTKTo7ZQo2lgZgDiSw0F_LArXrPK5fmgHIkkHzet4lxkKxt9n58brQuRdKjUqhretgE4-mM87PL80NRfRdvYU9z-ekmSiEKVNPKgiUqcTUCW-Ps5Q0n8M44FglneT4VntZJfy9doj-gSQj4BCnMMa8wnFwjmR5qZjrYmsDsIjlYPvc6pJK8khMRtWw-YLR3EzABI_BX1dfR_6KWDQbfhUlY39js6oYMBWOcn2oJIU3oh3EcPwXsaCbDA_vgRWkNIncmEQMKxMU1fOmM8hEDF3DQUBeZQDn-Vbjoh23rYHCHh7WMlj5T7BXdBUGM37B6V3Pru-FalTfav-YBhvEa7sO2w6r0HQVrksvvORbrsd4xp2USMAIrRcFIlRRARZnhB93yhNB-Biyk3hpmQiSY-cTXOwRYStKhcE905BjS7IqLnQdTKsGbUB5Cxyciovr86g8xJCdT94q6mpqm1Y1uCAdFHhIqVdoCY5Dn03K9hZof1WiVgc-4XL5oGrXfnug2bEGtl2g=w1000-no-tmp.jpg), and verified that the ground did indeed connect to pin 5, and that the brown and black wires connected to pins 2 and 3 respectively. Deciphering my earlier notes, the brown wire then should be SIN, the output of the X10 interface.
I had also learned previously that the CM11A would generated a stream of "A5"s after line power is reestablish. I put 2 NiMH batteries in the CM11a and 

It is an USB to RS232 interface using a MSP430G2553 Launchpad development board and a level converter module. I'm using it to interface to and program an old [CM11A](http://kbase.x10.com/wiki/CM11A) (X10 interface.)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ1Mzc4NjE1OCwxOTE1MTMxNDAzLDkzNz
AwNjEzOSw5NDAyNTcxMzJdfQ==
-->