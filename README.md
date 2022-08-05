# Acquisition_PharaGlow
LabVIEW code for acquisition of PharaGlow data

## Before starting
The code has been used in combination with the BASLER camera model acA3088-57um. For the program to work, the appropiate drivers need to be used for the camera (NI-IMAQdx USB3 Vision). The installation of the drivers can be done using the NI MAX software. 
Using NI MAX, it should be possible to grab pictures to test that the camera is functioning properly and that LabVIEW can access to it. The camera number should also be displayed in NI MAX. Note that upon replacement of the drivers, the camera will not be anymore available using the pylon viewer. The standard drivers can be restored using NI MAX. As a side note, in some occasions, restoring the appropiate driver could not be achieved with MAX and original drivers need to be reinstalled manually. We do not recommend changingback and forward from one driver to another. This might be solved in future LabVIEW releases (we use version 21).

Due to the large ammount of memory that is required to acquire continuosly for extended periods of time, it is required using the 64 bit LabVIEW version.

To run the program load Acquisition_Pharaglow.vi. Before starting the program, select the camera number (same number as displayed in NI MAX). The current program uses a default settings file that is loaded upon starting the program (DefaultCameraSettings.txt). This files contains all the parameters that are accessible using the Pylon software, including I/O signals. Editing this file can be usefull for synchronization of the camera with light sources using the I/O pins of the camera.

## Running the software
The program can be used in a standard mode, where the whole frame is saved or it can be used in segmentation mode. I this mode, the program automatically  segmentes the image and only areas containing worms, and their coordinates within the image, are stored. This procedure allows a data reduction by several orders of magnitude.

To ensure that frames are continuosly acquired and that interruptions of the operating system do not interfere with the acquisition, an image buffer has been set to save images in memory while the analysis of these is being performed (if segmentation is required) and images are finally saved into the hard disk. The current status of the buffer is displayed in the GUI of the program. If the buffer was at anytime filled, the program will throw an overflow message and a text file will be generated indicating the frame from which the data is not reliable any more.

Data is automatically saved in the selected folder. Within this folder, an additional folder with a name indicating the time of the recording will be generated where images and metadata will be stored. We assume that two recordings will not be made within the same minute. Please mind this if you are doing successive recordings with a time interval that is shorter than the minute.

## Recommendations
For a good recording, it is imperative that  the sample is well in focus. We recommend to start using the focus option in the program. Use the zooming option of the display and fine tune the focus of the objective until you can observe the isthmus of the pharynx. To come back to the full view, click with the right buttonon the display and select "Zoom to fit". If you want to use the segmentation option, then you can fine tune the parameters. During focuse, the sourrounding box of the segmented worm is not being displayed to spare resources. If required, you can clik on the corresponding box in the GUI.

## Please cite us!
If you use this software, please cite XXXXXXXXXXXXX

## Software license agreement
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>. 


