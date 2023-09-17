# Growatt-SPH4600-SDM630_PW11_over_wifi_TCP_Modbus
At first : all the needed links to helpfully webside's and where to buy the components, please find at the end off the read me.

Here you will find some information of my started project, to get my Growatt SPH4600 (at carport) and my SDM630 (inside house) connected, 
while using 1x PE11-h (at SPH4600) and 1 x PW11 (because I had already, inside house) - PW11 and PE11-h comes from protoss (ebay).

The reason is, because I would'nt connect with RS485 / RJ45 cable, which is normal, both together.
I do not like open the ground, and make some hole's in the wall off my house.
Wifi is already there around, so that will work. The shinephone app do the job very well over wifi.

To get the PW11 run,  and to be able, to get the data / register entry from the SDM630 with the PW11, it was a bit tricky, but
now it work's fine: 

I checked the running read with QModMaster (#1)
How to setup the PW11, please find in a separate discription inside this project

First todo:  In "Option" you have to put in the IP from the PW11 and the port (502 is recommend),
and connect to the PW11 

![image](https://github.com/tkbi/Growatt-SPH4600-SDM630_PW11_over_wifi_TCP_Modbus/assets/14960501/384aea4b-b9be-405b-b315-d575f531ec00)

As next put in the needed configuration:

Chosen inputs:

Modbus Mode         :    TCP
Unit ID             :    2 (it is the ID from SDM630 and has to be set there, if not)

Scan rate(ms)       :    1000, is good for the first trial, later 5000 or 10000 is better, if you not need a realtime view.

Function Code       :    Read Input Registers (0x04>) - that is than call up the data from 30000

Start Adress        :    1 and DEC, will start read from 30001, because of 2 byte the next will be 30003, 30005 . . . ., put in "101 or 201" for the next registers up to 30381, if you like to check

Number of Registers :    88, because that show the main important values from the SDM630, just for the test

Data Format         :    Float, because the data are send as xxxx.xx

Precison            :    5, otherwise some datas are not read able "1234E+2"

![image](https://github.com/tkbi/Growatt-SPH4600-SDM630_PW11_over_wifi_TCP_Modbus/assets/14960501/547f7700-644e-4b6d-980c-6cfc0c4c78fd)

What do we see here: Registers from SDM630 (at Phase 2, I have the SPH4600 (6,72 wkp) connected, single phase.

![image](https://github.com/tkbi/Growatt-SPH4600-SDM630_PW11_over_wifi_TCP_Modbus/assets/14960501/4a7a91df-9b11-4bcf-9626-5ebc623a7945)

![image](https://github.com/tkbi/Growatt-SPH4600-SDM630_PW11_over_wifi_TCP_Modbus/assets/14960501/f85ad7ec-ddb4-4a07-a02e-919498efa202)





#1 https://sourceforge.net/projects/qmodmaster
