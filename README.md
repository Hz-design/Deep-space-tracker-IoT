# Deep-space-tracker-IoT
This is a technical manual for the Internet of Things product "Deep Space Tracker". In this document there'll be tutorials, how to implement internet in this object to reach a certain level of IoT. Things like communicating the application to the cellphone and more. In this document the focus are on occuring errors and trying different programs. The goals is to document the errors and maybe I am able to solve them, please continue to find out!

*Last update 25th of October 2022 13:20, work in progress*
*By Hong Zhou*

## What is a Deep Space Tracker?
The deep space tracker is a smart tripod which helps the user capture, track or observe the deep space objects in the universe. Why it's an IoT? It reacts on voice commando's, You can get perfect camera setting from the hive mind feature, It can add obserable universe events to your google calendar, It's able to read the weather and tell the user how the weather is for today (is it good for shooting yes/no) and last but not least Automized tripod through the application. The user can select an object and the tripod will automatically locate the object and capture it with perfect settings for a certain amount of time.

# Inhoudsopgave
- Automizing Tripod through telegram
- Voice to commands
- News API showing on telegram feed
- Adafruit Hive mind
- Telegram and google calendar
- Weather API

## Automizing Tripod through telegram
Executing outputs from reading inputs in the serial monitor from telegram.

## Voice to commands 
Activitating inputs from sensors after that reading it in serial monitor and excetuing a different output from node mcu.

More difficult: Reading inputs from sensors, sending it too telegram and after that Telegram sends something automatically back to the ESP32.

<details>
  <summary> Button as voice </summary>
  
</details>

## News api showing on telegram feed
Connecting API in Node MCU, When a certain condition has met show it in the Telegram feed.


## telegram Hive mind
Sending something to telegram and telegram sents a better version back to the serial monitor.


## telegram and google calendar
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
  <summary>ESP8266 Weather Forecaster</summary>

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

• Apparantly my ArduinoJson version need to be updated, download this [file](https://github.com/bblanchon/ArduinoJson/archive/v5.13.5.zip) unpack your file rename it to: 'ArduinoJson' and overwrite every other version. After that make it a .zip file and include it in your Arduino library again, re-open your Arduino-Ide and the upload should be good now.


<img width="758" alt="Schermafbeelding 2022-10-26 om 12 24 06" src="https://user-images.githubusercontent.com/70894669/198002646-6271905c-4d0c-450d-8631-0c65ce6b444d.png">
• jsonBuffer still has a problem, I have installed the newest version but I can't fix the problem. jsonBuffer is a ArduinoJson version 5.0 class, it doesn't work on ArduinoJson version 6.0 - 6.19.3. 
After uninstalling the newer version (6.0+) and installing the .zip file the error has been fixed!

3. Now the code works withouth any problems it's time to combine the settings with a Adafruit led strip because I don't have the smaller lights.

4. Follow these steps: (How to command Individual LEDS within an RGB led strip using neopixel library)[https://www.sensingthecity.com/tutorial-how-to-command-individual-leds-within-an-rgb-led-strip-using-neopixel-library/)
  
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
  
7. Now I reïntegrated it and it works like normal changing the light every 800 ticks.
  
  
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

### Implementing this code with Weather forecaster code
  
1. 
                        
http://api.openweathermap.org/data/2.5/forecast?q=veenendaal,NL&APPID=fb374c0f8a61e457e8aacae341bede30&mode

</details>

