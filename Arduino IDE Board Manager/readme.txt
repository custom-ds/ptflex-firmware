Changes to the boards.txt need to be made inside of the avr-1.0.0 directory.

Also, libraries and core files inside of the /cores, /libraries, and /variants may need to be periodically
updated from the Arduino masters.  Those can be found in C:\Program Files (x86)\Arduino\hardware\arduino\avr.

Once any changes are made, zip up the /avr-1.0.0 and name it projecttravelerboards-1.1.x.zip or as appropriate.
Always increment this number or else you will have problems.


In PowerShell, get the new file hash of the new .zip archive.
 > get-filehash .\projecttravelerboards-1.1.x.zip

In the package_projecttraveler_index.json, update the two lines that indicate the .zip file name.  Also
update the file hash of the .zip file and the file size of the .zip file.


*** NOT SURE ABOUT THE VERSIN NUMBER OF THE AVR-1.0.0 DIRECTORY, OR THE VERSION NUMBER IN PLATFORM-VERSION. ***
***  THAT SEEMS TO BE THE TRIGGER TO CAUSE AN UPDATE TO THE FILE, HOWEVER IF ARDUINO LEAVES MULTIPLE        ***
***  VERSIONS INSIDE OF THE C:\USERS\USERNAME\APPDATA\LOCAL\ARDUINO15\PACKAGES\PROJECT-TRAVELER FOLDER      ***
***  THEN ARDUINO IDE GETS CONFUSED                                                                         ***


Upload the .zip file and the .json file to www.projecttraveler.org/downloads/.


***
To add new boards, add them to the bottom of the .json file in the Boards array, and also inside of the .zip
file inside of the boards.txt file.