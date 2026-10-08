# Interoperability

The Pollination plugins offer interoperability with a wide range of simulation engines and interfaces.
Exporters are supported for the following engines and file formats:

* [Ladybug Tools \(HBJSON and DFJSON\)](https://www.ladybug.tools/)
* [IES-VE \(GEM\)](https://www.iesve.com/)
* [TRACE 700 \(gbXML, XLSX, and EXP\)](https://www.trane.com/commercial/latin-america/pr/en/products-systems/design-and-analysis-tools/trane-design-tools/trace-700.html)
* [eQuest \(INP\)](https://www.doe2.com/equest/)
* [DesignBuilder \(dsbXML\)](https://designbuilder.co.uk/)
* [OpenStudio \(OSM\)](https://openstudiocoalition.org/)
* [EnergyPlus \(IDF and epJSON\)](https://energyplus.net/)
* [IDA ICE \(IDM\)](https://www.equa.se/en/ida-ice)
* [Radiance \(RAD\)](https://www.radiance-online.org/)
* [TRACE 3D Plus \(gbXML\)](https://www.trane.com/commercial/latin-america/gy/en/products-systems/design-and-analysis-tools/trane-design-tools/trace-3d-plus-load-design.html)
* [EnergyPro \(gbXML\)](https://www.energysoft.com/)
* [CBECC \(SDD XML\)](https://www.energy.ca.gov/programs-and-topics/programs/building-energy-efficiency-standards/2025-energy-code-compliance-software)
* [Green Building XML \(gbXML\)](https://www.gbxml.org/)

Many of the formats above can also be imported to the Pollination plugins.

All exporters and importers transfer geometry as faithfully as possible between platforms and many formats also support the transfer of attributes assigned to that geometry (eg. constructions, internal loads, etc.). For a full list of attributes that can be transferred to/from each format, see the complete documentation for [Export](export/README.md) and [Import](import/README.md) pages.

## Pollination Pact

Our pact with you is simple. Every valid Pollination model should export and import to the corresponding simulation tool with no errors. If you face any issues in the translation process with a valid model, that is a bug. If you find a bug, and report it, we will fix it. If we can't fix it, we'll give you a full refund.

## Validation

At the heart of this interoperability guarantee is a concept called [Model Validation](validation/README.md). All Pollination plugins come equipped with a validation routine, which can be run on any model to yield a list of issues to be fixed within Pollination software before export. If validation issues are not addressed before export, they can cause problems or errors in the destination software. Each type of validation issue has its own [Error Code](validation/validation-error-codes.md) and corresponds with a set of possible commands that can be run in the Pollination plugin to fix the problem in different ways.
