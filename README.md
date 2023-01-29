# EXPERIMENT-08
# ENCODER AND DECODER 

## AIM : 
To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
## HARDWARE REQUIRED :
- , Cyclone II 
- USB flasher
## SOFTWARE REQUIRED : 
- Quartus prime
## THEORY :

### ENCODER :
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
### Figure -01 3 to 8 Encoder
 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
### Figure -02 3 to 8 Encoder implenentation

### DECODERS 
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

## PROCEDURE :
```
1. Create module encoder and decoder.

2. Get inputs and outputs for encoders and decoders.

3. perform or operation for encoder and and logic for decoders.

4. perform RTL LOGIC and get waveform.

5. End the module.

```
## PROGRAM :
```python
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: MIDHUN AZHAHU RAJA P
RegisterNumber:  22008311
```

### ENCODER :
```python
module coder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or (a,d4,d5,d6,d7);
or (b,d2,d3,d6,d7);
or (c,d1,d3,d5,d7);
endmodule
```
### DECODER :
```python
module decoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```



## RTL LOGIC :

### RTL LOGIC  FOR ENCODER :

![214280703-de7afeaa-ebbd-4db0-a384-9dd087de7e88](https://user-images.githubusercontent.com/118054670/215304037-2705ecc3-c26a-45a9-b2ac-233443b70f93.png)

### RTL LOGIC  FOR DECDER :

![rtl decoder](https://user-images.githubusercontent.com/118054670/215304052-cafb977e-34da-4fe4-9af1-51a35f3236d9.png)

## TIMING DIGRAMS  :

### TIMING DIGRAMS FOR ENCODER :

![encode timing](https://user-images.githubusercontent.com/118054670/215304116-440c9302-0f86-4512-a8d3-0508421a2807.png)

### TIMING DIGRAMS FOR DECODER :

![decode timing](https://user-images.githubusercontent.com/118054670/215304134-3e3b1e17-a203-4b08-9902-f46a79ac8a78.png)


## TRUTH TABLE :

### TRUTH TABLE FOR ENCODER :

![encode table](https://user-images.githubusercontent.com/118054670/215304183-2c6eff6b-c566-4fd5-b2cc-5693193948d5.png)

### TRUTH TABLE FOR DECODER :


![decode table](https://user-images.githubusercontent.com/118054670/215304225-1c58aa43-013d-43eb-bc25-391a4ca72157.png)

## RESULTS :

Hence, 8 to 3 Encoder and 3 to 8 Decoder has been implemented by using verilog and its outputs are validated.


