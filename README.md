
SimpleTracks
==========
SimpleTracks is a sample application which demonstrates the usage of the 
TrackPoint Monitor API in Windows Phone 8.1. This application visualizes the
tracks on the map. The user is able to see the tracks from the last seven
days as well as tracks history by using the application bar buttons.


1. Instructions
--------------------------------------------------------------------------------

Learn about the Lumia SensorCore SDK from the Lumia Developer's Library. The
example requires the Lumia SensorCore SDK's NuGet package but will retrieve it
automatically (if missing) on first build.

To build the application you need to have Windows 8.1 and Windows Phone SDK 8.1
installed.

Using the Windows Phone 8.1 SDK:

1. Open the SLN file: File > Open Project, select the file `SimpleTracks.sln`
2. Remove the "AnyCPU" configuration (not supported by the Lumia SensorCore SDK)
or simply select ARM
3. Select the target 'Device'.
4. Press F5 to build the project and run it on the device.

Please see the official documentation for
deploying and testing applications on Windows Phone devices:
http://msdn.microsoft.com/en-us/library/gg588378%28v=vs.92%29.aspx


2. Implementation
--------------------------------------------------------------------------------

The application supports compatibility between new and old phone. On start it makes a call to the SDK to get the supported 
API. Based on the response it continues to run and if services are disabled, the corresponding error messages will be 
shown. 

For the next step the application checks if the track monitor is null and if the condition is satisfied it makes a 
call to the Sense SDK to initialize the trackpoint monitor by getting the default async. for this, the location and motion 
data have to be enabled. 

If the trackpoint monitor cannot be instantiated, the application wil throw an error message and will exit.
After instantiating the trackpoint monitor the map will load on the screen showing the current location of the 
user if this can be found, otherwise it will show a static location. Next, it makes a call to the trackpoint history 
getting all the recorded tracks for the current day o, a day from the past or in the last case, for all the days that have 
tracks in the history drawing a connecting line between all of them. 

In order to display the tracks, a push pin is drawn on the map for each track, this containing information about the place
for the track. The application also records activities that have been launched from one trackpoint to another. 
Tapping on a push pin will open a new page in the app displaying additional information for the track such as latitude 
and longitude, duration of stay and place information. 
Navigation between days is possible with the back and forward buttons.
	
	
3. Version history
--------------------------------------------------------------------------------
* Version 1.1.0.0: The first release.

4. Downloads
---------

| Project | Release | Download |
| ------- | --------| -------- |
| SimpleTracks | v1.1.0.0 | [simpletracks-1.1.0.0.zip](https://github.com/Microsoft/SimpleTracks/archive/v1.1.0.0.zip) |

5. See also
--------------------------------------------------------------------------------

The projects listed below are exemplifying the usage of the SensorCore APIs

* SimpleActivity - https://github.com/Microsoft/SimpleActivity
* SimpleSteps -  https://github.com/Microsoft/SimpleSteps
* SimplePlaces - https://github.com/Microsoft/SimplePlaces

