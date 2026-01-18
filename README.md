# Documentation_CreativeTechnology_Team_Macher

## About

 Our project is a **sound-reactive music animation** designed to create an immersive, drifting experience. The visuals respond in real time to the music, turning sound into movement, light, and form. Instead of watching a fixed animation, the audience enters a living audiovisual space that constantly changes with the audio.


The goal is to create a floating, meta-universe–like atmosphere that makes viewers feel as if they are leaving the physical room and slipping into another world. The experience is meant to be calming, hypnotic, and slightly surreal—somewhere between being awake and dreaming.


A key part of our visual identity is the use of eyes. The eyes act as a recurring visual motif that gives the world a sense of presence, awareness, and connection. They make the environment feel alive, as if it is observing and reacting to the sound together with the audience.


The animation is intended to be experienced while sitting or lying down, allowing the body to relax and the focus to shift fully toward sound and visuals. Music drives the entire environment: rhythm, volume, and texture influence how elements move, pulse, and transform, so the audience can not only hear the music but also see and feel it.


Overall, the project explores how sound and visuals merge into one immersive space, creating a unique journey where every piece of music generates a new, floating visual world.

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

#### Requirements

Software:
- Touchdesigner
- A video file (.mp4)
- An audio file (.mp3)


#### Instructions

![FullTD](Images/Eyeall.png)

The whole project is separated into two main sections:
- Audio separation (green Area)
- Movie into Particles (purple Area)

**Audio separation**

Create a new Touchdesign file and copy the CHOPs in the Screenshot below.
![FullTD](Images/EyeAudio.png)

1. audiofilein
- Insert .mp3 in "File"
- Loads and plays the audio
- Outputs two audio channels

2. Beat separator (Is not a Chop insert from Palette -> Tools)
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

Continue by copying the TOPs and CHOPs in the Screenshot below.
![FullTD](Images/EyeVideo.png)

1. moviefilein
- Insert .mp4 in "File"
- Loads a video file
- Each frame of the video is used as visual source data.

2. topto (TOP -> CHOP)
- change "First RGBA Contains" dropdown into: "Height (R)"
- Converts pixel data from the video into numeric values.
- These values later define particle positions.

3. random1 & random2
- Adds variation to particle positions.
- Prevents particles from forming a rigid grid.

4. Box (KickParticles)
- Connect the Node "Math" from the audioseparation into the Box **parameter** "Uniform Scale"
- Acts the base geometry
- Receives influence from the audio kick signal.
- This causes: Strong beats -> stronger particle movement. Quiet sections -> calmer visuals

5. copy
- Copies geometry points.
- Creates a particle like structure from data

6. geo (COMP)
- Combines geometry and particle data.
- Receives audio driven values that affect movement.

7. render
- Renders the Scene
- This will be the final visual output

8. cam, light1, light2 (COMPs)
- Connect these Comps to the Render
- Define camera perspectives and lightings
- Improve depth and readability of the particle system.







### Project DancingParticles

#### Description Project DancingParticles

This project displays a 3D particle cloud that reacts to music in real time. The high frequencies of the audio control the speed and motion of the particles, while the low frequency beats ("kicks") trigger rapid camera viewpoint changes. This creates the impression that the 3D object is dancing through dynamic shifts in perspective.

#### Requirements

Software:
- Touchdesigner
- A audio file (.mp3)

#### Instructions

![FullTD](Images/ParticleCloudall.png)

The whole project is separated into two main sections:
- Audio (green Area)
- ParticleCloud Visuals (purple Area)
- Camera Sequencer (grey Area)

**Audio separation**

Create new Touchdesign file and copy these CHOPs in the Screenshot below.

![FullTD](Images/ParticleCloudAudio.png)

1. audiofilein
- Insert .mp3 in "File"
- Loads and plays the audio
- Outputs two audio channels

2. beat separator (Is not a Chop insert from Palette -> Tools)
- Enable "Kick" and adjust the Thresh
- Analyzes the incoming audio signal
- Extracts frequency information

