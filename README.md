# Materials

- 3 pack of [esp32 controllers](https://www.amazon.com/ESP-WROOM-32-Development-Microcontroller-Integrated-Compatible/dp/B08D5ZD528/ref=sr_1_1?dib=eyJ2IjoiMSJ9.XBINg-sjhfF_gUtnMiKGjk-Cz998LZHcErnfMs35F-CdZb2KPa6mWS0zP-jB9fYmyv_GiikbENWw9Ty1F-b59u-5exgzrkbNP86wAC3pIldDOXva0Ujy6yOESwy8PRvhP6cX59MvWsxciJd9j3QPT6MvVx80leTZiXHMLPG1KLTnIdbPXFBGNaAiqHTWSoVbHQCyNwPe2FciF8RuuxI18bshwwHJaAhsHDMdDL9Vy4c.wAQEsVc1Z2ss2ZxftejkXBa0_LKOBlDTUX_IUU4rfSo&dib_tag=se&hvadid=695492812229&hvdev=c&hvexpln=67&hvlocphy=9033310&hvnetw=g&hvocijid=6801781420292322874--&hvqmt=e&hvrand=6801781420292322874&hvtargid=kwd-850628270119&hydadcr=24328_13533848&keywords=amazon%2Besp32&mcid=28303f1fc2c2315b89a7ecc1cbc80d09&qid=1742331884&sr=8-1&th=1) (you only need one, but having a spare is a good idea just in case
- A micro usb cable to plug into the ESP32 - but it needs to have data capabilities, ive found that many micro usb cables just do charging 
- Soldering iron + solder + "helping hands" - I have a cheapo $8 iron and it works fine. [A kit may be cheaper than buying separate](https://www.amazon.com/dp/B09HXD4L14). The little clampy "helping hands" are basically required unless you have a LOT of patience. 
- [5 meters of WS2812b LED strip](https://www.amazon.com/dp/B088FJF9XD?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_3&th=1) at 60 LED's per meter. 
- [A power supply](https://www.amazon.com/dp/B0BV64MHY6?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_2) - I've found using a 5 volt strip works really well, because the ESP32 also takes 5 volts - so you dont have to fool around with converting it inside the sign. if you were planning on making a very big sign - bigger than the COOPER one you saw, you might consider getting a [bigger power supply like this](https://www.amazon.com/dp/B0CH79ZCZC?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_6).  But for SAINT - you need 3 amps or more
- A [button](https://www.amazon.com/DIYhz-AC250V-AC125V-Momentary-Button/dp/B07BD1XKF4/), a [switch](https://www.amazon.com/ZUPAYIPA-Solder-Rocker-Switch-Toggle/dp/B01N2U8PK0), a [barrel connector](https://www.amazon.com/Antrader-24pcs-Female-Socket-Connector/dp/B07CTCLKPP) for power - I have a ton of these I can drop a couple of each into the mail for you if you shoot me your address
- [Some small wires](https://www.amazon.com/Elegoo-EL-CP-004-Multicolored-Breadboard-arduino/dp/B01EV70C78) (Dupont Wires) to connect everything together - having multiple colors is helpful
- Wire strippers - any kind will do, but [these](https://www.harborfreight.com/8-in-self-adjusting-wire-stripper-70291.html) are pretty slick
- [Digital Calipers](https://www.amazon.com/Neiko-01407A-Electronic-Digital-Stainless/dp/B000GSLKIW) - Super useful for measuring buttons / thicknesses, etc.

# Build

## 1: WLED Install

1. Take your esp32, plug the micro usb (with data) into the controller, and your computer.
2. Goto [https://install.wled.me/](https://install.wled.me/) . 
3. Use the latest version (currently 15.0), plain, and click install. 
4. It should ask you to select a device - usually something like COM4. If you have multiple of these you may need to unplug some stuff or just guess/check.
5. The install process takes a couple minutes
6. Follow the prompts to navigate to the WLED dashboard
7. From there get [your wifi setup](https://kno.wled.ge/basics/getting-started/#wifi-setup)

## 2: LED Test

1.  You'll need to get power and data to the LED strip, and power to the ESP32. Typically, I will take the little screw terminal that comes with the power supply and plug in two ground wires and two positive wires, and then use the little female attachments on the wire to plug into the VIN and GND pins on the controller. 
2. Using the other set of power and ground from the power supply screw terminal, attach to the power/ground on the led strip. I usually just twist them together and electical tape them (solder later)
	1. NOTE - look at the "data" label on your led strip - confirm that you are "pushing" the power in - you want the power and data to "flow" in the direction of the arrow. it WILL NOT work the other way
3. Attach one of the dupont wires from the ESP32 pin labeled "RX2" and connect it to the data (green) wire of the LED strip. 
4. Power everything on. You should see the first 30 LEDs light up. If they dont, check:
	1. Power - make sure both the ESP32 and Strip are power/ground
	2. Data - make sure all connections are solid
	3. Data out pin - If you're using a different ESP32 - the data out pin may be different - by default you want GPIO16 - sometimes called IO16. If you suspect this is the case, google "ESP32 Pinout" in google images and find a schematic that lines up with the labeled pins on your board, then find the GPIO16 pin and switch the data out wire to that pin.
	4. WLED configuration - open up the WLED app and make sure that the light is actually on. Try changing the colors or effects as well

So, you have the lighting part pretty well set at this point. On to Modelling

## 3: Modelling

1. [https://www.youtube.com/watch?v=3Mkf67_ZnEM](https://www.youtube.com/watch?v=3Mkf67_ZnEM) - I turned closed captioning on for this one - this was the main tutorial for handling most of the modeling.
	1. I used https://www.dafont.com/newyear-goo.font "newyear goo" as the font, but there are many others 
	2. If you want to get more control over letter spacing and rotation, [Inkscape](https://inkscape.org/) is a good free program that worked for me - Im not sure this is strictly needed, but it is a lot easier to play with the shapes here than in fusion.
	3. Since you're dealing with kind of finicky offsets and stuff in fusion, starting with the right size letters makes a difference. I used ~6" (150mm) as the size for that cooper/ben one and I think that was the right size. I believe that will fit on your printer
	4. use MORE than 13mm for the passthroughs (8:49 in) - this needs to be at least 5mm more than the width of your strip - or its very very frustrating to thread the strip.
2. When you're modelling - make absolutely sure to keep each letter as a separate body. You'll need to print them individually.
3. The step in the model where you reduce the thickness of the wall of the "lens" (10:30 in the video) is very very sensitive. This controls how "tight" the lens feels when you slide it in. I'd start with what they recommend in the video, but try a test first with one letter/lens before printing all of them and be prepared to tweak that value.
4. I modeled in 4 additional features that helped a lot that you might consider. I would say the Button, Switch, and Power plug are basically essential - you wont want to open the app to change the colors, and definitely wont want to open the app to turn it on/off. I left these off the first couple I made and severely regret it. 
	1. A hole for the push button on the top of the first letter
	2. A hole for the rocker switch on the back of the first letter
	3. A set of "prongs" that line up with the ESP32 holes in the corner to hold it in place 
	4. A progressive step down in the height of the letters
		1. This is in contrast to what is shown in the video at 9:55
		2. This allowed me more depth in the first letter. Since you're holding all your wires controller in the first letter, you need to ensure that NONE of the wires are hanging above the level of your LED strip. Even by a little bit. It will absolutely cast shadows and wreck the effect. 
		   So to give myself the room, I model all the letters at a normal height (45mm), then I make each letter 3mm taller, starting from the end. This creates a kinda cool looking offset on the face of the letters which accentuates the effect, but still keeps the back flat in case you want to hang on a wall or something so for instance 
		   S  - 57mm
		   A - 54mm
		   I - 51mm
		   N - 48mm
		   T - 45mm
		   You have an extra 12mm to help hide wires and whatnot on the S
5. Here is the [COOPER lamp](https://drive.google.com/file/d/1jMSK0Cl9lNf0YewP2eP6GYcCUbMBdHAZ/view?usp=sharing) Fusion file - In there there is the ESP32 standoff component - if you want to just copy/paste that instead of measuring - it should work. Maybe print that by itself really quick just to confirm

## 4: Initial Assembly

1. I just super glued the letters together - nothing special. Just align the holes in the letters that let the LED strip through
2. Consider which direction the LED strip should go, lots of WLED effects start at the beginning. I like to put it in the bottom left of the first letter and run it along the bottom of the letters first, but theres no right way.
3. The strip can be bent around very very tight corners if needed without breaking
4. I didnt put any lighting around the the little islanded part of the "A" "P", "R", etc. I just run along the outer perimeter and it looks great
5. I add super glue dabs all along the strip after I got it all in place, the glue doesnt like to hold in the sharper corners especially.

## 5 Final Assembly/Config

1. https://www.youtube.com/watch?v=uU7sucuoowc  Watch this whole video before you start the final button/switch soldering - the pinout for the board I linked is [here](https://myhomethings.eu/wp-content/uploads/2024/02/ESP32-30pin-Develeopmen-Board-1-2048x1114.webp) 
	1. I like to get this all running on the bench first before installing into the sign and soldering everything in place
2. If you want to use the presets and config I was using:
	2. https://drive.google.com/file/d/1Z74hxr4oetYn9aufC2bsm_3xvuhenn3c/view?usp=sharing
	3. https://drive.google.com/file/d/1MIObKg1dRt3G30v6T7FoP54sHv9s8jX2/view?usp=sharing
	4. Rocker switch goes to D5 (GPIO5)
	5. Push Button goes to TX0 (GPIO1)
3. From there - its just a matter of slotting the button/switch/power into place, and soldering everything up.
	1. I like to use a common ground off of the power plug, not the board
	2. I try to wire up the leads on the button and switch before I insert them into the sign
	3. Generally speaking the more you can solder outside the sign, the less frustrating it is
	4. My dad swears by[ this kinda thing](https://www.amazon.com/YOCTOSUN-Rechargeable-Magnifying-Professional-Interchangeable/dp/B07T4KPYN2?th=1) but I think a good lamp is enough. 
	5. Consider where the controller will be secured inside the letter before cutting the wires, leaving some slack is a good idea, but too much will make it difficult to manage.
	6. Ive hot glued the controller down, but if you use the little standoffs in the print, you can just poke the plastic prongs with the soldering iron it melt it into place - pretty cool
	7. If you're going to use the little nut that secures the button and barrel plug into place, be sure to thread your wires through that BEFORE YOU SOLDER - ask me how i know :)

**The end!**
