# Configuring the Arduino IDE

The Arduino IDE needs to be configured to handle the unique environment of the Project: Traveler tracking boards 
for the ptFlex, ptSolar, and ArduinoTrack. The following process creates the build environment, and prepares them for loading
into the Arduino IDE.

## Making the Adjustments

Generally, the changes are made to the boards.txt, and possibly the platform.txt files. Other CPU libraries may need
to be adjusted over time.

Those files are located in the avr-1.0.0 directory.

Also, libraries and core files inside of the /cores, /libraries, and /variants may need to be periodically
updated from the Arduino masters.  Those can be found in C:\Program Files (x86)\Arduino\hardware\arduino\avr.

Once any changes are made, zip up the /avr-1.0.0 and name it projecttravelerboards-x.y.z.zip or as appropriate.
Always increment this number or else you will have problems when the Arduino IDE checks for updated configurations.


In PowerShell, get the new file hash of the new .zip archive.
```get-filehash .\projecttravelerboards-x.y.z.zip```

In the package_projecttraveler_index.json, make a copy of the platforms section, and create a new entry at the top
of that array. Update the two lines that indicate the .zip file name.  Also
update the file hash of the .zip file and the file size of the .zip file.


## Publishing the Files
The resulting .zip file and .json files will be uploaded to https://www.projecttraveler.org/downloads/.

