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

### 2.

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
