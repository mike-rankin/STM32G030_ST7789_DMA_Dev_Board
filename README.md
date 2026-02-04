# STM32G030_ST7789_DMA_Dev_Board

![Image](https://github.com/user-attachments/assets/e3d956b0-4ead-4d27-bd57-9999583a4c13)

## DMA vs. Non-DMA for TFT Displays using a cooking analogy

When driving a TFT display with an STM32, there are two main ways to move pixel data: **Non-DMA (Polling)** and **DMA (Direct Memory Access)**.

### 1. Non-DMA: The "Chef Does Everything" Method
Imagine your STM32 is a busy chef (the CPU) and the display is a customer waiting for a meal.

*   **How it works:** The Chef manually carries every single pea and carrot to the table one by one.
*   **The Problem:** While carrying food, the Chef **cannot cook** anything else. The stove stays idle.
*   **The Result:** The screen updates slowly, and the system might feel "laggy" because the CPU is too busy moving pixels to check for button presses or sensor data.

### 2. DMA: The "Conveyor Belt" Method
Now, imagine the Chef installs a conveyor belt (the DMA controller) between the kitchen and the table.

*   **How it works:** The Chef puts a pile of food on the belt and flips a switch. He then immediately goes back to cooking the next meal.
*   **The Magic:** The belt moves the food automatically in the background without needing the Chef’s attention.
*   **The Result:** The CPU is free to do "smart" work (like math or game logic) while the "dumb" work (moving data) happens on its own.

### Performance Summary

| Feature | Non-DMA (Polling) | DMA (Direct Memory Access) |
| :--- | :--- | :--- |
| **CPU Load** | High (CPU is 100% busy) | Very Low (CPU is free) |
| **Speed** | Slower (limited by code loops) | Fastest (runs at max hardware speed) |
| **Multitasking** | Poor | Excellent |

---
*Tip: Use **Double Buffering** with DMA to eliminate screen flickering!*

In CubeMX 

<img src="https://github.com/user-attachments/assets/b3917d41-6550-48d1-8fb1-254ddc60ca46" width="800" />


<img src="https://github.com/user-attachments/assets/27ec0fea-4cb4-4d94-94ae-affed79888c0" width="400" />




