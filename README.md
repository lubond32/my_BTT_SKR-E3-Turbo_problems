### Here is described fatal problem with my new 3D printer board

Boadr: <code>BTT_SKR-E3-Turbo</code>

A problem:
TMC2209 reserved for X axis has stopped working.

About 2 months ago I bought 2 pieces of BTT SKR-E3-TURBO control boards through your e-shop. I used one of them in my 3D printer (Anet A8 Plus). But today, after about a month of normal use, the X-axis driver has stopped working.

Fault description:
Although the XC2209 X-driver communicates (tested with 'M122' - TMC Debugging Marlin's code), but the motor does not even move. Rewiring or switching to another stepper motor did not help. Remapping in Marlin FW to another driver  works well (TMC2209 dedicated to E1 e.g.), this confirms that the problem is not software but it is a problem of the TMC2209 chip.

My additional experience:
During 1 month of operation, it often happened to me that after the printing restart, the mother board got to a state where the driver did not remember its settings and had to be reset manually, then the board worked normally again.

It also sometimes happened to me (not during the printing) that the board seemed to react to 'an ESD event'. When touching the grounded frame of the printer, the motors (or one of the motors) jerked suddenly, and with the subsequent 'home' command the motor moved out in unpredictable direction and speed, altso the board did not respond to the limit switches (Stall Guard function in TMC2209). Subsequently, I read the content of the TMC's registers ('M122' Marlin's command) and I found that drivers were set to their defaut factory settings. This proves the fact that an internal reset has occurred in the TMC. Only after the master reset the firmware restored the correct registry settings.

I note that I am a professional electrical engineer, I have been designing similar control boards for many years. I strictly follow all the principles of working with ESD sensitive devices.

Solution:
Can you please advise me what can be done with that broken board? Can you repair or replace the defective board under warranty?

Unfortunately, the TMC2209-LA stand-alone circuits are not available worldwide at this time, otherwise I could be able to replace broken chip myself.

Post scriptum:
Recently I bought 2 pieces of your new Biqu H2 V3 extruder for my 3D printers, also through your e-shop. And I must say that I am extremely satisfied with them, I have never operated a better extruder. Biqu H2 was a real success for you, I wish you more such successful projects.
Regarding the SKR-E33-Turbo board, I hope it is not a systematic error but just an accidental failure. 
