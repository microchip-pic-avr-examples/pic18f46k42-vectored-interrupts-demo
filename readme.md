# Vectored Interrupts Demo using PIC18F46K42
How to use the vectored interrupt module

![](https://youtu.be/n9SXI12AuEk){align=center}
# Objective
The objective of this project is to demonstrate how to use MPLAB Code Configurator (MCC) in the MPLAB Xpress IDE to set up and use Vectored Interrupts with different peripherals.

### Goal of the Project 
Blink an LED using Timer0 and Vectored Interrupt. Use MCC to set up the project.

# The Process
## Step 1: Set up Timer0 using MCC
Open MCC by clicking MCC icon in the toolbar. Then set up Timer0 using MCC by setting the appropriate settings/options. Make sure to **Enable Timer Interrupt** by checking the appropriate box.
![](https://static.transim.com/img/22018/3781078fa7e44a47aeb67b733565c98b-dght5.png){width=auto height=auto align=center}

## Step 2: Set up Vectored Interrupts using MCC
In the system section of MCC, click on **Interrupt Module**. Click on **Vectored Interrupt Enable** and then enable the Timer0 Interrupt if it is not enabled already.
![](https://static.transim.com/img/22018/9a60050fd8ef48718b85de88825ff4b2-4ttpj.png){width=auto height=auto align=center}

## Step 3: Set up Output pin using MCC
Use MCC **Pin Module** to configure pin RA5 as output pin. Connect an external LED to this pin.

## Step 4: Generate, Modify and Build Code
Generate the code using MCC. Enable the global interrupts in main.c file.
![](https://static.transim.com/img/22018/3a914b1ad9d74f12b9ff7084cd68a11f-g2lkf.png){width=auto height=auto align=center}

Ensure that the vectored interrupt is initialized properly in mcc_generated_files/interrupt_manager.c file.
![](https://static.transim.com/img/22018/145bb5644aed4432b8b7fb429d476174-hg80b.png){width=auto height=auto align=center}

Ensure that the Timer0 interrupts are enabled in mcc_generated_files/tmr0.c file.
![](https://static.transim.com/img/22018/c1a1f3207f724901a98e3a88e3541210-y91k7.png){width=auto height=auto align=center}

Add code to toggle pin RA4 in Timer0 ISR in mcc_generated_files/tmr0.c file.
![](https://static.transim.com/img/22018/a5139a9ddcf64bfbb0a68e20673c6099-qn5ys.png){width=auto height=auto align=center}

In order to toggle pin RA4 from mcc_generated_files/tmr0.c file, pin_manager.h header must be included in the file.
![](https://static.transim.com/img/22018/dc43c2d5892a42beb00639d1880bb73d-013hs.png){width=auto height=auto align=center}

## Step 5: Make and Program Device
Based on the target board being used, MPLAB Xpress USB Bridge can be used to Make and Program the device. In case of certain Xpress board, the .hex file can be downloaded after building the code which can be drag-and-dropped to the Xpress board.

## Step 6: Watch the LED Blink!
This is the fun part where you can see your code work! Make sure you connect the LED to the correct pin through a resistor.

# Conclusion
Vectored Interrupts can be set up and used very easily and effectively using the MPLAB Code Configurator and MPLAB Xpress IDE.



