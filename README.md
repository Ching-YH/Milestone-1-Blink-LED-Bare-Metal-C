# Milestone-1-Blink-LED-Bare-Metal-C
To blink the LED of STM32 NUCLEO-F446RE as given in the milestone 1.
The code is used to blink the LED with pattern when there is power supply. An indication of power connection.

Blink Project Setup: NUCLEO-F446RE with STM32CubeIDE
Step 1 : Connect Board: Plug your NUCLEO-F446RE into your computer via USB (ST-LINK port).
Step 2 : Open STM32CubeIDE: Launch the software.
Step 3 : New Project: Go to File > New > STM32 Project.
Step 4 : Select Board: Choose NUCLEO-F446RE from the "Board Selector". 
Step 5 : Name Project (e.g., "Blinky") and click Finish.
Step 6 : Initialize Peripherals: Click Yes when prompted to initialize peripherals to default mode. This opens the configuration tool.
Step 7 : Go to directory :Core\Src\main.c for programming coding.
Step 8 : Check on library to ensure the required define and function are available. In the default template consist of #include "main.h".
Step 9 : Identify LED from the Nucleo board, confirm it named as LD2. Then go to library "main.h" to find the Port and Pin defined for LD2.
Step 10 : From "main.h" library LD2 defined as Port A Pin5 on the board, so begin the coding. In main.c file at int main(void)

		  RCC->AHB1ENR |= 0x01; // Enable GPIOA clock
		  GPIOA->MODER |= 0x00000400; // Set mode bits to output for PA5
		  GPIOA->OTYPER |= (0x00000020); // Set PA5 as OPEN-DRAIN
		  GPIOA->PUPDR |= 0x00000400; // Enable PULL-UP Resistor at PA5

Step 11 : Generate Code: Click the "Save" icon (or Project > Generate Code).
Step 12 : Add Blink Logic: In main.c, inside the while(1) loop, add:

		  GPIOA->ODR |= 0x00000020; // Turn ON LED PA5
	  	  HAL_Delay(100);
	  	  GPIOA->ODR &= ~(0x00000020); // Turn OFF LED PA5
	  	  HAL_Delay(100);
	  	  GPIOA->ODR |= 0x00000020; // Turn ON LED PA5
	  	  HAL_Delay(100);
	  	  GPIOA->ODR &= ~(0x00000020); // Turn OFF LED PA5
	  	  HAL_Delay(100);
	  	  GPIOA->ODR |= 0x00000020; // Turn ON LED PA5
	  	  HAL_Delay(100);
	  	  GPIOA->ODR &= ~(0x00000020); // Turn OFF LED PA5
	  	  HAL_Delay(100);
	  	  //blink 1time, on 1s and off 1s
	  	  GPIOA->ODR |= 0x00000020; // Turn ON LED PA5
	  	  HAL_Delay(1000);
	  	  GPIOA->ODR &= ~(0x00000020); // Turn OFF LED PA5
	  	  HAL_Delay(1000);

Step 13 : Build & Run: Click the "Build" (hammer) icon, then the "Debug" (green bug) icon, and finally "Resume" (green play) in the debug view.
Step 14 : LED blink with repeated pattern, 3 times fast and 1 time slow to indicated power supply is connected. 
Step 15 : Board is successfully coded with the program and uploaded the video into Youtube.

Youtube link : https://youtu.be/ObSKpKQ-dNY
