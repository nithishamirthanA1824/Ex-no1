# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="407" height="724" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,1234H
ADD AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   : 12       |       1204   :    24     |
|                         |                          |
|         1200  :  34     |       1205  :    68      |
|                         |                          | 
|       1202   :  12      |                          | 
|       1203  :  34       |                          |
 -----------------------------------------------------       
 
#### Manual Calculations

<img width="1000" height="800" alt="WhatsApp Image 2026-05-13 at 11 21 29 AM" src="https://github.com/user-attachments/assets/c9d039f7-268c-4f05-811f-1fdbbaed70f1" />


---
<img width="400" height="250" alt="Screenshot 2026-05-13 112507" src="https://github.com/user-attachments/assets/a84ee12a-7a8b-4860-a405-286f30c4807f" />

## OUTPUT IMAGE FROM MASM SOFTWARE

## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="350" height="400" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   : 12       |       1204   :    00    |
|                         |                          |
|         1200  :  34     |       1205  :    00     |
|                         |                          | 
|       1202   :  12      |                          | 
|       1203  :  34       |                          |
 -----------------------------------------------------     

#### Manual Calculations

<img width="1000" height="800" alt="WhatsApp Image 2026-05-13 at 11 21 28 AM (2)" src="https://github.com/user-attachments/assets/88cb551b-0417-425a-8b5d-38475b4e3ec1" />


<img width="400" height="200" alt="Screenshot 2026-05-13 112605" src="https://github.com/user-attachments/assets/f3d4f25d-2694-40d1-ab47-6877c3e18ca3" />

---


## OUTPUT SCREEN FROM MASM SOFTWARE

## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="300" height="400" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   : 12       |       1204   :    44    |
|                         |                          |
|         1200  :  34     |       1205  :    51     |
|                         |                          | 
|       1202   :  12      |       1206 :    97       | 
|       1203  :  34       |        1207 :   0A       |
 -----------------------------------------------------     


#### Manual Calculation
<img width="1000" height="600" alt="WhatsApp Image 2026-05-13 at 11 21 28 AM (1)" src="https://github.com/user-attachments/assets/ac659387-29da-4178-a5a4-68dd48f3c9e9" />
s

(Add your calculation here)
<img width="300" height="150" alt="Screenshot 2026-05-13 112656" src="https://github.com/user-attachments/assets/c1eedf8e-bfe0-432a-bbad-c1d7c34673d4" />

---

## OUTPUT SCREEN FROM MASM SOFTWARE

## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   : 12       |       1204   :    01    |
|                         |                          |
|         1200  :  34     |       1205  :    00     |
|                         |                          | 
|       1202   :  12      |       1206  :00            | 
|       1203  :  34       |                          |
 -----------------------------------------------------     


<img width="500" height="450" alt="WhatsApp Image 2026-05-13 at 11 21 28 AM" src="https://github.com/user-attachments/assets/264e3953-1c62-4517-a24e-2a7d0a1225c7" />


<img width="350" height="150" alt="Screenshot 2026-05-13 112628" src="https://github.com/user-attachments/assets/db0c9d51-5819-40bf-b6fd-14f9f862a934" />




## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

