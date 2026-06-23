# Validate model
<img src="images/validate-model.svg" width="50" height="50"> 

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

## Options

* **Destination engine**

  The destination engine for which validation will be performed. Selecting an option here will ignore checks that are not relevant for the engine. Use the 'Generic' option if the intention is to make a model for multiple engines.

* **Include Warnings**

  Select to have validation run checks for cases that are not true errors but are likely still indicative of poor modeling that should be fixed. For example, selecting this option will run a check for small gaps between rooms, which does not make the model invalid but will probably result in interior boundary conditions not being assigned in cases where they are expected.