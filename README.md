# SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

# Aim: 

To simulate and synthesis SR, JK, T, D - FLIPFLOPS, COUNTERS design using vivado..

# Apparatus Required:

vivado 2023.2

# Procedure:

STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

**LOGIC DIAGRAM**

# SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

# Verilog code:

module srff(clk,j,k,rst,q );

input s,r,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({s,r})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=1'bx;

endcase

end

end

endmodule

# Output:

 ![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/a0dfa2a9-eb35-4a11-a8a0-6abcde9e7b77)
 
# JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

# Verilog code:

module jkff(clk,j,k,rst,q );

input j,k,clk,rst;

output reg q;

always@(posedge clk)

begin

if(rst==1)

q=1'b0;

else

begin

case({j,k})

2'b00: q=q;

2'b01:q=1'b0;

2'b10:q=1'b1;

2'b11:q=~q;

endcase

end

end

endmodule

# Output:

 ![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/3c4466cb-7563-4a2a-902b-f0bae1506ab3)

# T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)

# Verilog code:

module tff(clk,reset,t,q);

input clk,reset,t;

output reg q;

always @(posedge clk)

begin

if(reset==1)

q=0;

else

begin

if(t==0)

q=q;

else

q=~q;

end

end

endmodule

# Output:

 ![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/c33c11c4-ae72-446d-ae75-6224b3a1319a)
 
# D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)

# Verilog code:

module tff(clk,reset,t,q);

input clk,reset,t;

output reg q;

always @(posedge clk)

begin

if(reset==1)

q=0;

else

begin

if(t==0)

q=q;

else

q=~q;

end

end

endmodule

# Output:

![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/1c5cff74-a60f-4574-b51d-e8cbac24481b)

# COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

# Verilog code:

# Up Down Counter

module updown(clk,rst,up_down,count);

input clk,rst,up_down;

output reg[3:0]count;

always@(posedge clk)

begin

if(rst==1)

count <= 4'b0000;

else if (up_down == 1'b1)

count <= count + 1'b1;

else

count <= count-1'b1;

end

endmodule

# Output:

![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/487edbf1-ca96-4c3d-ad64-3425c438436f)

# Mod10 Counter

module mod(clk,rst,count);

input clk,rst;

output reg[3:0]count;

always @(posedge clk)

begin

if(rst==1 | count==4'b1001)

count <= 4'b0000;

else

count <= count +1;

end

endmodule

# Ouput:

 ![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/34adac6f-1279-4dc7-b8fb-f77f221c089a)

# Ripple Counter

module ripplecounter(clk,rst,q);

input clk,rst;

output [3:0]q;

tff tff1(q[0],clk,rst);

tff tff2(q[1],q[0],rst);

tff tff3(q[2],q[1],rst);

tff tff4(q[3],q[2],rst);

endmodule

module tff(q,clk,rst);

input clk,rst;

output q;

wire d;

dff df1(q,d,clk,rst);

not n1(d,q);

endmodule

module dff(q,d,clk,rst);

input d,clk,rst;

output q;

reg q;

always@(posedge clk or posedge rst)

begin

if(rst)

q=1'b10;

else

q=d;

end

endmodule

# Output:

 ![image](https://github.com/riyamicheal/VLSI-LAB-EXP-4/assets/124061774/764b75f4-a98b-459b-a67e-03f9ad4cf628)

# RESULT:

Thus,the simulation and synthesis of SR,JK,T,D flipflops,counters by using vivado has been successfully excecuted and verified


