# PO_Extrude2DPlans

Extrude 2D plans (curves) to solid Breps based on height data. A default height will be used if curves do not contains height information.

## Options

* **GlobalHeight**

  set a number for the height of extrusion globally. If the UseLocalHeightIfAny option is set to true and there is height data found within geometry, then this global height will be ignored for this geometry individually.

* **UseLocalHeightIfAny**

  set to true to use embedded height data that is stored within each curve if any as opposed to use the global height.

* **DeleteInputs**

  set to true to delete input geometries. 

* **SimplifyCurves**

  set to true to simplify the generated curves and convert it to polylines. 


