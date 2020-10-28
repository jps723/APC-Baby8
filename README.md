# APCBaby8 Build Notes 2/16/20
 
**Design Notes:**
 
This design is based on the Atari Punk Console and the Baby8 Step Sequencer.  It utilizes three 555 timers, and a 4017 decade counter, to emit a square wave in a repeating series of frequencies.  It’s a stackable design broken into UI and Utility boards. 
 
The design operates off of 9v, with ‘+/-‘ symbols etched into the top layer of the bottom board, indicating polarity. There are additional ‘–‘ etchings indicating the required ‘notch’ orientation for all of the ICs.  The arrows indicate the directions that the boards should be facing when stacked.
 
The UI board contains 11 variable resistors in total; 8 for defining the pitch to be played in the sequencer, and three others for controlling the rate at which the sequence advances, the pulse width of the oscillation, and the master volume. 
 
Each of the 8 pitch variable resistors is connected to an output pin of a 4017 decade counter (located on the utility board), which counts through the 8 step sequence.  As each step is passed, the emitted voltage as determined by the position of the pot is applied to oscillator A of the APC, affecting its frequency.  Each step has an associated LED located above it for indicating which step is being played. The 1N4148 diode is for preventing noise from unintended steps.
 
The Utility board contains the decade counter, a 555 timer that serves as the master clock, and two more 555 timers serving as oscillators A and B for the APC.  Oscillator A is in astable mode, and oscillator B is in monostable mode, with its trigger coming from the output of oscillator A.  Oscillator B has a pot connected to it for varying the pulse width of the oscillation. The 4017 decade counter emits 10 steps, however step 9 triggers the reset pin, limiting the sequence to 8.  The output voltage from the stepped variable resistors are applied to the discharge pin on Oscillator B, dictating the charge rate of the attached capacitor, and ultimately the oscillation frequency. 

 
## **Build Process:**

**Bottom Board:**
**Top Layer:**
Bits: 1/32” / 1/64”
Mill Time: ~4 ½mins

**Bottom Layer:**
Bits: 1/32” / 1/64”
Mill Time: ~14 ½mins

**Top Board:
Bottom Layer:**
Bits: 1/32” / 1/64”
Mill Time: ~17 ½mins