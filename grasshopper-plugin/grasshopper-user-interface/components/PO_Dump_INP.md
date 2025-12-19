# PO\_Dump\_INP

![PO Dump INP](<../../../.gitbook/assets/PO_Dump_INP (1).png>)

Save entire model as INP file

## Inputs

*   **model \[Required]**

    A Honeybee Model object to be written to a INP file.
*   **name \[Default]**

    A name for the file to which the honeybee objects will be written. If unspecified, it will be derived from the model identifier.
*   **folder \[Default]**

    An optional directory into which the honeybee objects will be written. The default is set to the default simulation folder.
*   **hvac\_mapping \[Default]**

    An optional input to group rooms for HVAC mapping. Valid options are: `room`, `story`, `model`, and `assigned-hvac`. The default is set to 'story'.
*   **exclude\_InWalls \[]**

    Set to "True" to exclude all interior walls. The default is set to False to include all interior walls.
*   **exclude\_InCeilings \[]**

    Set to "True" to exclude all interior ceilings. The default is set to False to include all interior ceilings.
*   **switch\_statements \[Optional]**

    Set to "True" to use switch statements. The default is set to False.
*   **dump \[Required]**

    Set to "True" to save the honeybee model to a INP file.

## Outputs

*   **inp**

    The location of the file where the INP file is saved.
