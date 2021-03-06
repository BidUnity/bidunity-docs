# Parts

The Part object can represent many different types of items, such as items purchased individually, in a box, as a stock length, by area, or volume. This is called the Purchase Type. Each part is also assigned to an Account such as Caulking, Framing, etc.

## Terminology

Some definitions before we get started:

* **Package** is the thing that is being purchased.
* A package can contain a **single item** or a **group of items**.

## Purchase Types

| Purchase Type | Description | Example |
| :--- | :--- | :--- |
| **Per Unit** | Each item is sold individually. | A door closer |
| **Per Unit, Lot Quantity** | Multiple items are ordered together in a package. | A box of screws |
| **Total Length** | A length of any size may be ordered. | A bumper threshold, or labor for a polished edge |
| **Stock Length** | Lengths must be ordered in predefined sizes. Cutting patterns can be optimized for this. | Jamb, mullion, head or sill |
| **Stock Length, Spliceable** | Lengths must be ordered in predefined sizes, but multiple lengths may be spliced together to form larger lengths. | A roll of tape or vinyl |
| **Total Area** | Any number of square feet may be ordered. | Glass |
| **Container Volume** | Each item contains a specific volume. | A sausage of caulking, or a box of sausages |

## Examples

The following table shows examples of common parts and how they would be configured:

| Example | Purchase Type | Items per Package | Item Size |
| :--- | :--- | :--- | :--- |
| A door closer, sold individually | Per Unit | N/A | N/A |
| A box of 100 screws | Per Unit, Lot Quantity | 100 | N/A |
| A bumper threshold for 96" | Total Length | N/A | N/A |
| A stock length of head/sill/jamb at 288", sold individually | Stock Length | 1 | 288" |
| A box of stock lengths of aluminum, containing 4 lengths at 288" | Stock Length | 4 | 288" |
| A roll of masking tape, 180 ft, sold individually | Stock Length, Spliceable | 1 | 2160" |
| A box of vinyl rolls, containing 10 rolls at 120" | Stock Length, Spliceable | 10 | 120" |
| 500 square feet of glass | Total Area | N/A | N/A |
| A sausage of caulking containing 595 mL, sold individually | Container Volume | 1 | 595 mL |
| A box of caulking containing 16 tubes, with each tube containing 20 mL of caulking \(total of 320 mL for the box\) | Container Volume | 16 | 20 mL |

