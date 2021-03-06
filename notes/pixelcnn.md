## [Conditional Image Generation with PixelCNN Decoders](https://arxiv.org/abs/1606.05328)
Aaron van den Oord et al., Submitted on Jun 2016

TLDR; Deep neural network for generating images according to their probability distribution.

### Key Points
* Model: 
* Applications:


### Notes / Questions
* Blind spot: it exists because the mask only considers adjacent pixels to the current pixel to a certain extent, so pixels outside that mask aren't considered.
   * Solution: use of horizontal and vertical masks
      * Horizontal mask: conditions on the current row (regular conv)
      * Vertical mask: conditions on all rows above the current row

<p align="center">
<img src="https://github.com/gcunhase/PaperNotes/blob/master/notes/imgs/pixelcnn_blind_spot.png" width="300"/> <img src="https://github.com/gcunhase/PaperNotes/blob/master/notes/imgs/pixelcnn_vert_ho_masks.png" width="300"/> 
</p>


### Results
* [Code](https://github.com/anantzoid/Conditional-PixelCNN-decoder) only works for MNIST (black and white).
