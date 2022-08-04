# Acquisition_PharaGlow
LabVIEW code for acquisition of PharaGlow data

The code has been used in combination with the BASLER camera model acA3088-57um. For the program to work, the appropiate drivers need to be used for the camera (NI-IMAQdx USB3 Vision). The installation of the drivers can be done using the NI MAX software. Using NI MAX, it should be possible to grab pictures to test that the camera is functioning properly and that LabVIEW can access to it. The camera number should also be displayed in NI MAX. Note that upon replacement of the drivers, the camera will not be anymore available using the pylon viewer. The old drivers can be restored using NI MAX. As a side note, in several occasions, restoring the appropiate driver could not be achieved with MAX and all associated drivers need to be reinstalled.

To run the program load Acquisition_Pharaglow.vi. Before starting the program, select the camera number (same number as displayed in NI MAX). The current program uses a default settings file that is loaded upon starting the program (DefaultCameraSettings.txt). This files contains all the parameters that are accessible using the Pylon software, including I/O signals. Editing this file can be usefull for synchronization of the camera with light sources using the I/O pins of the camera.

The program can be used in a standard mode, where the whole frame is saved or it can be used in segmentation mode. I this mode, the program automatically  segmentes the image and only areas containing worms, and their coordinates within the image, are stored. This procedure allows a data reduction by several orders of magnitude.

If you use this software, please cite XXXXXXXXXXXXX


This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>. 


