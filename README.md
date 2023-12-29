## NAME:ALTRIN AHAS A
## REGISTER NUMBER:23011604

# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure

1.Create a new project in Quartus2 software .
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module declare as dc and uc for down counter and upcounter.
5.Within the module declare input and output variables.
6.Create a loop using if-else with condition parameter as reset.
7.End the loop.
8.End the module



### PROGRAM 
## UP COUNTER
```
module exp_6(clk, A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
	A[2]=(((A[0])&(A[1]))^A[2]);
	A[1]=(A[0])^A[1];
	A[0]=A[0]^1;
end
endmodule
```
## DOWN COUNTER
```
module exp_5__df(clk,A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
	A[2]=(((~A[0])&(~A[1]))^A[2]);
	A[1]=(~A[0])^A[1];
	A[0]=1^A[0];
end 
endmodule
```

### RTL LOGIC UP COUNTER AND DOWN COUNTER  

## UP COUNTER

![293352002-2337b000-a10a-4701-9e7a-039e4de6bd42](https://github.com/altrinahas/Exp-7-Synchornous-counters-/assets/145980038/dadf66da-fab9-4a50-86ef-e6e9ef7135b7)


## DOWN COUNTER

![293352102-6efdadd7-5d06-46c1-9bf4-54b0e39e6e4d](https://github.com/altrinahas/Exp-7-Synchornous-counters-/assets/145980038/48b8c5f0-af58-4fb1-98c6-a4abc7622b44)


### TIMING DIGRAMS FOR COUNTER

## UP COUNTER

![293351796-7edc3d1b-8a7d-4803-a44c-ad0f47da6941](https://github.com/altrinahas/Exp-7-Synchornous-counters-/assets/145980038/98c447d7-12ab-4625-9a8f-9eca27662053)


## DOWN COUNTER

![293352248-64fd4217-35c6-47c9-9a77-c19346e38be0](https://github.com/altrinahas/Exp-7-Synchornous-counters-/assets/145980038/b036227a-86e4-49da-981b-5d02d1d9da8a)

### TRUTH TABLE 

## UP COUNTER

![293351925-d5e809ac-c593-4471-b9cf-25ea4d19f930](https://github.com/altrinahas/Exp-7-Synchornous-counters-/assets/145980038/64792962-b0d6-4f6e-8d9e-9bd25cbb413c)


## DOWN COUNTER

![293352160-a1819724-71b9-4f9a-9600-445d2de493ad](https://github.com/altrinahas/Exp-7-Synchornous-counters-/assets/145980038/7aadac0a-dc06-4e9e-bcb5-4fceaf4cd57c)

## RESULTS
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verif
