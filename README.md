# Bitcoin_Tracker

Introduction:
We built and integrated a Bitcoin price tracker that continuously pulls market data off an API over Wi-Fi (using an ESP32) every 20 secconds. We display this information on the 16 bit LCD via a TM4C123GH6PM microcontroller. The user can set a target price threshold; when the thresholds is crossed, the system flashes the RGB LED yellow and beeps a buzzer. All data transfered from the ESP32 to the TM4C are done via UART, and timing/scheduling is managed by the TM4C. The esp 32 pulls and updates the LCD every 20 seconds with the current price and percentage change. We used a push-button that lets the user scroll through and set thresholds directly on the device where no PC or smartphone required.

Background and Methodology:
The ESP32 sticks to handling the Wi-Fi connectivity and HTTP requests to a public Bitcoin price API.
The TM4C123GH6PM is responsible for reading the UART data, driving the 16×2 LCD, controlling the RGB LED and buzzer and responding to button presses.

We used GPIO Interfacing by Controlling LEDs, buzzer, button, and LCD data/command lines. We also used UART Serial Communication (half duplex). We used SysTick for regular sampling and refresh intervals. We used Interrupts & ISRs for Debounced button‐press. We used custom LCD driver( 4-bit HD44780).

We were able to achive this project by starting with simple UART “echo” tests between ESP32 and TM4C, then layered on parsing, LCD output, and LED control one feature at a time. We also spent over a week fine-tuning UART settings and baud rate. Through trial and error we were able to build a fully fledge bitcoin tracker system. 
[View project video on Google Drive](https://drive.google.com/drive/folders/1L0WPg1FbFZD1QxlCLwG6NjdZSW5IKFz6?usp=drive_link)


![Block diagram](https://github.com/user-attachments/assets/f786a6e0-47f6-412e-bee7-703b9fe624a0)
![Pin outs](https://github.com/user-attachments/assets/b09ed893-b355-4ed7-ae3c-ac0f8972bf05)

![components ](https://github.com/user-attachments/assets/8796bda4-3327-4467-96f5-d2b1dae7c83b)

![Schematic](https://github.com/user-attachments/assets/ac65f244-a5e3-4c2b-872c-62e3f3cbf36d)
