# Experiment-08- Encoders-and-decoders 
## AIM: 
To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
## HARDWARE REQUIRED:  
PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED:   
Quartus prime
## THEORY 

### Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
### Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
### Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
### Figure -04 8 to 3 Decoder implementation 

## Procedure

### Step 1:
Open Quartus II and select new project and choose the file location.
### Step 2:
Module Declaration. Module should have the file name.
### Step 3:
Input-Output Delecaration.
### Step 4:
Use assign to define the functionality of logic circuits.
### Step 5:
At the end give endmodule.
### Step 6:
Run the program and choose RTL viewer to get RTL realization.

## PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: SUDHAKAR K
RegisterNumber: 212222240107
```
### ENCODER
```
module ex08(A,B,C,D0,D1,D2,D3,D4,D5,D6,D7);
output A,B,C;
input D0,D1,D2,D3,D4,D5,D6,D7;
or(A,D4,D5,D6,D7);
or(B,D2,D3,D6,D7);
or(C,D1,D3,D5,D7);
endmodule
```
### DECODER
```
module ex08(A,B,C,D0,D1,D2,D3,D4,D5,D6,D7);
input A,B,C;
output D0,D1,D2,D3,D4,D5,D6,D7;
assign D0=(~A&~B&~C);
assign D1=(~A&~B&C);
assign D2=(~A&B&~C);
assign D3=(~A&B&C);
assign D4=(A&~B&~C);
endmodule
```
## RTL LOGIC  

### ENCODER
![ENCODER](https://github.com/Sudhakaroffical/Experiment-08-Encoders-and-decoders-/assets/118622513/421cd9ea-5b74-45ba-99e9-554fa809413a)



### DECODER
![DECODER](https://github.com/Sudhakaroffical/Experiment-08-Encoders-and-decoders-/assets/118622513/1fe1f4cb-f5ff-489f-af83-1ca4593aa089)




## TIMING DIGRAMS  

### ENCODER
![TIM EN](https://github.com/Sudhakaroffical/Experiment-08-Encoders-and-decoders-/assets/118622513/ab8c662c-92c9-4330-9f71-9368b2acd301)



### DECODER
![TIM DE](https://github.com/Sudhakaroffical/Experiment-08-Encoders-and-decoders-/assets/118622513/7501fd29-3739-4082-8438-f8a4837d59ed)



## TRUTH TABLE 

### ENCODER

![TRUTH EN](https://github.com/Sudhakaroffical/Experiment-08-Encoders-and-decoders-/assets/118622513/511514bf-d84c-40c9-8446-1d113eafc5c2)


### DECODER
![TRUTH DE](https://github.com/Sudhakaroffical/Experiment-08-Encoders-and-decoders-/assets/118622513/cc824586-114f-427e-8405-9585f9b9e203)


## RESULT
8 to 3 Encoder and  3to8 Decoder has been implemented by using verilog and its outputs are validated.
