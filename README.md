# Chord Suite Manual (Work in progress)

For supports / bug reports / feature requests, contact jiahao@maglav.studio 

Note: **VCV 2 is now supported**

![Alt text](.//chordsuite.png?raw=true "Chord Suite")

## Quick Tips (How To Start):

Chord Player:

- modulate the Chord Set / Chord CV to get different scales and create chord progressions.
- modulate the Bass Note Select CV to create basslines.
- use 'Wonderwall' mode via menu to repace 7th note with 8th (root note but an octave higher).
- use 'Voice 1 Polyphonic' via menu to use voice 1 as polyphonic output.
- modulate the voicing cv input (activate by pressing the voicing button) to alter chord voicing.
- select your global song key via menu.

Arp Player:
- connect Arp Player to Chord Player by simply placing it on the right side of Chord Player without any empty space.
- modulate the Note Combination CV to get different combinations of chord notes.
- modulate the Quantize Mode CV to dynamically quantize to chord notes or scale notes.
- when patching a lfo into the Raw Pitch Input, using 'Arpeggiator Mode' via menu will give you a better pitch range.
- use the Sample N Hold CV to create rhythmic patterns.
- Arp Player is chain-able, add as many as you want, just remember to place it on the right side without empty space. 

## CHORD PLAYER

Chord Player is a 4-plus-1-voice quantizer designed for playing chord and bassline together.
It also has an expander module called Arp Player which is suitable for playing individual chord notes.

### Highlight Features:
	
- Selecable Chord Sets
- 4 pitch CV outputs for chord voices and 1 independent bassline pitch CV output
- Revoice mode with Voicing CV input
- High Defination OLED Display (Virtual)
- Optional arpeggiator expander module.

*outputs are marked with dark outlines.*

### Inputs, Outputs & Controls

**Chord Set Select Knob & CV:** Select a active Chord Set. Each Chord Set is a collection of chords, usually contains 7 chords within a musical scale.

Avaible Chord Sets:

| Chord Set | Scale            |
|-----------|------------------|
| maj       | Major            |
| min       | Minor            |
| dor       | Dorian           |
| phy       | Phygrian         |
| lyd       | Lydian           |
| hmn       | Harmonic Minor   |
| pmj       | Pentatonic Major |
| pmn       | Pentatonic Minor |

**Chord Select Knob & CV:** Select a Chord from a Chord Set.

**Bass Note Select Knob & CV:** Select the pitch of the Bass Note Output from a chord. It can be used as an arpeggiator.

**Voice Output 1 - 4:** Pitch CV outputs for individual chord voices. Usually voice 1 is the root of the chord.
	
| voice                | 1    | 2         | 3   | 4         |
|----------------------|------|-----------|-----|-----------|
| chord note (usually) | root | 3rd / 2nd | 5th | 7th / 6th |



**Bass Pitch CV Output:** Output for bass note pitch CV.

**Voicing Button:** Toggles revoice mode. When revoice mode is off, the default voicing is root, 3rd + 1 oct, 5th and 7th.

**Voicing CV & Led:** Input for voicing CV. When revoice is enabled (by toggling the revoice button), the higher the Voicing CV is, the higher the revoiced notes will be.
This led indicates how far the voicing cv is from the default voicing. When voicing cv is higher than the internal cv, led will light up green, if voicing cv is lower, it will light up green.

**Transpose:** Global transpose cv, 1v/oct standard.

### Menu Item
**Audio Rate:** When active, the module runs at audio rate. By default it runs at 1/16 of the audio sample rate. 

**Wonderwall:** When active, voice 4 is replaced by voice 1 + 1 octave. Musically speaking the 7th is omitted and replaced by the root note an octave higher. So you can play major and minor chord without the 7th,

**Use Flat Notation:** When active, chord names are displayed with flat note names instead of sharp ones.

**Voice 1 Polyphonic:** When active, voice 1 becomes a polyphonic output and outputs all the chord notes.

**Output add 3v:** When active, all outputs are added by 3 volts internally. This is use for some VCV modules having different 1v/oct range.

**Global Root Note:** Select the root note of the Chord Set. Useful to set your song???s key.

## ARP PLAYER

Arp Player is a chain-able quantizer/arpeggiator expander module for Chord Player. This allows users to use it to create melodies on top of Chord Player???s active chord.

**Arp Player has 3 sections, the Arpeggiator, the Scale Quantizer and the Sample N Hold section.**

*Signal flow for the module is:*
	*Pitch Input CV -> Arpeggiator/ Scale Quantizer -> Sample N Hold -> Quantized Output*

### How to install:  
Please place the module on the right side of a Chord Player module as the panel suggested. You can chain multiple instants of the Arp Player by placing another one on the right side of the previous one.

### Arpeggiator / Scale Quantizer Section
Pitch Input CV will be quantized by either the Arpeggiator section or the Scale Quantizer section. Users can select which section to use by toggling the Quantize Mode Button or using the co-responding Quantize Mode CV.

When in Arpggiator mode, pitch input is quantized to notes selected by the Note Combination Knob & CV. When In Scale Quantizer mode, pitch input is quantized to the musical scale of the Chord Set.

### Inputs, Outputs & Controls
**Note Led 1 - 4 ( from bottom to Top):** Each led co-responses to a note in the chord. When a Note Led lights up, it means the co-responding note is available as quantizing target. Led 1 (bottom) is usually co-response to the root note of a chord (voice 1) and Led 4 is usually the 7th (voice 4).

When in Scale Quantizer mode, no note led will light up.
 
**Note Combination Knob & CV:** Use this to select what notes the pitch input will be quantized to.
When the knob is in fully CW position, all 4 notes of the chord are available for quantization. When in fully CCW position, only the first note (root note) is available.

**Quantize Mode Select Button & CV:** Use this to toggle between Arpeggiator Mode and Scale Quanzier Mode.

**Sample N Hold Led & Sample N Hold Trigger In:** When the Sample N Hold Trigger is connected, the Sample N Hold Section of the module is active. The quantized result is temporarily stored away and quantized output will not update until a trigger signal is received.
The led indicates how far the stored pitch is from the current output. Red indicates a lower pitch and green indicates a higher one.

**Pitch Input & Output CV:** These are the unquantized pitch input and the quantized pitch output.

### Menu Item

**Audio Rate:** When active, the module runs at audio rate. By default it runs at 1/16th of the sample rate. 

**Arpeggio Mode:** This will adjust the ???voltage space??? between notes in Arpeggiator mode . By default, Arpeggiator Section quantizes the pitch input cv to a nearest chord note. 
For example, in a C Major 7 chord, voltage difference between B and C will be smaller than C and E. So if you use a triangle LFO as pitch input, it will stay longer between say note C and E and much shorter time between. B and C.
	When active, the voltage space is divided evenly between 4 notes. So you can have an equal amount of time stayed between notes as in the last example.


