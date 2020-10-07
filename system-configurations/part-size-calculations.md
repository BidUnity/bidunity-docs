# Part Size Calculations

A part is assigned a size from a set of formulas called **part use conventions** \(or "part use" for short\). These are meant to represent different ways the part may be _used_ in the component. Each part use returns a value calculated using attributes of the component.

### Example

For example, a Head component might have the following parts configured:

* 1 stick of head framing, assigned the _Daylight Width_ part use
* 4 fabrication screws, assigned the _Per Component_ part use
* 2 lengths of butyl tape 3/8" x 1/8", assigned the _Component Face Dimension_ part use

If the elevation drawing contains a Head component that is 30" long with a face dimension of 2", this will result in the following parts being added to the parts list:

* One 30" stick of head framing
* Four fabrication screws
* Two 2" lengths of butyl tape

## Part Use Conventions

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
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Per Component</td>
      <td style="text-align:left">One unit is required each time this component is used.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Eight Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 8 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Twelve Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 12 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Sixteen Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 16 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Twenty Four Inches on Center</td>
      <td style="text-align:left">The component&apos;s Length is divided by 24 and rounded up to the nearest
        integer.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Units Per Square Foot</td>
      <td style="text-align:left">The component&apos;s area is calculated in square feet. If logical, the
        result is assigned to the number of units required. If not logical (such
        as 10.1 screws is not logical) the result is rounded up to the next integer
        value then assigned to the number of units required.</td>
      <td style="text-align:left">Units</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Opening Height</td>
      <td style="text-align:left">The assigned value is equal to the elevation height.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Opening Width</td>
      <td style="text-align:left">The assigned value is equal to the elevation width.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Opening Perimeter</td>
      <td style="text-align:left">( Opening Height + Opening Width ) * 2</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Overall Frame Height</td>
      <td style="text-align:left">Opening Height - Top Shim Space - Bottom Shim Space</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Overall Frame Width</td>
      <td style="text-align:left">Opening Width - Left Shim Space - Right Shim Space</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Vertical Component Height</td>
      <td style="text-align:left">The vertical height of the component.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Not applicable to horizontal framing components.</td>
    </tr>
    <tr>
      <td style="text-align:left">Component Length</td>
      <td style="text-align:left">The length of a framing or receptor component.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">
        <p>Frames,</p>
        <p>Receptors</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Horizontal Assembly Width</td>
      <td style="text-align:left">Opening Width - Left Shim Space - Right Shim Space - Left Receptor Deduction
        - Right Receptor Deduction</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
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
    </tr>
    <tr>
      <td style="text-align:left">Component Thickness</td>
      <td style="text-align:left">The thickness/depth of the component. Any component may have a thickness,
        including framing, receptors, glass, even overall elevation and vertical
        section. If used in the Overall Elevation or Vertical Section, returns
        the Product System&apos;s depth.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">Any</td>
    </tr>
    <tr>
      <td style="text-align:left">Interior Sealant Height</td>
      <td style="text-align:left">The Product System&apos;s <em>Interior Sealant Height.</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Daylight Width</td>
      <td style="text-align:left">The distance between two vertical frames for a glass lite.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">TODO: SHOULD ONLY APPLY TO GLASS BUT IS USED ON MANY COMPONENT TYPES!!!</td>
    </tr>
    <tr>
      <td style="text-align:left">Daylight Height</td>
      <td style="text-align:left">The distance between two horizontal frames for a glass lite.</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left">TODO: Glass only</td>
    </tr>
    <tr>
      <td style="text-align:left">Daylight Perimeter</td>
      <td style="text-align:left">(Daylight Width * 2) + (Daylight Height * 2)</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Vertical Glass Bite</td>
      <td style="text-align:left">The Product System&apos;s <em>Actual Height </em>minus <em>Daylight Height</em>.</td>
      <td
      style="text-align:left">Length</td>
        <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Horizontal Glass Bite</td>
      <td style="text-align:left">The Product System&apos;s <em>Actual Width </em>minus <em>Daylight Width</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Horizontal Vinyl Length</td>
      <td style="text-align:left">Daylight Width + ( Daylight Width * The Product System&apos;s <em>Add Per Foot Vinyl</em> /
        12 )</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
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
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Perimeter Vinyl</td>
      <td style="text-align:left">The Sum of Horizontal and Vertical Vinyl</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Height</td>
      <td style="text-align:left">Daylight Height + The Product System&apos;s <em>Actual Height minus Daylight Height</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Width</td>
      <td style="text-align:left">Daylight Width + The Product System&apos;s <em>Actual Width minus Daylight Width</em>
      </td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Exact Area</td>
      <td style="text-align:left">BidUnity Uses Exact Area to Assign Glass Width &amp; Glass Height They&apos;re
        Used to Derive Areas, etc.</td>
      <td style="text-align:left">Length &amp; Width</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Block Area</td>
      <td style="text-align:left">Returns the Area Given By Rounding Each of Glass Width and Glass Height
        Up to the Nearest Even Inch The Length and Width are stored as cut-size
        dimensions</td>
      <td style="text-align:left">Area, Length, and Width</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">The Elevation&apos;s Total Width * The Elevation&apos;s Total Height,
        Units are Converted to Square Feet</td>
      <td style="text-align:left">Area</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Caulk Joint Depth</td>
      <td style="text-align:left">The Caulk Joint Depth is 1/2 of the shim space if this is less than 1/4,
        then 1/4 if this is more than 3/8, then 3/8 This is used to calculate the
        volume of caulk joints</td>
      <td style="text-align:left">Length</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Exterior Perimeter Joint Volume (x2 for waste)</td>
      <td style="text-align:left">One-Side Perimeter Joint Volume (x2 for waste) +
        <br />(Product System&apos;s <em>Interior Sealant Height</em> * Caulk Joint Depth
        @ Right * Right Shim Space) +
        <br />(Product System&apos;s <em>Interior Sealant Height</em> * Caulk Joint Depth
        @ Left * Left Shim Space) +
        <br />(Opening Width * Caulk Joint Depth @ Bottom * Bottom Shim Space)
        <br />This result is converted to mL</td>
      <td style="text-align:left">Volume</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Glass Perimeter Joint Volume x System Properties</td>
      <td style="text-align:left">Daylight Perimeter *
        <br />Product System&apos;s <em>Structural Sealant Width</em> *
        <br />Product System&apos;s <em>Structural Sealant Depth</em>
        <br />This Result is Converted to mL: 16.387 mL / in^3
        <br />This Result is Multiplied by 1.25 to Allow for Waste</td>
      <td style="text-align:left">Volume</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">One-Side Perimeter Joint Volume (x2 for waste)</td>
      <td style="text-align:left">Sum: (Caulk Joint Depth * Shim Space <em>at this side</em> * Length <em>at this side</em>)
        For Each Side of the Elevation
        <br />The result is converted to mL from cubic inches by multiplying by: 16.387
        ml / 1 in^3
        <br />This result is multiplied by 2 which compensates for waste.</td>
      <td style="text-align:left">Volume</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Exterior Perimeter Joint Volume (x2 for waste)</td>
      <td style="text-align:left">One-Side Perimeter Joint Volume (x2 for waste) +
        <br />(Product System&apos;s <em>Interior Sealant Height</em> * Caulk Joint Depth
        @ Right * Right Shim Space) +
        <br />(Product System&apos;s <em>Interior Sealant Height</em> * Caulk Joint Depth
        @ Left * Left Shim Space) +
        <br />(Opening Width * Caulk Joint Depth @ Bottom * Bottom Shim Space)
        <br />Again, the result is converted to mL</td>
      <td style="text-align:left">Volume</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

All Lengths are specified in inches. Area is square inches. Volume in milliliters.

