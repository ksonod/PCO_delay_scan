# PCO_delay_scan
GUI for controlling optical devices and getting images from PCO edge camera (Matlab)

## 1. Description
This repository provides a GUI tool for controlling the [Newport delay line stage](https://www.newport.com/f/delay-line-stages), [optical shutters](https://www.thorlabs.com/newgrouppage9.cfm?objectgroup_id=927), and [picomotors](https://www.newport.com/f/picomotor-piezo-linear-actuators) and getting images from [PCO edge camera](https://www.pco.de/). This GUI works under the following condisionts:
- Windows 10
- Matlab R2018b

## 2. Control Window
<img src="https://github.com/ksonod/PCO_delay_scan/blob/master/gui1.PNG" width="500px">  
  
If you run the myPCO_stage.m, a new window displayed above will show up. The window consists of 4 main sections:
- Image: Settings for a [sCMOS](https://en.wikipedia.org/wiki/SCMOS) camera and window for visualizing an image
- Delay Stage Scan: Settings for the delay line stage.
- Shutter: Open and close the shutter
- Picomotor: Motion control with motors connected to optical mirror mount 

### 2.1 Image
In this section, an image obtained by a camera is displayed. If you click the Get-an-Image button, the current image will be shown on the window. If you click the Scan-and-Get-Images button, you can see images obtained at different stage positions and save all images in a created folder "scanned images." 

### 2.2 Delay Stage Control
With the options in this section, you can control the delay stage. 
#### (1) Current Settings
After clicking the show button, the current position, velocity, and acceleration are shown. 

#### (2) Change Settings
You can change the position, velocity, and acceleration.

#### (3) Delay Scan 
You can move the stage automatically. Once you specify the initial and final positions and the number of steps, you can click the Calculate-Time-Settings button and get the time step and time range of the scan. The Start-Scanning button initiates the movement of the delay stage. The Scan-and-Get-Images button initiates the image acquisition while the delay stage is moving.

<img src="https://github.com/ksonod/newport_delay_stage_gui_matlab/blob/master/dls_matlab2.PNG" width="400px">


## 3. My main contribution
Image data acquisition from the camera is achieved by utilizing an official package provided by a company ([link](https://www.pco.de/software/third-party-software/)). The Matlab codes whose name start with "my" are modified version of the provided codes.
- I adjusted the timing of closing the camera in order to enable multiple image aquisition after proper averaging.
- I integrated the provided code with the motion control of the delay line stage and optical shutter.
- The difference of images obtained with a closed and opened shutter can be obtained during the process of the image data aquisition.

## 4. Useful References
- Official document of the Newport Delay Line Stage: https://www.newport.com/mam/celum/celum_assets/resources/DL_Controller_-_Command_Interface_Manual.pdf?1
- My repository 1 (moving the delay stage with GUI): https://github.com/ksonod/newport_delay_stage_gui_matlab 
- My repository 2 (getting images): https://github.com/ksonod/delayscan_images
- My repository 3 (same as the current repository, but no gui): https://github.com/ksonod/delayscan_images
- My repository 4 (basic usage of Matlab commands for controlling the delay stage): https://github.com/ksonod/newport_delay_stage_basic_matlab
