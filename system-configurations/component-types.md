# Component Types

The elevation drawing is made up of components from the system configuration, such as jamb, mullion, head, sill, horizontal, glass, etc. Each component can have a set of parts configured for it. When the elevation is saved, the part list will be generated and each part will be assigned a size based on the component size and it's part use convention.

There are a number of different component types that are supported:

* Glass
* Door
* Jamb
* Mullion
* Head
* Sill
* Horizontal
* Continuous Head
* Continuous Sill
* Continuous Horizontal
* Top Receptor
* Bottom Receptor
* Left Receptor
* Right Receptor
* Column/Section
* Overall Elevation



### Receptors

The receptor components have some special fields that do not apply for other components:

* **Deduction Size** - The distance in inches between the shim space and the framing or glass components.
* **Sizing** - The receptor can be sized the same as the frame, or it can run through the shim space on either end to the edge of the elevation opening.
* **Shim Space** - The receptor can be shimmed as usual, or you can choose not to use a shim space for the receptor. If no shim is used then there is no space between the receptor and the elevation opening.
* **Split by Doors** - The receptor can be cut around a door frame, or can run continuously above or below the door frame. This only applies to continuous top & bottom receptors.

#### Receptor Segments

Top and bottom receptors can be split into multiple segments in two different ways:

1. If the option to Split by Doors is selected and a door is inserted into the elevation drawing.
2. If the head or sill components are different from one column to another.

If there are multiple segments for a top or bottom receptor, the parts that are assigned to that receptor component have an additional option for the Add to Processed Size field. This added value can be applied to every segment of the receptor, or just to the segments that touch the perimeter sides. This is useful for **TODO EXAMPLE**.



