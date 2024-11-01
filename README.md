# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)
**Truthtable**
![Screenshot 2024-11-01 190101](https://github.com/user-attachments/assets/6a9aea0c-c36a-4b0d-93a5-9e07d3945e06)


**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**
![Screenshot 2024-11-01 190345](https://github.com/user-attachments/assets/d82e8068-3d39-41b9-8c4b-389c331340ee)

**Program:**
/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
Developed by:Harish Kumar S
RegisterNumber:24010415
*/
module unit22(sum,cout,a,b,cin);
output sum;
output cout;
input a;
input b;
input cin;

wire s1,c1,c2;

xor (s1,a,b);
and(c1,a,b);
xor(sum,s1,cin);
and(c2,s1,cin);
or(cout,c2,c1);

endmodule

module unit23 (df,bo,a,b,bin);
output df;
output bo;
input a;
input b;
input bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule

**RTL Schematic**
![Screenshot 2024-11-01 192317](https://github.com/user-attachments/assets/9131932c-265e-42eb-adb1-ae205e8d2a43)
![Screenshot 2024-11-01 191934](https://github.com/user-attachments/assets/5d940cf5-74b3-4b04-a1ae-2a02f6c8b5e5)
**Output Timing Waveform**
![Screenshot 2024-10-21 140205](https://github.com/user-attachments/assets/226a518d-e197-4250-a617-4a2ed00700cb)
![Screenshot 2024-10-21 141918](https://github.com/user-attachments/assets/0b998c47-1651-4608-9b6a-1e9e2ab6cf45)
**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



