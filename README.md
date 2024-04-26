# SIMULATION AND IMPLEMENTATION OF COMBINATIONAL LOGIC CIRCUITS

# AIM:

To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using vivado.

# APPARATUS REQUIRED:

vivado 2023

# PROCEDURE:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# LOGIC DIAGRAM

# ENCODER

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/4134d495-3573-49f9-add3-ff1063f97d56)

# DECODER

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/9c784739-7f95-4c1e-b6e1-a41b56f5cb20)

# MULTIPLEXER

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/01761ba8-b23e-4176-b6ac-6efcac83f537)

# DEMULTIPLEXER

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/d2479ec3-d8dc-4651-85ea-7b6983c750cc)

# MAGNITUDE COMPARATOR

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/7a34d9ab-1b6b-4e1a-97a5-91ed90106603)

# VERILOG CODE

# 8-3 ENCODER:

module encoder(d,a,b,c);

input [7:0]d; output a,b,c;

or (a,d[4],d[5],d[6],d[7]);

or (b,d[2],d[3],d[6],d[7]);

or (c,d[1],d[3],d[5],d[7]);

endmodule

# 3-8 DECODER:

module decoder(A,E,Y);

input [1:0]A;

input E;

output [3:0]Y;

assign Y[0]=~A[1]&~A[0]&E;

assign Y[1]=~A[1]&A[0]&E;

assign Y[2]=A[1]&~A[0]&E;

assign Y[3]=A[1]&A[0]&E;

endmodule

module decoder(A,Y);

input[2:0]A;

output[7:0]Y;

decoder_2_4 d1(A[1:0],~A[2],Y[3:0]);

decoder_2_4 d2(A[1:0],~A[2],Y[7:4]);

endmodule

# 8-1 MULTIPLEXER:

module multi(i,s,y);

input[7:0]i;

input[2:0]s;

output reg y;

always@(*)

begin

case({s[2],s[1],s[0]})

3'b000:y=i[0];

3'b001:y=i[1];

3'b010:y=i[2];

3'b011:y=i[3];

3'b100:y=i[4];

3'b101:y=i[5];

3'b110:y=i[6];

3'b111:y=i[7];

endcase

end

endmodule

# 1-8 DEMULTIPLEXER:

module demultiplexer(d1,d2,d3,d4,d5,d6,d7,d8,i,s0,s1,s2);

input i,s0,s1,s2;

output d1,d2,d3,d4,d5,d6,d7,d8;

wire w1,w2,w3;

not g1(w1,s0);

not g2(w2,s1);

not g3(w3,s2);

and g4(d1,w1,w2,w3,i);

and g5(d2,w1,w2,s2,i);

and g6(d3,w1,s1,w3,i);

and g7(d4,w1,s1,s2,i);

and g8(d5,s0,w2,w3,i);

and g9(d6,s0,w2,s2,i);

and g10(d7,s0,s1,w3,i);

and g11(d8,s0,s1,s2,i);

endmodule

# 2 BIT MAGNITUDE COMPARATOR :

module mag_com(a,b,gt,it,eq);

input [3:0]a,b;

output reg gt,it,eq;

always @(a,b)

begin

if(a>b)

begin

gt = 1'b1;

it = 1'b0;

eq = 1'b0;

end

else if(a<b)

begin

gt = 1'b0;

it = 1'b1;

eq = 1'b0;

end

else

begin

gt = 1'b0;

it = 1'b0;

eq = 1'b1;

end

end

endmodule

# OUTPUT WAVEFORM:

# ENCODER:

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/4306c3f7-f032-4061-834a-226bb7bd8073)

# DECODER:

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/491e588b-cd67-4c1a-b0be-0229f430f40e)

# MULTIPLEXER:

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/552c0428-3905-4c30-91b8-7a09b35f01cd)

# DEMULTIPLEXER:

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/1acb175d-8a4c-4f61-a492-ce8f474ad132)

# 2 BIT MAGNITUDE COMPARATOR:

![image](https://github.com/venkatesh2634/VLSI-LAB-EXP-2/assets/168212451/bf0eb5f7-4fac-447e-aca0-562567e3bb33)

# RESULT:

Thus the simulation and synthesis of ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, 2bit MAGNITUDE COMPARATOR using vivado is successfully completed and executed.





















