# Paramapadam (Snakes and Ladders Robot) Project

Welcome to the **Paramapadam** project! This project is a robotic implementation of the traditional Snakes and Ladders game. The robot uses sensor data to navigate and play the game autonomously.



 Introduction

Paramapadam is a robot designed to play a physical version of the Snakes and Ladders game. It uses white line sensors to detect and navigate the board and determines moves using a random number generator, simulating the roll of a dice. The robot's progress is displayed on an LCD screen.

 Hardware Requirements

Microcontroller: ATmega2560
Motors:2 DC motors
Sensors: 3 white line sensors
LCD Display: 16x2 or compatible
Buzzer: For sound alerts
Push Button: For starting the game
Miscellaneous: Resistors, capacitors, and connectors

 Software Requirements

Development Environment: AVR Studio or equivalent
Programming Language: C
Libraries: 
  - `avr/io.h`
  - `avr/interrupt.h`
  - `util/delay.h`
  - `time.h`
  - `stdio.h`
  - `stdbool.h`
  - `firebird_simulation.h`
  - `lcd.c`

Setup and Configuration

1. Circuit Assembly:
   - Connect the motors to the appropriate motor driver pins.
   - Attach the white line sensors to the ADC channels.
   - Connect the LCD to the designated port.
   - Integrate the buzzer and push button.

2. Code Configuration:
   - Ensure `firebird_simulation.h` and `lcd.c` are included in the project directory.
   - Configure the ports in the `port_init()` function according to your circuit design.

Compiling and Uploading Code

1. Open the project in AVR Studio or your preferred IDE.
2. Compile the code to generate the hex file.
3. Use an AVR programmer to upload the compiled hex file to the ATmega2560 microcontroller.

 How to play:

1. Power on the robot.
2. Press the interrupt switch to start the game.
3. The robot will roll a virtual dice, move according to the game rules, and display its position on the LCD.
4. The robot uses sensors to follow lines and detect position changes.

 Code Overview

The code is organized into several functional blocks:

 Initialization Functions

- 'lcd_port_config()`: Configures the LCD pins.
- `adc_pin_config()`: Sets up ADC pins for sensor inputs.
- `motion_pin_config()`: Configures motor driver pins.
- `port_init()`: Calls all the configuration functions.
- `timer5_init()`: Initializes Timer 5 for PWM control.
- `adc_init()`: Initializes the ADC.

Sensor Handling Functions

- `ADC_Conversion(unsigned char Ch)`: Converts analog sensor data to digital values.
- `print_sensor(char row, char coloumn, unsigned char channel)`: Prints sensor values on the LCD.

Motor Control Functions

- `velocity(unsigned char left_motor, unsigned char right_motor)`: Controls the motor speeds.
- `motion_set(unsigned char Direction)`: Sets motor direction.
- `forward()`, `left()`, `right()`, `stop()`: Control the robot's movement.

Main Game Logic

- `main()`: Contains the game loop, reads sensor data, determines robot movement, and displays the game status.
- The robot moves based on a random value simulating a dice roll and follows the game board according to sensor readings.

 Authors and Acknowledgments

This project was developed by [Pranavi] and inspired by traditional board games and robotics principles. Special thanks to the developers of the libraries used.


Feel free to modify the README to better suit your project's specific needs and configurations. Enjoy playing Snakes and Ladders with your autonomous robot!
