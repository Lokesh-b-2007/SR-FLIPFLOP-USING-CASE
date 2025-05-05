AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![300539786-0f710028-ad52-4d3e-9276-8714cf023a25](https://github.com/user-attachments/assets/e8bf3657-118c-42ed-87e4-ffd3721a3002)


This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![300539899-dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30](https://github.com/user-attachments/assets/d7499d9f-cfbd-477e-8bab-88478effa8fd)


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![300540000-dd90d16c-aec5-4290-a586-e2346b1e9eb5](https://github.com/user-attachments/assets/22e59043-1284-40e1-8f9f-7edbb3cded71)


By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![300540120-473efad6-d70b-4ca7-aeb7-898bbfca319f](https://github.com/user-attachments/assets/b0048c43-0699-471d-ab94-a5151a9215fe)



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
![435921458-9c54ae00-a24a-44bf-ba97-dddb221e9ed3](https://github.com/user-attachments/assets/c779c1ef-e71e-4240-82e7-f912c80c24a3)


TIMING DIGRAMS FOR FLIP FLOPS

![435921560-ea5f5d3c-adea-481e-8e4a-df6b431817ce](https://github.com/user-attachments/assets/b48d76da-5fdc-4832-a4da-01ea2f10e85e)


RESULTS

Thus the program to implement SR flipflop using verilog and validating their functionality using their functional tables has been verified successfully.
