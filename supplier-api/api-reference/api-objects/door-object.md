---
description: >-
  Defines the structure of the Door object, which is used in the quote request
  API.
---

# Door Object

## Overview

The Door object contains the information for the door frame and leaf.

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
      <td style="text-align:left">The unique identifier for the door.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The name of the door.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>width</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The width of the door, in inches.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>height</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The height of the door, in inches.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hand</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>The hand type for the door. Possible values:</p>
        <ul>
          <li><code>doorHand.LEFT</code>- single door with handle on left</li>
          <li><code>doorHand.RIGHT</code>- single door with handle on right</li>
          <li><code>doorHand.PAIR</code>- for a pair of doors</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>swing</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>The swing type for the door. Possible values:</p>
        <ul>
          <li><code>doorSwing.OUT</code>
          </li>
          <li><code>doorSwing.IN</code>
          </li>
          <li><code>doorSwing.DOUBLE_ACTING</code>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>quantity</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The quantity needed of this door configuration.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>unit_cost</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The cost for a single quantity of this door configuration.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>total_cost</code>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">The total cost for all quantities of this door configuration. This is
        equal to the <code>quantity</code> times <code>unit_cost</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">An object representing the door frame.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.name</code>
      </td>
      <td style="text-align:left">name</td>
      <td style="text-align:left">The name of the door frame.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components</code>
      </td>
      <td style="text-align:left">array</td>
      <td style="text-align:left">The component objects making up the door frame.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components.name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The name of the frame component.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components.type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The type of the frame component. TODO LINK</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components.order_code</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">This is field not yet supported, but in the future will contain the supplier&apos;s
        order code for the component</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf</code>
      </td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">An object representing the door leaf.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The name of the door leaf.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components</code>
      </td>
      <td style="text-align:left">array</td>
      <td style="text-align:left">The component objects making up the door leaf.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components.name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The name of the leaf component.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components.type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The type of the leaf component.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components.order_code</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">This is field not yet supported, but in the future will contain the supplier&apos;s
        order code for the component</td>
    </tr>
  </tbody>
</table>

## Example

```yaml
{
    id: “407f191e810c19729de860aa”,
    name: “Door 101”,
    width: 72,  # inches
    height: 84,  # inches
    hand: “doorHand.LEFT”,
    swing: “doorSwing.OUT”,
    quantity: 2,
    unit_cost: 500.00,
    total_cost: 1000.00,
    frame: {
        name: “FL500 for 9/16" Transom Glass”,
        components: [{
            name: “FL501 Transom Head”,
            type: “Transom Frame Head”,
            order_code: null  # Not yet supported
        }, {
            name: "FL504 Door Transom Mullion (Left Side)",
            type: "FL504 Door Transom Mullion (Left Side)",
            order_code: null
        }]
    },
    leaf: {
        name: “Impact Resistant Doors”,
        components: [{
            name: “D102 (4") Top Rail”,
            type: “Top Rail”,
            order_code: null  # Not yet supported
        }, {
            name: "",
            type: "",
            order_code: null
        }]
    }
}

```

