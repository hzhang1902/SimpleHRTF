# SimpleHRTF

A new, easy and fast method to get your Head Related Transform Function. Includes a concept prototype Max 7 program for testing.

The project is based on FFT-based binaural panner by Mr. JAKOB HOUGAARD ANDERSEN. 
<a>https://cycling74.com/tools/fft-based-binaural-panner</a> 


## How to Try out the Program
The main max file is Simple HRTF Individualization.maxpat. Open it.


### Preparation
1. Click on "Set HRTF file folder” at the top of the grey panel, and set the folder to “All HRTF matrix files”. This loads the HRTF files of all subjects. You can download it from <a>http://jakobhandersen.dk/projects/fft-based-binaural-panner/download/</a>
2. Click on “open” button on top of sfplay~ on the right, and select the stimulus sound file (in this case, cowbell.aiff). This loads the stimulus for testing
3. Click on every “average” button in the ITD matcher (purple panel area). This initializes the environment with average ITDs across the board
4. Click “confirm” and then “confirm 2” below ITD matcher

### Fast Fourier Transform Matcher
First start with the FFT matcher (blue panel area)
1. Click on a direction button (i.e.: “0 0”, “36 80”). The first number is azimuth, second is elevation
2. Pick a function model at the right side of the direction button (number buttons)
3. Click on the play button below to test it out
4. If what you hear does not match the direction, pick another function model and play
5. Repeat 2- 4 until you find the best match
6. Click save/ok button right to the play button
7. Repeat 1 - 6 until all 7 directions are calibrated

You can always check out your calibrated result by clicking the “7” button at the top right corner, result will be printed on the console

### HRTF Subject Matcher
Then use the HRTF subject matcher (orange panel area)
1. Click on “find match” button
2. Click on “print the result” button


The best match subject number and the number of matches will be printed on the console.


Keep in mind subject number is not the name of the subject. i.e.: Subject no.3 doesn’t mean subject3, it means the third subject which is subject9.


You can now load the subject to the best match subject on the grey panel by clicking “choose from menu”

### ITD matcher
Optional: Anytime you feel unbalanced delay in your ears, use the ITD matcher (purple panel area). Each ear’s left/front/right delay refers to each ear’s delay in ms of sound coming from direct left/front/right. 


For example, if you are listening from direct front, but you think it is a little to the right, it means either your left ear’s front delay is too high, or your right ear’s front delay is too low, or both. You can calibrate it by setting left ear’s front delay to low, and/or right ear’s front delay to high. 


Another example, if you are listening from direct right, but you think it is a bit to the left, it means either your left ear’s right delay is too low, or your right ear’s right delay is too high, or both. You can calibrate it by setting left ear’s right delay to high, and/or right ear’s right delay to low. 



You can always test out the effect by clicking on any direction button on the left of the ITD matcher and “1” on top of sfplay~ to play
After you are done with ITD matcher, always click “confirm” and then "confirm 2" button below to apply it to all directions. 


##Details about this Max patch

### About elevation and azimuth
Azimuth is from 0 (direct left) to 72 (direct right), so the center is 36.
Elevation is from 0 (45 degrees downward) to 127 (46 degrees downward), so front is 16, top is 48, back is 80 and bottom is 112.

### ITD matcher
* The high/average/low is calculated based on the ITDs of the first ten subjects in the database. 
* The ITD matcher assumes ITD has no relationship with elevation. So ITDs of the same azimuth will always be the same no matter how elevation is changed. 
* “Confirm” estimates ITDs between azimuth 0 and 36 (and 36 to 72) by making a linear function between the two. “Confirm 2” fill all ITDs of the same azimuth same value.

### FFT macher
* The FFT matcher does not create a custom HRTF. It only helps find the best match within the database.




## Liscence

Copyright 2017 Haofan Zhang

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

