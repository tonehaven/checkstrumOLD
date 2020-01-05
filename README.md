# chordings
**Find, describe, and display chord voicings for string instruments featuring necks and fretboards.**

There are many online resources and apps that provide chord voicings for common instruments like
6 string guitar and ukulele tuned in standard tunings.  The goal of this project is to provide
automated chord voicings for not only those cases, but that is extensible to a variety of unique
instruments and non-traditional tunings for common instruments.  Do you have an eight string
guitar?  Do you want to tune your uke to GDEA tuning?  Perhaps this library can help you find
voicings for common chords.

## Project Objectives
A python library of tools for:
* machine-oriented description of string instruments
* machine-oriented description of chord theory
* machine-oriented description of chord voicings for specific string instruments
* lookup api for obtaining chord voicings from various sources
* automatic generation of chord voicings and fret maps
* display of chord voicings

## Thoughts on String Instruments
There are many unique musical instruments in the world with creative methods for vibrating
strings and adjusting the pitch, tension, and timbre of those strings.  The author(s) of
this project do not claim to be experts on world-wide musical instruments and likely have 
missed the opportunity to properly represent some interesting instruments.  This section
describes the type of instrument envisioned by the author, the language used in the 
project to define supported string instruments, and the limitations of the current
implementation.

It is anticipated that this library will be most helpful for players of instruments in the
composite chordophone family.  This family of instruments make sound by way of vibrating
strings that are stretched between two points and that run roughly parallel to an
integrated neck.  As the focus of the library is chords, or multiple musical notes played
in harmony, Chordings is most useful for instruments featuring multiple (likely three or
more) strings.

Supported instruments stretch the strings above a neck that features some means of
optionally limiting the length of the string that is vibrating and, thereby, raising the
musical pitch of the vibrating string.  Often this involves the player pressing zero or
more strings against a finger board or frets on the neck, but other mechanisms have been
used.  Frets are narrow protrusions from the neck or finger board that run roughly
perpendicular to the strings and stop the string vibration at specific pitch changes.
Frets can improve playability by ensuring intonation and limitting both the distance 
the string must be depressed and the amount of mechanical pressure required to cleanly
sound the new pitch.  For simplicity, the processes of limiting the vibrating string
length will be referred to as "**fretting**" even when applied to fretless instruments.
Strings thus limited are said to be **fretted**.

It is not uncommon for strings to be grouped.  A single group of strings is called a
**course**.  The strings of a course are usually tightly grouped together with narrower
spacing than the spacing between courses.  Not all courses on an instrument may have
the same number of strings or be multi-string.

At this time, Chordings will assume that all strings in a course:
* are meant to be sounded/played simultaneously
* are fretted at the same place on the neck
* either sound the same note (unison) or octave variants of the same pitch family

Playing individual strings in a course (either via selective sounding or muting) is 
not supported nor is intra-course string selection when fretting.


Using multiple strings in can increase 
volume and 

two or more
groupings 
Sometimes multiple strings are grouped together closely and are meant to be sounded 
simultaneously and fretted at the same stop location (fret).  



COURSES

The number of known instruments this description can cover is vast.  Some of the more
popular instruments include:
* guitars
  * classical, acoustic or electric
  * 6, 7, 8, 12 or any number of strings
  * different scale lengths: standard, tenor, baritone, ...
  * dobro, dojo, ...
* bass guitar (acoustic or electric; any number of strings, ...)
* ukulele
* banjo (mandolin banjo, banjolele, ...)
* mandolin (mondola, mandora, octave mandolin, mandocello, mando-bass, mandriola, ...)
* cigar box guitar
* strumstick
* dulcimer
* oud
* sitar
* other spike lutes: sintir, rubab, sanshin, shamisen, sanxian, ...
* other necked bowl lutes:  bağlama, bouzouki, charango, laúd, lute, pipa, tricordia, ...
* violin, viola, cello, double-bass, and family variants
* tenor, alto, tenor, and bass viol and family variants
* lyra, rebec, hurdy-gurdy, and other regional bowed instruments

Note that bowed instruments typically can only play one or two strings at a time, or, with
more bow pressure, sometimes three.  Chords are typically played by arpeggiating on the
single notes or intervals (pairs of notes).

References include:
* Wikipedia:
  * [Chordophone](https://en.m.wikipedia.org/wiki/Chordophone)
  * [string instrument](https://en.wikipedia.org/wiki/String_instrument)
  * [Hornbostel–Sachs number: 32](https://en.m.wikipedia.org/wiki/List_of_musical_instruments_by_Hornbostel%E2%80%93Sachs_number:_32)
* [Atlas of plucked Instruments](https://www.atlasofpluckedinstruments.com)

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


[Chord Scale Generator](http://www.pluck-n-play.com/en/index.html)
[Scale and Chord Generator](https://12bar.de/php/scale_generator.php)
[Chord and Scale Printer](https://www.studybass.com/tools/chord-scale-note-printer/)
[Look no Hands](http://www.looknohands.com/chordhouse/guitar/index_rb.html)
[gootar](http://www.gootar.com/)
[Wikipedia Guitar Chords](https://en.wikipedia.org/wiki/Guitar_chord)
[Regular Tunings for Guitar](https://sethares.engr.wisc.edu/alternatetunings/regulartunings.pdf)
