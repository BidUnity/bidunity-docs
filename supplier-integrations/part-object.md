---
description: >-
  Defines the structure of the Part object, which is used by the quote request
  API.
---

# The Part Object

The Part object can represent many different types of items, such as items purchased individually, in a box, as a stock length, area, or volume. But no matter how the part is purchased, it has the same JSON object structure.

Some definitions before we get started:

* **Package** is the thing that is being purchased.
* A package can contain a **single item** or a **group of items**.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>id</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">BidUnity&apos;s unique id for the part.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The name of the part.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>part_number</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The supplier&apos;s part number.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>finish_type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The metal finish for the part, or null if not applicable. See Finish Types
        (TODO link)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>finish_color</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The finish color for the part, or null if not applicable. See Finish Colors
        (TODO link)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>finish_multiplier</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">A value to multiply against the configured finish price to calculate the
        cost for the part. This defaults to 1.0 but can be modified by users when
        creating the proposal.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>total_cost</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The total cost for the part, including all quantities of the part being
        ordered.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>package_unit_cost</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The cost for a single quantity of the part. The unit cost multiplied by
        the package quantity to order will equal the total cost for the part.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>package_quantity_to_order</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>The quantity of the package being ordered.</p>
        <p>item_measurement_type - Describes what is being ordered.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>item_measurement_type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>Describes what is being ordered. Possible values:</p>
        <p><code>each</code>, <code>box</code>, <code>stock_length</code>, <code>block_area</code>, <code>container</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>items_per_package</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>The number of items contained in each package. This will be 1 for items
          purchased individually.</p>
        <p>Examples:</p>
        <ul>
          <li>If purchasing a box of 4 stock lengths then the value would be 4.</li>
          <li>If purchasing a box of 200 screws then the value would be 200.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>item_stock_size</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>The stock size for the item. The units of measure depend on the measurement
          type:</p>
        <ul>
          <li>For <code>each </code> this will be 1.</li>
          <li>For <code>box</code> this will be equal to <code>items_per_package</code>.</li>
          <li>For <code>stock_length</code> this may be 288 inches.</li>
          <li>For <code>block_area</code> this will be 1 square foot.</li>
          <li>For <code>container</code> this may be 500 milliliters.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>item_size_unit_of_measure</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The units of measure for the item_stock_size. Possible values: <code>item</code>, <code>in</code> (inches), <code>sqft</code> (square
        feet), <code>ml</code> (milliliters)</td>
    </tr>
  </tbody>
</table>### Examples

#### Example \#1: Per each \(i.e. door closer\)

Purchasing 5 door closers, purchased individually.

```yaml
{
    id: “407f191e810c19729de860ea”,
    name: “Example Door Closer Part Name”,
    part_number: “CLO482”,
    finish_type: “Class 1 Anodized”,
    finish_color: “Dark Bronze”,
    finish_multiplier: 1.0,
    total_cost: 100.00,
    package_unit_cost: 20.00,
    package_quantity_to_order: 5,
    item_measurement_type: “each”,
    items_per_package: 1,  # Sold individually
    item_stock_size: 1,
    item_size_unit_of_measure: “item”,
    sizes: null  # Items without a length do not have a size array
}
```

#### Example \#2: Box of screws

Purchasing 5 boxes of screws, with each box containing 200 screws.

```yaml
{
    id: “407f191e810c19729de860eb”,
    name: “Fastener: Tapcon 1/4" Diameter, Hex Washer Head”,
    part_number: “ELE435-100”,
    finish_type: null,
    finish_color: null,
    finish_multiplier: 1.0,
    total_cost: 100.00,
    package_unit_cost: 20.00,
    package_quantity_to_order: 5,
    item_measurement_type: “box”,
    items_per_package: 200,  # Each box contains 200 screws
    item_stock_size: 200,
    item_size_unit_of_measure: “item”,
    sizes: null  # Items without a length do not have a size array
}
```

#### Example \#3A: Stock lengths sold individually

Purchasing 5 stock lengths of framing at 288” per stock length.

```yaml
{
    id: “407f191e810c19729de860ec”,
    name: “Trulite 3101 Head/Sill/Jamb”,
    part_number: “3101”,
    finish_type: “Class 1 Anodized”,
    finish_color: “Dark Bronze”,
    finish_multiplier: 1.0,
    total_cost: 100.00,
    package_unit_cost: 20.00,
    package_quantity_to_order: 5,
    item_measurement_type: “stock_length”,
    items_per_package: 1,   # Lengths sold individually
    item_stock_size: 288,   # 288” stock lengths
    item_size_unit_of_measure: “in”,  // Inches
    sizes: [{  // Array of sizes needed
        component: “Head”,
        length: 29.125   # inches
    },{
        component: “Sill”,
        length: 29.125   # inches
    }]
}
```

#### Example \#3B: Stock lengths sold as a group

Purchasing 2 boxes of stock lengths, with each box contains 4 lengths at 288” for a total of 8 stock lengths.

```yaml
{
    id: “407f191e810c19729de860ec”,
    name: “Trulite 3101 Head/Sill/Jamb”,
    part_number: “3101”,
    finish_type: “Class 1 Anodized”,
    finish_color: “Dark Bronze”,
    finish_multiplier: 1.0,
    total_cost: 100.00,
    package_unit_cost: 50.00,
    package_quantity_to_order: 2,
    item_measurement_type: “stock_length”
    items_per_package: 4   # 4 stock lengths per box
    item_stock_size: 288   # 288” stock lengths
    item_size_unit_of_measure: “in”
    sizes: [{
        component: “Head”,
        length: 29.125   # inches
    },{
        component: “Sill”,
        length: 29.125   # inches
    }]
}
```

#### Example \#4: Glass

Purchasing 300 block area square feet of glass.

```yaml
{
    id: “407f191e810c19729de860ed”,
    name: “Glass: 1-5/16" Overall: 1/4" Temp X 1/2" Air Space X 1/4" HS X 0.090 PVB X 1/4" HS”,
    part_number: “1/4" Clear Temp X 1/2" Air Space X 1/4" Clear HS X 0.090 PVB X 1/4" Clear HS”,
    finish_type: null,
    finish_color: null,
    finish_multiplier: 1.0,
    total_cost: 3000.00,
    package_unit_cost: 10.00,
    package_quantity_to_order: 300
    item_measurement_type: “block_area”
    items_per_package: 1
    item_stock_size: 1
    item_size_unit_of_measure: “sqft”
    sizes: [{  // Array of the actual (not block) glass sizes needed
        width: 28.63,   // inches
        height: 12.63,  // inches
        quantity: 3
    }]
}
```

