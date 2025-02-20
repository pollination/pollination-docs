# ![](../../.gitbook/assets/simplify-windows.svg) Simplify windows

Simplify the windows and skylights of a room for either simulation speed or overall model cleanliness.

## Options

* **Merge Distance**

  The maximum distance between rooms at which point they will be merged together. Setting a non-zero value here will allow you to merge rooms that have gaps in between them (crossing gaps up to the specified distance). This option is particularly useful for IDA-ICE users who must work with rooms that are exported at the interior wall finish

* **Single Window**

  Select to have the windows simplified to a single window within the center of each wall, which matches the overall area of the original windows

* **Delete Interior**

  Select to have the interior windows removed from the rooms, which can increase simulation speed in several BEM platforms

* **Ignore Skylights**

  Select to have the windows left exactly as they are during the process of simplifying skylights

* **Ignore Windows**

  A boolean to note if the windows should be ignored during the process of simplifying the windows

## Details

Note that this command is not intended to fix invalid or un-simulate-able windows and the "Repair windows" command should be used for these purposes.