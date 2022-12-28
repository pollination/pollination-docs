---
description: Reset a honeybee object&apos;s identifier and boundary condition. You can also select partial room&apos;s sub-faces for resetting boundary conditions.
---

# PO_ResetIdentifier

Reset a honeybee object&apos;s identifier and boundary condition. You can also select partial room&apos;s sub-faces for resetting boundary conditions.

## Options

* **ID**

  Reset identifier criteria.

* **GenerateNewID**

  Create a new ID randomly.

* **ByDisplayName**

  Use display name as ID.

* **ByDisplayNameAndID**

  It combines display name and random ID.

* **Face**

  Yes to reset all faces&apos; ID.

* **Room**

  Yes to reset rooms&apos; ID.

* **SensorGrid_View**

  Yes to reset sensor grids&apos; ID.

* **Validate**

  Yes to run model validation after resetting.

Notes:

* **All geometries&apos; boundary condition will be reset to Outdoor, unless geometry touches the ground (0) and then it will be set to Ground.
**

  

