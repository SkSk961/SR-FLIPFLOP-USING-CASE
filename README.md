SR-FLIPFLOP-USING-CASE
AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![300539786-0f710028-ad52-4d3e-9276-8714cf023a25](https://github.com/user-attachments/assets/3f5518c1-049d-47f2-9726-ce3cf28f20b4)


This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![300539899-dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30](https://github.com/user-attachments/assets/628b6cf7-3648-4e4c-a80c-f27e9d79e617)


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![300540000-dd90d16c-aec5-4290-a586-e2346b1e9eb5](https://github.com/user-attachments/assets/42c08be3-ea61-498a-bbee-bb14356d489e)


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![300540120-473efad6-d70b-4ca7-aeb7-898bbfca319f](https://github.com/user-attachments/assets/e1a14d23-4d3c-4f53-9900-157950329d3b)


The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

Procedure

1 .Type the program in Quartus software.

2 .Compile and run the program.

3 .Generate the RTL schematic and save the logic diagram.

4 .Create nodes for inputs and outputs to generate the timing diagram.

5 .For different input combinations generate the timing diagram.

PROGRAM
~~~
module SR_FF(s,r,clk,q,qbar);
input s,r,clk;
output reg q;
output reg qbar;
initial 
  begin
  q=0;
  qbar=1;
  end
  always @(posedge clk)
  begin
    q=s|(~r&q);
    qbar=r|(~s&~q);
  end
endmodule
~~~
RTL LOGIC FOR FLIPFLOPS
![435921458-9c54ae00-a24a-44bf-ba97-dddb221e9ed3](https://github.com/user-attachments/assets/7f5b0660-bdfc-4717-a78a-a8f1f5a9b236)


TIMING DIGRAMS FOR FLIP FLOPS

![435921560-ea5f5d3c-adea-481e-8e4a-df6b431817ce](https://github.com/user-attachments/assets/093b3639-f180-4e27-96ab-c8b72baca297)


RESULTS

Thus the program to implement SR flipflop using verilog and validating their functionality using their functional tables has been verified successfully.
