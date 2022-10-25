# Deep-space-tracker-IoT
Dit is een technische manual over het IoT product "Deep Space Tracker". Hierin wordt beschreven wat voor tutorials er gebruikt worden om een bepaald IoT level te behalen. Denk aan communicatie via de applicatie naar de telefoon en meer. In dit document wordt de focus voornamelijk gelegd op turtorials die ik volg om het doel te behalen en worden de fouten gedocumenteerd en opgelost.

*Laatste update 25 oktober 2022 13:20, work in progress*
*Door Hong Zhou*

# Inhoudsopgave
- 

## Automizing Tripod through telegram
Executing outputs from reading inputs in the serial monitor from telegram.

## Voice to commando's 
Activitating inputs from sensors after that reading it in serial monitor and excetuing a different output from node mcu.

More difficult: Reading inputs from sensors, sending it too telegram and after that Telegram sends something automatically back to the ESP32.

## News api showing on telegramn feed
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
  8. Fill in your your own hongzhou826@gmail.com
  9. I made a new account on google to be an imposter for deep space tracker company.
  10. Made some appointments from for the calendar
  11. filled in the information
  <img width="725" alt="Schermafbeelding 2022-10-25 om 15 17 27" src="https://user-images.githubusercontent.com/70894669/197783487-f0e9bc4f-7faa-45a4-a11a-62fe38264d0d.png">
  12. got an error:
  <img width="1043" alt="Schermafbeelding 2022-10-25 om 15 16 01" src="https://user-images.githubusercontent.com/70894669/197783212-82a901fa-803e-4fd3-af52-c17b9a06360b.png">
  13. Not continuing on this programm, on to the next programm.
<img width="695" alt="Schermafbeelding 2022-10-25 om 15 18 21" src="https://user-images.githubusercontent.com/70894669/197783700-495d4803-a7e6-425c-a855-a946b8ed90ad.png">
</details>

<details>
  <summary>Business automated medium - Create Google Calendar events from new telegram messages (failed)</summary>
  
### Create Google Calendar Events From New Telegram Messages
[source](https://business-automated.medium.com/create-google-calendar-events-from-new-telegram-messages-4f5930f224aa)
  
  1. Follow the instructions described at the [source](https://business-automated.medium.com/create-google-calendar-events-from-new-telegram-messages-4f5930f224aa)
  2. <img width="1301" alt="Schermafbeelding 2022-10-25 om 15 32 22" src="https://user-images.githubusercontent.com/70894669/197787686-15bfcb16-a106-41c1-a1dd-49a92accd6e6.png">
3. After filling out the information: 
  <img width="443" alt="Schermafbeelding 2022-10-25 om 15 35 19" src="https://user-images.githubusercontent.com/70894669/197788165-9c31cd8c-b204-4a90-be81-5ac365241d79.png">
  <img width="1301" alt="Schermafbeelding 2022-10-25 om 15 32 22" src="https://user-images.githubusercontent.com/70894669/197788202-0b9df2cd-f636-46d8-9ceb-c5468cea0337.png">
It would stay on this screen for a long time so it seems like it's not working properly.
  4. After that I tried deleting the inputs and it couldn't read the parameters:
  <img width="803" alt="Schermafbeelding 2022-10-25 om 15 36 24" src="https://user-images.githubusercontent.com/70894669/197788533-6d1d3148-6823-467e-97ca-a2825c59216b.png">

  So I stopped with this method and went on.

</details>

## weather API
Connecting the API to your node mcu, The weather API gives conditions to the eps32 and with lights it will show if the weather is good enough for camera weather.

<details>
  <summary>ESP8266 Weather Forecaster</summary>

### Esp8266 Weather Forecaster
[Source](https://randomnerdtutorials.com/esp8266-weather-forecaster/)
In this tutorial we'll use Open weather map API to generate lights on our leds. The goal is to eventually send the output back to Telegram.

#### Required parts
- [ESP8266](https://makeradvisor.com/tools/esp8266-esp-12e-nodemcu-wi-fi-development-board/)
- [4x LEDs](https://makeradvisor.com/tools/3mm-5mm-leds-kit-storage-box/)
- [4x Resistors](https://makeradvisor.com/tools/resistors-kits/)
- [Breadboard](https://makeradvisor.com/tools/mb-102-solderless-breadboard-830-points/)
- [Jumper wires](https://makeradvisor.com/tools/jumper-wires-kit-120-pieces/)
- [Adafruit LED](https://www.adafruit.com/product/1138?length=2)
  
  1. Follow the steps at the [Source](https://randomnerdtutorials.com/esp8266-weather-forecaster/)Document. 
  2. API KEY: fb374c0f8a61e457e8aacae341bede30


  </details>

