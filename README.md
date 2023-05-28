# Design-and-Characterization-of-a-Flip-flop-

Introduction:

Flip-Flops are the basic elements of a sequential circuit. In this project, we will design a Flip-Flop to characterize its delay, input capacitance and its setup and hold time.

Setup time: It is the time required for the input data signal at the Flip-Flop to be valid before the incoming clock edge arrives.

Hold time: It is the time required for the input dat signal to be valid after the transition on the clock edge. 

Design of a Flip-Flop
Two back-to-back latches that function on the opposing edges of the clock signal are used to construct a flip-flop. The Master and Slave are those two things. 

The Master latch receives the input at one clock edge, and the Slave latch moves the Master latch's output to the output at the next clock phase. 

Flip-Flop Schematic:

![Schematic](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/0bb261ab-9651-4b2a-b209-2a308adb1288)

Flip-Flop Symbol:

![Symbol](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/c2935d62-4808-44ac-9498-b1fbf108190f)

Flip-Flop Layout:

![Layout](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/172fcfb9-4247-4825-b128-4479c6122080)

Flip-Flop Test-bench:

![testbench](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/3855cd55-215f-4f1a-8a0a-766ae6882a3e)

Characterization:

We will make use of the testbench to characterize the Flip-Flop Design.

1. Cell Delay Table: 
The rising and falling delay of the flip-flop is calculated by varying the load the output from 1fF to 100fF.
Since the flip-flop latches a new value only on the active edge of the clock, we need to note down the clock-to-Q delay of the circuit.
To make sure that the rising and falling delay difference is not more than 10%, we may need to size the transistors.

Plot verifying the correctness of the design. (CLK, _CLK, falling & rising of D and Q).

1fF:

![1f](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/144363cd-2d99-4fce-8471-a09a37c2f948)

100fF:

![image](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/e4603463-6d50-4eff-b952-978f93824285)

Delay Calculations:

![image](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/20c722c8-84a8-44aa-abb0-4ae2d25afdb7)

![image](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/c437ec5a-8ba5-45ec-b288-918d64a0b36e)

2. Input Capacitance:
We perform the ac analysis and observe the output from a frequency of 1Hz to 1GHz.
To calculate the input sink capacitance, we shall plot the current waveform that will show the current flowing into the input D. 
To plot the output, we shall select the + terminal of vsin.
After running the simulations, we observe the plot of current flowing to input D Vs Frequency. 
Change the axis to Logarthmic. 
To calculate the input sink capacitance, we will choose 10 points and for each point we shall note down the frequency, current and procced to calculate the capacitance using C= 1/2*(Pi)*f. 

Circuit:

![Vsin_crkt](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/3b0d2eaf-28a6-4b47-8645-1f8c547006fa)

Plot:

![100fplot](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/7888a754-7f1d-44ed-b68c-b542ddfb3219)

Capacitance-Frequency Table:

![image](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/34929c72-5fff-48cc-8c3a-925ce3d01222)

Mean capacitance: 2.47E-15

3. Set-up time:
To measure the set-up time, we need to measure the clock-to-Q delay of the Flip-Flop by varying the time between the input D and clock's rising edge. 
Continue this until the FF reaches a meta-stable state, i.e., the FF will give an erroneous output. This can be simply observed when either: 
a) The D input does not cause a change in output in the present clock cycle 
b) Or the clock-to-Q delay increases drastically 
c) Or there are oscillations in the output between 0 and 1. 
We will likely observe a or b. 

Plot:

![setup_f](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/6fe217c1-39d2-42cd-9157-7e67b941b18c)

![setup_r](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/c226c2be-c1fd-453e-9153-93707b54510a)

Calculation:

![image](https://github.com/RoshiniUdayaKumar/Design-and-Characterization-of-a-Flip-flop-/assets/133715179/2e43eaf1-6fcb-4d75-9640-bcbefa42176a)

Determining the setup time of the design:

Setup is calculated using the expression: setup=max {setup-r; setup-f} which is 0.28
