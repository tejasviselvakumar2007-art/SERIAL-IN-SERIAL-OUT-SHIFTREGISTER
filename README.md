# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**

First, Quartus II software is opened and a new project is created using the New Project Wizard by giving a suitable project name. Then a Block Diagram/Schematic file is created. Required D flip-flops are selected from Primitives → Storage → Flip-Flop and placed on the schematic. Input pins are added and named as DIN (serial input) and CLK (clock), and an output pin is added and named as DOUT (serial output). The serial input DIN is connected to the D input of the first flip-flop, and the Q output of each flip-flop is connected to the D input of the next flip-flop. All clock inputs are connected to a common clock signal. The Q output of the last flip-flop is connected to DOUT. After completing the connections, the design is saved and compiled successfully. Then a University Program VWF file is created, input waveforms are applied to DIN and CLK, and functional simulation is run. The output waveform is observed, and it is verified that the serial data applied at the input appears at the output after each clock pulse, thus confirming the operation of the SISO shift register.

**PROGRAM**
```
module EXP10(clk, sin, q);
input clk;
input sin;
output [3:0] q;
reg [3:0] q;
always @(posedge clk)
begin
q[0] <= sin;
q[1] <= q[0];
q[2] <= q[1];
q[3] <= q[2];
end
endmodule
```


Developed by:Tejasvi S

RegisterNumber: 25018602


**RTL LOGIC FOR SISO Shift Register**
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/3c00ec54-f34f-4adb-8c8d-f7cbeaa16684" />


**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1920" height="1080" alt="Screenshot (151)" src="https://github.com/user-attachments/assets/9fc86d19-0c2c-43e2-9197-8687499f6ce9" />


**RESULTS**
The Serial In Serial Out (SISO) shift register was successfully designed and simulated using Quartus II.

