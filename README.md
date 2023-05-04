# lab-2-may

## Initial config
![image](https://user-images.githubusercontent.com/49484290/236119726-f0185be2-5a13-452a-a06e-169adc8e7fd9.png)
![image](https://user-images.githubusercontent.com/49484290/236120933-d72e8d11-fe6e-4591-a20b-4a17ac161e2d.png)

## Custom configs
1. Change `Channel1` of `TIM2` to `PWM Generation CH1`:

![image](https://user-images.githubusercontent.com/49484290/236120549-6049018f-d055-40e0-a24e-827fc3633b4e.png)

2. Change `Prescaler` or `PSC` value to `15999` & `Counter Period (AutoReload Register` or `ARR` to `999`:

![image](https://user-images.githubusercontent.com/49484290/236121664-3cee57a3-dd7b-4ef6-a26d-7056bd7c5f98.png)

3. Change `Pulse` value to `500`. The Pulse's value interval ranges between 0 and `ARR` value, in our case 999. 
Pulse value of 500 represents approximatively 50% duty cycle. We can change this value to change the duty cycle. Ex: `ARR` set to `749` is 75% duty cycle, 250 is 25% duty cycle, 100 is 10% duty cycle, and so on.

![image](https://user-images.githubusercontent.com/49484290/236124419-bc3754d6-feb0-48c2-85d3-413794717d40.png)

4. Change `PA5` from `LED_GREEN` to `TM2_CH1`. This way we output the PWM signal generated from TIM2 to the LED pin.

![image](https://user-images.githubusercontent.com/49484290/236122040-89def7ea-2db4-4e75-8e6a-a06ed3faa65b.png)

5. Start the PWM channel:

![image](https://user-images.githubusercontent.com/49484290/236125160-dd0d856f-1a1d-412b-b2a0-735049f86bb8.png)

## Lessons

1. In `debug` mode. Confirm the perspective switch to the Debug perspective.
![image](https://user-images.githubusercontent.com/49484290/236126579-94b6dd88-db69-4ce4-b6cb-c6143edbee34.png)

2. Find the `CCR1` Register under `TIM2` in the `SFRs` (Special Function Registers) tab.
![image](https://user-images.githubusercontent.com/49484290/236127912-9c364392-0907-4d24-8edb-8a8d6b6fdb31.png)

3. Resume then pause the program to allow the registers to be initialized.
![image](https://user-images.githubusercontent.com/49484290/236128434-e1e04716-23bc-47f1-9ff4-e5ac31ae502e.png)
![image](https://user-images.githubusercontent.com/49484290/236128541-4e2e6157-a32e-4e8a-87f2-876cb3b6f462.png)

4. Change value formatting to be displayed in decimal.
![image](https://user-images.githubusercontent.com/49484290/236128791-1035f9bc-69ff-4025-baaa-76b646d42d7d.png)

5. `CCR1` value can be changed in the IDE. Despite the program being paused, since the PWM module of TIM2 is a hardware module, it continues to run, the changes in the register can be seen on the development board by looking at the LED. We can change `CCR1` to 100 to change the duty cycle to 10%, to 899 to change the duty cycle to 90%, etc.
![image](https://user-images.githubusercontent.com/49484290/236129417-67b873cc-c083-4adb-a307-578d96c05c4d.png)
