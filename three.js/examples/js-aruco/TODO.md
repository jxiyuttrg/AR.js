- expose all the hardcoded parameters from AR.Detect in the debug,html
  - thus you can tune them

---
- see how to include it in ar.js
  - so basically a context and a controls
  - the source can remain the same without trouble
- how to handle all the options between the various backend

# Performances
- jsaruco use a kernel size of 2 in adaptative thresholding
  - could i reduce the resolution of the source image and use a kernel size of 1 ?
  - it would produce more fps. what the difference would be ? create errors ?
- jsaruco - adaptiveThreshold is doing it on ALL bytes - so all channel ??? check if it is correct
  - it use blackwhite image - it only needs 1 channel - 8 bits is already a lot to store blackwhite
  - this mean 4 times more work than needed
  - NOTES: unclear this is true - grayscale is packing it all in 1 channel. check it out ?
- in posit1: image difference is computed by a manathan distance. not a euclidian distance... how come ?
  -     imageDifference += Math.abs(sopImagePoints[i].x - oldSopImagePoints[i].x);
        imageDifference += Math.abs(sopImagePoints[i].y - oldSopImagePoints[i].y);