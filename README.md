# LED and Button Control Project

### Description

This project is designed to control three LEDs using three buttons connected to an Arduino. The first LED turns on while the button is pressed, the second LED toggles its state with each press of the button, and the third LED toggles its state based on the duration of the button press (short press vs long press).

### Components

- 3 LEDs
- 3 Push Buttons
- Arduino Board
- Resistors (appropriate values for LEDs)
- Breadboard and jumper wires

### Pin Configuration

- LED 1: Connected to digital pin 25
- Button 1: Connected to digital pin 12
- LED 2: Connected to digital pin 26
- Button 2: Connected to digital pin 13
- LED 3: Connected to digital pin 27
- Button 3: Connected to digital pin 14

### Code Explanation

#### Global Variables

- ledPin1, ledPin2, ledPin3: Pin numbers where the LEDs are connected.
- buttonPin1, buttonPin2, buttonPin3: Pin numbers where the buttons are connected.
- ledState1, ledState2, ledState3: Store the state of each LED (ON or OFF).
- button2Pressed, button3Pressed: Flags to track the state of the second and third buttons.
- button3PressTime: Variable to store the time when the third button is pressed.
- longPressDuration: Define the duration for a long press (in milliseconds).

#### setup() Function

The setup() function initializes the pins for the LEDs and buttons:

- Set the LED pins as OUTPUT.
- Set the button pins as INPUT with an internal pull-up resistor.
- Ensure all LEDs are initially turned off.

#### loop() Function

The loop() function continuously checks the state of the buttons and updates the LEDs accordingly:

1. First Button and LED:

- If the first button is pressed, the first LED turns on.
- If the first button is released, the first LED turns off.

2. Second Button and LED:

- If the second button is pressed and the flag button2Pressed is false, the flag is set to true, and the state of the second LED is toggled.
- If the second button is released, the flag is reset.

3. Third Button and LED:

- If the third button is pressed, the flag button3Pressed is set to true, and the press time is recorded.
- If the third button is released and the flag button3Pressed is true, the duration of the press is calculated.
- If the press duration is greater than or equal to longPressDuration, the state of the third LED is toggled.
- The flag button3Pressed is reset after processing.

### Usage

1. Connect the components as described in the pin configuration.
2. Upload the provided code to the Arduino board.
3. Press the buttons to control the LEDs as described:

- Button 1: LED 1 is on while the button is pressed.
- Button 2: LED 2 toggles its state with each press.
- Button 3: LED 3 toggles its state with a long press.

### Conclusion

This project demonstrates basic digital input and output operations using Arduino. It covers how to read button states, control LEDs, and implement debouncing and long press detection. This can be a foundation for more complex projects involving multiple inputs and outputs.
