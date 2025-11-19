# LiteWave-full-sine-wav-inverter-
![LiteWave_1-transformed](https://github.com/user-attachments/assets/41e0301e-12b0-4001-9d77-e6e19f5a4edd)



### **README for Full Sine Wave Inverter (EGS002 v2)**

<p align="center">Sponsored By </p>
<p align="center">
  <a href="https://pcbway.com/g/D6Z94Y">
    <img src="./PCBWay logo.png" alt="PCBWay" width="200"/>
  </a>
</p>

<p>This project is proudly supported by PCBWay, a company I personally rely on for PCB manufacturing and prototyping. I’ve used their services for my hardware builds, and their quality, turnaround time, and pricing beat most of what I’ve tried before.

🔧 Why PCBWay stands out:

High-quality boards with excellent finishing

Fast production & reliable global shipping

Low-cost prototypes and student-friendly pricing

Options for assembly, CNC machining, 3D printing & more

Easy-to-use online quote & order system

Their support helps me keep this project alive and evolving. If you're building hardware and need professional PCB manufacturing, I genuinely recommend trying PCBWay — they've earned my trust long before sponsoring me.

👉 Check them out: ([PCBWay link](https://www.pcbway.com/))</p>

---

#### **Table of Contents**
1. [Introduction](#1-introduction)  
2. [Circuit Modules and Components](#2-circuit-modules-and-components)  
   - [2.1 Voltage Regulation (18V DC | 12V DC | 5V DC)](#21-voltage-regulation-18v-dc--12v-dc--5v-dc)  
   - [2.2 High-Frequency Transformer](#22-high-frequency-transformer)  
   - [2.3 High-Frequency MOSFET Bridge](#23-high-frequency-mosfet-bridge)  
   - [2.4 Battery Input](#24-battery-input)  
   - [2.5 EGS002 Module](#25-egs002-module)  
   - [2.6 Voltage Feedback](#26-voltage-feedback)  
   - [2.7 IGBT Bridge](#27-igbt-bridge)  
   - [2.8 Fan Control](#28-fan-control)  
   - [2.9 Output Section](#29-output-section)  
3. [Working Principle](#3-working-principle)
4. [List of Components](#List-of-Materials)
5. [BOM CSV data is available here click to view](https://github.com/nithinmathewjoji/LiteWave-full-sine-wav-inverter/blob/master/bom/README.md)
6. [View ibom (interactive bill of materials webpage)](https://nithinmathewjoji.github.io/LiteWave-full-sine-wav-inverter/)
7. [PCB Details & preview](https://github.com/nithinmathewjoji/LiteWave-full-sine-wav-inverter/blob/master/README.md#pcb-details--preview)
8. [Note](#Notes)
9. [Advantages](#4-advantages)
10. [Read License](https://github.com/nithinmathewjoji/LiteWave-full-sine-wav-inverter/blob/master/LICENSE)

---

### **1. Introduction**
The Full Sine Wave Inverter circuit is designed to convert DC power into a clean and stable sine wave AC output, suitable for powering household appliances, renewable energy setups, and backup power systems. Utilizing the EGS002 SPWM module, this design ensures high-quality performance and reliability.

---

### **2. Circuit Modules and Components**

#### **2.1 Voltage Regulation (18V DC | 12V DC | 5V DC)**
- **Components:** HER107 diodes, L7815CV (15V regulator), L7805CV (5V regulator), capacitors (100µF, 470µF).
- **Function:** Converts 18V AC to regulated DC voltages (18V, 12V, 5V) for different sections of the circuit. Ensures consistent and noise-free operation.

---

#### **2.2 High-Frequency Transformer**
- **Components:** Center-tapped transformer, GBU404 bridge rectifier, filter capacitors.
- **Function:** Steps up low voltage DC to 380V AC at high frequency. It also provides electrical isolation between input and output circuits.

---

#### **2.3 High-Frequency MOSFET Bridge**
- **Components:** IRF3205 MOSFETs, gate resistors, diodes.
- **Function:** Converts the 12V DC into a high-frequency AC signal, which is fed into the HF transformer for voltage stepping.

---

#### **2.4 Battery Input**
- **Components:** Battery connectors, bypass capacitors.
- **Function:** Serves as the power source for the inverter. Ensures stable input voltage to the circuit.

---

#### **2.5 EGS002 Module**
- **Components:** Integrated SPWM generator, feedback pins, and driver outputs.
- **Function:** Generates sinusoidal PWM signals and provides control for the IGBT bridge, maintaining a pure sine wave AC output.

---

#### **2.6 Voltage Feedback**
- **Components:** Resistors, capacitors.
- **Function:** Monitors the output voltage and sends feedback to the EGS002 module for precise voltage regulation.

---

#### **2.7 IGBT Bridge**
- **Components:** FG40N65 IGBTs, IN4148 diodes, resistors, snubber capacitors.
- **Function:** Converts the high-voltage DC into a sine wave AC output, controlled by the SPWM signals from the EGS002 module.

---

#### **2.8 Fan Control**
- **Components:** SS8050S transistor, thermistor (NTC 10k), resistor.
- **Function:** Activates a cooling fan based on temperature, ensuring efficient thermal management.

---

#### **2.9 Output Section**
- **Components:** AC terminals for load connection.
- **Function:** Delivers a stable 220V 50Hz pure sine wave AC output for external devices.

---

### **3. Working Principle**

1. **DC Input and Regulation:**  
   The inverter uses a 12V battery as the primary power source. The input voltage is stepped up and regulated to 18V, 12V, and 5V DC for various subsystems.

2. **High-Frequency Switching:**  
   The MOSFET bridge converts the 12V DC into a high-frequency AC signal, which is processed by the HF transformer.  

3. **Voltage Step-Up and Rectification:**  
   The HF transformer steps up the voltage to 380V AC. This is rectified and filtered to produce a stable high-voltage DC.

4. **SPWM Signal Generation:**  
   The EGS002 module generates SPWM signals, which are used to drive the IGBT bridge.

5. **AC Output Conversion:**  
   The IGBT bridge converts the high-voltage DC into a sinusoidal AC output. This is filtered to ensure a clean sine wave.  

6. **Feedback Control:**  
   The voltage feedback system continuously monitors the output and adjusts the SPWM signals for stable operation.

7. **Thermal Management:**  
   The fan control circuit activates the cooling fan when the temperature exceeds a certain threshold, preventing component overheating.

---



#### **List of Materials**  

| **Quantity** | **Component**                          | **Specification**                    | **Notes**                          |
|--------------|----------------------------------------|--------------------------------------|------------------------------------|
| 1            | EGS002 Driver                          | Integrated SPWM driver module        | Main control module               |
| 4            | FGH40N65 IGBTs                         | 650V, 40A                            | Used in the IGBT bridge           |
| 1            | Inverter                               | 500W                                 | Output power rating               |
| 2            | Shunt Resistor                         | 20mΩ                                 | For current sensing               |
| 2            | Electrolytic Capacitor                 | 450V, 100µF                          | High voltage DC filtering         |
| 1            | Electrolytic Capacitor                 | 35V, 100µF                           | Voltage regulation support        |
| 2            | Electrolytic Capacitor                 | 25V, 470µF                           | Voltage stabilization             |
| 1            | L7815 Regulator                        | 15V output voltage                   | For regulated 15V supply          |
| 1            | L7805 Regulator                        | 5V output voltage                    | For regulated 5V supply           |
| 4            | HER207 Diode                           | High-efficiency rectifier            | For rectification in power stage  |
| 1            | S8050 BJT Transistor                   | NPN, 1.5A                            | Fan control circuit               |
| 1            | Potentiometer                          | 10K, 20-turns                        | Used in voltage feedback loop     |
| 4            | 1N4148 Diode                           | Signal diode                         | Snubber circuit for IGBTs         |
| 1            | Inductor                               | 2000W, 2.5mH, 10A                   | Sine wave filtering               |
| 4            | Resistor                               | 100K, 1/2W                           | For voltage feedback              |
| 1            | Choke Filter                           | Custom specification                 | Reduces EMI interference          |
| 1            | Film Capacitor                         | 100nF, 275V                          | AC filtering                      |
| 2            | Ceramic Capacitor                      | 2.2µF, 630V                          | Snubber for transformer           |
| Varies       | Through-Hole Resistors                | Per schematic values                 | Used throughout the circuit       |
| 1            | Heatsink                               | Compatible with IGBTs                | Dissipates heat                   |
| 1            | Slide Switch                           | SPST                                 | Power control                     |
| 1            | Cooling Fan                            | 40mm                                 | For thermal management            |
| 1            | Case                                   | 240mm x 120mm                        | For housing the inverter          |
| 1            | Plastic Screw                          | M3                                   | For secure mounting               |
| 1            | Rectifier Bridge                       | GBU404 or equivalent                 | High-voltage rectification        |

---
#### **PCB Details & preview**
[View in Detail](https://github.com/nithinmathewjoji/LiteWave-full-sine-wav-inverter/blob/master/PCB%20Preview/README.md)



### **Notes**  
1. **Component Sourcing:** All components should be sourced from trusted suppliers to ensure reliability and performance.  
2. **Assembly Tips:** Use appropriate heatsinks for IGBTs and regulators, and ensure proper insulation of high-voltage components.  
3. **Testing:** Test individual subsystems (e.g., voltage regulation, feedback, and driver circuits) before full assembly.  
4. **Safety:** Ensure the enclosure is non-conductive and well-ventilated for safe operation.

### **4. Advantages**
- **Pure Sine Wave Output:** Ensures compatibility with sensitive electronics.  
- **Efficient Thermal Management:** Built-in fan control for reliable operation.  
- **Feedback Stability:** Maintains consistent voltage and frequency.  
- **Modular Design:** Simplifies troubleshooting and allows for future upgrades.  

---

