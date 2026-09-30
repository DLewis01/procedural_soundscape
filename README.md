# Infinite Blade Runner Score

**Procedural Soundscape** is a standalone browser-based generative music system inspired by the atmospheric electronic score of *Blade Runner*.

It uses the **Web Audio API** to continuously generate an evolving musical environment rather than playing back a fixed composition. Musical material is derived from a supplied MIDI source and transformed into motifs, melodies, bass figures, ostinatos, rhythmic patterns, drones, and other layers.

The result is intended to feel like an **infinite, continuously evolving score** rather than a conventional song.

---

## Features

### Generative Composition

The program generates music continuously using a combination of:

* Melodic motifs
* Counter-melodies
* Bass movement
* Chord progressions
* Ostinatos
* Rhythmic patterns
* Drones
* Mechanical pulses
* High-register textures
* Chromatic passages
* Long-form musical development
* Randomised rests and phrase lengths
* Dynamic velocity and articulation

The musical material is probabilistic, so each performance develops differently.

---

## MIDI-Derived Musical DNA

A MIDI composition is used as a **source of musical vocabulary**, rather than being played back directly.

The MIDI material provides:

* Main melodic motifs
* Lower-register responses
* Counter-melodies
* Bass movement
* Four-note ostinatos
* Rhythmic cells
* Duration patterns
* Expressive high-register material
* Chromatic runs

The program transforms this material through operations such as:

* Original presentation
* Fragmentation
* Transposition
* Rhythmic stretching
* Call-and-response development
* Motif reuse
* Register variation
* Harmonic scale constraints

This allows the original musical material to remain recognisable while producing new combinations and developments.

---

## Musical Memory

The score maintains a memory of previously used musical material.

The system remembers:

* Motifs
* Motif usage
* Source material
* Previous harmonic positions
* Scene relationships
* Chapter position
* Motif generations
* Call-and-response material

Motifs can therefore return later in altered forms rather than being completely discarded after each phrase.

Motifs may also be handed between different instrumental roles, allowing a musical idea to migrate through the arrangement.

---

## Voice Roles

Musical material can be assigned to different timbral roles:

* **Brass**
* **Rachel**
* **Choir**
* **Drone**
* **Spinner**
* **Tears**
* **Scream**

This allows the same underlying musical idea to be presented with different synthesised characteristics.

The system also supports call-and-response behaviour, where a musical phrase can be followed by a transformed response rather than simply being repeated.

---

## Long-Form Composition

The score is organised into a larger musical arc consisting of seven chapters:

1. **Introduction**
2. **Establishment**
3. **Development**
4. **Intensification**
5. **Climax**
6. **Dissipation**
7. **Return**

The current chapter influences musical density and development.

Different sections can alter:

* Motif activity
* Response frequency
* Ostinato activity
* Chromatic material
* Musical density
* Development behaviour

This gives the continuously generated music a sense of longer-term direction.

---

## Scenes

The program contains several musical scenes:

* **Rain / Night**
* **City / Neon**
* **Memory**
* **Rachel**
* **Spinner**
* **Replicant**
* **Tyrell**
* **Tears / Rain**
* **Random**

Each scene has its own musical profile controlling factors such as:

* Phrase density
* Chord activity
* Drone activity
* Pulse activity
* MIDI-derived material
* Overall density

Changing scenes therefore changes the musical character without simply switching to another fixed track.

Scene transitions can also introduce transitional MIDI material to connect the outgoing and incoming musical environments.

---

## Harmonic Architecture

The generative system includes harmonic constraints intended to keep the generated melodic material musically coherent.

Melodic notes can be:

* Snapped to the current scene's scale
* Approached through controlled pitch movement
* Developed relative to previous notes

The system also maintains harmonic continuity between generated material and scene changes.

Chromatic material is deliberately allowed to bypass some of these constraints when tension is desired.

---

## Activity and Tension

The interface provides controls for:

### Activity

Controls the overall amount of musical activity.

Higher activity can produce:

* More phrases
* More pulses
* Greater rhythmic density
* More active MIDI material

Lower activity allows:

* Longer spaces
* More sparse textures
* Greater emphasis on drones and sustained material

### Tension

Controls the likelihood of more intense harmonic and melodic behaviour.

Higher tension can introduce:

* Chromatic material
* Increased harmonic activity
* Greater musical density
* More developmental activity

---

## Tempo

The score has a global tempo control.

Tempo affects the timing of:

* Beats
* Phrases
* Rhythmic patterns
* Chords
* Pulses
* MIDI-derived material
* Sample scheduling

---

## Samples

The program can load MP3 samples from the local `samples` directory.

A `samples.json` manifest can be used to identify the available files. If the manifest is unavailable, the program can fall back to an Apache directory listing.

Samples are decoded into Web Audio `AudioBuffer` objects and then reused during playback.

There are two sample playback modes.

### Wet Samples

Wet samples are processed through through the atmospheric audio chain.

Playback can apply:

Random playback rate
Random low-pass filtering
Random filter Q
Random level
Delay
Reverb
Master processing

Wet samples are limited to a maximum playback duration of 12 seconds.

The duration is calculated from the source buffer duration and playback rate, then capped at 12 seconds.

### Dry Samples

Dry samples use a separate audio path and bypass the atmospheric effects used by the wet samples.

This provides a more direct version of the sample material.

### Sample Controls

The interface provides independent enable/disable controls for:

Background tunes
Wet samples
Dry samples

All three are enabled by default.

The wet and dry sample systems also have independent frequency controls that determine how frequently samples are introduced into the score.

Disabling a source prevents new instances of that source from being scheduled. Sounds that have already been scheduled can finish naturally.

Background Music Control

The Background Tunes control enables or disables the generated musical layers.

When enabled, the score can generate:

Chords
Phrases
Drones
Pulses
MIDI-derived material
Chapter cadences
Transitional MIDI material

The sample systems remain independently controllable.

This makes it possible, for example, to use the sample system without the generated background music.

### Audio Architecture

The program is built around the browser's Web Audio API.

The audio system contains separate processing paths for different types of material, including:

Generated musical voices
Wet samples
Dry samples
Master processing
Compression
Delay
Reverb

Active audio sources are tracked so that playback can be stopped cleanly when the score is stopped or restarted.

### Randomisation

Randomisation is used throughout the composition engine, but it is constrained by the musical structures described above.

Randomisation can affect:

Note selection
Motif development
Phrase length
Velocity
Register
Articulation
Rest placement
Sample selection
Sample playback rate
Filter settings
Sample level
Layer density
Scene behaviour
Musical development

The intention is to produce variation without reducing the music to completely unrelated random notes.

### Scene Changes

A scene can be selected manually or scenes can be randomised.

When the scene changes while the score is running, the program creates a transition between the previous and new scene.

Musical memory is retained across scene changes so that motifs can continue to develop across the larger composition.

After sufficient scene changes, older musical material can eventually be retired and replaced with new material.

Continuous Playback

The score uses scheduled bars rather than generating the entire composition in advance.

This allows the composition to continue indefinitely.

As playback progresses, the system continually evaluates:

Current scene
Activity
Tension
Tempo
Long-form chapter
Musical memory
Harmonic state
Randomised musical probabilities

New material is then scheduled ahead of playback.

### Interface

The interface provides controls for:

Scene selection
Background tune enable/disable
Scene interval
Activity
Tension
Tempo
Wet sample enable/disable
Wet sample frequency
Dry sample enable/disable
Dry sample frequency
Start / Stop
New Scene

A playback status and audio level meter are also provided.

Running the Program

The program is designed to run directly in a modern web browser.

The HTML file can be served from a local web server, for example:

http://127.0.0.1:8080/

A local HTTP server is recommended rather than opening the HTML file directly, particularly when loading local audio resources.

The sample directory should be available relative to the HTML file:

/
├── Infinite_Blade_Runner_Score.html
└── samples/
    ├── samples.json
    ├── sample1.mp3
    ├── sample2.mp3
    └── ...
Concept

The goal of the project is not to reproduce a particular Blade Runner track.

Instead, it attempts to capture some of the characteristics associated with the film's electronic score:

Spaciousness
Sustained harmony
Slow development
Repetition with variation
Melancholic melodic material
Electronic textures
Long reverberation
Sudden sparse passages
Mechanical rhythmic elements
Chromatic tension
Gradual musical evolution

The combination of musical memory, scene structure, MIDI-derived vocabulary, harmonic constraints, probabilistic generation, and long-form chapters allows the program to continually produce new music while retaining a coherent musical identity.
