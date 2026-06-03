⭐ **1. Introduction**

Modern commercial vehicles are equipped with a wide range of Driver Assistance Systems (DAS) designed to improve vehicle safety, stability, and operational efficiency. Advances in Model-Based Development (MBD) and vehicle dynamics simulation enable these systems to be developed, calibrated, and validated in virtual environments across a broad spectrum of real-world driving scenarios before deployment to production hardware.

This project focuses on the development of multiple DAS functionalities within the Electronic Braking System (EBS) architecture of commercial vehicles using MATLAB/Simulink. In addition, an automated Verification & Validation (V&V) framework is implemented to execute simulation-based test campaigns, evaluate system performance, and generate validation reports through co-simulation workflows.

<table>
  <tr>
    <td align="center">
      <b></b><br>
      <img src="VV_intro.gif" width="700"/>
    </td>
  </tr>
</table>

---

🔒 **2. Project Availability & Confidentiality**

This project was developed in collaboration with a leading German commercial vehicle OEM. Due to confidentiality agreements and the proprietary nature of the MATLAB/Simulink and IPG TruckMaker models, the original implementation, simulation assets, calibration data and test environments cannot be publicly shared.

To demonstrate the technical scope of the work, this repository provides system architecture diagrams, workflow illustrations, pseudo-codes  , validation methodologies, and conceptual dashboards that mirror the development and testing process. The objective is to showcase practical experience in Systems Engineering, Model-Based Development (MBD), co-simulation, and automated V&V workflows while fully respecting intellectual property and confidentiality requirements.

---

⚙️ **3. Service Brake System (SBS)**

**Input**
- Driver deceleration demand  
- Vehicle configuration parameters  

**Output**
- Brake pressure demand per wheel 

**Function** <br>
Computes required braking performance by translating driver deceleration demand into brake force level (BFL) and brake force distribution (BFD), including trailer braking coordination. Generates wheel-level brake pressure requests for downstream EBS actuation.

---

⚙️ **4. Traction Control System (TCS)**

The TCS is structured into three core control functions within the vehicle dynamics control architecture: Engine Control, Brake Control, and Drag Torque Control.

**Input**
- Driven and non-driven wheel speeds  
- Vehicle speed and acceleration state  
- Road friction estimate (μ / “mu”)  
- Differential lock status  
- Gear shift / driveline state  

**Output**
- Engine torque reduction request  
- Individual wheel brake pressure (selective braking)  
- Engine torque increase request (drag torque compensation)  

**Function**
Prevents wheel slip and instability during low-μ or split-μ driving conditions by coordinating engine torque and brake interventions. Compares wheel speed differentials across axles to detect slip, then applies engine torque limitation, selective wheel braking (active up to ~40 km/h), or drag torque compensation during downshifts to maintain traction and vehicle stability.

---


