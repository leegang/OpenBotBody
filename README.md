
# OpenBot: Robot Body
[简体中文](/中文版说明.md)

We have designed a body for a wheeled robot which relies on low-cost, readily available hobby hardware. 
![Assembly](/images/assembly.gif)

## 3D printed chassis
You will need to print the following parts in order to build your OpenBot. 
1) body_bottom ([STL](body_bottom.stl), [STEP](body_bottom.step))
2) body_top ([STL](body_top.stl), [STEP](body_top.step))
3) phone_mount_bottom ([STL](phone_mount_bottom.stl))
4) phone_mount_top ([STL](phone_mount_top.stl))

On an Ultimaker S5, we achieved good results with the following settings:
- layer height: 0.2mm
- wall thickness: 1.5mm
- infill density: 20%
- infill pattern: grid
- print speed 80 mm/s
- no support

We were able to print the chassis with PLA, ABS and CPE. In our experience the print was not affected very much by the print settings. However, if you have the patience, printing slower and with smaller layer height will improve the print. Also adding a support structure can improve the print, but it will require additional work to remove afterwards.

Since a lot of common 3D printers have a smaller build volume, we have also made a [body_bottom_slim.stl](body_bottom_slim.stl) and [body_top_slim.stl](body_top_slim.stl) which fit on a 223x223 build plate at 45 degrees. These have not been tested, but should work fine.

## Bill of materials
You will need the following components.
- 4x TT motors with tires ([<$2](https://s.click.aliexpress.com/e/_d9leRia) )
- 1x L298N Motor Driver ([$ 1.34](https://s.click.aliexpress.com/e/_dZaQCaI))
- 1x Arduino Nano ([< $ 2](https://www.aliexpress.com/item/32647196840.html?spm=a2g0o.productlist.0.0.4fc0c98fL3tVJG&algo_pvid=3f03ed1f-a5df-460d-8d5b-61f7fdd7a26b&algo_expid=3f03ed1f-a5df-460d-8d5b-61f7fdd7a26b-3&btsid=0b86d80215987092423996118e7530&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_ ))
- 2 x Speed Sensor ([< $2](https://www.aliexpress.com/i/32990256417.html))
- 3x 18650 battery ([< $5](https://s.click.aliexpress.com/e/_dSw0T3y))
- 1x 18650 battery holder([<$5 ](https://www.aliexpress.com/item/33037738446.html?spm=a2g0o.productlist.0.0.5c602568XlNOGM&algo_pvid=b667d7dc-7798-4fbc-8fbc-760fd4ebc4ef&algo_expid=b667d7dc-7798-4fbc-8fbc-760fd4ebc4ef-0&btsid=0bb47a2215986864956914727e0253&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_))
- 1x USB OTG cable ([< $5](https://s.click.aliexpress.com/e/_dWhjoMa))
- 1x spring or rubber band ([< $2](https://s.click.aliexpress.com/e/_dSINmUw))
- 16x M3x25 screw ([< $5](https://www.aliexpress.com/item/32850849521.html?spm=a2g0o.productlist.0.0.605d7959tDbcCu&algo_pvid=e2d60094-7a8a-46b2-b6df-ff08abecadfa&algo_expid=e2d60094-7a8a-46b2-b6df-ff08abecadfa-0&btsid=0bb47a2215986878981485610e029a&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_))
- 16x M3 nut ([< $1](https://www.aliexpress.com/item/32977174437.html?spm=a2g0o.productlist.0.0.4ecb4db1RlFaMC&algo_pvid=5227fb58-7578-4afd-af6b-bd2583ae0bcd&algo_expid=5227fb58-7578-4afd-af6b-bd2583ae0bcd-0&btsid=0b01114515986880925225032e85af&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_))
- 6x M3x5 screw ([<$2](https://s.click.aliexpress.com/e/_dY4nr7G))
- Wires ([< $2 ](https://s.click.aliexpress.com/e/_dXC79zg))

(Optional)
- 1x Ultrasonic Sensor ([< $1](https://s.click.aliexpress.com/e/_dZ2LZJ4))
- 1x On/Off Switch ([< $1](https://www.aliexpress.com/item/1000005699023.html?spm=a2g0o.productlist.0.0.1a6c7fb71FhAHs&algo_pvid=aecb292e-471e-4598-99f5-4f74161ddd75&algo_expid=aecb292e-471e-4598-99f5-4f74161ddd75-1&btsid=0bb47a1a15986883373795667e47f9&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_))
- 2x Orange LED 5mm ([< $2](https://s.click.aliexpress.com/e/_d8cjMy2))

## Build instructions
1) Connect wires to the motors if neccessary
2) Insert the positive and negative leads of two motors into OUT1 (+) and OUT2 (-) of the L298N board
3) Insert the positive and negative leads of the other two motors into OUT4 (+) and OUT3 (-) of the L298N board
4) Mount the L298N with four M3x5 screws and the motors with eight M3x25 screws and nuts
5) (Optional) Install the ultrasonic sensor and orange LEDs
6) Mount the bottom of the phone mount to the top plate using two M3x25 screws and nuts
7) Insert the top of the phone mount and install the spring or rubber band
8) Mount the speed sensors with one M3x5 screw each
9) Install the battery case (e.g. velcro)
10) (Optional) Insert the on/off switch
11) Connect the PWM inputs of the L298N to pins D5, D6, D9 and D10 of the Arduino
12) Connect the speed sensors and ultrasonic sensor to 5V and GND
13) Connect D0 of the speed sensors to pins D2 (left) and D3 (right) of the Arduino
14) Connect Echo and Trigger of the ultrasonic sensor to pin D4 of the Arduino
15) Connect the USB cable to the Arduino and route it through the top cover
16) (Optional) Connect the LEDs to pins D7 (left) and D8 (right) of the Arduino and GND
17) (Optional) Connect the voltage divider to pin A7 of the Arduino
18) Connect the battery cables to Vin of the L298N. If you installed the switch, put it in the current path.
19) Insert six M3 nuts into the bottom plate and mount the top cover with six M3x25 screws
20) Install the wheels
