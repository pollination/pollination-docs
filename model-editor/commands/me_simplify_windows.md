# Simplify windows
<img src="images/simplify-windows.svg" width="50" height="50"> 

Simplify and reduce the number of windows and/or skylights while maintaining the overall exterior window/skylight area. Useful for improving simulation speed without significantly changing energy use results.

## Options

* **Merge Distance**

  The maximum distance between windows at which point they will be merged together into a single simpler window

* **Single Window**

  Select to have the windows simplified to a single window within the center of each wall, which matches the overall area of the original windows

* **Delete Interior**

  Select to have the interior windows and doors removed from the rooms, which often have a negligible impact on overall building energy use

* **Ignore Skylights**

  Select to have the windows left exactly as they are during the process of simplifying skylights

* **Ignore Windows**

  A boolean to note if the windows should be ignored during the process of simplifying the windows

## Details

Note that this command is not intended to fix invalid or un-simulate-able windows and the "Repair windows" command should be used for these purposes.