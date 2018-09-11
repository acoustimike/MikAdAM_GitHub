## MikAdAM_GitHub
### Programme name: MikAdAM - Mike's Admittance App for Matlab (Matlab)

### Current Version: 1a

### Date: 11/09/2018

### Author: Michael Newton (http://acoustimike.co.uk/ // https://twitter.com/acoustimike)

### Key requirements: Matlab 2018a (or newer), Matlab Data Acquisition Toolbox, Windows 7 (or newer)

---

### Description
This app is used to measure the vibroacoustic properties of solid bodies such as violins, plates,
bar, hedgehogs (please don't use it for hedgehogs).

The app performs data acquisition using Matlab's Data Acquisition Toolbox, and has been built in the
Matlab App Designer. Acquisitions are triggered/windowed according to a user-specified (analog) trigger level.

Multiple acquisitions (for a given transducer configuration) can be carried out, and the measurements compared and 
retained/deleted as required (e.g. by use of the so-called 'coherence', as computed for 2 or more repeat measurements).

Example uses are: 
* Admittance and transfer function measurements for musical stringed instruments 
* Basic vibration testing of beams and plates

### Overall workflow
The main principle behind the app is to allow students, academics, musical instrument makers (or whoever) to perform 
input admittance (and other transfer function) measurements on solid bodies, using the hammer method, directly within Matlab. 
A typical workflow would be:

1. Set up an impact hammer and an accelerometer on the bridge of a violin - power to the IEPE/ICP transducers comes from a NI cDAQ 9234 unit (selectable within the App)
2. Configure MikAdAM's data acquisition setup (DAQ) within the graphical user interface (channel names, calibration number, etc)
3. Turn on the DAQ, and undertake a hammer measurement - data is retained based on a user-defined triggering level
4. Inspect the acquired data, and discard or retain as appropriate
5. Go to step 3 and repeat until satisfied (using the coherence estimate where appropriate when averaging multiple measurements together)
6. Export the data as a Matlab (.MAT) data file, ready for further processing/plotting 

### Tech summary
The app is based on the so-called 'hammer method', which generally proceeds as follows:

1. Typically, a piezoelectric impact hammer is used to apply a small 'tap' to the item under test
(DUT). The hammer provides an electric output proportional to the force it imparts, and this is
digitised through an ADC (e.g. National Instruments cDAQ 9234 card, or a regular sound card with
appropriate setup), potentially (though not essentially) with some pre-amp gain applied.

2. At the same time, one or more further transducers (e.g. accelerometer(s), microphone(s), laser vibrometer(s)) provide 
'response' signals, which are (normally) also digitised synchronously via the same ADC unit. 

3. Signal processing of the digitised input/output signals leads to the calculation of frequency-domain transfer functions. 
In the case that the 'input' (hammer) and 'output' (as a body velocity) are taken at (or very close to) the same position, a so-called "input admittance"
may be obtained. In such cases it is fairly common to obtain the 'velocity' signal by integrating (in the frequency domain) an accelerometer signal. 
	* Where sound radiation is of interest, it is common to record the response to the input 'tap' with one or more microphones. In such cases
a kind of vibroacoustic transfer function is obtained describing how mechanical energy injected into the DUT is converted to acoustic energy (at a given position).

### How to use MikAdAM
A series of 3 short introductory videos that explain how to install and use MikAdAM:

1. https://youtu.be/efN6BOS6yfo 
2. https://youtu.be/85igh2mUCAQ 
3. https://youtu.be/plX04j1MJKU

---

Happy AdAM-ing!  