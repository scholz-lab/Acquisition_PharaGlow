# Acquisition_PharaGlow

LabVIEW code for acquiring data suitable for PharaGlow analysis. The particular strength of this program resides on the live segmentation feature, which enables long recordings at a continuous >= 30 Hz frame rate by reducing the amount of data by several orders of magnitude.

## Before starting
The code has been used in combination with the BASLER camera model acA3088-57um. For the program to work, the appropriate drivers need to be used for the camera (NI-IMAQdx USB3 Vision). The installation of the drivers can be done using the NI MAX software. Using NI MAX, it should be possible to grab pictures to test that the camera is functioning properly and that LabVIEW can access it. The camera number should also be displayed in NI MAX. Note that upon replacement of the drivers, the camera will not be anymore available using the Pylon viewer. The standard drivers can be restored using NI MAX. As a side note, in some occasions, restoring the appropriate driver could not be achieved with MAX and original drivers had to be reinstalled manually. We do not recommend changing back and forward from one driver to another. This might be solved in future LabVIEW releases (we use version 21).

Due to the large amount of memory that is required to acquire continuously for extended periods of time, it is required using the 64-bit LabVIEW version.

## Running the software
Load the program Acquisition_Pharaglow.vi. Before starting the program, select the camera number (same number as displayed in NI MAX). The current program uses a default settings file that is loaded upon starting the program (DefaultCameraSettings.txt). This file contains all the parameters that are accessible using the Pylon software, including I/O signals. Editing this file can be useful for synchronization of the camera with light sources using the I/O camera pins.

The program can be used in a standard mode, where the whole frame is saved or it can be used in segmentation mode. In segmentation mode, the program automatically segments the image and only areas containing worms, and their coordinates within the image, are stored. This procedure allows a data reduction by several orders of magnitude (~1000 fold).

To ensure that frames are continuously acquired and that interruptions of the operating system do not interfere with the acquisition, an image buffer has been set to save images in memory while the analysis of these is being performed (if segmentation is required) and images are finally saved into the hard disk. The current status of the buffer is displayed in the GUI of the program. In the eventuality that the buffer was at any time filled, the program will throw an overflow message and a text file will be generated indicating the frame from which the data is not reliable any more.

Data is automatically saved in the selected folder. Within this folder, an additional folder with a name indicating the time of the recording will be generated where images and metadata will be stored. We assume that two recordings will not be made within the same minute. Please mind this if you are doing successive recordings with a time interval that is shorter than the minute.

## Recommendations
For a good recording, it is imperative that the sample is well in focus. We recommend starting using the focus mode. Use the zooming option of the display and fine tune the focus of the objective until you can observe the isthmus of the pharynx. To come back to the full view, click with the right button on the display and select "Zoom to fit". If you want to use the segmentation option, select it and tune the parameters. During acquisition, the surrounding box of the segmented worm is not being displayed to spare computer resources. If required, you can click on the corresponding box in the GUI.

## Please cite us!
If you use this software, please cite:
Automatically tracking feeding behavior in populations of foraging C. elegans Elsa Bonnard, Jun Liu, Nicolina Zjacic, Luis Alvarez, and Monika Scholz bioRxiv 2022.01.20.477072; doi: https://doi.org/10.1101/2022.01.20.477072

## License
scholz-lab/Acquisition_PharaGlow is licensed under the GNU General Public License v3.0
