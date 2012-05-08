## introduction

One of the most essential components of an effective **natural user interface** is **speech recognition** (also commonly referred to as voice recognition). In simple terms, **speech recognition** reflects the interaction between a person and some sort of computing device or system that involves the person using his/her voice to provide input to the system.

Here is how the British-English dictionary [defines](http://www.macmillandictionary.com/dictionary/british/voice-recognition) the term **voice recognition**:

> the ability of a computer to know the voice of a person speaking into it, so that only voices that the computer knows can use the system

Let's look at a simple example of how this technology is being used by popular modern applications:

![Siri](http://images.apple.com/iphone/features/images/siri_mean.jpg)

Siri (Speech Interpretation and Recognition Interface) is an application developed by Apple for the most recent version of their incredibly popular product, the iPhone. In this example of its use, a user simply asks their question to their phone with this application running on their phone, and the software responds by presenting the user with a list of appropriate restaurants along with reviews and maps for each one. Siri exemplifies the pinnacle of how **speech recognition** technology is being used in consumer products today.

## kinect

### technical aspects

In addition to color, depth, and skeletal data, Microsoft's [Kinect](http://www.xbox.com/kinect/) collects sound data, which allows the device to respond to voice commands. According to [Microsoft's press release](http://www.microsoft.com/en-us/news/press/2009/sep09/09-23tgsnatalpr.aspx), the Kinect (originally introduced as Project Natal) is equipped with a "multi-array microphone", which handles processing the voice commands. The folks at [iFixit](http://www.ifixit.com/) [disassembled](http://www.ifixit.com/Teardown/Microsoft-Kinect-Teardown/4066/) the sensor and discovered that it contains 4 downward facing microphones that the array is composed of.

![kinect microphone internals](http://guide-images.ifixit.net/igi/VNIBCIuTyLIAUXqT.medium)

The audio capabilities of the Kinect are as follows:

  * acoustic noise suppression
  * echo cancellation
  * beam formation

Here's a [link](http://support.xbox.com/en-US/kinect/voice/speech-recognition#d7e21da22ba34426bf8f46afc9028e79) to a listing of languages that the Kinect's speech recognition software currently recognizes and supports.

To be used effectively, the device needs to be calibrated, so that it can better recognize voice commands. Also, the [Kinect SDK](http://www.microsoft.com/en-us/kinectforwindows/) gives third party developers access to these audio features.

### dashboard integration

Microsoft [utilizes](http://support.xbox.com/en-US/kinect/voice/speech-recognition) the speech recognition capabilities of the Kinect by allowing Xbox 360 users to control their gaming consoles with their voice. On the main dashboard interface for the 360, a microphone icon is visible whenever users are able to use voice commands. If visible, users start by saying "Xbox" and then follow that with one of many different options that appear on the screen in a way that is context sensitive depending on the section of the dashboard that is being used. For example:

> "Xbox"<br />
> "...play disc."

Without any physical contact from the user, the Xbox will then load the software on the current disc.

![dashboar integration](http://nxeassets.xbox.com/shaxam/0201/6e/42/6e42ae2a-4ed8-4050-b5ea-3804036bdaeb.PNG?v=1#kinect-voice-recognition-m-m.PNG)

## technology

TODO

## applications

TODO
