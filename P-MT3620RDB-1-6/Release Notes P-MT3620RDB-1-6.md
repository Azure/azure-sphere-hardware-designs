Changes between v1.0 -> v1.6

- The 3.3V voltage regulator has been changed to a new part: TLV62569DBVR 
- The RTC battery circuit has been changed such that when the main 3.3V supply is present, 
  this will supply the RTC, even when a coin cell has been installed in the board's battery 
  holder. When a battery is present and the main 3.3V supply is disconnected, the RTC will 
  then be powered from the battery. Switch over between the main 3.3V supply and the battery
  happens automatically.
- The PMU_EN signal is now pulled low by default (R42). This change allows software to enable the MT3620 RTC low power mode.