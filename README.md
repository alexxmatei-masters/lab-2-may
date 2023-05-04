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
