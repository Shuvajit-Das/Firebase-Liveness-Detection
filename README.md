
# Firebase-Liveness-Detection  
Lightweight Liveness Detection using Firebase ML Kit - file size less than 5 Mb. Currently only available on detecting left and right head movement
  
  
# Implementation  
  
Add this script to your app gradle file:  
`compile 'id.privy.livenessfirebasesdk:livenessdetection:0.0.1'`  
  
  
Add builder to your activity to start  

    LivenessApp livenessApp = LivenessApp.Builder(this)  
    			 .setDebugMode(false) //to enable face landmark detection 
    			 .setSuccessText($SUCCESSTEXT) 
    			 .setInstructions($INSTRUCTIONS) 
    			 .build()

Initiate with callback

     livenessapp.start(object : PrivyCameraLivenessCallBackListener {  
        override fun success(livenessItem: LivenessItem?) {  
		      //your callback here
        }  
      
        override fun failed(t: Throwable?) {  
		      //handle error here
        }  
    })

`LivenessItem` is an instance of model that return a bitmap with `getImageBitmap()` so that you can set the image directly

