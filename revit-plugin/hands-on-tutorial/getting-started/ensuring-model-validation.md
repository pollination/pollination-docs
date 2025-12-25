# Ensuring Model Validation

{% embed url="https://youtu.be/LHDnugFvTpw" %}

For anyone who might need the files, here are the files you'll need to follow this section.

{% file src="../../../.gitbook/assets/06-Revit Advanced Sample Model-Rooms-Filled.pomf" %}

One last step before exporting the model is to ensure there are no more issues in the model that we might have missed, and ensure the model is valid. This is a very important step in the process. A valid model is guaranteed to be exported successfully without any issues. We take this responsibility very seriously. [You can see the Pollination Pact here](https://www.pollination.solutions/pact).

To ensure the validity of the model we check every level for small gaps, and any mistakes in adjacency before using the validation routine. The Model Editor provides a collection of commands and utilities to help with this process:

* ![](../../../.gitbook/assets/find-adjacency-gaps.svg)[Find Adjacency Gaps](../../../model-editor/commands/me_find_adjacency_gaps.md)
* Highlight Non-orthogonal Walls (Alt + O)
* ![](<../../../.gitbook/assets/solve-adjacency (1).svg>) [Solve Adjacency](../../../model-editor/commands/me_solve_adjacency.md)
* Highlight External Walls (Alt + E)

We will also use the validation routine to ensure the model is valid. If you have followed the previous steps, you should have already resolved most of the validation errors related to the floor plans.

The most common validation issues that you might see at this point are related to the overlapping windows and doors. We will use the [Repair Windows](../../../model-editor/commands/me_repair_windows.md) command to fix those validation issues.
