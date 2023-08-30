# PO_AlignInPlan

Align geometries (generic geometries or Pollination geometries) to a grid system.
Non-planar faces will be triangulated.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/9031066/211238032-5833de73-ac07-48e7-8bb7-d3289a81649a.gif" alt="">
  <figcaption>
    <p>This command automatically triangulates non-planar surfaces.</p>
  </figcaption>
</figure>
</div>

## Options

* **Threshold**

  A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.

* **Angle Tolerance**

  A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.


## Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}Fix Models with Alignment Errors{% endembed %}

