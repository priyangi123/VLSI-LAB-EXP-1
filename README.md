# VLSI-LAB-EXPERIMENTS
# AIM:

To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.

# APPARATUS REQUIRED:

vivado 2023.2

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

Logic Diagram :

Logic Gates:
![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/4fe42d1d-c46d-48d4-bfbe-57e1f26654b4)



Half Adder:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/99779024-41fc-4eda-a9e8-a6e1f4a18f3f)



Full adder:

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/d12912a7-0d70-4b99-8dfa-b6addce54289)


Half Subtractor:
![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/756c5ce4-fcb8-41a3-9ef9-cf1cc4102829)

Full Subtractor:
![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/ea5ad8fe-0a7c-423e-9fa4-f026a94b7ac8)

8 Bit Ripple Carry Adder

![image](https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/a1caae96-8c04-4a88-a298-c9c60fe7e4bb)





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
<img width="838" alt="LOGIC" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/4ef0e976-4225-4718-8db0-7f63002f5523">

HALF ADDER:

<img width="809" alt="ha (1)" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/bb43a856-8a94-4d17-a1c3-7dd65fca1478">


FULL ADDER:

<img width="1203" alt="fa (2)" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/cdc753f5-8032-4a31-bcfb-fd73a13ebb36">


HALF SUBTRACTOR:

<img width="785" alt="halfsub" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/0bd68dc2-6231-412c-8968-b6f631f35165">



FULL SUBTRACTOR:

<img width="1280" alt="fs" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/082b3e4f-3ba4-4134-95f3-852696b0058d">



8 BIT RIPPLE CARRY ADDER:

<img width="752" alt="RCA_8" src="https://github.com/priyangi123/VLSI-LAB-EXP-1/assets/165141104/ec18ae98-0a61-4314-af03-0debe9fd5319">







RESULT:

Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .

