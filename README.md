
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include<reg51.h> 
void main(void) 
{ 
TMOD=0X20;//TIMER 1,MODE 2 
TH1=0XFA; 
SCON=0X50; 
TR1=1; 
while(1) 
{ 
SBUF='s'; 
while(TI==0); 
TI=0; 
} 
}

```
### (ii) Serial Port to Transfer a Message

```
#include<reg51.h> 
void main(void) 
{ 
unsigned char msg[]="Srikanimozhi"; 
unsigned char i; 
TMOD=0X20;
TH1=0XFA; 
SCON=0X50; 
TR1=1; 
for (i=0; i<17;i++) 
{ 
SBUF= msg[i]; 
while(TI==0); 
TI=0; 
} 
while(1); 
} 



```

### OUTPUT:
![WhatsApp Image 2025-11-11 at 20 58 46_d32d8ef6](https://github.com/user-attachments/assets/1e657824-9081-4804-ba98-cb86f12aca89)
![WhatsApp Image 2025-11-11 at 21 05 14_967d9580](https://github.com/user-attachments/assets/60e9dbee-c30e-4ebd-ba67-31574a10a57b)

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
