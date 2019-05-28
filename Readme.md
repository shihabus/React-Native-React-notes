In RN there are two worlds, native and JS. RN makes use of the native UI layer, which make the app more native when compared to other web based mobile apps. In react we have direct access to the dom node and we can call methods directly on the node, but in RN it is not like that. For the c/m between these two worlds RN has a BRIDGE, which is  a C++ implementation.

RN Bridge:
  When reconsilation happens there are a bunch of commands that get created in JS world. RN form a JSON array of these commands, serializes it as a string and send across the Bridge to the native layer.
  
Layout thread:
  React uses FlexBox for default layout but when come to RN it is not the case. Mainly Android(RCTView) is not able to understand the flexbox layouting so RN uses YOGA for layout It takes the layout in terms of flexbox and convert them into relative compositions of components in UI. The o/p of this thread is send to the native UI layer where the UI is being painted.
  
RN have mainly 3 threads:

  Native UI thread(Platform UI)
  
  Layout thread(Shadow tree)
  
  JS thread

The c/m between this threads are asynchronous. Platform UI thread is least loaded, where the JS thread is the most laoded as it have all the reconsilation, business logic and other stuff running.

Upcoming

But the RN bridge is being burned and a new JavaScript Interface(JSI) is coming up. 

In React, the layout engine is more closer to the native layer(browser) and it creates the output which are more closer to the browser. RN is trying to bring the same implementation to using JSI. Now they have a UI Management called FABRIC which can do both synchronous and asynchronos UI updates. Fabric is trying to eliminate the bridge and letting the JS thread control the UI thread directly. For this native apis are directly exposed to JS thread and JS tread work on references made available by JSI. 

![architecture](https://github.com/shihabus/React-Native-React-notes/blob/master/Architecture.JPG)

React Native Fabric

(https://www.slideshare.net/axemclion/react-native-fabric-review20180725)
(https://www.freecodecamp.org/news/how-react-native-constructs-app-layouts-and-how-fabric-is-about-to-change-it-dd4cb510d055/)


