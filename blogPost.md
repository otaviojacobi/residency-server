## Voice Assistant Builder

Voice Assistants represent an entire different way on how we (humans) can interact with machines. In the past years, [Google Assistant](https://assistant.google.com/), [Siri](https://www.apple.com/siri/) and [Alexa](https://www.alexa.com/) revolutionized the entire field, however, all these devices work "on-line" meaning that they send your voice command to a server, where this data can possibly be stored for further improvements on their models. 

If you, as many others, have [privacy concerns](https://www.theguardian.com/technology/2019/oct/09/alexa-are-you-invading-my-privacy-the-dark-side-of-our-voice-assistants) about what your audio file could be possibly being used for, this projects features a full "off-line" model (all the language understanding and parsing is done in your Intel NUC or a Raspberry Pi) called [Rhasspy](https://rhasspy.readthedocs.io/en/latest/), an easy UI to build the sentences you want to be understandable and integrate with [Home Assistant](https://www.home-assistant.io/).

## Setup

Hardware Required
 - Intel NUC (can be replaced with a RaspberryPi or BalenaFin)
 - A micro SD card
 - Microphone and Speakers (or a old headset)

In my case I used an USB Headset which contained microphone and loud enough speakers but this can be replaced by any means you have to input/output audio physically.

## Deploying the project 
### Deploy with Balena
### Deploy manually

## Booting the device for the first time

Once your deployment is done we have to set up two environment variables to allow Rhasspy and Home Assistant to communicate with each other. To set these variables, follow these steps:

1) In your device Summary tab you will find a page very similar to Image 1 below:
   Locate the Local IP Address and insert it as a Device Variable called LOCAL_IP_ADDRESS (as per Image 2)

                           |                           
:-------------------------:|:-------------------------:
![]([https://...Dark.png](https://github.com/otaviojacobi/balena-voice-assistant/blob/main/docs/1.png?raw=true))  |  ![](https://github.com/otaviojacobi/balena-voice-assistant/blob/main/docs/2.png?raw=true)

___note___: If your device IP changes (e.g. network change) you will need to re-run steps 1) and 3).

1) In a computer within the same network access <local_ip_address>:8123 and create your Home Assistant account
   After creating an account, click on your username on the bottom left, scroll down and click on 'CREATE TOKEN' as in Image 3. Give it a name and copy it. Add it as a Device Variable in balena dashboard, with the name "HASS_ACCESS_TOKEN". 
   At the end you will have something as in Image 4.

2) Restart the containers.