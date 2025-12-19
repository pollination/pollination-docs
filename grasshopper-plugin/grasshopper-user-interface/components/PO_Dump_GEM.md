# PO\_Dump\_GEM

![PO Dump GEM](<../../../.gitbook/assets/PO_Dump_GEM (1).png>)

Save entire model as GEM file

## Inputs

*   **model \[Required]**

    A Honeybee Model object to be written to a GEM file.
*   **name \[Default]**

    A name for the file to which the honeybee objects will be written. If unspecified, it will be derived from the model identifier.
*   **folder \[Default]**

    An optional directory into which the honeybee objects will be written. The default is set to the default simulation folder.
*   **dump \[Required]**

    Set to "True" to save the honeybee model to a GEM file.

## Outputs

*   **gem**

    The location of the file where the GEM file is saved.
