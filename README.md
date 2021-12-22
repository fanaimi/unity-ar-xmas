# unity-ar-xmas

## CONFIGURATION
* AR foundation 
	* window > package manager > unity registry (4.1.7)
* AR Core XR Plugin (for Android - ARKit for iOS)
	* window > package manager > unity registry (4.1.7)

* file > build settings > Android > switch platform

* edit > projects settings > XR plugin management > click on android > check ARCore

* edit > projects settings > Player > Android
	* remove Vulcan from under Other Settings > Graphics APIs (keep OpenGLES3)
		* ARCore does not support Vulcan yet
	* under Other Settings > Identification > set MINIMUM API LEVEL as 	API LEVEL 24
* include XR Interaction Toolkit
* select BOTH NEW and Old input managers in 
	project settings > player => other settings > ACTIVE INPUT HANDLING 

## SETTING UP PROJECT	
* in Hierarchy > new > XR > AR Session 
* in Hierarchy > new > XR > AR Session Origin
	* AR Session Origin has AR CAMERA, so we can delete the original main camera
	
* under AR Session Origin > Add Component > AR Tracked Image Manager	

* in project / assets panel: create > XR > Reference Image Library

* select Reference Image Library > add image 
	* drag an image in top left corner in inspector
	* specify size (in meters)
	
* TRACKABLE IMAGES:
	* high contrast
	* no repeated patterns
	* colours are irrelevant
	
* drag Reference Image Library from assets into
	AR session Origin > AR tracked Image Manager > serialised library	