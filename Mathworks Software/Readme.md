# MathWorks Software Implementation

## What Problem Are We Focusing On?

When our team visited the Añú community in Santa Rosa de Agua, we witnessed a stark generational contrast: while elderly musicians displayed extraordinary manual dexterity playing traditional instruments, youth faced an estimated **18% decline in fine motor skills** due to passive screen consumption, alongside a **95% loss of their cultural heritage**.

Conventional clinical assessments rely on strapping expensive Inertial Measurement Units (IMUs), bulky exoskeletons, or EMG electrodes onto a patient's hand. These setups intimidate young patients, restrict natural movement, and lead to high therapy abandonment. Conversely, the World Health Organization (WHO) demonstrates that playing an instrument and rhythmic-auditory training activate cerebral sensorimotor pathways, significantly improving upper-limb control and manual dexterity in youth, [as shown in this study](https://github.com/anuwarobotics/Anuwa-robotics-/blob/main/Resources/OMS_Study.pdf).

Our MathWorks implementation introduces a new paradigm in biomechanical telemetry: **transforming a traditional wind instrument into a non-invasive, autonomous clinical diagnostic device using capacitive touch sensing.** By capturing micro-variations across six built-in capacitive copper spirals on our flute unit (*Joroi*) and processing them through **Simulink**, we turn cultural preservation into precision occupational therapy.

---

## What the MathWorks System Does

Acting as both an autonomous clinical diagnostician and real-time orchestrator, the architecture executes three functions simultaneously without manual calibration:

1. **Non-Invasive Capacitive Biometric Telemetry:** Captures raw capacitive signals from the user's fingers across the flute's six note pads, treating micro-fluctuations in contact stability and transitional agility as a continuous neuromuscular data stream.
2. **Real-Time Spectral Analysis (0–12 Hz Band):** Evaluates physical finger stability by analyzing the rate of change in touch across the **0 to 12 Hz spectrum**, isolating the three most dominant oscillation frequencies and overall movement intensity.
3. **Autonomous Classification (0–4 Hz vs. 4–12 Hz):** Autonomously classifies the user's motor profile in real time to adapt the robotic ecosystem:
   - **Voluntary & Physiological Motion (0 to 4 Hz):** Oscillations within the lower **0 to 4 Hz** spectrum are classified as healthy coordination. The system rewards adherence, advances the clinical score, and triggers synchronized robotic accompaniment.
   - **Pathological Tremor & Motor Impairment (4 to 12 Hz):** Dominant peaks within **4 to 12 Hz** are autonomously flagged as motor anomalies. The system shifts the clinical gauge into the alert zone, quantifies instability severity, and adjusts gamified scoring for omissions or involuntary ghost touches.

---

## Why MathWorks Over Bare-Metal ESP32 C++?

Building a medical-grade rehabilitation system demands mathematical rigor and timing determinism. Attempting to write and debug complex finite state machines and digital signal processing (DSP) pipelines directly in bare-metal C++ on the ESP32 presented two major bottlenecks:

- **Edge Computing Limitations:** Coding high-order filters and spectral transforms from scratch requires delicate fixed/floating-point approximations, where a single miscalculation introduces phase lag or spectral leakage, causing false clinical diagnoses.
- **Lack of Pre-Deployment Validation:** Flashing unverified C++ code onto hardware in a rural community like Santa Rosa de Agua is clinically irresponsible; we needed to mathematically simulate healthy and tremor patient profiles before touching physical hardware.

---

## MathWorks Software Suite Breakdown

Adopting a **Model-Based Design** workflow allowed us to solve these bottlenecks by assigning a specific role to each MathWorks tool:

### Simulink
Used as our central system-level integration and simulation environment. It allowed us to visually connect serial hardware telemetry, multi-rate signal processing, and interactive clinical dashboards (gauges and scopes), enabling us to test 7-channel synthetic patient profiles offline before field deployment.

### Stateflow
Used to design our deterministic Finite State Machine (FSM). Rather than writing nested `switch-case` statements in raw C++, Stateflow allowed us to visually model complex hierarchical states (*Standby Telemetry*, *Initialization Sequence*, and *Therapy Execution*) alongside temporal logic and real-time scoring transitions.

### MATLAB
Used for custom algorithmic scripting via *MATLAB Function* blocks. It powers our spectral peak-isolation algorithm (sorting FFT magnitudes to extract the top three dominant frequencies $\le 12\text{ Hz}$) and synthesizes the mathematical patient datasets used in our offline validation harness.

### DSP System Toolbox
Used to build a zero-phase-lag signal conditioning pipeline. It provided verified blocks for outlier suppression (*Median Filter*), high-frequency noise attenuation (*13.5 Hz FIR Filter*), spectral leakage mitigation (*Hamming Window*), and real-time frequency transformation (*FFT* and *Moving Average* for RMS quantification).

### Simulink Coder & Embedded Coder
Used to bridge simulation and physical hardware. Instead of error-prone manual coding, these tools automatically compiled our verified Stateflow chart into a clean, highly optimized, standalone **ISO C++03** class (`.h` and `.cpp`) that runs deterministically inside Joroi's ESP32 firmware.

---

## Scientific & Clinical Justification

Every frequency threshold and classification boundary in our model is backed by peer-reviewed neurological research indexed in **PubMed Central (PMC)**:

1. **Sensor-Based Quantification of 4–12 Hz Essential Tremors:**  
   In [**"Quantifying Tremor in Essential Tremor Using Inertial Sensors—Validation of an Algorithm"**](https://pmc.ncbi.nlm.nih.gov/articles/PMC7608862/) (*McGurrin et al., 2021*), researchers validate that essential tremor occurs specifically within the **4 to 12 Hz** window and can be objectively quantified via algorithmic spectral analysis, matching clinical rating scales without human visual estimation.

2. **Neurological Differentiation Across the 0–12 Hz Spectrum:**  
   According to [**"Tremor Pathophysiology"**](https://pmc.ncbi.nlm.nih.gov/articles/PMC13235525/), normal voluntary coordination and benign physiological oscillations remain anchored in the lower frequency band ($\le 3.5\text{ Hz}$), whereas central neurogenic and pathological motor disorders manifest as distinct peaks between **4 and 12 Hz**—justifying our 12 Hz upper limit and 4 Hz classification boundary.

3. **Clinical Assessment of Finger Dexterity and Action Tremors:**  
   As detailed in [**"The Clinical Evaluation of Parkinson's Tremor"**](https://pmc.ncbi.nlm.nih.gov/articles/PMC4923747/), hand and finger tremors present between **4 and 6 Hz** at rest and extend up to **9–12 Hz** during postural and kinetic tasks (such as holding and playing a flute), validating continuous spectral monitoring during active finger manipulation.
