# EXPERIMENT 05 - INTERFACING A 4X4 KEYPAD TO LPC2148 ARM 7 MICROCONTROLLER

## Aim:
To Interface 4x4 keypad interface LPC2148 ARM 7 and write a code for displaying the inputs on a 16x2 LCD.
## Components required:
Proteus ISIS professional suite, Kiel μ vision 5 Development environment 
## Theory:
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

What is an ARM7 Processor?
<br>
ARM7 processor is commonly used in embedded system applications. Also, it is a balance among classic as well as new-Cortex sequence. This processor is tremendous in finding the resources existing on the internet with excellence documentation offered by NXP Semiconductors. It suits completely for an apprentice to obtain in detail hardware & software design implementation.
<br><br>
LPC2148 Microcontroller
<br>
The LPC2148 microcontroller is designed by Philips (NXP Semiconductor) with several in-built features & peripherals. Due to these reasons, it will make more reliable as well as the efficient option for an application developer. LPC2148 is a 16-bit or 32-bit microcontroller based on ARM7 family.
<br><br>
Features of LPC2148
<br>
The main features of LPC2148 include the following.
*	The LPC2148 is a 16 bit or 32 bit ARM7 family based microcontroller and available in a small LQFP64 package.
*	ISP (in system programming) or IAP (in application programming) using on-chip boot loader software.
*	On-chip static RAM is 8 kB-40 kB, on-chip flash memory is 32 kB-512 kB, the wide interface is 128 bit, or accelerator allows 60 MHz high-speed operation.
*	It takes 400 milliseconds time for erasing the data in full chip and 1 millisecond time for 256 bytes of programming.
*	Embedded Trace interfaces and Embedded ICE RT offers real-time debugging with high-speed tracing of instruction execution and on-chip Real Monitor software.
*	It has 2 kB of endpoint RAM and USB 2.0 full speed device controller. Furthermore, this microcontroller offers 8kB on-chip RAM nearby to USB with DMA.
*	One or two 10-bit ADCs offer 6 or 14 analogs i/ps with low conversion time as 2.44 μs/ channel.
*	Only 10 bit DAC offers changeable analog o/p.
*	External event counter/32 bit timers-2, PWM unit, & watchdog.
*	Low power RTC (real time clock) & 32 kHz clock input.
*	Several serial interfaces like two 16C550 UARTs, two I2C-buses with 400 kbit/s speed.
*	5 volts tolerant quick general purpose Input/output pins in a small LQFP64 package.
*	Outside interrupt pins-21.
*	60 MHz of utmost CPU CLK-clock obtainable from the programmable-on-chip phase locked loop by resolving time is 100 μs.
*	The incorporated oscillator on the chip will work by an exterior crystal that ranges from 1 MHz-25 MHz
*	The modes for power-conserving mainly comprise idle & power down.
*	For extra power optimization, there are individual enable or disable of peripheral functions and peripheral CLK scaling.
 

## 4x4 keypad 

![image](https://user-images.githubusercontent.com/36288975/198944736-c16e2134-193e-4810-a21e-1256c6eefc2d.png)

![image](https://user-images.githubusercontent.com/36288975/198944803-b9298867-c5f1-4167-98f8-f17a6bab5ffe.png)


Step 1: First set all ROWS to OUTPUT and set them at +5V. Next set all COLUMNS as INPUT to sense the HIGH logic. Now consider a button is pressed on keypad. And that key is at 2ND COLUMN and 3rd ROW.
 
With the button being pressed the current flows as shown in figure. With that a voltage of +5V appears at terminal C2. Since the COLUMN pins are set as INPUTS, the controller can sense C2 going high. The controller can be programmed to remember that C2 going high and the button pressed is in C2 COLUMN.
 
Step 2: Next set all COLUMNS to OUTPUT and set them at +5V. Next set all ROWS as INPUT to sense the HIGH logic. Since the key pressed is at 2ND COLUMN and 3rd ROW. The current flows as shown below.

![image](https://user-images.githubusercontent.com/36288975/198944818-632726a7-c582-45b5-9ea0-97d2d0b07939.png)

With that current flow a positive voltage of +5V appears at R3 pin. Since all ROWS are set as INPUTS, the controller can sense +5V at R3 pin. The controller can be programmed to remember the key being pressed at third ROW of KEYPAD MATRIX.
![image](https://user-images.githubusercontent.com/36288975/198944848-bc93731c-dc7d-4e33-b32e-14d4c84c5a0b.png)

From previous step, we have known the COLUMN number of key pressed and now we know ROW number. With that we can match the key being pressed. We can take the key INPUT provided by this way for 4X4.

<br><br><br><br><br><br><br>

## Procedure:
For creation of project on Kiel μ vision 5 Development environment (LPC21 XX/48/38)
1.	Click on the menu Project — New µVision Project creates a new project. Select an empty folder and enter the project name, for example Project1. It is good practice to use a separate folder for each project.
2.	Next, the dialog Select Device for Target opens.
![image](https://user-images.githubusercontent.com/36288975/193398020-d0963a16-4349-4979-87d7-4c9dc11e2346.png)
Figure -01 Target selection
Select the device database. Default is Software Packs. You can have various local device databases, which show up in the drop-down box. For legacy devices (Arm7, Arm9), use the Legacy Device Database [no RTE]
3.	Select the device for your application. This selection defines essential tool settings such as compiler controls, the memory layout for the linker, and the Flash programming algorithms.
4.	Click OK.
5.	Click on the new file option and save the file using save option with .C extension 

For creating the simulation environment in Proteus suite Starting New Design

Step 1: Open ISIS software and select New design in  File menu

![image](https://user-images.githubusercontent.com/36288975/193398023-cb8690cf-914a-47e3-8901-c8db3e4cd223.png)

Figure -02 Proteus File Menu

Step 2: A dialogue box appears to save the current design. However, we are creating a new design file so you can click Yes or No depending on the content of the present file. Then a Pop-Up appears asking to select the template. It is similar to selecting the paper size while printing. For now select default or according to the layout size of the circuit.

![image](https://user-images.githubusercontent.com/36288975/193398027-fd5ae82c-341e-4ed9-aaa4-6bf7574c1a39.png)

Figure -03 Proteus Default Template Select
 
Step 3: An untitled design sheet will be opened, save it according to your wish,it is better to create a new folder for every layout as it generates other files supporting your design. However,it is not mandatory.

![image](https://user-images.githubusercontent.com/36288975/193398031-03ecd6a5-d9b1-4a60-9dee-009c17a3f5dd.png)

Figure -04 Proteus Design Sheet
 
Step 4: To Select components, Click on the component mode button.

![image](https://user-images.githubusercontent.com/36288975/193398044-5e0d1fe6-1d2b-4b54-9c54-f2904b234343.png)

Figure -05 Component Mode

Step 5: Click On Pick from Libraries. It shows the categories of components available and a search option to enter the part name.

![image](https://user-images.githubusercontent.com/36288975/193398047-f1d5f143-7980-45de-99f2-30b3c4bc04d6.png)

Figure -06 Pick from Libraries

![image](https://user-images.githubusercontent.com/36288975/193398058-2519b9d0-a2ca-421f-957d-7507fc7791b8.png)

Figure -07 Keywords Textbox

Step 6: Select the components from categories or type the part name in Keywords text box. Place all the required components and route the wires i.e, make connections. Either selection mode above the component mode or component mode allows to connect through wires. Left click from one terminal to other to make connection. Double right-click on the connected wire or the component to remove connection or the component respectively. Double click on the component to edit the properties of the components and click on Ok.

![image](https://user-images.githubusercontent.com/36288975/193398050-d6d28800-0c5b-4f5c-a77c-227f3336a125.png)

Figure -08 Component Properties Selection

Step 7: Select ARM microcontroller from the library – pick part 

![image](https://user-images.githubusercontent.com/36288975/193398055-587ebd36-4b82-4eaf-837c-f94c3cf2d071.png)
  
Figure -09 LPC2138/48 selection

Step 8: After making necessary connections click on debug.

Step 9: The selected components will appear in the devices list. Select the component and place it in the design sheet by left-click., post which select all the associated components as shown in the circuit diagram below. Example shows selection of push button. Select the components accordingly.

![image](https://user-images.githubusercontent.com/36288975/198945047-9ef54f44-c4df-46f1-970a-f168330a7048.png)

Figure -10 Circuit diagram of 4X4 keypad and 16x2 LCD interface with LPC2148/38

![image](https://user-images.githubusercontent.com/36288975/193398065-c12b4984-db8e-40cc-890d-221db1c35b0d.png)

Figure -11 Push Button Selection

Step 10: Select the hex file from the Kiel program folder and import the program in to the microcontroller as shown in figure 12,  debug and if no errors in connections are found, run the VSM simulation to view the output.

![image](https://user-images.githubusercontent.com/36288975/193398071-76df0a57-7e76-4868-9769-c63d220482b8.png)

Figure -12 Hex file for simulation

## Kiel - Program:
```c
#include <lpc21xx.h> 
#define RS (1<<0)
#define RW (1<<1)
#define E (1<<2)

void LCD_command(unsigned char command);
void  delay_ms(unsigned char time);
void LCD_data(unsigned char data);
void LCD_init() ;


int main(void)
{
 //PINSEL1 = 0x00000000;
 //PINSEL2 = 0X00000000;
 IODIR1= 0x00780000;
 IODIR0= 0x00FF0007;
 LCD_init();
 LCD_command(0x01); 
 while(1)
   {
      IOCLR1|=(1<<19);
      IOSET1|=(1<<20)|(1<<21)|(1<<22);
      if(!(IOPIN1&(1<<16)))
       {
        while(!(IOPIN1&(1<<16)));
        LCD_data('1');                          
       }
      if(!(IOPIN1&(1<<17)))
       {
         while(!(IOPIN1&(1<<17)));
          LCD_data('2'); 
       }
      if(!(IOPIN1&(1<<18)))
       {
         while(!(IOPIN1&(1<<18)));
          LCD_data('3'); 
       }
      IOCLR1|=(1<<20);
      IOSET1|=(1<<21)|(1<<22)|(1<<19);
      if(!(IOPIN1&(1<<16)))
{
        while(!(IOPIN1&(1<<16)));
         LCD_data('4'); 
      }
      if(!(IOPIN1&(1<<17)))
{
        while(!(IOPIN1&(1<<17)));
         LCD_data('5'); 
     }
      if(!(IOPIN1&(1<<18)))
{
        while(!(IOPIN1&(1<<18)));
         LCD_data('6'); 
     }
      IOCLR1|=(1<<21);
      IOSET1|=(1<<22)|(1<<20)|(1<<19);
      if(!(IOPIN1&(1<<16)))
{
        while(!(IOPIN1&(1<<16)));
         LCD_data('7'); 
     }
      if(!(IOPIN1&(1<<17)))
{
       while(!(IOPIN1&(1<<17)));
        LCD_data('8'); 
    }
      if(!(IOPIN1&(1<<18)))
{
        while(!(IOPIN1&(1<<18)));
         LCD_data('9'); 
}
      IOCLR1|=(1<<22);
      IOSET1|=(1<<19)|(1<<20)|(1<<21);
      if(!(IOPIN1&(1<<16)))
{
        while(!(IOPIN1&(1<<16)));
         LCD_data('*'); 
}
      if(!(IOPIN1&(1<<17)))
{
        while(!(IOPIN1&(1<<17)));
         LCD_data('0'); 
}
      if(!(IOPIN1&(1<<18)))
{
        while(!(IOPIN1&(1<<18)));
         LCD_data('#'); 
} 
   }
}


void  delay_ms(unsigned char time)    
{  
 unsigned int  i, j;
 for (j=0; j<time; j++)
 {
  for(i=0; i<8002; i++)
  {
  }
}
}

void LCD_command(unsigned char command)
{
 IOCLR0 = 0xFF<<16;
 IOCLR0=RS;
 IOCLR0=RW;
 IOSET0=command<<16;
 IOSET0=E; 
 delay_ms(10);
 IOCLR0=E;
}

void LCD_data(unsigned char data)
{
 IOCLR0 = 0xFF<<16;
 IOSET0=RS;
 IOCLR0=RW;
 IOSET0= data<<16;
 IOSET0=E;
 delay_ms(10);
 IOCLR0=E;
 }

void LCD_init()
{
 LCD_command(0x38);
 delay_ms(10);
 LCD_command(0x0c);
 delay_ms(10);
    LCD_command(0x0e);
    delay_ms(10);
 LCD_command(0x01);
 delay_ms(10);
 LCD_command(0x80); 
  delay_ms(10);
 
}
```
## Output:
<img width="1515" alt="Experiment 5" src="https://user-images.githubusercontent.com/75234991/200135374-632bda4d-55ba-4189-899b-d07a9ac732b7.png">

### Circuit Diagram:
<img width="1515" alt="Experiment 5" src="https://user-images.githubusercontent.com/75234991/200135407-8d1f0a07-602d-49d4-8ac8-db1fa0b410c2.png">

## Result:
Thus, Interfacing a 4x4 keypad with ARM microcontroller is executed successfully and displayed the inputs.
