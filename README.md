# My master's thesis in compression for real-time audio filtering. 

Here I store my [master's thesis](Thesis.pdf), [popular abstract](Popular_abstract.pdf), and a guide and download link for the GUI as mentioned in the thesis.

# Binaural Convolver GUI

A real-time binaural audio convolver for the Saints Marcellino and Pietro church, Cremona, Italy. Load a room impulse response (RIR) for a specific source–microphone pair, then feed it either a local audio file or your system's live audio output to hear what the sound would be like from that seat in the church.

---

### Download

[Download GUI](https://github.com/ollep333/Master-Thesis/releases/latest)

## Requirements

### Windows
No installation needed. Run gui.exe directly.

For SYSTEM mode (capturing live audio from Spotify, YouTube, etc.) you also need:

- [VB-Audio Virtual Cable](https://vb-audio.com/Cable/) (free)

### Linux & macOS (via Wine)
The .exe can be run on Linux and macOS using [Wine](https://www.winehq.org/). Only FILE mode will work.

---

## Tutorial

The GUI does not have a resize function implemented. So if the window is too big, you will need to go into your settings and lessen the resolution scale.

### 1. Select a source and microphone position

The floor plan of the church is shown in the centre of the window.

- Red stars are the three source positions: R (right), C (centre), L (left).
- Blue triangles are the 30 microphone positions arranged in three rows R, C and L across 10 bench columns.

Click a source first, then click a microphone. The status line below the floor plan will confirm your selection.

### 2. Load the RIR

Once both a source and a microphone are selected, press LOAD RIR. The app reads the corresponding pre-computed impulse response from the precompute/ folder. A green checkmark confirms it loaded successfully.

### 3. Choose your audio source

Use the FILE / SYSTEM toggle to select how audio is fed into the convolver.

#### FILE mode
1. Press BROWSE… and select any .wav, .flac or .mp3 file.
2. Press PLAY.

#### SYSTEM mode *(Windows only)*
This mode captures whatever is playing through your system in real time.

This mode is bugged, however, there is a way around it. When you switch to SYSTEM mode for the first time, you will be presented with a pop-up window. Follow the instructions for the workaround.

1. Open Windows Sound Settings, Playback and set CABLE Input (VB-Audio Virtual Cable) as the default playback device. All system audio will now route through it.
2. Back in the app, select the CABLE Output capture device and your headphone output device from the dropdowns. Use REFRESH if a device is missing.
3. Press PLAY.

### 4. Playback controls

| Button | Action |
|--------|--------|
| PLAY | Start playback / convolution |
| PAUSE | Pause (resume by pressing again) |
| STOP | Stop and reset to the beginning |

The circle indicator in the top right corner shows the engine state: white = idle, light blue = paused, green = playing.

### 5. Change position on the fly

You can click a different source or microphone at any time and press LOAD RIR again to switch the room position without stopping playback.

---

## Output device

The OUTPUT DEVICE selector in the Playback panel controls where the binaural audio is sent. Select your headphones here for the full spatial effect. The convolver outputs a stereo (L/R) binaural signal, headphones are required for the effect to work correctly.

---

## Floor plan reference

The church floor plan displayed in the GUI is taken from:

> Riccardo Giampiccolo, Sofia Parrinelli, and Fabio Antonacci. *Churchir: A dataset of multichannel church impulse responses for spatial audio applications*. In Proceedings of the 33rd European Signal Processing Conference (EUSIPCO), pages 161–165, Isola delle Femmine, Italy, September 2025. IEEE.
