
At first: I sincerely hope the inconveniences described here is not a systematic problem, but just a random manufacturing failure.  Perhaps ...

> __Incriminated controll board__  
<code>BTT_SKR-E3-Turbo</code>, product link 
<a href="https://www.biqu.equipment/products/btt-skr-v1-4-skr-v1-4-turbo-32-bit-control-board-with-tft35-v3-0-e3-v3-0-screen-with-tmc2208-tmc2209-driver-board?_pos=1&_psq=SKR-E3-Turbo&_ss=e&_v=1.0&variant=31917893124194">was here</a>  

- Wow - 'Page not found' !
- Does it mean "product discontinued" ? Quite soon ...
- Maybe it indicates something ...

<picture>
  <source media="(min-width:650px)" srcset="https://github.com/lubond32/my_BTT_SKR-E3-Turbo_problems/blob/main/picture.png">
  <source media="(min-width:465px)" srcset="https://github.com/lubond32/my_BTT_SKR-E3-Turbo_problems/blob/main/picture.png">
  <img src="https://github.com/lubond32/my_BTT_SKR-E3-Turbo_problems/blob/main/picture.png" alt="Flowers" style="width:auto;">
</picture>




So at least link to BTT's github, maybe still it works:  
https://github.com/bigtreetech/BIGTREETECH-SKR-E3-Turbo  

  
> __What's a problem?__  
<code>X-stepper driver does not work.</code>  <br>  

One Trinamic driver chips has stopped working. It communicates (with processor) but does not source the stepper motor.  

I bought two BTT SKR-E3-TURBO control boards at https://www.biqu.equipment/ eshop, about 2 months ago. I used one of them in my 3D printer (Anet A8 Plus). But today, after about a month of normal use, the X-axis __driver has stopped working__. It occured suddenly, after 

> __Fault description__  

Although the XC2209 X-driver communicates (tested with 'M122' - TMC Debugging Marlin's code), but the motor does not even move. Rewiring or switching to another stepper motor did not help. Remapping in Marlin FW to another driver  works well (TMC2209 dedicated to E1 e.g.), this confirms that <code>the problem is not software, it is problem of the TMC2209 chip</code>.

> __The first hints__  

- During 1 month of operation, it often happened after the printing restart that the mother board got to a state where the driver did not remember its settings and had to be reset manually. After the board reset it worked normally again.

- Also, it sometimes happened to me (but not during the printing) that the board seemed to react to 'an ESD event'. When touching the grounded frame of the printer, the motors (or one of the motors) jerked suddenly, and with the subsequent 'home' command the motor moved out in unpredictable direction and speed, altso the board did not respond to the limit switches (Stall Guard function in TMC2209).

- Subsequently, I read the content of the TMC's registers ('M122' Marlin's command) and I found that drivers were set to their defaut factory settings. This proves the fact that an internal reset has occurred in the TMC. Only after the board reset the firmware restored the correct registry settings.

> NOTE  
I am a professional electrical engineer, I have been designing similar control boards for many years. Of course I strictly follow all principles of working with ESD sensitive devices.

So  what now?

> __Possible solutions__  

Dear BQIQU EQUIPMNETS, Can you please advise to me what can be done with that broken board? Can you repair or replace the defective board under warranty?

Unfortunately, the TMC2209-LA stand-alone circuits are not available worldwide at this time, otherwise I could be able to replace broken chip myself.

Post scriptum:
Recently I bought 2 pieces of your new Biqu H2 V3 extruder for my 3D printers, also through your e-shop. And I must say that I am extremely satisfied with them, I have never operated a better extruder. Biqu H2 was a real success for you, I wish you more such successful projects.
Regarding the SKR-E33-Turbo board, I hope it is not a systematic error but just an accidental failure. 
