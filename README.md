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
  <summary>Click here for Instructions</summary>
  
  ### Integrating the Google Calendar API with the Telegram Bot API
  1.  Click on [Pipedream](https://pipedream.com/apps/google-calendar/integrations/telegram-bot-api) for popular ways to connect google calendar and Telegram bot.
  2. Select Create Trigger > New messages update (instant)
  3. follow the instructions on creating a new Telegram bot
  <img src=" https://user-images.githubusercontent.com/70894669/197770418-e5f304da-af90-430e-9eba-071a88b32282.gif" width = 40% />
     * Qux

  ### Some Code
  ```js
  function logSomething(something) {
    console.log('Something', something);
  }
  ```
</details>


## weather API
Connecting the API to your node mcu, The weather API gives conditions to the eps32 and with lights it will show if the weather is good enough for camera weather.


