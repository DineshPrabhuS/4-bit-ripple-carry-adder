# 4-BIT-RIPPLE-CARRY-ADDER

**AIM:**

To implement 4 Bit Ripple Carry Adder using verilog and validating their functionality using their functional tables.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A 4-bit ripple carry adder is a digital circuit that performs the addition of two 4-bit binary numbers using four full adders in a chain, with the carry output of each full adder connected to the carry input of the next full adder. The carry input of the least significant full adder is set to 0.
The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![Screenshot 2025-01-06 090620](https://github.com/user-attachments/assets/4a18971c-0ab8-4c34-93e1-c915ef93c9e9)

**Procedure**

1. Type the program in Quartus software.
2. Compile and run the program.
3. Generate the RTL schematic and save the logic diagram.
4. Create nodes for inputs and outputs to generate the timing diagram.
5. For different input combinations generate the timing diagram.

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
```
// 4-bit Ripple Carry Adder Module
module workshop (
    input [3:0] A, B,      // 4-bit Inputs: A and B
    input Cin,             // Carry-in
    output [3:0] Sum,      // 4-bit Sum output
    output Cout            // Carry-out
);

    wire C1, C2, C3;       // Internal carry wires

    // Instantiate 4 full adders
    full_adder FA0 (A[0], B[0], Cin, Sum[0], C1);  // Least significant bit (LSB)
    full_adder FA1 (A[1], B[1], C1, Sum[1], C2);
    full_adder FA2 (A[2], B[2], C2, Sum[2], C3);
    full_adder FA3 (A[3], B[3], C3, Sum[3], Cout); // Most significant bit (MSB)

endmodule 

// Full Adder Module
module full_adder (
    input A, B, Cin,       // Inputs: A, B, and Carry-in
    output Sum, Cout       // Outputs: Sum and Carry-out
);

    assign Sum = A ^ B ^ Cin;            // Sum = A ⊕ B ⊕ Cin
    assign Cout = (A & B) | (Cin & (A ^ B)); // Cout = (A ⋅ B) + (Cin ⋅ (A ⊕ B))

endmodule
```
 Developed by: DINESH PRABHU S
 
 RegisterNumber: 24004388
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**

![Screenshot (206)](https://github.com/user-attachments/assets/ee2ecc74-79ac-4808-86b1-9fe707990a1d)


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

![Screenshot (207)](https://github.com/user-attachments/assets/c1ebd5d5-857e-4a01-91e0-940b868b97b8)


**RESULTS**

Successfully implemented 4 Bit Ripple Carry Adder using verilog and validated their functionality using their functional tables.
