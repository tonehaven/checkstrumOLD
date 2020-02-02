# chordings
**Find, describe, and display chord voicings for string instruments featuring necks and fretboards.**

**THIS PROJECT IS NOT STARTED YET!  IT IS JUST A SET OF THOUGHTS AT THIS POINT.**
## Project Objectives
A python library of tools for:
* machine-oriented description of string instruments
* machine-oriented description of chord theory
* machine-oriented description of chord voicings for specific string insruments
* lookup api for obtaining chord voicings from various sources
* automatic generation of chord voicings for a specific string instrument
* display of chord voicings

## Thoughts on String Instruments
There are many unique musical instruments in the world with creative methods for vibrating
strings and adjusting the pitch and timbre of those strings.  The author(s) of this project
do not claim to be experts on world-wide musical instruments and likely have missed the
opportunity to represent some interesting instruments properly.  This section describes the
language used in the project to define supported string instruments.

This library focuses on instruments in the **lute** family of string instruments that feature
a neck and fretboard on which one hand can change the musical pitches of zero or more strings
by shortening the length of the vibrating strings.

This includes instruments such as:
* guitar
* bass
* ukulele
* banjo
* mandolin
* viola
* violin

### Physical Description of a String Instrument
Each string instrument will be defined using a series of properties.  The library will
come with definitions for some common instruments but be extensible via user defined
instruments.

An instrument definition will include:
* right or left handed (defining which hand vibrates the strings (via plucking, bowing, ...))
* number of courses (groupings of one or more strings)
* per course:
  * number of strings in course
  * is course a drone or fretted
Per each string in a course, the following properties are defined:
* nut fret
  * zero for open string at longest scale length of the instrument
  * positive integer giving the number of semi/half-tones above the zero fret the string's open fret is (i.e. the 5th string on a banjo)
* ...
    
Not currently supported are methods for defining the scale length, material, or
diameter for each string.  These properties affect the timbre of the instrument and available 
tuning range, but not the notes of the chords.

### Methods of String Vibration
It is envisioned that the individual strings of supported string instruments are sounded by
either plucking (with fingers or plectrum) or bowing (e.g. a horsehair bow).  It is also
feasible that hammers (either hand-held or operated by fingered keys) may generate the
vibration.  The library is most useful for instruments on which multiple strings can vibrate
simultaneously in harmony either by simultaneous (or near simultaneous) activation or
musically-timed succession (arpeggio).

### Chords
The group of notes in a single harmony is called a chord.

...
