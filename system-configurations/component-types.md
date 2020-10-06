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
* Elevation



### Receptors

The receptor components have some special fields that do not apply for other components:

* **Deduction Size** - The distance in inches between the shim space and the framing or glass components.
* **Shim Space** - The receptor can be shimmed as usual, or you can choose not to use a shim space for the receptor. If no shim is used then there is no space between the receptor and the elevation opening.
* **Split by Doors** - The receptor can be cut around a door frame, or can run continuously above or below the door frame. This only applies to continuous top & bottom receptors.

#### Receptor Sizing

The top and bottom receptors extend to the left and right opening, through the left and right shim spaces. Similarly, the left and right receptors extend through the top and bottom shim spaces to the edge of the opening.



