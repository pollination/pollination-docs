# ![](../../.gitbook/assets/snap-to-grid.svg#thumbnail) Snap to grid

Snap the selected rooms to a cartesian grid defined by a Grid Increment distance, which sets the resolution of the grid. This command is useful for IES VE modelers who need geometry on a grid for ease of edit-ability.

## Options

* **Grid Increment**

  A positive number for dimension of each grid cell. This should be less than the smallest detail to resolve on the rooms. NOTE that this value can be different from the grid size in the preview

* **Exclude Angle**

  A positive number in degrees for the maximum difference that a geometry segment can differ from the grid for it to be ignored/excluded from snapping. Setting the exclude angle to zero will guarantee that all geometry is snapped to the grid. However, this may produce jagged geometries, particularly when there are parts of a geometry that are not intended to be aligned with a grid

## Details

{% embed url="https://drive.google.com/open?id=1XiU0mR1sLE7yBO51psrl-vOsI9ne74fD&usp=drive_fs" %}
Snap to Grid
{% endembed %}

<style>
img[src*="#thumbnail"] {
   width:50px;
   height:50px;
}
</style>