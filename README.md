# MOS_Amplifier_Design

## HSpice Circuit :

![image](https://user-images.githubusercontent.com/50498845/213210450-f2927e7c-3882-454c-b417-a4375885c68e.png)

## Hspice Code 

---

```
*********//devices//*********
.option vntol=1p
.option nomod
.option post
.option accurate = 0.01

***//Resistant//***
Rref	2	1	24.3
R2		18	0	----
R3		100	18	----
R4		17	0	----
R5		100	17	----

***//Capacitors//***



***//Transistor//***
M1	10	5	8	0	mosn  w=14.4u  l=0.36u as=6.48p 	ps=25.08u ad=6.48p pd=25.08u
M2	13	6	8	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u

M3	12	5	7  	100	mosp  w=14.4u  l=0.36u as=6.48p 	ps=25.08u ad=6.48p pd=25.08u
M4	15	6	7	100	mosp  w=14.4u  l=0.36u as=6.48p 	ps=25.08u ad=6.48p pd=25.08u	
M5	11	18	10	100	mosp  w=14.4u  l=0.36u as=20.25p	ps=76.08u ad=20.25p pd=76.08u	
M6	14	18	13	100	mosp  w=14.4u  l=0.36u as=20.25p 	ps=76.08u ad=20.25p pd=76.08u	
M7	10	2	100	100	mosp  w=14.4u  l=0.36u as=67.5p 	ps=251.08u ad=67.5p pd=251.08u
M8	13	2	100	100	mosp  w=14.4u  l=0.36u as=67.5p 	ps=251.08u ad=67.5p pd=251.08u

M9	11	17	12	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u
M10	14	17	15	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u
M11	12	1	0	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u
M12	15	1	0	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u

M13	9	11	100	100	mosp  w=14.4u  l=0.36u as=67.5p 	ps=251.08u ad=67.5p pd=251.08u
M14	16	14	100	100	mosp  w=14.4u  l=0.36u as=67.5p 	ps=251.08u ad=67.5p pd=251.08u

M15	1	1	0	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u
M16	8	1	0	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u

M17	2	2	100	100	mosp  w=14.4u  l=0.36u as=67.5p 	ps=251.08u ad=67.5p pd=251.08u
M18	7	2	100	100	mosp  w=14.4u  l=0.36u as=67.5p 	ps=251.08u ad=67.5p pd=251.08u

M19	16	1	0	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u
M20	9	1	0	0	mosn  w=14.4u  l=0.36u as=6.48p		ps=25.08u ad=6.48p pd=25.08u


***//Voltage//***
VDD	100	0	1.8


***//Diff//***
Vin 
E1	
E2	


***//models//***



***//analysis//***
.op
.tran	1ps	10ms	START=0
.ac		dec	100		1		10000G
.pz		v(10)		Vin

.end
```
