# Arduino_MadLib_Generator
Final project for ECE/CSE 474 (Intro to Embedded Systems) at the UW

# Hardware Organization
See this simulation environment to see hardware organization
https://wokwi.com/projects/366925946850567169

# How it works
Demo Video: https://drive.google.com/file/d/1l0hLff5ODTJ4vruzkmB21UgjIhKylvcM/view?usp=sharing <br>
The arduino is concurrently handling input and output at the same time using RTOS with a few 
functions aiding it. There are four tasks that are ran by the RTOS, LEDControl, LCDControl,
ScrollHandler, and SelectHandler. Values are passed between them by queues, in which 3 exist.
ledQueue which accepts values from SelectHandler, lcdQueue which accepts values from SelectHandler,
and scrollQueue which accepts values from ScrollHandler. There is one model in this build, primarily
in the python interface which is called in the LCDControl function once enough words are selected. 
Once enough words are selected, via PySerial, the information is sent to Python which prompts
chatGPT to make a sentence with the 5 selected words. After that is done it will send that back
to the arduino which is then displayed on the LCD
