# Part Size Calculations

A part is assigned a size from a set of formulas called **part use conventions** \(or "part use" for short\). These are meant to represent different ways the part may be _used_ in the component. Each part use returns a value calculated using attributes of the component.

### Example

For example, a Head component might have the following parts configured:

* 1 stick of head framing, sized by the _Daylight Width_ part use
* 4 fabrication screws, assigned the _Per Component_ part use
* 2 lengths of butyl tape 3/8" x 1/8", sized by the _Component Face Dimension_ part use

If the elevation drawing contains a Head component that is 30" long with a face dimension of 2", this will result in the following parts being added to the parts list for that instance of the Head component:

* One 30" stick of head framing
* Four fabrication screws
* Two 2" lengths of butyl tape

## Part Use Conventions

Some definitions before we get started:

* **Package** is the thing that is being purchased.
* A package can contain a **single item** or a **group of items**.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Part Use</th>
      <th style="text-align:left">Value</th>
      <th style="text-align:left">Assigns</th>
      <th style="text-align:left">
        <p>Supported</p>
        <p>Component Types</p>
      </th>
      <th style="text-align:left">Supported Purchase Types</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Per Component</td>
      <td style="text-align:left">One unit is required each time the component is used.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Eight Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 8 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Twelve Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 12 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Sixteen Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 16 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Twenty Four Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 24 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Custom Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by a custom number and rounded
        up to the nearest integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">One Unit</td>
      <td style="text-align:left">Set the quantity to include a specific number of units of the part.</td>
      <td
      style="text-align:left">Units</td>
        <td style="text-align:left">Any</td>
        <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Units Per Square Foot</td>
      <td style="text-align:left">The component&apos;s area is calculated in square feet. If logical, the
        result is assigned to the number of units required. If not logical (such
        as 10.1 screws is not logical) the result is rounded up to the next integer
        value then assigned to the number of units required.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Overall Elevation, Glass, Vertical Section</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Per Horizontal/Jamb Intersection</td>
      <td style="text-align:left">One unit is required for each jamb component that the horizontal intersects.</td>
      <td
      style="text-align:left">Units</td>
        <td style="text-align:left">Horizontal frame components</td>
        <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Per Horizontal/Mullion Intersection</td>
      <td style="text-align:left">One unit is required for each mullion component that the horizontal intersects.</td>
      <td
      style="text-align:left">Units</td>
        <td style="text-align:left">Horizontal frame components</td>
        <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Per Perimeter Contact</td>
      <td style="text-align:left">One unit is required for each perimeter side the receptor comes into contact
        with.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left">Receptors</td>
      <td style="text-align:left">Per unit/box</td>
    </tr>
    <tr>
      <td style="text-align:left">Opening Size Height</td>
      <td style="text-align:left">The assigned value is equal to the elevation height.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Opening Size Width</td>
      <td style="text-align:left">The assigned value is equal to the elevation width.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Opening Perimeter</td>
      <td style="text-align:left">( Opening Height + Opening Width ) * 2</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Overall Frame Height</td>
      <td style="text-align:left">Opening Height - Top Shim Space - Bottom Shim Space</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Overall Frame Width</td>
      <td style="text-align:left">Opening Width - Left Shim Space - Right Shim Space</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Vertical Component Height</td>
      <td style="text-align:left">The vertical height of the component.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any (but horizontal components will return their face dimension)</td>
      <td
      style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Component Length</td>
      <td style="text-align:left">The length of a framing or receptor component.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">
        <p>Framing,</p>
        <p>Receptors</p>
      </td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Horizontal Assembly Width</td>
      <td style="text-align:left">Opening Width - Left Shim Space - Right Shim Space - Left Receptor Deduction
        - Right Receptor Deduction</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any (but vertical components will return their face dimension)</td>
      <td
      style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Component Face Dimension</td>
      <td style="text-align:left">The visible face dimension of the framing or receptor component. If applied
        to the Overall Elevation, then returns the Product System&apos;s <em>Typical System Face</em>.</td>
      <td
      style="text-align:left">Length</td>
        <td style="text-align:left">
          <p>Frames,</p>
          <p>Receptors,</p>
          <p>Overall Elevation</p>
        </td>
        <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Component Thickness/Depth</td>
      <td style="text-align:left">The thickness/depth of the component. Any component may have a thickness,
        including framing, receptors, glass, even overall elevation and vertical
        section. If used in the Overall Elevation or Vertical Section, returns
        the Product System&apos;s depth.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">System Depth</td>
      <td style="text-align:left">TODO: Eliminate this and instead use the &quot;Component Thickness&quot;
        on Overall Elevation component.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Interior Sealant Height</td>
      <td style="text-align:left">The Product System&apos;s <em>Interior Sealant Height.</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Daylight Width</td>
      <td style="text-align:left">The distance between two vertical frames for a glass lite.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any -- TODO: SHOULD NOT BE USED ON VERTICALS!</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Daylight Height</td>
      <td style="text-align:left">The distance between two horizontal frames for a glass lite.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any -- TODO: SHOULD NOT BE USED ON HORIZONTALS!</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Daylight Perimeter</td>
      <td style="text-align:left">(Daylight Width * 2) + (Daylight Height * 2)</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Horizontal Vinyl Length</td>
      <td style="text-align:left">Daylight Width + ( Daylight Width * The Product System&apos;s <em>Add Per Foot Vinyl</em> /
        12 )</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Vertical Component Vinyl Length</td>
      <td style="text-align:left">Behaves Differently Depending on the Component Because it Returns the
        Total Daylight Height of All Rows in the Component
        <br />For elevations and glass there can be only one row. Vertical section components
        can have multiple rows.
        <br />Returns the total daylight height of all rows in the component +
        <br />The total daylight height of all rows in the component * The Product System&apos;s <em>Add Per Foot Vinyl</em> *
        2</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Perimeter Vinyl</td>
      <td style="text-align:left">The Sum of Horizontal and Vertical Vinyl</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Height</td>
      <td style="text-align:left">Daylight Height + The Product System&apos;s <em>Actual Height minus Daylight Height</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Width</td>
      <td style="text-align:left">Daylight Width + The Product System&apos;s <em>Actual Width minus Daylight Width</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Block Area</td>
      <td style="text-align:left">Returns the Area Given By Rounding Each of Glass Width and Glass Height
        Up to the Nearest Even Inch The Length and Width are stored as cut-size
        dimensions</td>
      <td style="text-align:left">Area, Length, and Width</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Area</td>
    </tr>
    <tr>
      <td style="text-align:left">Square Feet</td>
      <td style="text-align:left">The Elevation&apos;s Total Width * The Elevation&apos;s Total Height,
        converted to square feet.</td>
      <td style="text-align:left">Area</td>
      <td style="text-align:left">Overall Elevation, Glass, Vertical Section</td>
      <td style="text-align:left">Area</td>
    </tr>
    <tr>
      <td style="text-align:left">Caulk Joint Depth</td>
      <td style="text-align:left">The Caulk Joint Depth is 1/2 of the shim space if this is less than 1/4,
        then 1/4 if this is more than 3/8, then 3/8. This is used to calculate
        the volume of caulk joints.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Custom Length</td>
      <td style="text-align:left">Enter the length (in inches) of the part to include and set the quantity
        at that length.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">By length</td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Perimeter Joint Volume x System Properties</td>
      <td style="text-align:left">Daylight Perimeter *
        <br />(Product System&apos;s <em>Structural Sealant Width)</em> *
        <br />(Product System&apos;s <em>Structural Sealant Depth).</em>
        <br />This Result is Converted to mL and multiplied by 1.25 to allow for waste.</td>
      <td
      style="text-align:left">Volume</td>
        <td style="text-align:left">Any</td>
        <td style="text-align:left">Volume</td>
    </tr>
    <tr>
      <td style="text-align:left">One-Side Perimeter Joint Volume (x2 for waste)</td>
      <td style="text-align:left">
        <p>The sum for <em>each side </em>of the elevation of: (Caulk Joint Depth
          * Shim Space <em>at this side</em> * Length <em>at this side</em>).</p>
        <p>The result is converted to mL and doubled to account for waste.</p>
      </td>
      <td style="text-align:left">Volume</td>
      <td style="text-align:left">Any</td>
      <td style="text-align:left">Volume</td>
    </tr>
    <tr>
      <td style="text-align:left">Exterior Perimeter Joint Volume (x2 for waste)</td>
      <td style="text-align:left">The one-side perimeter caulk volume for the left, right, and bottom sides
        of the elevation. One-Side Perimeter Joint Volume (x2 for waste) +
        <br />(Product System&apos;s <em>Interior Sealant Height</em> * Caulk Joint Depth
        @ Right * Right Shim Space) +
        <br />(Product System&apos;s <em>Interior Sealant Height</em> * Caulk Joint Depth
        @ Left * Left Shim Space) +
        <br />(Opening Width * Caulk Joint Depth @ Bottom * Bottom Shim Space)
        <br />Again, the result is converted to mL</td>
      <td style="text-align:left">Volume</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

All Lengths are specified in inches. Area is square inches. Volume in milliliters.

