# Image to FEN

Extract the FEN out of images of chess diagrams.

It works in multiple steps:
1. Detect if there exists any chess board in the image
2. Get a bounding box of the (most prominent) chess board
3. Check if the board image is rotated by 0, 90, 180, or 270 degrees
4. Finally detect the FEN by looking at each square tile and predicting the piece (but also getting the entire board as additional input to make distinguishing between black and white pieces easier)
5. Detect if the perspective is from blacks or whites perspective (using a simple fully connected NN)

All these steps (except the fifth) basically use some common pretrained convolutional models available via torchvision with slightly modified heads. Detection is made robust using demanding generated training data and augmentations.




