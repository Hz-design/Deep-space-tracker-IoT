# Deep-space-tracker-IoT
This is a technical manual for the Internet of Things product "Deep Space Tracker". In this document there'll be tutorials, how to implement internet in this object to reach a certain level of IoT. Things like communicating the application to the cellphone and more. In this document the focus are on occuring errors and trying different programs. The goals is to document the errors and maybe I am able to solve them, please continue to find out!

*Last update 27th of October 2022 02:23, work in progress*
*By Hong Zhou*

## What is a Deep Space Tracker?
The deep space tracker is a smart tripod which helps the user capture, track or observe the deep space objects in the universe. Why it's an IoT? It reacts on voice commando's, You can get perfect camera setting from the hive mind feature, It can add obserable universe events to your google calendar, It's able to read the weather and tell the user how the weather is for today (is it good for shooting yes/no) and last but not least Automized tripod through the application. The user can select an object and the tripod will automatically locate the object and capture it with perfect settings for a certain amount of time.

# Inhoudsopgave
- Automizing Tripod through telegram
- Voice to commands
- News API showing on telegram
- Adafruit Hive mind
- Telegram and google Calendar
- Weather API

## Automizing Tripod through telegram
Executing outputs in Arduino from reading Telegram inputs.

[Check out this tutorial](https://github.com/Hz-design/IoT_eps32_Telegram_outputs-Arduino-IDE-)

## Voice to commands 
Activitating inputs from sensors after that reading it in serial monitor and executing a different output from node mcu.

## News API showing on Telegram
Connecting API in Node MCU, When a certain condition has met show it in Telegram bot.

## Telegram Hive mind
Sending something to telegram and telegram sents a better version back to the serial monitor.

## Telegram and google calendar
Connecting the api in telegram, for certain conditions add it to your calendar.

<details>
  <summary>Pipedreams - Integrating the Google Calendar API with the Telegram Bot API (failed)</summary>
  
  ### Integrating the Google Calendar API with the Telegram Bot API
  1.  Click on [Pipedream](https://pipedream.com/apps/google-calendar/integrations/telegram-bot-api) for popular ways to connect google calendar and Telegram bot.
  2. Select Create Trigger > New messages update (instant)
  3. follow the instructions on creating a new Telegram bot
  
  ![Telegram_BotFather](https://user-images.githubusercontent.com/70894669/197772306-53215806-586d-4365-913a-bbbf970b44a8.gif)

  4. After generating your bot you'll gain acces to your bot token, place the token in the input form.
<img width="688" alt="Schermafbeelding 2022-10-25 om 14 34 51" src="https://user-images.githubusercontent.com/70894669/197774246-b68ce2ec-db14-48e3-b66a-15d86b3be0bb.png">

  5. type "/start" in your bot chat, after that you'll see a instant notification on your pipedreams window:
  <img width="778" alt="Schermafbeelding 2022-10-25 om 14 41 53" src="https://user-images.githubusercontent.com/70894669/197775754-d0d5a096-ea4f-4d49-b52e-be7eb3f56faf.png">

  6. Press on the "plus" button and add a step
  7. Search voor Google calendar and look for the "update event" action.
  8. Fill in your your own gmail.
  9. I made a new account on google to be an imposter for deep space tracker company.
  10. Made some appointments from for the calendar
  11. filled in the information
  <img width="725" alt="Schermafbeelding 2022-10-25 om 15 17 27" src="https://user-images.githubusercontent.com/70894669/197783487-f0e9bc4f-7faa-45a4-a11a-62fe38264d0d.png">
  12. got an error:
  <img width="1043" alt="Schermafbeelding 2022-10-25 om 15 16 01" src="https://user-images.githubusercontent.com/70894669/197783212-82a901fa-803e-4fd3-af52-c17b9a06360b.png">
  13. Not continuing on this programm, on to the next programm. I couldn't understand what went wrong. Couldn't find anything helpful on google..
<img width="695" alt="Schermafbeelding 2022-10-25 om 15 18 21" src="https://user-images.githubusercontent.com/70894669/197783700-495d4803-a7e6-425c-a855-a946b8ed90ad.png">
</details>

<details>
  <summary>Business automated medium - Create Google Calendar events from new telegram messages (failed)</summary>
  
### Create Google Calendar Events From New Telegram Messages
>[source](https://business-automated.medium.com/create-google-calendar-events-from-new-telegram-messages-4f5930f224aa)
  
1. Follow the instructions described at the [source](https://business-automated.medium.com/create-google-calendar-events-from-new-telegram-messages-4f5930f224aa)
2. An error occured it wouldn't connect and it's not giving me any feedback or what so ever.
<img width="1301" alt="Schermafbeelding 2022-10-25 om 15 32 22" src="https://user-images.githubusercontent.com/70894669/197787686-15bfcb16-a106-41c1-a1dd-49a92accd6e6.png">
3. After filling out the information: 
 <img width="443" alt="Schermafbeelding 2022-10-25 om 15 35 19" src="https://user-images.githubusercontent.com/70894669/197788165-9c31cd8c-b204-4a90-be81-5ac365241d79.png">
 <img width="1301" alt="Schermafbeelding 2022-10-25 om 15 32 22" src="https://user-images.githubusercontent.com/70894669/197788202-0b9df2cd-f636-46d8-9ceb-c5468cea0337.png">
It would stay on this screen for a long time so it seems like it's not working properly.
  
4. After that I tried deleting the inputs 'Full Moon', '25.10.2022', '26.10.2022' and it couldn't read the parameters:
<img width="803" alt="Schermafbeelding 2022-10-25 om 15 36 24" src="https://user-images.githubusercontent.com/70894669/197788533-6d1d3148-6823-467e-97ca-a2825c59216b.png">

So I stopped with this method and went on.

</details>

## weather API
Connecting the API to your node mcu, The weather API gives conditions to the eps32 and with lights it will show if the weather is good enough for camera weather.

<details>
  <summary>ESP8266 Weather Forecaster (almost but failed)</summary>

### Esp8266 Weather Forecaster
>[Source](https://randomnerdtutorials.com/esp8266-weather-forecaster/)
In this tutorial we'll use Open weather map API to generate lights on our leds. The goal is to eventually send the output back to Telegram.

#### Required parts
- [ESP8266](https://makeradvisor.com/tools/esp8266-esp-12e-nodemcu-wi-fi-development-board/)
- [4x LEDs](https://makeradvisor.com/tools/3mm-5mm-leds-kit-storage-box/)
- [4x Resistors](https://makeradvisor.com/tools/resistors-kits/)
- [Breadboard](https://makeradvisor.com/tools/mb-102-solderless-breadboard-830-points/)
- [Jumper wires](https://makeradvisor.com/tools/jumper-wires-kit-120-pieces/)
- [Adafruit LED](https://www.adafruit.com/product/1138?length=2)
  
1. Follow the steps at the [Source](https://randomnerdtutorials.com/esp8266-weather-forecaster/) Document. 
2. After completing the steps above, we're now going to install Arduino Json Library. follow these [steps](https://randomnerdtutorials.com/esp8266-weather-forecaster/#:~:text=Installing%20the%20ArduinoJson%20library)

>Error After uploading a The code on my board I get the following error

<img width="1613" alt="Schermafbeelding 2022-10-26 om 12 08 17" src="https://user-images.githubusercontent.com/70894669/198000265-df900776-7880-41e4-9c4f-01b06f747fd9.png">

??? Apparantly my ArduinoJson version need to be updated, download this [file](https://github.com/bblanchon/ArduinoJson/archive/v5.13.5.zip) unpack your file rename it to: 'ArduinoJson' and overwrite every other version. After that make it a .zip file and include it in your Arduino library again, re-open your Arduino-Ide and the upload should be good now.


<img width="758" alt="Schermafbeelding 2022-10-26 om 12 24 06" src="https://user-images.githubusercontent.com/70894669/198002646-6271905c-4d0c-450d-8631-0c65ce6b444d.png">
??? jsonBuffer still has a problem, I have installed the newest version but I can't fix the problem. jsonBuffer is a ArduinoJson version 5.0 class, it doesn't work on ArduinoJson version 6.0 - 6.19.3. 
After uninstalling the newer version (6.0+) and installing the .zip file the error has been fixed!

3. Now the code works withouth any problems it's time to combine the settings with a Adafruit led strip because I don't have the smaller lights.

4. Follow these steps: [How to command Individual LEDS within an RGB led strip using neopixel library](https://www.sensingthecity.com/tutorial-how-to-command-individual-leds-within-an-rgb-led-strip-using-neopixel-library/)
  
<details>
  <summary> The code of commanding the individual LEDs </summary>
  
```
  /*
 * This tutorial is part of the course CPLN 571 - Sensing the City, at the University of Pennsylvania, taught by Dr. Allison Lassiter. It is also a part
 * of the final project of the class. It is based on the NeoPixel Library by AdaFruit.
 * 
 * In order to run this tutorial, you will need to install the AdaFruit NeoPixel library.
 */

#include <Adafruit_NeoPixel.h> // include the Neopixel Library in this Sketch

#define PIN 6 // This is the Arduino Pin controlling the LEDstrip.

#define NUMPIXELS 60 // Here, you are informing how many LEDs you have on your strip.
                     // You can also control only a part of the existing LEDs, if you wish.
                     // This strip has 60 LEDs, so I am informing this number.

/* 
 *  Remember that I keep annoying you whith capital IMPORTANT warnings? This next line is where it really matters.
 */

Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRBW + NEO_KHZ800); // Here, you are specifying your strip,
                                                                                     // Let's go over the details:

/*
 * The command Adafruit_NeoPixel pixels assigns (inside the parenthesis, separated by commas (,)):
 * 1) the number of pixels you control, We have created the variable NUMPIXELS, so we can change this number more easily according to our need
 * 2) the PIN on the Arduino Board that sends the signal. In this case, we use PIN 06, as declared globally above
 * 3) The Type of LED flag. In this case, we have a RGB White LED, with 800Khz bitstream. You can check this out on the datasheet we linked above.
 * 
 * Please notice that your LEDs won't work if you do not get this line right. So, here are some tips for more recent fixtures:
 * 
 * NEO_KHZ800 will be common in most NeoPixel products with WS2812 LEDs. If you check the datasheet, of your strip, it should be under
 * data speed, or something similar.
 * NEO_KHZ400 will be preent in WS2811 LEDs. Again, check the datasheet to be sure.
 * 
 * NEO_GRB will be common in NeoPixel products
 * NEO_RGB will be common in Flora Pixel products.
 * 
 * REMEMBER, if yor LED is a RGB White, you have to add a W at the end of this code, so they will be either NEO_RGBW or NEO_GRBW 
 */

/*
 * OK, now let's start controlling the leds. The strip I am using has 60 LEDs. I want to control it in 6 groups of 10 LEDs, to make my life easier.
 * So, let's define the following arrays:
 */

int PXL1[] = {0,1,2,3,4,5,6,7,8,9}; // array controlling the first 10 LEDs. Please notice the "LED 0" is the first one, not "LED 1"
int PXL2[] = {10,11,12,13,14,15,16,17,18,19};
int PXL3[] = {20,21,22,23,24,25,26,27,28,29};
int PXL4[] = {30,31,32,33,34,35,36,37,38,39};
int PXL5[] = {40,41,42,43,44,45,46,47,48,49};
int PXL6[] = {50,51,52,53,54,55,56,57,58,59};

int delayval = 50; // Here we set a delaytime

void setup() {

  pixels.begin(); // This initializes the NeoPixel library.
}

void loop() {

  for(int i=0;i<10;i++){ // Since each array has 10 LEDs, we are going to turn them sequentially on using this index.

/*
 * Notice that the lines below are just setting up the color of each pixel. This is not yet the command to turn them on. The 
 * pixels.setPixelColor command is a very easy way to define the color of each pixel. The syntax is:
 * pixels.setPixelColor(x, pixels.Color(R,G,B)), where:
 * x = the pixel you want to define a color for. In this example, we are using the arrays we created for the 6 control groups, hence the PXL1[i] input.
 * R,G,B = the values of red, green, and blue on a RGB scale.
 */

pixels.setPixelColor(PXL1[i], pixels.Color(139,0,139)); // array number 1 is magenta
pixels.setPixelColor(PXL2[i], pixels.Color(255,255,0)); // array number 2 is yellow
pixels.setPixelColor(PXL3[i], pixels.Color(255,255,255)); // array number 3 is white
pixels.setPixelColor(PXL4[i], pixels.Color(0,255,0)); // array number 4 is green
pixels.setPixelColor(PXL5[i], pixels.Color(0,0,255)); // array number 5 is blue
pixels.setPixelColor(PXL6[i], pixels.Color(255,0,0)); // array number 6 is red

pixels.show(); // Okay, we have informed which colors we want. Now, it is time to flip the switch and let the magic happen. The pixels.show() command does that

delay(delayval); // Let's add a little delay here. So we can appreciate more the dynamic lighting we can do with this simple and cheap components.
}

    for(int i=10;i>-1;i--){  // Now, we are going to turn them off sequentially, so we can create a pulsing dynamic for each group

pixels.setPixelColor(PXL1[i], pixels.Color(0,0,0)); // The 0,0,0 values means that nothing is being turned on. So we repeat it for all groups.
pixels.setPixelColor(PXL2[i], pixels.Color(0,0,0));
pixels.setPixelColor(PXL3[i], pixels.Color(0,0,0));
pixels.setPixelColor(PXL4[i], pixels.Color(0,0,0));
pixels.setPixelColor(PXL5[i], pixels.Color(0,0,0));
pixels.setPixelColor(PXL6[i], pixels.Color(0,0,0));

pixels.show(); // Again, we have only defined the colors above, remember we must instruct the Arduino to show what we came up with.

delay(delayval); // Another delay, to make the presentation consistent.

/*
 * You are done. Upload the code and see if you like it.
 */

}

}
```
  
  </details>

5. First I changed the code to see if it's working and if changing it to the right amount of LEDs.

<details>
  <summary> Open for the code </summary>
  
  ```
  /*
 * This tutorial is part of the course CPLN 571 - Sensing the City, at the University of Pennsylvania, taught by Dr. Allison Lassiter. It is also a part
 * of the final project of the class. It is based on the NeoPixel Library by AdaFruit.
 * 
 * In order to run this tutorial, you will need to install the AdaFruit NeoPixel library.
 */

#include <Adafruit_NeoPixel.h> // include the Neopixel Library in this Sketch

#define PIN D5 // This is the Arduino Pin controlling the LEDstrip.

#define NUMPIXELS 14 // Here, you are informing how many LEDs you have on your strip.
                     // You can also control only a part of the existing LEDs, if you wish.
                     // This strip has 60 LEDs, so I am informing this number.

/* 
 *  Remember that I keep annoying you whith capital IMPORTANT warnings? This next line is where it really matters.
 */

Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRBW + NEO_KHZ400); // Here, you are specifying your strip,
                                                                                     // Let's go over the details:

/*
 * The command Adafruit_NeoPixel pixels assigns (inside the parenthesis, separated by commas (,)):
 * 1) the number of pixels you control, We have created the variable NUMPIXELS, so we can change this number more easily according to our need
 * 2) the PIN on the Arduino Board that sends the signal. In this case, we use PIN 06, as declared globally above
 * 3) The Type of LED flag. In this case, we have a RGB White LED, with 800Khz bitstream. You can check this out on the datasheet we linked above.
 * 
 * Please notice that your LEDs won't work if you do not get this line right. So, here are some tips for more recent fixtures:
 * 
 * NEO_KHZ800 will be common in most NeoPixel products with WS2812 LEDs. If you check the datasheet, of your strip, it should be under
 * data speed, or something similar.
 * NEO_KHZ400 will be preent in WS2811 LEDs. Again, check the datasheet to be sure.
 * 
 * NEO_GRB will be common in NeoPixel products
 * NEO_RGB will be common in Flora Pixel products.
 * 
 * REMEMBER, if yor LED is a RGB White, you have to add a W at the end of this code, so they will be either NEO_RGBW or NEO_GRBW 
 */

/*
 * OK, now let's start controlling the leds. The strip I am using has 60 LEDs. I want to control it in 6 groups of 10 LEDs, to make my life easier.
 * So, let's define the following arrays:
 */

int PXL1[] = {0,1,2,3,4,5,6,7,8,9}; // array controlling the first 10 LEDs. Please notice the "LED 0" is the first one, not "LED 1"
int PXL2[] = {10,11,12,13};

int delayval = 50; // Here we set a delaytime

void setup() {

  pixels.begin(); // This initializes the NeoPixel library.
}

void loop() {

  for(int i=0;i<1;i++){ // Since each array has 10 LEDs, we are going to turn them sequentially on using this index.

/*
 * Notice that the lines below are just setting up the color of each pixel. This is not yet the command to turn them on. The 
 * pixels.setPixelColor command is a very easy way to define the color of each pixel. The syntax is:
 * pixels.setPixelColor(x, pixels.Color(R,G,B)), where:
 * x = the pixel you want to define a color for. In this example, we are using the arrays we created for the 6 control groups, hence the PXL1[i] input.
 * R,G,B = the values of red, green, and blue on a RGB scale.
 */

pixels.setPixelColor(PXL1[i], pixels.Color(139,0,139)); // array number 1 is magenta
pixels.setPixelColor(PXL2[i], pixels.Color(255,255,0)); // array number 2 is yellow

pixels.show(); // Okay, we have informed which colors we want. Now, it is time to flip the switch and let the magic happen. The pixels.show() command does that

delay(delayval); // Let's add a little delay here. So we can appreciate more the dynamic lighting we can do with this simple and cheap components.
}

    for(int i=1;i>-1;i--){  // Now, we are going to turn them off sequentially, so we can create a pulsing dynamic for each group

pixels.setPixelColor(PXL1[i], pixels.Color(0,0,0)); // The 0,0,0 values means that nothing is being turned on. So we repeat it for all groups.
pixels.setPixelColor(PXL2[i], pixels.Color(0,0,0));

pixels.show(); // Again, we have only defined the colors above, remember we must instruct the Arduino to show what we came up with.

delay(delayval); // Another delay, to make the presentation consistent.

/*
 * You are done. Upload the code and see if you like it.
 */

}

}

```
</details>
    

6. Now the code is flicking it's first and last Led. Time to change some settings. The reason why it was flicking was because I changed the 10 in 1 in this code ` for(int i=1;i>-10;i--){ ` .
  
7. Now I re??ntegrated it and it works like normal changing the light every 800 ticks.
  
  
<details>
    <summary> Code renewd </summary>
  
    
```
  
    /*
 * This tutorial is part of the course CPLN 571 - Sensing the City, at the University of Pennsylvania, taught by Dr. Allison Lassiter. It is also a part
 * of the final project of the class. It is based on the NeoPixel Library by AdaFruit.
 * 
 * In order to run this tutorial, you will need to install the AdaFruit NeoPixel library.
 */

#include <Adafruit_NeoPixel.h> // include the Neopixel Library in this Sketch

#define PIN D5 // This is the Arduino Pin controlling the LEDstrip.

#define NUMPIXELS 14 // Here, you are informing how many LEDs you have on your strip.
                     // You can also control only a part of the existing LEDs, if you wish.
                     // This strip has 60 LEDs, so I am informing this number.

/* 
 *  Remember that I keep annoying you whith capital IMPORTANT warnings? This next line is where it really matters.
 */

Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRBW + NEO_KHZ400); // Here, you are specifying your strip,
                                                                                     // Let's go over the details:

/*
 * The command Adafruit_NeoPixel pixels assigns (inside the parenthesis, separated by commas (,)):
 * 1) the number of pixels you control, We have created the variable NUMPIXELS, so we can change this number more easily according to our need
 * 2) the PIN on the Arduino Board that sends the signal. In this case, we use PIN 06, as declared globally above
 * 3) The Type of LED flag. In this case, we have a RGB White LED, with 800Khz bitstream. You can check this out on the datasheet we linked above.
 * 
 * Please notice that your LEDs won't work if you do not get this line right. So, here are some tips for more recent fixtures:
 * 
 * NEO_KHZ800 will be common in most NeoPixel products with WS2812 LEDs. If you check the datasheet, of your strip, it should be under
 * data speed, or something similar.
 * NEO_KHZ400 will be preent in WS2811 LEDs. Again, check the datasheet to be sure.
 * 
 * NEO_GRB will be common in NeoPixel products
 * NEO_RGB will be common in Flora Pixel products.
 * 
 * REMEMBER, if yor LED is a RGB White, you have to add a W at the end of this code, so they will be either NEO_RGBW or NEO_GRBW 
 */

/*
 * OK, now let's start controlling the leds. The strip I am using has 60 LEDs. I want to control it in 6 groups of 10 LEDs, to make my life easier.
 * So, let's define the following arrays:
 */

int PXL1[] = {0,1,2,3,4,5,6,7,8,9}; // array controlling the first 10 LEDs. Please notice the "LED 0" is the first one, not "LED 1"
int PXL2[] = {10,11,12,13};

int delayval = 800; // Here we set a delaytime

void setup() {

  pixels.begin(); // This initializes the NeoPixel library.
}

void loop() {

  for(int i=0;i<10;i++){ // Since each array has 10 LEDs, we are going to turn them sequentially on using this index.

/*
 * Notice that the lines below are just setting up the color of each pixel. This is not yet the command to turn them on. The 
 * pixels.setPixelColor command is a very easy way to define the color of each pixel. The syntax is:
 * pixels.setPixelColor(x, pixels.Color(R,G,B)), where:
 * x = the pixel you want to define a color for. In this example, we are using the arrays we created for the 6 control groups, hence the PXL1[i] input.
 * R,G,B = the values of red, green, and blue on a RGB scale.
 */

pixels.setPixelColor(PXL1[i], pixels.Color(139,0,139)); // array number 1 is magenta
pixels.setPixelColor(PXL2[i], pixels.Color(255,255,0)); // array number 2 is yellow

pixels.show(); // Okay, we have informed which colors we want. Now, it is time to flip the switch and let the magic happen. The pixels.show() command does that

delay(delayval); // Let's add a little delay here. So we can appreciate more the dynamic lighting we can do with this simple and cheap components.
}

    for(int i=1;i>-10;i--){  // Now, we are going to turn them off sequentially, so we can create a pulsing dynamic for each group

pixels.setPixelColor(PXL1[i], pixels.Color(0,0,0)); // The 0,0,0 values means that nothing is being turned on. So we repeat it for all groups.
pixels.setPixelColor(PXL2[i], pixels.Color(0,0,0));

pixels.show(); // Again, we have only defined the colors above, remember we must instruct the Arduino to show what we came up with.

delay(delayval); // Another delay, to make the presentation consistent.

/*
 * You are done. Upload the code and see if you like it.
 */

}

}
    
```
    
</details>
    
It should now look something like this:
![IMG_0762](https://user-images.githubusercontent.com/70894669/198155080-096b8caf-366e-4a1d-a046-8c6e4c1c6f07.png)
    
8. We're going to change the code: `pixels.setPixelColor(PXL1[i], pixels.Color(139,0,139)); // array number 1 is magenta
pixels.setPixelColor(PXL2[i], pixels.Color(255,255,0)); // array number 2 is yellow `
                         
into ` pixels.setPixelColor(PXL1[1], pixels.Color(139,0,139)); // array number 1 is magenta
pixels.setPixelColor(PXL1[2], pixels.Color(255,255,0)); // array number 2 is yellow
pixels.setPixelColor(PXL1[3], pixels.Color(139,0,139)); // array number 1 is magenta
pixels.setPixelColor(PXL1[4], pixels.Color(255,255,0)); // array number 2 is yellow `.

Now select the color of your wish and change the value's `(000,0,000)`. You can select the colors of the tutorial earlier.
- Blue for **Rain**. `(0,0,255)`
- Green for **Clear Sky**. `(0,255,0)`
- White for **Snow**. `(255,255,255)`
- Yellow for **Hail**. `(255,255,0)`
    
The for loop should be looking like this:
    
<details>
    <summary> Open for the void loop </summary>
    
```
void loop() {

  for(int i=0;i<4;i++){ // Since each array has 10 LEDs, we are going to turn them sequentially on using this index.

/*
 * Notice that the lines below are just setting up the color of each pixel. This is not yet the command to turn them on. The 
 * pixels.setPixelColor command is a very easy way to define the color of each pixel. The syntax is:
 * pixels.setPixelColor(x, pixels.Color(R,G,B)), where:
 * x = the pixel you want to define a color for. In this example, we are using the arrays we created for the 6 control groups, hence the PXL1[i] input.
 * R,G,B = the values of red, green, and blue on a RGB scale.
 */
 
pixels.setPixelColor(PXL1[1], pixels.Color(0,0,255)); // array number 1 is blue for Rain
pixels.setPixelColor(PXL1[2], pixels.Color(255,255,0)); // array number 2 is yellow for Hail
pixels.setPixelColor(PXL1[3], pixels.Color(0,255,0)); // array number 3 is green for Clear Sky
pixels.setPixelColor(PXL1[4], pixels.Color(255,255,255)); // array number 4 is white for Snow

pixels.show(); // Okay, we have informed which colors we want. Now, it is time to flip the switch and let the magic happen. The pixels.show() command does that

delay(delayval); // Let's add a little delay here. So we can appreciate more the dynamic lighting we can do with this simple and cheap components.
}

    for(int i=1;i>-4;i--){  // Now, we are going to turn them off sequentially, so we can create a pulsing dynamic for each group
pixels.setPixelColor(PXL1[1], pixels.Color(0,0,0)); // array number 1 is blue for Rain
pixels.setPixelColor(PXL1[2], pixels.Color(0,0,0)); // array number 2 is yellow for Hail
pixels.setPixelColor(PXL1[3], pixels.Color(0,0,0)); // array number 3 is green for Clear Sky
pixels.setPixelColor(PXL1[4], pixels.Color(0,0,0)); // array number 4 is white for Snow

pixels.show(); // Again, we have only defined the colors above, remember we must instruct the Arduino to show what we came up with.

delay(delayval); // Another delay, to make the presentation consistent.

/*
 * You are done. Upload the code and see if you like it.
 */

}
```
  
</details>
  
> Error occured the colors are not correctly displayed
  
9. Change the code to `for(int i=1;i>-3;i--)` and start with the array from [0] to [3] instead of [0] to [4].
 
> Error the colors where still not correct
10. Change the code `Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRBw + NEO_KHZ800);` into `Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRB + NEO_KHZ400);`.

### Implementing this code with Weather forecaster code
  
1. Changing the code ```digitalWrite(rainLed,HIGH);
      digitalWrite(clearLed,LOW);
      digitalWrite(snowLed,LOW);
      digitalWrite(hailLed,LOW); ```
   to  ```pixels.setPixelColor(rainLed, pixels.Color(0,0,255)); // Turning rainLed blue
      pixels.setPixelColor(clearLed, pixels.Color(0,0,0)); // Turning clearLed off
      pixels.setPixelColor(snowLed, pixels.Color(0,0,0)); // Turning snowLed off
      pixels.setPixelColor(hailLed, pixels.Color(0,0,0)); // Turning hailLed off ```
2. Repeat at the other diffDataActions (representing data).
  
3. After that upload the sketch
  
<details>
  <summary> "Final Sketch" </summary>

```
/*
  * Author: Emmanuel Odunlade 
  * Complete Project Details https://randomnerdtutorials.com
  */
  
#include <ArduinoJson.h>
#include <ESP8266WiFi.h>
#include <WiFiClient.h>
#include <Adafruit_NeoPixel.h>

// Which pin on the Arduino is connected to the NeoPixels?
#define PIN D5  // On Trinket or Gemma, suggest changing this to 1

// How many NeoPixels are attached to the Arduino?
#define NUMPIXELS 14  // Popular NeoPixel ring size

Adafruit_NeoPixel pixels = Adafruit_NeoPixel(NUMPIXELS, PIN, NEO_GRB + NEO_KHZ400);

// Replace with your SSID and password details
char ssid[] = "YOUR_SSID_NAME";        
char pass[] = "PASSWORD_OF_SSID";   

WiFiClient client;

// Open Weather Map API server name
const char server[] = "api.openweathermap.org";

// Replace the next line to match your city and 2 letter country code
String nameOfCity = "PLACE,LANDCODE"; 
// How your nameOfCity variable would look like for Lagos on Nigeria
//String nameOfCity = "Lagos,NG"; 

// Replace the next line with your API Key
String apiKey = "YOUR_API_KEY"; 

String text;

int jsonend = 0;
boolean startJson = false;
int status = WL_IDLE_STATUS;

int rainLed = 0;  // Indicates rain
int clearLed = 1; // Indicates clear sky or sunny
int snowLed = 2;  // Indicates snow
int hailLed = 3;  // Indicates hail



#define JSON_BUFF_DIMENSION 2500

unsigned long lastConnectionTime = 10 * 60 * 1000;     // last time you connected to the server, in milliseconds
const unsigned long postInterval = 10 * 60 * 1000;  // posting interval of 10 minutes  (10L * 1000L; 10 seconds delay for testing)

void setup() {
  pixels.begin();
  Serial.begin(9600);
  
  text.reserve(JSON_BUFF_DIMENSION);
  
  WiFi.begin(ssid,pass);
  Serial.println("connecting");
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("WiFi Connected");
  printWiFiStatus();
}

void loop() { 
  //OWM requires 10mins between request intervals
  //check if 10mins has passed then conect again and pull
  if (millis() - lastConnectionTime > postInterval) {
    // note the time that the connection was made:
    lastConnectionTime = millis();
    makehttpRequest();
  }
}

// print Wifi status
void printWiFiStatus() {
  // print the SSID of the network you're attached to:
  Serial.print("SSID: ");
  Serial.println(WiFi.SSID());

  // print your WiFi shield's IP address:
  IPAddress ip = WiFi.localIP();
  Serial.print("IP Address: ");
  Serial.println(ip);

  // print the received signal strength:
  long rssi = WiFi.RSSI();
  Serial.print("signal strength (RSSI):");
  Serial.print(rssi);
  Serial.println(" dBm");
}

// to request data from OWM
void makehttpRequest() {
  // close any connection before send a new request to allow client make connection to server
  client.stop();

  // if there's a successful connection:
  if (client.connect(server, 80)) {
    // Serial.println("connecting...");
    // send the HTTP PUT request:
    client.println("GET /data/2.5/forecast?q=" + nameOfCity + "&APPID=" + apiKey + "&mode=json&units=metric&cnt=2 HTTP/1.1");
    client.println("Host: api.openweathermap.org");
    client.println("User-Agent: ArduinoWiFi/1.1");
    client.println("Connection: close");
    client.println();
    
    unsigned long timeout = millis();
    while (client.available() == 0) {
      if (millis() - timeout > 5000) {
        Serial.println(">>> Client Timeout !");
        client.stop();
        return;
      }
    }
    
    char c = 0;
    while (client.available()) {
      c = client.read();
      // since json contains equal number of open and close curly brackets, this means we can determine when a json is completely received  by counting
      // the open and close occurences,
      //Serial.print(c);
      if (c == '{') {
        startJson = true;         // set startJson true to indicate json message has started
        jsonend++;
      }
      if (c == '}') {
        jsonend--;
      }
      if (startJson == true) {
        text += c;
      }
      // if jsonend = 0 then we have have received equal number of curly braces 
      if (jsonend == 0 && startJson == true) {
        parseJson(text.c_str());  // parse c string text in parseJson function
        text = "";                // clear text string for the next time
        startJson = false;        // set startJson to false to indicate that a new message has not yet started
      }
    }
  }
  else {
    // if no connction was made:
    Serial.println("connection failed");
    return;
  }
}

//to parse json data recieved from OWM
void parseJson(const char * jsonString) {
  //StaticJsonBuffer<4000> jsonBuffer;
  const size_t bufferSize = 2*JSON_ARRAY_SIZE(1) + JSON_ARRAY_SIZE(2) + 4*JSON_OBJECT_SIZE(1) + 3*JSON_OBJECT_SIZE(2) + 3*JSON_OBJECT_SIZE(4) + JSON_OBJECT_SIZE(5) + 2*JSON_OBJECT_SIZE(7) + 2*JSON_OBJECT_SIZE(8) + 720;
  DynamicJsonBuffer jsonBuffer(bufferSize);

  // FIND FIELDS IN JSON TREE
  JsonObject& root = jsonBuffer.parseObject(jsonString);
  if (!root.success()) {
    Serial.println("parseObject() failed");
    return;
  }

  JsonArray& list = root["list"];
  JsonObject& nowT = list[0];
  JsonObject& later = list[1];

  // including temperature and humidity for those who may wish to hack it in
  
  String city = root["city"]["name"];
  
  float tempNow = nowT["main"]["temp"];
  float humidityNow = nowT["main"]["humidity"];
  String weatherNow = nowT["weather"][0]["description"];

  float tempLater = later["main"]["temp"];
  float humidityLater = later["main"]["humidity"];
  String weatherLater = later["weather"][0]["description"];

  // checking for four main weather possibilities
  diffDataAction(weatherNow, weatherLater, "clear");
  diffDataAction(weatherNow, weatherLater, "rain");
  diffDataAction(weatherNow, weatherLater, "snow");
  diffDataAction(weatherNow, weatherLater, "hail");
  
  Serial.println();
}

//representing the data
void diffDataAction(String nowT, String later, String weatherType) {
  int indexNow = nowT.indexOf(weatherType);
  int indexLater = later.indexOf(weatherType);
  // if weather type = rain, if the current weather does not contain the weather type and the later message does, send notification
  if (weatherType == "rain") { 
    if (indexNow == -1 && indexLater != -1) {
      pixels.setPixelColor(rainLed, pixels.Color(0,0,255)); // Turning rainLed blue
      pixels.setPixelColor(clearLed, pixels.Color(0,0,0)); // Turning clearLed off
      pixels.setPixelColor(snowLed, pixels.Color(0,0,0)); // Turning snowLed off
      pixels.setPixelColor(hailLed, pixels.Color(0,0,0)); // Turning hailLed off
      Serial.println("Oh no! It is going to " + weatherType + " later! Predicted " + later);
    }
  }
  // for snow
  else if (weatherType == "snow") {
    if (indexNow == -1 && indexLater != -1) {
      pixels.setPixelColor(rainLed, pixels.Color(0,0,0)); // Turning rainLed off
      pixels.setPixelColor(clearLed, pixels.Color(0,0,0)); // Turning clearLed off
      pixels.setPixelColor(snowLed, pixels.Color(255,255,255)); // Turning snowLed white
      pixels.setPixelColor(hailLed, pixels.Color(0,0,0)); // Turning hailLed off
      Serial.println("Oh no! It is going to " + weatherType + " later! Predicted " + later);
    }
    
  }
  // can't remember last time I saw hail anywhere but just in case
  else if (weatherType == "hail") { 
   if (indexNow == -1 && indexLater != -1) {
      pixels.setPixelColor(rainLed, pixels.Color(0,0,0)); // Turning rainLed off
      pixels.setPixelColor(clearLed, pixels.Color(0,0,0)); // Turning clearLed off
      pixels.setPixelColor(snowLed, pixels.Color(0,0,0)); // Turning snowLed off
      pixels.setPixelColor(hailLed, pixels.Color(255,255,0)); // Turning hailLed yellow
      Serial.println("Oh no! It is going to " + weatherType + " later! Predicted " + later);
   }

  }
  // for clear sky, if the current weather does not contain the word clear and the later message does, send notification that it will be sunny later
  else {
    if (indexNow == -1 && indexLater != -1) {
      Serial.println("It is going to be sunny later! Predicted " + later);
      pixels.setPixelColor(rainLed, pixels.Color(0,0,0)); // Turning rainLed off
      pixels.setPixelColor(clearLed, pixels.Color(0,255,0)); // Turning clearLed green
      pixels.setPixelColor(snowLed, pixels.Color(0,0,0)); // Turning snowLed off
      pixels.setPixelColor(hailLed, pixels.Color(0,0,0)); // Turning hailLed off
    }
  }
}
  
```

</details>
                       
> Weirdly enough the Serial monitor doesn't show just a certain amount of response, While it's connected to my iphone hotspot:
<img width="847" alt="Schermafbeelding 2022-10-27 om 01 40 26" src="https://user-images.githubusercontent.com/70894669/198158790-83e32577-6cd3-45c7-bb72-fdf1a3885088.png">
  
This is the final result of Led strip, It displays 4 colors each representing different weather conditions. It should be only showing one color, but the ESP8266 is not giving any response.. 
![IMG_0763](https://user-images.githubusercontent.com/70894669/198159754-db928ffe-3e9c-4054-a3be-99b68d449245.png)

> The Arduino is only giving this kind of response after pressing RST button not much of a help..
<img width="1630" alt="Schermafbeelding 2022-10-27 om 01 53 44" src="https://user-images.githubusercontent.com/70894669/198160056-65b39941-a271-4276-9e84-05e8b983b675.png">
  
I couldn't find a clear solution so this is where it stops sadly..

http://api.openweathermap.org/data/2.5/forecast?q=veenendaal,NL&APPID=fb374c0f8a61e457e8aacae341bede30&mode

</details>

