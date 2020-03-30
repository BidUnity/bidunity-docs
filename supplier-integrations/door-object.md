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
      <td style="text-align:left">id</td>
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
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.name</code>
      </td>
      <td style="text-align:left">name</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components</code>
      </td>
      <td style="text-align:left">array</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components.name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>frame.components.type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
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
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components</code>
      </td>
      <td style="text-align:left">array</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components.name</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leaf.components.type</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
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

