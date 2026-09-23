# Code Flowcharts

## What platform do we use?
Our team's flowcharts were created on the [**Whimsical**](https://whimsical.com/) platform, through which we were able to represent the logic of our programming using text boxes. We used 3 main symbols:

1. **Pill**: Defines the start and end of the algorithms. We used light blue for the start and red for the end, making them easily distinguishable.
2. **Rectangle**: Used to represent the equivalent of high-level functions using natural language. In this case, we used a green color.
3. **Diamond**: Represents a conditional statement. It gives the robot the ability to make its own decisions based on its current state at the moment of evaluation.

## Why did we choose this platform?

This is because it features various ready-to-use templates and text boxes in a *drag and drop* style, which allows us to save time and improve efficiency. It does not limit us to a *pseudocode* with strict rules like **Pseint**. Furthermore, being 100% online and requiring no installation allows us to work from any computer with internet access.

## How do we implement it?

To implement these flowcharts in our robotic system, we will program the ESP32 boards in **C++** using the Arduino IDE because it offers a balanced level of abstraction—not as high as MicroPython, allowing us to optimize the code, but not as low-level as assembly or similar languages, which saves us development time. The Nvidia Jetson AGX Orin was developed using **Python** to execute AI models on the platform where they are standard. On the other hand, the HMI screen was programmed with a **Python** backend, while the frontend was built in **HTML, CSS, and JavaScript** due to their aesthetic contributions.

> Communication between units will be carried out via *ESPNOW*. This allows us to maintain stable telemetry, as it is a communication system developed by Espressif.

## Direct Image Visualization
### Apiña
![Image](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Api%C3%B1a%20flowchart.png)

### Ariyuu

![Image](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Ariyuu%20flowchart.png)

### Arusha

![Arusha](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Arusha%20flowchart.png)


### Joroi

![Image](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Code%20Flowcharts/Joroi%20flowchart.png)
