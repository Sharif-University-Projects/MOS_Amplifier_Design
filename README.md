# MOS_Amplifier_Design


## Hspice Code 

---

```
*********//devices//*********
.option vntol=1p
.option nomod
.option post
.option accurate = 0.01

***//Resistant//***
Rref	2	1	24.3k

R2		18	0	10k
R3		100	18	10k

R4		16	0	10k
R5		100	16	6.36k

R6		17	0	10k
R7		100	17	10k


***//Transistor//***
M1 		 8     3     6  	0     Nmos  w=0.36u  l=0.18u 
M2		 14	   4     6		0	  Nmos  w=0.36u  l=0.18u

M3 		 10    3     5  	100   Pmos  w=0.045u  l=0.18u 
M4		 12	   4     5		100	  Pmos  w=0.045u  l=0.18u 	
M5		 9	   18    8		100	  Pmos  w=9u	  l=0.18u 	
M6		 13	   18    14		100	  Pmos  w=9u	  l=0.18u	
M7		 8	   2     100    100	  Pmos  w=9u	  l=0.18u 
M8		 14	   2     100	100	  Pmos  w=9u	  l=0.18u
 	
M9		 9	   16    10		0	  Nmos  w=1.44u  l=0.18u	
M10		 13	   16    12     0	  Nmos  w=1.44u  l=0.18u
M11		 10	   17    11		0	  Nmos  w=1.44u  l=0.18u 	
M12		 12	   17    11		0	  Nmos  w=1.44u  l=0.18u

M13		 7	   9     100    100	  Pmos  w=0.25u  l=0.18u
M14		 15	   13    100	100	  Pmos  w=0.25u  l=0.18u
 
M15		 1	   1     0		0	  Nmos  w=147u  l=0.18u	
M16		 6	   1     0      0	  Nmos  w=147u  l=0.18u

M17		 2	   2     100	100	  Pmos  w=9u  l=0.18u 	
M18		 5	   2     100	100	  Pmos  w=9u  l=0.18u

M19		 15	   1     0      0	  Nmos  w=147u   l=0.18u
M20		 7	   1     0		0	  Nmos  w=147u   l=0.18u 	
M21		 11	   7     0		0	  Nmos  w=0.18u  l=0.18u	
M22		 11	   15    0      0	  Nmos  w=0.18u  l=0.18u

***//Voltage//***
VDD		 100		0		1.8

Vin 500	0	ac=1	sin(0	1u	1k	0	0	0)
E1	3	0	500	0	0.5
E2	4	0	500	0	-0.5

***//models//***
.model  Nmos    NMOS  LEVEL=1 vto=0.6  KP=0.25	NSUB=5000000G
+UO=280	TOX=3.4n	LAMBDA=0.2	GAMMA=0.45	PHI=0.9	LD=0.025u	CGDO=0.2n
+CJ=1.2m	CJSW=0.02n

.model  Pmos    PMOS  LEVEL=1 vto=-0.6  KP=0.08	NSUB=5000000G
+UO=90	TOX=3.4n	LAMBDA=0.2	GAMMA=0.4	PHI=0.9	LD=0.025u	CGDO=0.2n
+CJ=1.2m	CJSW=0.02n  

***//analysis//***
.op
.tran	1ps	10ms	START=0

.ac	dec	100	1	10000G

***.pz	v(10)	Vin
.end

```



```
*********//devices//*********
.option vntol=1p
.option nomod
.option post
.option accurate = 0.01

***//Resistant//***
Rref	2	1	29k

R2		18	0	10k
R3		100	18	13k

R4		16	0	10k
R5		100	16	6.36k

R6		17	0	10k
R7		100	17	11.68k

***Rt	9	8	0.1
***Et	500	0	9	8	0.1	

***//Transistor//***
M1 		 8     3     6  	0     Nmos  w=100u  l=0.18u 
M2		 14	   4     6		0	  Nmos  w=100u  l=0.18u

M3 		 10    3     5  	100   Pmos  w=1u   l=0.18u 
M4		 12	   4     5		100	  Pmos  w=1u   l=0.18u 	
M5		 7	   18    8		100	  Pmos  w=20u	  l=0.18u 	
M6		 15	   18    14		100	  Pmos  w=20u	  l=0.18u	
M7		 8	   2     100    100	  Pmos  w=2u	  l=0.18u 
M8		 14	   2     100	100	  Pmos  w=2u	  l=0.18u
 	
M9		 7	   16    10		0	  Nmos  w=10u   l=0.18u	
M10		 15	   16    12     0	  Nmos  w=10u   l=0.18u
M11		 10	   17    11		0	  Nmos  w=0.7u   l=0.18u	
M12		 12	   17    11		0	  Nmos  w=0.7u   l=0.18u

***M13		 7	   9     100    100	  Pmos  w=0.25u  l=0.18u
***M14		 15	   13    100	100	  Pmos  w=0.25u  l=0.18u
 
M15		 1	   1     0		0	  Nmos  w=147u  l=0.18u	
M16		 6	   1     0      0	  Nmos  w=147u  l=0.18u

M17		 2	   2     100	100	  Pmos  w=2u  l=0.18u 	
M18		 5	   2     100	100	  Pmos  w=2u  l=0.18u

***M19		 15	   1     0      0	  Nmos  w=147u   l=0.18u
***M20		 7	   1     0		0	  Nmos  w=147u   l=0.18u 	
M21		 11	   7     0		0	  Nmos  w=0.3n  l=0.18u	
M22		 11	   15    0      0	  Nmos  w=0.3n  l=0.18u

***//Voltage//***
VDD		 100		0		1.8

Vin1 3	0	ac=1	sin(0.714	5u	1k	0	0	0)
Vin 4	0	ac=1	sin(0.714	5u	1k	0	0	180)


Eo 500	0	7	15	1
Ro 7	15	10x

***E1	3	0	500	0	0.5
***E2	4	0	500	0	-0.5

***//models//***
.model  Nmos    NMOS  LEVEL=1 vto=0.6  KP=0.25	NSUB=5000000G
+UO=280	TOX=3.4n	LAMBDA=0.2	GAMMA=0.45	PHI=0.9	LD=0.025u	CGDO=0.2n
+CJ=1.2m	CJSW=0.02n

.model  Pmos    PMOS  LEVEL=1 vto=-0.6  KP=0.08	NSUB=5000000G
+UO=90	TOX=3.4n	LAMBDA=0.2	GAMMA=0.4	PHI=0.9	LD=0.025u	CGDO=0.2n
+CJ=1.2m	CJSW=0.02n  

***//analysis//***
.op
.tran	1ps	10ms	START=0

.ac	dec	100	1	10000G

.meas   tran   gain   max   par('db(vm(12))')

***.pz	v(10)	Vin
.end

```

![image](https://user-images.githubusercontent.com/50498845/213549886-5a83b067-a65f-40f7-9aa7-8756dddd5457.png)
