# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

STEP 1:Type the program in Quartus software.

STEP 2:Compile and run the program.

STEP 3:Generate the RTL schematic and save the logic diagram.

STEP 4:Create nodes for inputs and outputs to generate the timing diagram.

STEP 5:For different input combinations generate the timing diagram.
**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by:JEGATHEESWARI R
RegisterNumber:212223230092
*/
```

module SRFLIPFLOPUSINGCASE(q, q_bar, s,r, clk, reset);//SR Flip Flop Behavioral Level using ‘case’ 
  input s,r,clk, reset;
  output reg q;
  output q_bar;
 
  always@(posedge clk) begin // for synchronous reset
    if(!reset)
		q <= 0;
    else 
  begin
      case({s,r})       
	     2'b00: q <= q;    // No change
		  2'b01: q <= 1'b0; // Write logic for reset
        2'b10: q <= 1'b1; // Write logic for set
		  2'b11:	q <= 1'bx; // Write logic for Invalid state
      endcase
    end
  end
  assign q_bar = ~q;
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**
![rtl 1](https://github.com/Jegatheeswarir/JKFLIPFLOP-USING-IF-ELSE/assets/144871077/4b17a95a-4868-4bdb-a52f-ee777bc293c0)



**TIMING DIGRAMS FOR FLIP FLOPS**
![timingdiagram 2](https://github.com/Jegatheeswarir/JKFLIPFLOP-USING-IF-ELSE/assets/144871077/021f8782-1302-45ab-9c7b-2194e10a1b4b)


**RESULTS**

Therefore the code has been successfully executed.

