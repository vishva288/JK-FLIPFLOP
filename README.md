## JK-FLIPFLOP
## AIM:
To implement JK flipflop using verilog and validating their functionality using their functional tables

## SOFTWARE REQUIRED:
Quartus prime

## THEORY
## JK Flip-Flop
JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

<img width="472" height="307" alt="image" src="https://github.com/user-attachments/assets/d2bd75d9-01c2-4586-8636-9b2c09cdd14d" />

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

<img width="443" height="317" alt="image" src="https://github.com/user-attachments/assets/da33c6c7-3f41-413a-bab3-1bdaba82047a" />

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

<img width="555" height="446" alt="image" src="https://github.com/user-attachments/assets/7acfe98a-9750-414a-a721-acc40b9e9224" />

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="253" height="207" alt="image" src="https://github.com/user-attachments/assets/7aec9296-e5df-4209-9207-a40f52d0202a" />

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

## Procedure
1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

## PROGRAM
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

module JK_FF (q, qb, j, k, clock, reset);

input j, k, clock, reset;
output reg q, qb;

always @(posedge clock)
begin
    if (!reset)
    begin
        q <= 0;
        qb <= 1;
    end
    else
    begin
        if (j == 0 && k == 0)
        begin
            q <= q;
            qb <= qb;
        end
        else if (j == 0 && k == 1)
        begin
            q <= 0;
            qb <= 1;
        end
        else if (j == 1 && k == 0)
        begin
            q <= 1;
            qb <= 0;
        end
        else if (j == 1 && k == 1)
        begin
            q <= ~q;
            qb <= ~qb;
        end
    end
end

endmodule
*/
```
RTL LOGIC FOR FLIPFLOPS
<img width="805" height="317" alt="image" src="https://github.com/user-attachments/assets/a2beb6ae-7f6f-4cd8-b1b1-6dd4a860dc03" />

TIMING DIGRAMS FOR FLIP FLOPS
<img width="857" height="191" alt="image" src="https://github.com/user-attachments/assets/674af9bf-a397-4cb6-855f-eff9d88502f3" />

## RESULT:
Thus, the JK Flip-Flop was successfully implemented using Verilog HDL with an if-else behavioral description, and its functionality was verified according to the JK flip-flop functional table. The flip-flop performed hold, set, reset, and toggle operations correctly for the corresponding input combinations.
