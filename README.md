# VLSI-LAB-EXPERIMENTS
AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.
APPARATUS REQUIRED:
vivado 2023.2

PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
Logic Diagram :

Logic Gates:

<img width="838" alt="LOGIC" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/4ef0e976-4225-4718-8db0-7f63002f5523">


Half Adder:

<img width="809" alt="ha" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/015bb0e6-9ee8-49f5-869e-b359a0d7c77b">



Full adder:

<img width="1203" alt="fa (2)" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/cdc753f5-8032-4a31-bcfb-fd73a13ebb36">



Half Subtractor:
<img width="785" alt="halfsub" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/0bd68dc2-6231-412c-8968-b6f631f35165">




Full Subtractor:
<img width="1280" alt="fs" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/082b3e4f-3ba4-4134-95f3-852696b0058d">





8 Bit Ripple Carry Adder

<img width="752" alt="RCA_8" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/ec18ae98-0a61-4314-af03-0debe9fd5319">




VERILOG CODE:

LOGIC GATES:
module logic(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate );

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

HALF ADDER:
module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule

FULL ADDER:
module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule

HALF SUBTRACTOR:
module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule

FULL SUBTRACTOR:
module full_sub(a,b,bin,diff,borrow);

input a,b,bin;

output diff,borrow;

wire w1,w2,w3;

xor g1(w1,a,bin);

and g2(w2,~a,b);

xor g3(diff,w1,bin);

or g4(borrow,w2,w3);

and g5(w3,~w1,bin);

endmodule

8 BIT RIPPLE CARRY ADDER:
module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule


OUTPUT:

LOGIC GATES:
![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/eda9ff28-2da1-4987-9532-df8e3921c3ff)

HALF ADDER:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/2e1f2cf2-76d5-48a2-b5b9-5201c05ddcca)

FULL ADDER:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/5b92cbaf-4bbe-480a-b2b9-d0e878f2be73)

HALF SUBTRACTOR:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/62aeddbf-7685-4a2b-bce1-cef520fea6d3)

FULL SUBTRACTOR:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/0e8ccb95-b89d-4a9b-8d90-40a6cc30ad92)


8 BIT RIPPLE CARRY ADDER:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/71bbdc5c-7996-4f55-baec-62281286a7d2)







RESULT:
Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .

