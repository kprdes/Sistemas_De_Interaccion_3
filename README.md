# The Longing - Music Composition in OpenMusic
## Members:

- Kevin Pérez

## Link to Youtube video

- Link: https://youtu.be/jtlr4QS2f0A

## Project Overview

This project is a custom music composition designed for the game **The Longing**, using the **OpenMusic** environment. The goal was to create calm and soothing music without abrupt transitions, fitting for the game's slow-paced and introspective atmosphere.

The composition features **two main audio tracks**, which are varied using frequency modifications in a loop. Through this loop, the frequencies are altered, resulting in a total of **eight distinct tracks** with frequency variations. These variations ensure that every 30 seconds, a new track is introduced, providing fresh content without repetition.

## How the Music Was Created

The core of the project revolves around generating variations of the two original tracks by manipulating their frequencies. Here’s how the music was structured:

- **Chord-seq** was used to arrange the notes and chords for the two primary tracks.
- A **loop** was implemented to modify the frequencies of the tracks dynamically, creating variations. Each frequency is adjusted by adding different values (100, 500, or -300), producing eight unique tracks.
- Every 30 seconds, a new track is introduced to meet the requirement of fresh content.

### Key Elements of the Program Logic

1. **Frequency Manipulation**:
    - The main logic is built around capturing the frequency list's size using the **`length`** function.
    - The **`forloop`** runs from 0 to `length - 1`, iterating through the list of frequencies.
    - Using **`nth`**, the program captures each frequency value and adds the corresponding variation (100, 500, or -300 depending on the patch).

2. **Condition Checking**:
    - The **`equal`** function is used to check if the loop has reached the end.
    - The **`omif`** object is passed a boolean value and the modified frequency to ensure that only the correct frequencies are processed in each cycle.

3. **Data Accumulation**:
    - The modified frequency values are accumulated using the **`collect`** function, which stores each iteration's output.
    - Finally, the **`append`** function combines the results in different orders, creating the final audio tracks with variations.

4. **Flattening Lists**:
    - In the patch named **`patch`**, the **`flat`** function is used to flatten the list after an **`append`** between four sounds. This allows the flattened list to be used in the loop to apply the -300 variation to each frequency.
    - Once the variations have been applied, an **`append`** operation combines the four original sounds with the four newly modified ones, resulting in a final list of eight sounds with frequency variations.

5. **Exporting the Tracks**:
    - The final list of eight sounds is stored in a **chord-seq** and exported as a **MIDI** file.
    - This MIDI file is then opened in **Audacity**, where it is converted to an **MP3** format, making it compatible for use in the gameplay.

### Result

By the end of the process, eight audio tracks are generated, each with subtle frequency variations derived from the two original tracks. The tracks are smoothly looped to ensure continuous playback with no sharp transitions, aligning with the mood of **The Longing**.

## File Structure

- **OM patches**: The patches created in OpenMusic are stored in `.omp` files.
- **README.md**: This file contains the project documentation.
- **MIDI files**: The tracks are exported as MIDI files.
- **MP3 file**: The final audio, converted from MIDI using Audacity.
