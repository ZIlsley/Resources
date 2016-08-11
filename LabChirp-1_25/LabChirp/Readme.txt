LabChirp version 1.25
By Labbed

INDEX
1. About
 1.1 License
2. Changelog
3. Usage
 3.1 Overview
 3.2 Save/Load/Settings
 3.3 Quality
 3.4 Waves
 3.5 Envelopes
 3.6 Copy channel
 3.7 Mutator
 3.8 Randomizer
 3.9 Batch save
 3.10 Keyboard Shortcuts
4. Contact



_____________________________________
1. ABOUT
-------------------------------------

LabChirp is a powerful, free, easy-to-use program. With it you can create sound effects for whatever you like, with a lot of precision and control.

If you find any bugs or have a great suggestion on how to improve LabChirp, please let me know!

Contact information can be found at the end of this readme.


1.1 LICENSE
------------------
LabChirp is free to download and free to use. Any sounds you create with LabChirp (including randomized ones) are yours, which means you can use them however you want, even for commercial projects.
Feel free to redistribute LabChirp in any way you want, but please include this readme unmodified along with the program and make sure you don't charge for LabChirp itself in any way.

You do not have to pay anything to use LabChirp. However, if you find it useful, and if you feel generous, you can donate using the instructions found on the About page on my website. It would be very appreciated! See "CONTACT" below for more details.



_____________________________________
2. CHANGELOG
-------------------------------------

What happened since last version?


-- v1.25 --
* More quality options!
   You can now apply dither and oversampling.

* A more intuitive way of editing envelopes!
   Simply click anywhere to add a point, and move a point by dragging it.

* Curves for the envelopes!
   To create some really smooth envelopes without having to add many points.

* Mutator!
   To randomly tweak a sound.

* Back/forward buttons for the randomizer!
   If you accidentally skipped a cool random sound you can restore it.

* Batch save random sounds!
   Select a preset in the randomizer and save a whole bunch of sounds at once!

* Faster sound generation!
   Taking advantage of multiple cores.

* Copy/paste for envelopes!
   Copy one envelope and paste it into another!

* Added shortcuts to switch channels.
   Ctrl+Tab/Ctrl+Shift+Tab or Ctrl+1-8.

* More customization.
   You can choose your own colors for the envelopes, among other things!

* Save/export split!
   Before, both a WAV and LCH file was created when you saved. Now you can choose to save only one of these, if you want.

* General UI fixes.
   Such as grayed out buttons for muted channels, double buffered panels and DPI compatibility.


-- v1.00 --
* Higher quality sound!
   You can now choose between 22050/44100 Hz and 8-bit/16-bit.

* More envelopes!
   Modulation waves also have envelopes now.

* New waveform!
   Noise2! Which is like Noise with a linear interpolation. Also, modulations have the Custom Wave too now.

* Randomizer!
   To generate random sounds!

* General interface redesigns.
   Some things has been moved to a more logical position and some other stuff has been added or removed.

* More wave accuracy.
   There were some problems with offset and Noise but it should be fixed now. Also, most values now have one decimal.

* Easier value edit!
   You can now click on the number next to a slider to edit its value.

* Undo!
   You can now undo and redo.

* Other not very interesting stuff.
   Like settings, bug fixes, an about box, menu bar and more!


-- v0.85 --
* Initial release



_____________________________________
3. USAGE
-------------------------------------

Here follows a complete explanation for every control in LabChirp.


3.1 OVERVIEW
------------------
At the top is the menu bar. Here you will find save and load and undo and stuff like that.

Below the menu bar you will see "Length" and "Delay".
Length:
The length of the sound. One length value is one sample for 22050 Hz and two samples for 44100 Hz. To the right of it you can input the length in seconds.
Delay:
How long before the sound plays. Same unit as Length.

To the right you will see eight different channels and next to each of them there is a check box.
When the box is checked, the channel is enabled (not muted).
To switch to another channel, just click on the button with the channel name.

To the left/middle there are three different groups of controls. These are the different waves.
See "WAVES" below for more details.

Towards the bottom you will see the envelope/Custom Wave edit boxes. To switch envelope, click on the button to the left corresponding to the envelope you want to edit. To edit Custom Wave, click the button below the waveform selector.
See "ENVELOPES" below for more details.

At the very bottom, you will see a graphical representation of your generated sound.

To the lower right, below the channel buttons you will find:
Copy: For copying elements from one channel to another. See "COPY CHANNEL" below.
Mutate: Shows the mutator. See "MUTATOR" below for more details.
Randomizer: Brings up a window with lots of different buttons and controls. This is the random generator! See "RANDOMIZER" below for details.
Play: This plays the sound. Press this often!


3.2 SAVE/LOAD/SETTINGS
------------------
Save:
Did you create something you like? Save it! You can save a project file (LCH) so you can edit it later, or you can export your sound to a WAV-file so you can use it elsewhere, or you can do both at once! You will find the save options under "File" in the menu.
The output quality of the wave file depends on what you have set under "Quality". I recommend using 8-bit 22050 Hz (faster generation) when editing the sound and then changing this to the desired quality before exporting. See "QUALITY" below for more details.

Load:
To load a previously saved sound, click "File > Open..." (or press Ctrl+O), find the file and click "Open".

New:
"File > New" (or Ctrl+N) will reset all parameters.

Settings:
To edit settings click "Edit > Settings...". You'll see two tabs:
General:
"Default output quality" sets the quality that new projects will have by default.
"Default Dither" and "Default Oversampling" sets the dither/oversampling that new projects will have by default.
"Envelope editing" lets you choose how to edit the envelopes.
"Max undo" lets you limit the amount of undos, in case you have very little RAM or something...
"Ctrl+S = " determines what happens when you press Ctrl+S.
Appearance:
"Line smoothing" determines if the envelope lines are anti-aliased or not.
"Point shape" changes the appearance of the envelope points.
Then there's a bunch of color boxes. Here you can edit the colors of the different elements of the envelopes and the WAV graphic! There is a sample envelope at the bottom. Use the selector to see how different envelopes will look.
Click "OK" to save your settings ("settings.cfg" will be created in the same directory as "LabChirp.exe").


3.3 QUALITY
------------------
22050 Hz/44100 Hz:
Hertz (Hz) determines the sample rate of the output sound. Basically how many values per second it stores. Higher sample rate means you can achieve higher frequencies.

8-bit/16-bit:
Bit depth determines the resolution of the stored values. 8-bit is 256 different values per sample, while 16-bit is 65536 different values per sample. Higher resolution means you can get more fine detail. You can clearly hear a difference for instance at the end of long fade outs.

Dither:
With a limited resolution, the program needs to round a generated value so it fits the resolution. Imagine a really quiet sine wave with values ranging from -0.4 to +0.4. If the rounding is consistent, all its values will be rounded to 0.
Dither is basically inconsistent rounding, to get a more accurate average representation, so you can still hear the wave even after you really shouldn't be able to with the current resolution. Although it can be a bit noisy.
There are two different methods of dither in LabChirp.
Floyd-Steinberg simply forwards the rounding error to the next sample and adds it to its value, which gives a very even and reliable estimation of the sound. However, it does in itself create some audible artifacts. Maybe not optimal for sound.
Noise basically adds a really quiet noise to the sound, so the rounding will be more chaotic. Has no audible artifacts.
Dither doesn't always improve the quality of the sound and often creates unnecessary noise. Try it out for your sound and see if it sounds better!

Oversampling:
Oversampling can be used to really improve the quality of sharp waveforms. Actually all waveforms but it's most notable with sharp ones like saw or square.
With oversampling, each sample will become an average of adjacent values between the previous sample and the next. This gives a much better representation of the actual value.
Higher oversampling setting means more adjacent value gathering per sample, but also longer generation time. "Low" is usually good enough.

Note that dither and oversampling does not affect the output sound file size.


3.4 WAVES
------------------
There are three waves to keep in mind:

Main wave:
The basic wave of your sound.

Frequency modulation:
Modulates ("vibrates") the pitch of your main wave.

Volume modulation:
Modulates the volume of your main wave.

Each have their own volume/amplitude slider, frequency slider, waveform and waveform offset slider.
The volume/amplitude slider determines the strength of the wave.
The frequency slider determines how fast the wave will repeat (in Hz).
The waveform is the shape of the wave. Try them out!
"Custom" will not have any shape unless you change the envelope for it (click the "Custom" button below the waveform selector to edit it).
The Offset slider determines the offset of the wave. Or by how much it will be "pushed to the left". This can be useful for a bit more advanced sounds.
When Noise is selected, offset determines the seed for the noise generation.


3.5 ENVELOPES
------------------
Main wave, Frequency modulation and Volume modulation have two envelopes and one Custom wave each.

Volume/Amplitude:
This changes the volume of the wave over time.

Frequency:
This changes the frequency (or pitch) of the wave over time.

Custom wave:
This lets you create your very own waveform! Be sure to have the "Custom" waveform selected in the waveform selector.

Here's how to edit the envelope:
Mode A:
Left-click to move the selected point to the cursor
Mode B:
Left-click a point to select it
Left-click and drag a point to move it
Drag a point outside the envelope to delete it
Left-click on an empty space to create a point there

The following commands always apply, regardless of editing mode:
To select a point, right-click on or near it. You can select a different point with Shift+left/Shift+right.
You can move the selected point using the arrow keys for more precision (Ctrl+arrow keys moves it more).
To add a point in the envelope, click "+" to the right and a point will be added between the currently selected point and the next one (so it will not do anything if the last point is selected).
To remove a point from the envelope, click "-" to the right and the currently selected point will be removed. Note that the first and last point in the envelope cannot be removed.

There is also an edit menu, with more commands:
Flip Horizontally: Flips the envelope horizontally.
Flip Vertically: Flips the envelope vertically.
Copy: Copies the current envelope to clipboard.
Paste: Pastes a copied envelope into the current. Note that it doesn't have to be the same kind of envelope as the copied one. You can for instance copy the main frequency envelope and paste it into the main volume envelope.
Reset: Resets the points of the envelope.

Check the Curves checkbox to get curves between the points instead of straight lines.


3.6 COPY CHANNEL
------------------
To copy elements of a channel to another channel, do this:

1. Select the channel you would like to copy from.
The text below the channel buttons should say "Copy Channel X to:" where X is the currently selected channel.

2. Select from the list which channel you would like to copy to.

3. Click "Go!".
You will see a lot of checkboxes. De-select anything you don't want to copy from that channel and then click "Copy".


3.7 MUTATOR
------------------
If you want to slightly change something with your sound but you're not sure what, you can use the Mutator. When you click "Mutate!", the parameters of your sound will change randomly. How much depends on the sliders.
You can apply the mutation to all enabled channels or only the selected channel.


3.8 RANDOMIZER
------------------
If you are lazy or something and don't want to create your own sound from scratch, you can use the Randomizer to let LabChirp generate a sound for you! Just click the button labeled "Randomizer" below the channel buttons and it will pop up. Now, there's a lot of controls here! But don't worry! Just select one of the presets and click "Randomize!". Congrats! You made a sound!
...
But what are all the controls for?
Well, you can edit or create your own randomize presets if you want. Here's how:

Main:
In this tab you can set the limits for most of the controls in the main window. For instance, if you set Main Frequency to Minimum 100 and Maximum 200, the generated sound will have its main frequency value somewhere between 100 and 200.

Waveforms:
Select all waveforms you want included in the randomization. So if you only want Noise, have only that selected.
"Custom" will generate a random Custom wave!

Envelopes:
This controls how the different envelopes will be generated. Maybe you want it to mostly move downwards? OK!
"Start" simply means where the first point will be. If you want it to start at the top always, set minimum to 100 and maximum to 100. To make it start somewhere between 20 and 50, just set minimum to 20 and maximum to 50.
"Next X" is how far away the next and following points will be horizontally. "1" means it will be created only one step from the previous, and "500" means it will jump all the way to the right.
"Next Y" determines how far up or down the next and following points will move. To make the envelope move towards the bottom, have a maximum and minimum value of 0 or less.

If you like your new preset and would like to use it again sometime, save it! Type a new name for it (in the preset selector) and click "Save".
Once saved, it will show up in the list with the other presets.

"Randomize!" will generate the sound. This changes the controls of all channels so anything you might have done before that will be replaced.

With the arrow buttons next to the randomize button, you can re-generate a previously generated sound. Very useful if you randomize a lot, impatiently looking for a cool sound, and then you hear it but you accidentally randomized a new sound, replacing that cool sound. Well, don't worry! Just click the back button to restore it.

"Batch..." will open the Batch Save dialog.


3.9 BATCH SAVE
------------------
With this, you can generate a whole bunch of sounds at once! What gets saved depends on the randomizer settings.
Select how many sounds you want to be generated, and file type (LCH and/or WAV), then click Save.
Now you get to input a base file name. All generated files will use this name as a prefix, followed by a number and the file extension.


3.10 KEYBOARD SHORTCUTS
------------------
Here is a list of all the keyboard shortcuts you can use in LabChirp.

P................Play the sound
Esc..............Stop currently playing sound
Ctrl+N...........Reset/New
Ctrl+O...........Load
Ctrl+S...........Save
Ctrl+Z...........Undo
Ctrl+Y...........Redo
Ctrl+Shift+Z.....Redo
Alt+F4...........Exit
Ctrl+Tab.........Select next channel
Ctrl+Shift+Tab...Select previous channel
Ctrl+1-8.........Select specific channel

ENVELOPE
Up...............Move point up one step
Down.............Move point down one step
Left.............Move point left one step
Right............Move point right one step
Ctrl+Up..........Move point up five steps
Ctrl+Down........Move point down five steps
Ctrl+Left........Move point left five steps
Ctrl+Right.......Move point right five steps
Shift+Left.......Select previous point
Shift+Right......Select next point
Numpad+..........Add point
Insert...........Add point
Numpad-..........Remove point
Delete...........Remove point



_____________________________________
4. CONTACT
-------------------------------------

You can contact me by sending an email to labbed@labbed.net.
Please also visit my website for other stuff!
http://labbed.net/

Have fun!

