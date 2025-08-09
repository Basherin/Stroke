# Stroke Screening Algorithm

## Overview
Combined tool for:
- **Acute recognition**: BE-FAST (rapid field screening for possible acute stroke).
- **Preventive risk assessment**: Framingham-style risk factors for primary prevention.

---

## BE-FAST (use for **acute** sudden symptoms)
- **B**alance — sudden loss of balance/coordination  
- **E**yes — sudden visual disturbance or loss  
- **F**ace — facial droop (ask to smile)  
- **A**rm — arm weakness or drift (ask to raise both arms)  
- **S**peech — slurred/strange speech (ask to repeat a sentence)  
- **T**ime — if *any* sign is present, call emergency services immediately

---

## Flowchart (Mermaid)
```mermaid
flowchart TD
  Start([Person with symptoms or screening])
  AcuteCheck{"Are symptoms sudden / within hours?"}
  BEFAST["Perform BE-FAST check:
B: Balance
E: Eyes
F: Face
A: Arm
S: Speech
T: Time (call EMS)"]
  Positive{"Any BE-FAST sign present?"}
  EMS["Call emergency services
Arrange rapid transport
Activate stroke pathway (CT/MRI)"]
  NoAcute["No acute signs (or screening visit)"]
  RiskAssess["Perform preventive risk assessment
(age, BP, diabetes, smoking,
AF, CVD, LVH...)"]
  Low["Low risk: Lifestyle advice
Recheck periodically"]
  Moderate["Moderate risk: Lifestyle + primary care review
Optimize BP/DM/lipids"]
  High["High risk: Specialist referral
Consider anticoagulation if AF
Aggressive risk control"]
  End([End])

  Start --> AcuteCheck
  AcuteCheck -- Yes --> BEFAST
  BEFAST --> Positive
  Positive -- Yes --> EMS --> End
  Positive -- No --> NoAcute
  AcuteCheck -- No --> NoAcute
  NoAcute --> RiskAssess
  RiskAssess --> Low
  RiskAssess --> Moderate
  RiskAssess --> High
  Low --> End
  Moderate --> End
  High --> End
```
