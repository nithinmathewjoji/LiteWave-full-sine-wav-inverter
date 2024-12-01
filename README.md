# LiteWave-full-sine-wav-inverter-
![LiteWave_1-transformed](https://github.com/user-attachments/assets/41e0301e-12b0-4001-9d77-e6e19f5a4edd)



### **README for Full Sine Wave Inverter (EGS002 v2)**

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
4. [Advantages](#4-advantages)  

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

### **4. Advantages**
- **Pure Sine Wave Output:** Ensures compatibility with sensitive electronics.  
- **Efficient Thermal Management:** Built-in fan control for reliable operation.  
- **Feedback Stability:** Maintains consistent voltage and frequency.  
- **Modular Design:** Simplifies troubleshooting and allows for future upgrades.  

---

