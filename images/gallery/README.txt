QUEENS BORO BASH 2026 — EVENT GALLERY
=====================================

Photos are served in TWO tiers, same filename in each folder:

  images/gallery/qbb-NN.jpg        full size  (~2000px)  -> lightbox
  images/gallery/thumb/qbb-NN.jpg  thumbnail  (~640px)   -> grid

They are named qbb-01.jpg .. qbb-127.jpg in a pre-randomized order
(shuffled across skaters on purpose, so the grid is not grouped).

The site renders them from a manifest in index.html, not by scanning
this folder. The gallery script has:

  var COUNT = 127;   // number of photos

TO CHANGE THE SET
-----------------
1. Add or remove matching files in BOTH folders (full + thumb), keeping
   the qbb-NN.jpg naming contiguous and zero-padded (qbb-01, not qbb-1).
2. Update COUNT in the gallery script in index.html to the new total.
3. Commit and push. Vercel redeploys.

REGENERATING FROM ORIGINALS (how these were made)
-------------------------------------------------
Full:  sips -Z 2000 --setProperty format jpeg --setProperty formatOptions 82 SRC --out qbb-NN.jpg
Thumb: sips -Z 640  --setProperty format jpeg --setProperty formatOptions 72 SRC --out thumb/qbb-NN.jpg
