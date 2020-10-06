# Part Size Calculations

A part is assigned a size from a set of formulas called **part use conventions** \(or "part use" for short\). These are meant to represent different ways the part may be _used_ in the elevation. Each part use returns a value calculated using attributes of the component.

### Example

For example, a Head component might have the following parts configured:

* 1 stick of head framing, assigned the _Component Length_ part use
* 4 fabrication screws, assigned the _Per Component_ part use
* 2 lengths of butyl tape 3/8" x 1/8", assigned the _Component Face Dimension_ part use

If the elevation drawing contains a Head component that is 30" long with a face dimension of 2", this will result in the following parts being added to the parts list:

* One 30" stick of head framing
* Four fabrication screws
* Two 2" lengths of butyl tape

## Part Use Conventions

* Opening Height
* Opening Width
* Opening Perimeter
* Overall Frame Height
* Overall Frame Width
* Vertical Component Height
* Component Length
* Horizontal Assembly Width
* 
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
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>



