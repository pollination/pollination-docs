# Typical Editing Process for Windows and Doors

Exporting windows and doors can be one of the most challenging parts of the process. If you spend enough time [selecting the correct windows and doors family types](../revit-plugin/export-analytical-model/selecting-doors-and-windows-families/), you should have a great starting point when you get to the Model Editor. That said, we all know how it goes when you're on a deadline and you want to get the model out as soon as possible. That's why we have developed a collection of commands in the Model Editor to help you with the worst-case scenario.

Here is the list of available commands:

1. ![](../.gitbook/assets/make-windows-flush.svg) [Make Windows Flush](commands/me_make_windows_flush.md)
2. ![](<../.gitbook/assets/offset-windows (1).svg>) [Offset Windows for Frame](commands/me_offset_windows.md)
3. ![](../.gitbook/assets/remove-windows.svg) [Remove Small Windows](commands/alphabetically/remove-small-windows.md)
4. ![](<../.gitbook/assets/repair-windows (1).svg>) [Repair Invalid Windows](commands/me_repair_windows.md)
5. ![](../.gitbook/assets/rectangularize-windows.svg) [Rectangularize windows](commands/me_rectangularize_windows.md)
6. ![](<../.gitbook/assets/simplify-windows (1).svg>) [Simplify Windows](workflows/simplifying-windows.md)

Here is the typical process for editing windows in the Model Editor.

## Resolve small gaps and overlaps

The first step of the process is to ensure the gaps or overlaps between the windows are fixed. You can use the [Make Windows Flush](commands/me_make_windows_flush.md) command to flush the windows.

## Adjusting windows for frame thickness

In some cases, the gap between the curtain wall panels is due to the frame thickness. In those cases, try using the [Offset Windows for Frame](commands/me_offset_windows.md) command. This command not only fills the gap between the windows, but it also offsets the boundary of the windows based on the input value for frame thickness.

When working on adjusting the windows for frames, it is important to understand the difference between "windows" and "curtain wall panels".

### Windows

In most cases, the window family includes the frame as part of the family, but with a different material. You can include or exclude the frame from the exported window [by selecting or deselecting the frame material](../revit-plugin/export-analytical-model/selecting-doors-and-windows-families/selecting-window-family-types.md#understanding-panel-calculation-options).

### Curtain wall panels

The frame is not included in the curtain wall panels. As explained above, you can use the [Make Windows Flush](commands/me_make_windows_flush.md) in the Model Editor to adjust the window size to include the frame.

## Remove small windows

The next step in the cleanup is to remove the small windows that might exist in the model. Small windows usually exist because of the curtain wall panels that cover part of the floor slab thickness of the upper level. That results in creating small windows at the edge of the floor. The other typical case is when the windows are projected on a curved wall. Depending on the complexity of the model, you might find some small windows being projected by mistake. In both cases, you could use the [Remove Small Windows](commands/alphabetically/remove-small-windows.md) command to remove these windows from the model.

## Rectangularize windows

In some cases, you might end up with windows and doors with non-aligned edges. This is usually the result of not filtering the materials correctly and not selecting the correct panel calculation method when selecting doors and windows ([see here](../revit-plugin/export-analytical-model/selecting-doors-and-windows-families/selecting-window-family-types.md#understanding-panel-calculation-options)), but regardless of the reason, you can use the [Rectangularize Windows](commands/me_rectangularize_windows.md) command to change these windows and doors to clean rectangles.

## Repair invalid windows

If you have followed the steps above, at this point, the only possible issues are windows and doors with large overlaps or windows and doors that extend outside the walls. In both cases, you can use the [Repair Invalid Windows](commands/me_repair_windows.md) command to resolve these issues automatically.

## Reducing the number of windows

Once you have cleaned up the windows, you may want to use the [Simplify Windows](workflows/simplifying-windows.md) command to simplify the windows' geometry and reduce the number of windows in the model. This command allows you to simplify the geometry by merging multiple windows into a single window per wall or roof.

## FAQ

### Is it possible to apply these commands to only a selection of the windows in a room?

Yes. If you select one or more lines in addition to the rooms when you run these commands, only the windows that align with these lines will be affected by the command.
