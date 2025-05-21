# Milestone-1-Blink-LED-Bare-Metal-C
To blink the LED of STM32 NUCLEO-F446RE as given in the milestone 1

Go to directory :Core\Src\main.c
Library "main.h" included for F446RE in the "main.c" template which used to define the board function

Blink Project Setup: NUCLEO-F446RE with STM32CubeIDE
Step 1 : Connect Board: Plug your NUCLEO-F446RE into your computer via USB (ST-LINK port).
Step 2 : Open STM32CubeIDE: Launch the software.
Step 3 : New Project: Go to File > New > STM32 Project.
Step 4 :Select Board: Choose NUCLEO-F446RE from the "Board Selector."
Step 5 : Name Project (e.g., "Blinky") and click Finish.
Step 6 : Initialize Peripherals: Click Yes when prompted to initialize peripherals to default mode. This opens the configuration tool.
Step 7 : Configure LED Pin: Find Port A Pin5 on the chip diagram and set it to GPIO_Output.
Step 8 : Generate Code: Click the "Save" icon (or Project > Generate Code).
Step 9 : Add Blink Logic: In main.c, inside the while(1) loop, add:

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

Step 10 : Build & Run: Click the "Build" (hammer) icon, then the "Debug" (green bug) icon, and finally "Resume" (green play) in the debug view.

Youtube link : https://youtu.be/ObSKpKQ-dNY
