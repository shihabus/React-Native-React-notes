In RN there are two worlds, native and JS. RN makes use of the native UI layer, which make the app more native when compared to other web based mobile apps. In react we have direct access to the dom node and we can call methods directly on the node, but in RN it is not like that. For the c/m between these two worlds RN has a BRIDGE, which is  a C++ implementation.

RN Bridge:
  When reconsilation happens there are a bunch of commands that get created in JS world. RN form a JSON array of these commands, serializes it as a string and send across the Bridge to the native layer.
  
Layout thread:
  React uses FlexBox for default layout but when come to RN it is not the case. Mainly Android(RCTView) is not able to understand the flexbox layouting so RN uses YOGA for layout It takes the layout in terms of flexbox and convert them into relative compositions of components in UI. The o/p of this thread is send to the native UI layer where the UI is being painted.
  
RN have mainly 3 threads:

  __Native UI thread
  
  __Layout thread
  
  __JS thread
