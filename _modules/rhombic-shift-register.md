---
description: Complex shift register for algorithmic composition
status: beta
index: 10
---
The <span class="newthought">Rhombic Shift Register</span> (RSR) is a four-voice, demuxing shift
register for the <a href="http://www.vcvrack.com/">VCVRack</a> modular synthesis environment.
The RSR consists of four looping “analog” shift registers whose inputs and outputs are
switched via control voltage.
By skillfully applying modulation, automatic variations upon
source patterns may be generated. Using the Rhombic Shift Register with a sequenced melody allows you to
design complex arabesque patterns and arpeggiations.
On the other hand, you need not need not use a sequencer or keyboard
to play the RSR. Good results have been obtained with quantized stepped and random voltages,
feedback patches and other unconventional sources.<label for="sn-westcoast" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-westcoast" class="margin-toggle">
<span class="sidenote">
 Commonly termed “West coast synthesis”
</span>

## Shift Registers

The Rhombic Shift Register has four independent shift
 registers<label for="sn-asr" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-asr" class="margin-toggle"><span class="sidenote">Familiarity with basic <a href="https://sites.google.com/site/westcoastsynthesis/asr">analog shift register</a> operation will help comprehension of this document.</span>,
 denoted <strong>lanes</strong>. Each lane
has two <strong>channels</strong>. The left-hand channel is intended for a pitch CV, for generating a melody.
The right-hand channel may be utilized for a secondary modulation, or a pattern of gates.

Each lane has two parameters associated with it. The left-hand lane slider determines
the <em>length</em> of the shift register. In the fully lowered position, there are 16
stages. The right-hand slider moves the location of the tap or output. If the right <em>tap</em>
value is greater than the left <em>length</em> value, the tap will be set to the last stage
of the lane. Independent values for the tap position and the lane length will be
useful when utilizing the looping feature. In short:

* The left hand slider controls the capacity of the shift register (length).
* The right hand slider controls which step of the shift register is selected to play notes (tap).
* When the shift register loops, the loop is fed from the final cell (length).
* If the right hand control (tap) is set to a value greater than the left hand (length), the tap is set to the length – that is, there is no memory past the tap point.

## Outputs

Each lane has a pair of outputs, the left corresponds to CV1, the right corresponds
to CV2 with some logic applied.<label for="sn-seemodes" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-seemodes" class="margin-toggle"><span class="sidenote">
  See <a href="#modes">Modes</a>
</span>


## Lane Selection Blocks

Below the primary CV inputs there are two <strong>lane selection blocks</strong><label for="sn-ps" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-ps" class="margin-toggle"><span class="sidenote">Other modules with a similar control scheme include Make Noise RxMx, Verbos Pan and Scan, &amp; Toppobrillo Mixiplexer.</span>
blocks, for the lane inputs and outputs respectively. By adjusting the position of these knobs and applying
modulation, you may control which lanes are receiving input and which lanes are outputting.
The state of each lane and its activity are indicated by the LEDs above and below each channel.

When neither the input the output nor the input of a lane is active, a clock trigger
will not cause the state of a lane to change.<label for="sn-muted" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-muted" class="margin-toggle"><span class="sidenote">
  This functionality may change in future revisions to be controlled by a panel switch.
</span>

When the input for a lane is disabled but the output is enabled, a clock pulse
will advance the pattern normally, but the memory cell of the lane<label for="sn-looping" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-looping" class="margin-toggle"><span class="sidenote">
e.g. the cell at the position pointed to by <em>tap</em>
</span> will be
copied into the input, causing <em>looping</em>.

Normal output and looping output correspond to magenta and amber LEDs respectively.
The top block of LEDs only illuminate for activity momentarily; the bottom remain illuminated
as long as a lane keepings sounding a note.<label for="sn-neg" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-neg" class="margin-toggle"><span class="sidenote">
  Generally, corresponding to the pulse width of the input clock.
</span>


By passing the width control counterclockwise, past 12 o'clock,<label for="sn-neg" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-neg" class="margin-toggle"><span class="sidenote">
  Or by applying modulation such that the summed <em>width</em> voltage is negative.
</span>
we engage <em>inverted channel width</em>. By doing so, the channel with grows inwards from
the outer channels towards the center point.

## Modes

The CV2 channel has three modes accessible from the panel switch:

<span class="newthought">Gate</span> mode triggers a 10-volt gate if the value
in the CV channel is high. When CV2 is normalled to the clock input, the CV2 channels
will generate short trigger pulses instead of gates.

<span class="newthought">Velocity</span> mode outputs the stored CV while the
input clock is high. This is useful for generating a variable height modulation
envelope with a slew limiter.<label for="sn-befaco" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-befaco" class="margin-toggle"><span class="sidenote">
    The Slew Limiter and Rampage modules from Befaco are good candidates for this application in VCVRack.
</span>

<span class="newthought">CV</span> mode causes the right channel to operate identically
to the left-hand channel. This is useful for encoding a timbre parameter.

## Normalling

CV2 and clock inputs are bidirectionally normalled to each other.
<em>Width</em> and <em>center</em> modulation inputs are normalled downwards
from the input block to the output block.

## Demos

I've compiled a few demos from the development process.

<figure class="iframe-wrapper fullwidth">
<iframe width="1280" height="720" src="https://www.youtube-nocookie.com/embed/videoseries?list=PLXG1DTcPHByw0bAFYJRXT4XNtOtAl_J2o" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</figure>

## Design Notes

Although the module takes inspiration from a number of existing designs, the overall
scheme is novel to the best of my knowledge. The visual design attempts to draw on
 elements from Digital Equipment Corporation's 1970s era minicomputer<label for="sn-dec" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-dec" class="margin-toggle"><span class="sidenote">
  The color elements in this module are based on the <a href="https://en.wikipedia.org/wiki/PDP-11">PDP 11</a>.
  An interested reader may note that the <a href="http://gunkies.org/wiki/PDP-11/20">PDP 11/20</a> also featured <a href="http://gunkies.org/wiki/ASR33">ASRs</a>.
 </span>
 consoles.
