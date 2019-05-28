In RN there are two worlds, native and JS. RN make use of the native UI layer, which mkaes the app more native when compared to other web based mobile apps. In react we have direct access to the dom node and we can call methods directly on the node, but in RN it is not like that. For the c/m between these two world RN have a BRIDE, which is  a C++ implementation.

RN Bridge:
  When reconsilation happens there are bunch  of commands that get created in JS world. RN form a JSON array of these commands, serializes it as a string and send across the Bridge to the native layer.
