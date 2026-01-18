# CreativeTech_Team_Macher

## About

aölksjdfölqwkej

LINK VIDEO



## Usage

**Hardware:**
- MacBook Pro (Apple M2 Pro)
- Mixer Console (Audio Tech) 
- Projector

**Softwares**
- Touchdesigner (Version 2025.31310, non-commercial)
- Mireilles music shit

**Connection scheme**
Music - Mixer - Stem separator - Touchdesigner - Projector



### Project Eyevisual

#### Description Project Eyevisual

This Project transforms a video into a particle system. Each pixel of the video becomes a particle and the movement of these particles is influenced by audio specifically by detecting the low frequencies of the music.

**Requirements**

Software:
- Touchdesigner
- A video file (.mp4)
- An audio file


**Instructions**

![FullTD](Images/Eyeall.png)

The whole project is separated into two main sections:
- Audio separation (green Area)
- Movie into Particles (purple Area)

**Audio separation**

Create a new Touchdesign file and copy the CHOPs in the Screenshot below.
![FullTD](Images/EyeAudio.png)

1. audiofilein
- Insert Audio in "File"
- Loads and plays the audio
- Outputs two audio channels

2. audioAnalysis (Is not a Chop insert from Palette -> Tools)
- Enable "Kick" and adjust the Thresh
- Analyzes the incoming audio signal
- Extracts frequency information

3. select
- in Dropdown Channel names choose "kick"
- Selects the low frequency band labeled "kick"
- This isolates the beat of the music

4. audiofilter
-  Smooths the kick signal.
Prevents jittery or unstable motion in visuals.

5. math
- Remaps and scales the kick values
- Ensures the values are usable for controlling particle movement.

6. audiodevout
- Sends the audio to the speakers to test and hear the sound


**Video into particle conversion**

Create a new Touchdesign file and copy the CHOPs in the Screenshot below.
![FullTD](Images/EyeVideo.png)
