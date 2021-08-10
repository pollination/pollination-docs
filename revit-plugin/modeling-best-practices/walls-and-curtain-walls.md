# Walls and Curtain Walls

## Walls

## Compound Walls

On many projects, there are instances where compound walls are required. For example, a project may have a concrete curb at the base or there is a shorter furred wall over masonry. To properly export a model from Revit for analysis, Pollination requires dissimilar wall types to be a compound wall instead of multiple walls drawn in parallel or stacked on top of each other. This not only makes it easier to model doors and windows for architectural purposes, but it also facilitates a seamless model export. 

### Stacked Wall 

Under wall properties, select the option to create a Stacked Wall family for instances where you have a stone, concrete, or other material at the base of the wall. 

![](../../.gitbook/assets/image%20%28130%29.png)

You can stack multiple wall types in sections while maintaining a single wall definition for simulation and analysis. The wall types will render in section view from the top down. 

![](../../.gitbook/assets/image%20%2874%29.png)

### Basic Wall with Baseboard, Wainscoting, or Other Details

If you model multiple walls in parallel, ensure that **only ONE** wall, the main room bounding wall, has room bounding properties assigned to it. All other walls, should **NOT** have room bounding properties assigned. 

You can also use the sweeps, reveals, merge, and split options \(only visible when section preview is selected in the view\) to add baseboards and other custom wall details. 

![](../../.gitbook/assets/image%20%28134%29.png)

 

## Curtain and Storefront Walls

When curtain walls are modeled full height and assigned room bounding properties, they export flawlessly. But when you make a "cut" in the wall or modify the wall profile to create a storefront or curtain wall to fill the void, the glazing will fail to export correctly. In this example, a round window was modeled using a curtain wall instead of a window. 

If you use a curtain or storefront wall to create room separations that don't fully enclose a space, ensure they are not room bounding.  Because it takes longer to process a curtain wall than a basic wall, you can save time by ensuring non-room bounding walls are not specified as bounding. 

