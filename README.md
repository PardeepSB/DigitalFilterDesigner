# Digital Filter Designer

## What is this project?

A filter design tool to help users design, and test various filters made using a minimum number of built-in functions.  
These filters consist of filter types: LowPass, Highpass, BandPass, BandStop  
These filters consist of filter designs: Butterworth, Chebyshev I, Moving Average, and Windowed-Sinc  
The required implementation uses offline processing, but an attempt at real time implementation is made.


![image](https://user-images.githubusercontent.com/73859429/186488102-cacb9e14-9023-40f2-9640-a73f713fc5db.png)

## Capabilities of the design:

- User can choose to input an audio file OR record their own audio through a microphone 
  (over a specified time) to filter using the GUI

- All required digital filters are applicable to audio signals (FIR and the IIR filters)
	- Digital Filter Designs: Butterworth, Chebyshev I, Moving Average, Windowed-Sinc
		- User can select number of points for Moving Average and type of Windowed-Sinc
	- Filter Type: LowPass, HighPass, BandPass, BandStop

- The windows implemented for windowed-sinc function are: 
	- Rectanguler, Blackman-Harris, Kaisser and Hamming

- Software is able to plot the input signal, output signal and the
  filters time and frequency responses 

- User can filter response based on what filter minimum requirements they set
	- Filter Order, LowPass/HighPass Cut-Off, BandPass/BandStop Cut-Offs 
	- Set Order will set the order of the TF to change the frequency response of the filter

- Implemented Custom FFT function to calculate the frequency and 
  the phase response of the input and output signals (not highly delayed compared to built-in)

- User can record an Audio input, have it filtered, and output the filtered audio
  on plots and playback in Real-Time (1 second delay)

## Shortcoming of the design:

- Not able to get a full proper response for moving average's stopband filter

- Cutoff frequency is not used to calculate the points required for the moving average filter, 
  instead user is asked for the points/number of points they want to use

- When real-time recording takes place, it results in audio getting choppy due to
  recording 1 second intervals, as the interval time is increased, audio is less choppy,
  but the audio output/playback is then delayed by that increase 
  (we have set the recording intervals to 1 seconds)

- The signals are not plotted directly on the GUI, however they are still plotted and can be viewed

## Suggested Future Implementation:

- Display plot Visualizers on the GUI with ability to switch between the following  
	i. The input signal (Time and Frequency Response)  
	ii. The filter’s frequency response  
	iii. The output signal (Time and Frequency Response)

- Decrease window size for real-time implementation (1 second to 0.1 second or less for reduced delay response)
  
- Implement Analog Filters, more window-sinc windows, and other missing filters such as Bessel, Chebyshev II, etc.

- Allow user to chose when to start/stop recording of audio rather than restricting them to a time limit



