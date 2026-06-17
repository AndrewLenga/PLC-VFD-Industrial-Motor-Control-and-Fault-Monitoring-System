# ⚙️ PLC-VFD-Industrial-Motor-Control-and-Fault-Monitoring-System

<div align="center">

![PLC](https://img.shields.io/badge/PLC-Omron-blue?style=for-the-badge)
![VFD](https://img.shields.io/badge/VFD-Industrial%20Drive-green?style=for-the-badge)
![Control](https://img.shields.io/badge/Control-Motor%20Automation-orange?style=for-the-badge)
![Monitoring](https://img.shields.io/badge/Monitoring-Fault%20Detection-red?style=for-the-badge)

### Industrial Motor Control • VFD Integration • Fault Monitoring • Automation Engineering

</div>

---

## 📖 Overview

This project implements a complete **PLC-VFD Industrial Motor Control and Fault Monitoring System** using **Omron PLC** programmed with **CX-Programmer**.

The system is designed to control an industrial motor through a Variable Frequency Drive (VFD) while continuously monitoring motor status, drive feedback, overload conditions, and fault conditions.

The project demonstrates industrial automation techniques commonly used in:

- Manufacturing Plants
- Conveyor Systems
- Pump Stations
- Ventilation Systems
- Material Handling Equipment
- Process Industries

---

## 🎯 Project Objectives

- Safe Motor Start/Stop Control
- Automatic Operation Mode
- VFD Run Command Interface
- VFD Feedback Monitoring
- Motor Fault Detection
- Fault Latching and Reset
- Alarm Generation
- Industrial Safety Interlocks

---

## 🏭 System Architecture

```text
                    ┌──────────────────┐
                    │   Operator HMI   │
                    └─────────┬────────┘
                              │
                              ▼

                    ┌──────────────────┐
                    │    Omron PLC     │
                    │  CX-Programmer   │
                    └─────────┬────────┘
                              │
                ┌─────────────┼─────────────┐
                ▼                           ▼

       ┌─────────────────┐      ┌─────────────────┐
       │ Fault Monitoring│      │ Alarm Handling  │
       └─────────────────┘      └─────────────────┘
                │
                ▼

       ┌─────────────────┐
       │       VFD       │
       └────────┬────────┘
                │
                ▼

       ┌─────────────────┐
       │  AC Motor Load  │
       └─────────────────┘
```

---

## ⚙️ Main Functions

### Start/Stop Control

- Start Pushbutton initiates motor operation
- Stop Pushbutton stops motor operation
- Internal run command latch maintains operation

### Auto Mode

- Auto mode selection
- Automatic motor operation
- Interlocked startup conditions

### System Health Monitoring

The system continuously checks:

- Emergency Stop Status
- Motor Overload Status
- Active Fault Status

Only healthy systems are allowed to run.

### VFD Control

The PLC sends a RUN command to the VFD.

The VFD starts the motor and returns a RUN feedback signal.

### Feedback Monitoring

The PLC verifies that the VFD feedback signal is received within a preset time.

If feedback is not received:

- Fault becomes active
- Fault is latched
- Alarm output activates

### Alarm Management

The system generates alarms for:

- Motor Startup Failure
- VFD Feedback Loss
- Motor Overload
- Active Fault Conditions

---

## 🔄 Control Sequence

```text
START PUSHBUTTON
        │
        ▼
Run Command Latched
        │
        ▼
System Health Check
        │
        ▼
Motor Run Output
        │
        ▼
VFD Receives Run Command
        │
        ▼
VFD Run Feedback
        │
        ▼
Normal Operation
```

### Fault Sequence

```text
Motor Run Command
        │
        ▼
No VFD Feedback
        │
        ▼
Timer Starts
        │
        ▼
Timer Expired
        │
        ▼
Fault Active
        │
        ▼
Fault Latched
        │
        ▼
Alarm Output
```

---

## 🧠 Ladder Logic Functions

| Function | Description |
|-----------|------------|
| Run Command Latch | Maintains motor run request |
| System Healthy Logic | Safety and permissive checks |
| Auto Mode Logic | Automatic operation selection |
| Motor Run Output | Sends run command to VFD |
| Feedback Timer | Monitors startup confirmation |
| Fault Active Logic | Detects operational faults |
| Fault Latching | Stores fault condition |
| Fault Reset | Operator reset function |
| Alarm Output | Alarm indication |

---

## 🚨 Fault Monitoring Logic

### Fault Conditions

| Condition | Action |
|------------|----------|
| Motor Overload | Stop Motor |
| VFD Feedback Failure | Activate Fault |
| Emergency Stop | Shutdown System |
| Active Fault | Disable Run Command |
| Startup Timeout | Alarm Activation |

---

## 📊 Symbol Table
---

## 📸 Project Screenshots

### Ladder Logic

```markdown
<img width="1205" height="861" alt="image" src="https://github.com/user-attachments/assets/a1e913ae-0554-4e23-9042-d60055a92700" />

```

### Symbol Table

```markdown
<img width="1405" height="980" alt="image" src="https://github.com/user-attachments/assets/321bc5d5-92bb-4695-ac0d-2819bcd9dbdf" />

```

### VFD Control Logic

```markdown
![VFD Control](Screenshots/VFDControl.png)
```

### Fault Monitoring Logic

```markdown
<img width="1157" height="512" alt="image" src="https://github.com/user-attachments/assets/2588d64f-5df9-495e-bbe2-df45d24f0722" />


```
## 🛠️ Development Environment

| Item | Description |
|--------|------------|
| PLC Platform | Omron PLC |
| Programming Software | CX-Programmer |
| Programming Language | Ladder Logic |
| Drive Type | Variable Frequency Drive (VFD) |
| Application | Industrial Motor Control |

---

## 📂 Repository Structure

---

## 🚀 Future Improvements

- HMI Integration
- SCADA Connectivity
- Alarm History Logging
- Runtime Monitoring
- Energy Consumption Monitoring
- Remote Diagnostics
- Predictive Maintenance Features

---
