# Code Flowcharts

## What platform do we use?

Our team built all of our flowcharts on [**Whimsical**](https://whimsical.com/). Using simple text blocks, we mapped out our programming logic using three primary shapes:

1. **Pill**: Marks where our algorithms start and end. We chose light blue for start points and red for end points to keep things visual and straightforward.

2. **Rectangle**: Outlines high level functions written out in everyday language, color coded in green.

3. **Diamond**: Represents conditions and decision points, giving our robot the ability to react depending on its current state.

## Why did we choose this platform?

We picked Whimsical mainly for its ready-made templates and intuitive drag and drop workflow. It lets us build quickly and efficiently without getting bogged down by rigid pseudocode rules like in tools like **Pseint**. Also, because it runs completely online without requiring any software installation, our team can jump in and work from any computer with an internet connection.

## How do we implement it?

To translate these flowcharts into our actual robotic setup, we program our ESP32 boards in **C++** through the Arduino IDE. This gives us a great middle ground for abstraction. It gives us better performance optimization than MicroPython, while keeping us away from the slow development times of low level assembly code. 

For the Nvidia Jetson AGX Orin, we use **Python** so we can easily run industry standard AI models. Finally, our HMI display uses a **Python** backend paired with an **HTML, CSS, and JavaScript** frontend to ensure the user interface looks clean and visually engaging.

> We handle communication between hardware units using *ESPNOW*, which ensures reliable telemetry since the protocol is natively developed by Espressif.

## Direct Image Visualization

### Apiña
![Image](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Api%C3%B1a%20flowchart.png)

### Ariyuu

![Image](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Ariyuu%20flowchart.png)

### Arusha

![Arusha](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Arusha%20flowchart.png)

### Joroi

![Image](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Joroi%20flowchart.png)
