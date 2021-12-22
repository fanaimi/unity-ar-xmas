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


## PROBELM WITH BLACK SCREEN / NO BG
* in the project panel at the bottom: Assets > Settings => select ForwardRenderer
* in the inspector => Renderer Features > click on Add Renderer Feature
* select New AR Background Renderer Feature


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
	
## WORKING ON WHAT WE WANT TO APPEAR
* create an empty game object and populate it, then make it a PREFAB 
	* connect the prefab 
	* in AR Session Origin > AR Tracked Image Manager > Tracked Image Prefab

* for text add a canvas and set Render Mode > World Space

* in canvas, drag AR Camera into Event Camera	

## ANIMATIONS AND TIMELINE
* select ARContent > Window > Sequencing > TIMELINE, hit CREATE and save the director
* Activation Track to make object appear / disappear at given time
* to animate the text: canvas > window > animation > animation to get a new timeline