
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG OOH
MOV TMOD, #20H
MOV TH1, #OFDH
MOV SCON, #50H
SETB TR1
MAIN LOOP:
MOV SBUF, #'B'
WAIT TI:
JNB TI, WAIT_TI
CLR TI
SJMP MAIN_LOOP
END

```
### (ii) Serial Port to Transfer a Message

```
ORG 0000
MOV TMOD, #20H
MOV THI, #OFDH
MOV SCON, #50H
SETB TRI
MOV A, #'G'
ACALL TRANS
HOV A, #'A'
ACALL TRANS
MOV A, #'צ
ACALL TRANS
MOV A, #E'
ACALL TRANS
MOV A, #E
ACALL TRANS
SJMP $
TRANS: MOV SBUF, A
WAIT: JNB TI, WAIT
CLR TI
RET
END

```

### OUTPUT:
<img width="1671" height="649" alt="Screenshot 2025-09-29 114403" src="https://github.com/user-attachments/assets/4dbce8d5-56bd-4bc5-85a4-32a04c724fc2" />

<img width="1909" height="882" alt="Screenshot 2025-09-30 133703" src="https://github.com/user-attachments/assets/42d41a4e-c118-4129-b3cd-9270bcc32c42" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
