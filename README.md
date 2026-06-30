# MOSFET-Thermal-Aging-Analysis

## Overview
This project analyzes MOSFET degradation patterns under thermal stress
using the NASA Thermal Overstress Aging dataset.
The goal is to identify Rds_on degradation trends and connect them
to physical failure mechanisms.

## Key Findings
- OFF state noise filtering was required for accurate Rds_on calculation
- All devices showed a common inflection point around Run 4,
  after which degradation accelerated
- Device 12 showed the highest degradation rate among all tested devices
- Run 7 distribution collapse in Device 12 indicates
  intermittent thermal path disruption due to die-attach crack progression
## Results
### 1. Total Rds_on trend 
<img width="2229" height="1180" alt="Image" src="https://github.com/user-attachments/assets/21fd63db-bd29-49cf-a2aa-17ebd5e130a0" />

- Y-axis shows Rds(on) Run and Figure average Rds(ON)value of each device at each cycle, illustrating the thermal degradation process.

### 2. The highest Rds_on value 
<img width="1479" height="880" alt="Image" src="https://github.com/user-attachments/assets/be94964b-d9de-4840-b388-1634ac7c252f" />

- Device 12 shows the highest Rds(on) increase among all tested devices, indicating more severe thermal degradation

### 3. Rds_on increase rate
<img width="1179" height="730" alt="Image" src="https://github.com/user-attachments/assets/ac370bcf-3f54-40bc-84e7-9d347f629b79" />

- The lowest (Run 4) and highest values (Run 7) were captured
- The percentage increase was calculated to compare the extent of thermal degradation among the devices.
  
<img width="1179" height="730" alt="Image" src="https://github.com/user-attachments/assets/29144e66-38bf-4bec-ade2-69febf2cb83c" />

### 4. Rds_on from Device 12 Distribution
<img width="1479" height="855" alt="Image" src="https://github.com/user-attachments/assets/b2b53515-844a-464a-83c7-a3f713196e15" />

- For Device 12, Rds_on remains tightly distributed across runs 1 through 6, with narrow IQRs centered around 1.5–2Ω, indicating stable and repeatable on-state resistance.
- In run 7, however, the distribution widens dramatically — the IQR expands to roughly 2–6Ω with a maximum exceeding 10Ω — while the median stays comparable to earlier runs.

### 5. Correlation with Rds_on and PackageTemperature on Device 12
<img width="786" height="487" alt="Image" src="https://github.com/user-attachments/assets/29cf9d62-e90d-4313-81cf-50e1407d9c48" />

- The test setup has no heatsink, so heat builds up inside the device instead of escaping.
- This means the case temperature measured is likely much lower than the real temperature inside the chip.
- This setup looks like an intentional worst-case test, designed to stress the device as much as possible and cause failure faster, rather than represent how the device would   normally operate in the field.

### 6. Correlation with Rds_on and PackageTemperature all devices
<img width="1487" height="787" alt="Image" src="https://github.com/user-attachments/assets/93c31c61-c2b0-4ecf-acc3-df9b99cf8ba1" />

- From run 1 to run 4, Rds_on and case temperature drop together, which looks like correlation but is likely coincidental — both values happen to follow the early test ramp-down.
- it simply does not capture the real thermal stress driving the degradation at the junction.


## Analysis Process
1. Data preprocessing - ON state filtering (supplyVoltage ≥ 3.5V, drainCurrent ≥ 0.5A)
2. Rds_on trend visualization per device
3. Quantification of degradation rate per device
4. Deep dive analysis on Device 12 (boxplot + Rds_on vs Temperature overlay)

## Tools
Python, Pandas, Matplotlib

## Data Source
NASA Prognostics Data Repository  
https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/

13 Metal-Oxide-Semiconductor Field-Effect Transistor (MOSFET) Thermal Overstress Aging
Data Set Citation: J. R. Celaya, A. Saxena, S. Saha, and K. Goebel “MOSFET Thermal Overstress Aging Data Set”, NASA Prognostics Data Repository, NASA Ames Research Center, Moffett Field, CA
Publication Citation: J. R. Celaya, A. Saxena, S. Saha, and K. Goebel, “Prognostics of Power MOSFETs under Thermal Stress Accelerated Aging using Data-Driven and Model-Based Methodologies,” in the Proceedings of the Annual Conference of the Prognostics and Health Management Society, (Montreal QC, Canada), September 2011.
