## introduction

One of the most essential components of an effective **natural user interface** is **speech recognition** (also commonly referred to as voice recognition). In simple terms, **speech recognition** reflects the interaction between a person and some sort of computing device or system that involves the person using his/her voice to provide input to the system.

Here is how the British-English dictionary [defines](http://www.macmillandictionary.com/dictionary/british/voice-recognition) the term **voice recognition**:

> the ability of a computer to know the voice of a person speaking into it, so that only voices that the computer knows can use the system

Let's look at a simple example of how this technology is being used by popular modern applications:

![Siri](http://images.apple.com/iphone/features/images/siri_mean.jpg)

Siri (Speech Interpretation and Recognition Interface) is an application developed by Apple for the most recent version of their incredibly popular product, the iPhone. In this example of its use, a user simply asks their question to their phone with this application running on their phone, and the software responds by presenting the user with a list of appropriate restaurants along with reviews and maps for each one. Siri exemplifies the pinnacle of how **speech recognition** technology is being used in consumer products today.

## technology

### overview

There are many components that make up the broad category of speech recognition. While the most important one is the actual recognition of speech itself, some of the lesser known of its components include **speaker recognition**, **talk-through** (also known as barge-in), **word spotting**, and **decoy**. First, I'd like to take a look at the primary algorithms involved with speech recognition.

### algorithms

#### summary

The following is a very simplified summary of [the speech recognition algorithm](http://arxiv.org/pdf/cmp-lg/9608018.pdf) as described by researchers from AT&T:

The basic problem that this algorithm is attempting to solve can be given by the following prompt:

> Given an utterance, find its most likely written transcription.

The general solution for this involves transforming audio into weighted acyclic graphs that map possible interpretations of segments of the audio in the form of phonemes, phones, syllables, and words. The final written transcription for the audio is derived from the optimal path in this graph.

The first step in this process is analyzing acoustic wave patterns from speech that at regular short intervals (for example, 10 milliseconds).

#### details

The basic process of recognizing speech is simplified as

Speech `-> 1. Feature Extraction -> 2. Hypothesis Search ->` Decoded Hypothesis

1. **Feature Extraction**<br /><br />
In the feature extraction phase, the software system extracts a set of 39 parameters describing the audio segment in a vector called a feature. The collection of features are often referred to as acoustic observations.

2. **Hypothesis Search**<br /><br />
The hypothesis search phase uses the feature vectors to analyze speech. Here, a lexicon is used in combination with a language and acoustic model. A lexicon is a list of every possible word with a unique pronunciation. Lexicons are often created with a certain task in mind to limit its size and therefore reduce the complexity of the algorithm. A language model computes the probability of a sequence of words and an acoustic model computes the probability of sequences of feature vectors. Together, these 3 things are used to create the weighted acyclic graph that was mentioned earlier. The nodes in this graph are word possibilities and the edges are weighted by the probabilities. Each path through the graph represents a possible sequence of words, and the final result is the sequence that has the best combined probability, which is the speech that the software has recognized.

(source [Padmanabhan, Picheny](http://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=9&ved=0CHoQFjAI&url=http%3A%2F%2Fciteseerx.ist.psu.edu%2Fviewdoc%2Fdownload%3Fdoi%3D10.1.1.108.2469%26rep%3Drep1%26type%3Dpdf&ei=3Wi9T_qKMavbiALJ3uGnDg&usg=AFQjCNGAnyvKFVpi4N6VUNCCKE5AZoirMQ&sig2=_e3iD8KUZlXO25J5JCpJjg))

### related technology

#### speaker recognition

Speaker recognition refers to the ability of the software to identify the individual who is speaking and is sometimes referred to as speaker identification. (source [Kurfess](http://users.csc.calpoly.edu/~fkurfess/Courses/486/S12/Slides/486-S12-07-Speech.pdf))

This capability requires additional intelligence from the software system, so that it can accurately distinguish the voices of different people with minimal errors. In this way, this technology can be used in biometric systems, which are used to prevent access to unauthorized users. The most common use case for voice based biometric systems are as security measures. An example of this in the real life is the [Loquendo Speaker Verification](http://www.loquendo.com/en/products/speaker-verification/), which is a product used in a variety of businesses worldwide.

For these types of applications, the term speaker identification is usually referred to as speaker **verification** in an attempt to better clarify the nature of the technology (security). Since a speaker verification system only needs to check for the correct user, it usually requires less complexity in the underlying algorithm. Speaker identification, on the other hand, requires more complexity in the underlying algorithm, because it has to attempt to actually match the voice to the appropriate user.

There are two main types of speaker recognition:

1. **text-dependent**:<br />
requires a matching text phrase to be spoken by the appropriate person to recognize the speaker

2. **text-_in_dependent**:<br />
only requires the actual voice to match up

(source: [Beigi](http://www.intechopen.com/books/biometrics/speaker-recognition))

#### talk-through

Talk-through, also known as barge-in, is simply the name for the technology that allows users of speech recognition systems to interrupt the system as it is prompting them for input. (source: [Kurfess](http://users.csc.calpoly.edu/~fkurfess/Courses/486/S12/Slides/486-S12-07-Speech.pdf))

The most obvious example of this in use in the real world is from the automated phone systems of many large telephony companies. This is something that I have personal experience with. Recently, I was attempting to contact the support group for my cable company on the phone. This company used automated voice recognition software that began to list off the available options for me to speak. Before it had finished, I voiced the appropriate command for my system. In response, the system recognized my command and discontinued listing the other options, so that it could help me with the option that I chose.

This type of voice technology is one that is becoming increasingly common with each passing year. Big companies like [AT&T](http://www.google.com/patents/US6563915), [Cisco](http://www.google.com/patents/US6947895), [Hewlett Packard](http://www.google.com/patents/US20020184031), and [IBM](http://www.google.com/patents/US6418216) all have patents that relate to barge-in enabled software.

#### word spotting

Word spotting is the ability of a voice recognition system to correctly identify specific words, even when surrounded by miscellaneous words that are irrelevant to the desired ones. (source: [Kurfess](http://users.csc.calpoly.edu/~fkurfess/Courses/486/S12/Slides/486-S12-07-Speech.pdf))

This technology is essential for software that needs to analyze spoken words in an attempt to detect if a certain phrase was spoken or not. The U.S. government is one of the key users of word spotting technology. Homeland Security uses it in its surveillance of many different audio sources on a regular basis. In an attempt to help prevent terrorist plots, they analyze spoken audio in an automated fashion, using word spotting tuned for phrases that may indicate terrorist activity. (source: [Alon](http://www.nscspeech.com/pdf/kws-whitepaper.pdf))

Other major users of word spotting technology are call centers. Some of them use software that is tuned to listen to phrases that indicate that a call is "problematic", so that they can assist supervisors in finding and resolving them. Others use it to analyze their customers' responses to the company itself after calls have taken place in order to better assess their effectiveness. (source [Alon](http://www.nscspeech.com/pdf/kws-whitepaper.pdf))

#### decoy

In the world of speech recognition, a decoy is defined as a word, phrase, or sound that is used to identify when the voice input has either stopped or been interrupted. (source: [Kurfess](http://users.csc.calpoly.edu/~fkurfess/Courses/486/S12/Slides/486-S12-07-Speech.pdf))

Decoys are separated into 2 main categories:

  * natural
  * artificial

*Natural* decoys are inherent to the user and are most often associated with sounds having to do with hesitation or confusion on the user's part. *Artificial* decoys are not typically associated with the user's speech but with noises that are a product of the environment that he or she is in.

Decoys are crucial for dictation software. Programs that offer dictation need to be able to reproduce a user's speech with text at a very accurate and consistent level. In order to do this, the software needs to be able to correctly identify accidental utterances like "uh" and "um", so that it doesn't record these mistakes. By training the system to recognize these words as decoys, this problem can potentially be avoided.

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
