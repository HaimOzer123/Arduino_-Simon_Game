# Arduino Real-Time Simon Game
Haim Ozer 
---------------------------------

## Overview
This project is an implementation of a **real-time Simon Game** using an Arduino Uno, buttons, LEDs, and a buzzer. 
The goal of this project is to demonstrate real-time system concepts such as:
- Handling multiple tasks simultaneously.
- Responding to user inputs in real-time.
- Managing precise timing for tasks such as LED flashing and sound generation.
  
This project isdone for gaining experience in **Realtime Software Engineering** as it involves:
- **Interrupt-driven programming**.
- **Precise control** of hardware peripherals.
- **Non-blocking task handling** to ensure the game logic and user interactions run smoothly.

## Hardware Components
- **Arduino Uno**
- **4 Push Buttons** (for game input)
- **4 LEDs** (to display patterns)
- **Buzzer** (for audio feedback)
- **Resistors** (for buttons and LEDs)

## Software Features
- **FreeRTOS Integration**: Handles task scheduling and resource management.
- **Button Input Handling (Interrupt-driven)**: Uses interrupts for real-time detection of button presses.
- **LED Pattern Display**: Shows randomized LED patterns that the player must mimic.
- **Buzzer Feedback**: Provides audio signals for game events like correct and incorrect inputs.
- **Real-Time Task Management**: Separate tasks manage LED control, button input, and buzzer feedback, ensuring non-blocking, smooth operation.

## How to Use
### 1. Setup the Hardware
- Connect the buttons to digital pins (e.g., pins 2, 3, 4, and 5).
- Connect the LEDs to digital pins (e.g., pins 6, 7, 8, and 9).
- Connect the buzzer to a digital pin (e.g., pin 10).

### 2. Install Required Libraries
In the **Arduino IDE**:
- Go to **Sketch** -> **Include Library** -> **Manage Libraries...**.
- Search for **FreeRTOS** and install the library.

### 3. Upload the Code
- Open the `.ino` file provided in this repository.
- Upload the code to your Arduino Uno.

### 4. Play the Game
- The system will light up a sequence of LEDs.
- Press the corresponding buttons to mimic the LED sequence.
- The buzzer will provide feedback on whether your input was correct or incorrect.

### 5. Reset
- Press the reset button on the Arduino board to start the game again.


## Real-Time Engineering Concepts
This project utilizes several **Realtime Software Engineering** techniques, including:

1. **Task Scheduling with FreeRTOS**: Each function of the game (LED control, button input, buzzer feedback) runs as a separate task.
2. **Non-blocking Delays**: Uses `vTaskDelay()` from FreeRTOS instead of `delay()`, ensuring other tasks continue to execute.
3. **Interrupts and Semaphores**: Button input is handled with interrupts and semaphores to ensure real-time responsiveness.
4. **Task Prioritization**: Critical tasks such as button handling have higher priority than less critical tasks like LED flashing.

