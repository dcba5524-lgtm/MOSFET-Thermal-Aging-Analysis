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
- Device 14 showed the highest degradation rate among all tested devices
- Run 7 distribution collapse in Device 14 indicates
  intermittent thermal path disruption due to die-attach crack progression
## Results
### 1. Total Rds_on trend 
<img width="2229" height="1180" alt="Image" src="https://github.com/user-attachments/assets/21fd63db-bd29-49cf-a2aa-17ebd5e130a0" />

- Figure X shows Rds(on) Run and Figure average Rds(ON)value of each device at each cycle, illustrating the thermal degradation process.

### 2. The highest Rds_on value 
<img width="1479" height="880" alt="Image" src="https://github.com/user-attachments/assets/be94964b-d9de-4840-b388-1634ac7c252f" />

- Device 12 shows the highest Rds(on) increase among all tested devices, indicating more severe thermal degradation

### 3. Rds_on increase rate
<img width="1179" height="730" alt="Image" src="https://github.com/user-attachments/assets/ac370bcf-3f54-40bc-84e7-9d347f629b79" />

- The lowest (Run 4) and highest values (Run 7) were captured
- The percentage increase was calculated to compare the extent of thermal degradation among the devices.

### 4. Rds_on increase rate

## Analysis Process
1. Data preprocessing - ON state filtering (supplyVoltage ≥ 3.5V, drainCurrent ≥ 0.5A)
2. Rds_on trend visualization per device
3. Quantification of degradation rate per device
4. Deep dive analysis on Device 14 (boxplot + Rds_on vs Temperature overlay)

## Tools
Python, Pandas, Matplotlib

## Data Source
NASA Prognostics Data Repository  
https://www.ti.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/
