# Proposals

**BidUnity's Estimating Philosophy**

When your estimating process is limited to researching costs and then writing proposals for customers, running projects is made more difficult. Your assumptions about how projects will run should be documented, let's call that a budget. Budgets provide a reference for managing the project.

When construction proposals are very detailed, addressing everything, they become internally useful. Estimators must be judicious with their time, but if your work will ever run smoothly, your proposals must be more than something that customers use to make a decision.

BidUnity provides a superior way for estimators to form complete proposals because running the work is more of a challenge than selling it. BidUnity takes the view that externally useful proposals should be derived from internally useful information.

Internally useful proposals are developed by the following process. Identify the work, note quantities, determine the material and labor required, add up those costs, add indirect expenses, and finally decide what margin to assign. BidUnity organizes this entire process and finally derives your sales proposals from the information recorded along the way.

**Proposal Data Entry & How it is Used**

Proposal data entry includes five parts.

1. Scheduling Doors
2. Adding Specifications
3. Adding Elevations
4. Making Selections when you 'Get Pricing'
5. Adding Indirect Expenses
6. Assigning Your Margins

**The Door Schedule**

Each proposal, not each project, has a door schedule. Note that when you duplicate a proposal, the door schedule is copied to the new proposal.

Door schedules include three parts.

1. **Leaf Schedule:** Defines the intended door leaf component attributes.
2. **Hardware Schedule:** Defines the intended door hardware.
3. **Door Schedule:** Uniquely identifies each of the proposal's door and its specifications.

The door schedule provides a convenient way for you to specify what it is _wanted_. Your door schedule is used to include doors that match the door schedule _as closely as possible_. Suppliers provide many door and hardware options, but as everyone knows, there can be an almost unlimited number of customizations when it comes to doors. In addition to many available options, material suppliers are always on the lookout for additional ways to differentiate their products from competitors.

BidUnity uses your door schedule to find exactly what you specify in terms of the leaf and hardware components. If a supplier does not have exactly what you specified, it looks for the closest match. Note that when you review costs the quality of the match is scored for each door and indicated with colors.

1. An exact match resulted.
2. One or more comonents was matched. You should check to see if the most appropriate selection was deermined.
3. No valid components were found. This can happen when the size of the door is too large for available components. Be careful that your cost basis includes the items needed, BidUnity will not add values of things that are not included in your proposal.

Note that you can make changes and select alternate items when you review costs.

**Reviewing Costs The Proposal Review Interface**

**Overview:** BidUnity's 'Proposal Review' is really all about understanding options and qualifying risks. It puts together cost estimates for each specification independently based on the instructions for building systems. Those instructions are contained in the product system's _Product Validation\(s\)_. Note that each specification stands on its own in the proposal review. Parts are not optimized or shared between specifications here, but materials are combined later when you get to the _Proposal Summary_. Product systems are included on the proposal review when they meet _all_ of the following criteria.

1. Only systems matching the specification's system type are elidgable.
2. Only when the 'primary supplier' that the system is registered to is also one of your company vendors are the systems elidgable.

**Proposal Data What you need to know**

The 'Proposal Review' is where you review alternate costs and make selections as to what will form the basis of your proposal. All of the cost items on the proposal review page are direct costs as opposed to indirect costs. Direct costs, think of material and labor, are directly related to the work. Indirect costs, think of travel or equipment rental, are not directly related to the work itself and are added after products are selected.

**Build Data The Takeoff**

When you load the Proposal Review page, BidUnity checks to see if the specifications have already been 'built'. If they have been built, BidUnity loads them where you left off. If you loaded the page previously, selected different components, systems, vendors, doors, hardware, etc. those selections will be exactly as you prevously left them. If specifications have not previously been built, BidUnity builds them for you now, see _Building Specifications_ below.

**Proposal Review Page Controls Manage the Data at the Macro Level**

**Building Specifications** involves several different things. Lets look at each step of the process to understand what is happening.

1. BidUnity finds valid product systems for each specificaiton.
   * BidUnity finds all _equivalent_ product systems which are taken to be those systems which are of the same system type.
   * Of these systems, BidUnity discards any that have a 'primary vendor' which is not included in your company vendors.
     * By default no constraints are selected when you load the proposal review and all of the systems meeting the above criteria are returned.
     * When 'Florida Product Approval' constraints are selected, product validations are checked to ensure that they meet or exceed the most extreme cases within the specification's elevations.
2. BidUnity performs a complete takeoff for each specification.
   1. For each 'Product Validation' of each product system, component parts are assigned sizes based on the product system's properties and each elevation's size and configuration.
   2. Once all required parts and their sizes are known, BidUnity looks at all of your vendor's catalogs for each part. For each vendor that has the part, BidUnity gets all available purchase sizes.
   3. The total number of units required to be purchased is calculated for each size.
   4. BidUnity then gets the prices for each part based on the specification's finsh color.
      * If no prices are found for the color, it returns the 'Mill/Unfinished' price.
      * If no price is found, the particular vendor's part is discarded.
   5. BidUnity gets the catalog section for each of the parts and finds your company vendor multiplier for that catalog section.
   6. Your cost per each part is calcuated based on the finish price and your catalog multiplier value.
   7. Your total cost for each alternate vendor is evaluated based on the units that need to be ordered and your cost on that item.
3. BidUnity selects components.
   1. Components are ordered from least expensive to most expensive.
   2. Each component is checked based on the selected constraint type. You can select the constraint type to apply by clicking 'Options' in the top left of the page.
      * If 'No Constraints' is selected, which is the default setting, components are not validated, all components are returned.
      * If 'Structural Constraints' is selected the Modulus of Elasticity and Section Modulus of each vertical intermediate component is checked against the span, spacing, and pressure to qualify it. Any such components which do not have adequate property values are removed from the results. Note that these components will also be removed if they do not have values defined for these properties.
      * If 'Florida Product Approval' is selected, components which were not tested to meet the size, spacing, pressure are removed.
   3. Of the components remaining after constraints are applied, the least expensive is selected by default.
4. BidUnity builds display data.
   * Each product validation is equally represented in a table, side-by-side with other equal products. All of the expenses associated with each system are broken out by their expense category.
   * Clicking on any of the prices exposes the list of required parts. By defualt, the lowest cost vendor is selected. Clicking on the part's price brings up a list of all potential vendors so that you can select that vendor which you prefer, if other than the least expensive.

**Constraints and How They are Applied**

**Constraints** are a useful tool for qualifying the components before you finalize a proposal. There is nothing worse than selling a job inexpensively only to later find out that you have to make a choice between meeting the code and breaking your budget or breaking the code to stay on budget. By default, no constraints are applied. By clicking the opitons button, you can choose to apply structural constraints or Florida Product Approval Constraints.

**Structural Constraints** are based on IBC 2403.3 which specifies limitations on the deflection of framing components that support glazing. We calculate the theoretical minimum _moment of inertia_ and _section modulus_ of the intermediate componets based on the span, pressure, and effective spacing.

**Moment of Inertia =** \( 5 \* designPressure \* tributaryArea \* mullionLength^4 \) / \( 384 \* aluminum6063T3ModulusOfElasticity \* permissibleDeflection \)  
Where:  
 designPressure = The greatest absolute pressure \(psi\).  
 mullionLength = Opening height less shim spaces and flashing dimension. Subtract the typical system face dimension. Add 2.5 to get the _mullion length_.  
 aluminum6063T3ModulusOfElasticity = 10000000 psi  
 permissibleDeflection = mullionLength / 175 OR a maximum of 0.75, per IBC 2403.3.  
tributaryArea = effective spacing = average center-to-center mullion at right and left sides.

**Section Modulus =** \( moment / aluminumFiberConstant \)  
Where:  
 moment = \( designPressure \* tributaryArea \* mullionLength^2 \) / 8  
 aluminumFiberConstant = 11000 psi

**Florida Product Approval Constraints** When Florida Product Approval constraints are selected, only product validations that test large enough and at a high enough pressure are returned for consideration. Sometimes these systems will be Missing Components. Look for the red warning indication.

**Energy Performance Based Constraints:** We designed BidUnity in a way that will allow it to constrain glazing systems and components based on specified energy performance criteria. Like everything else, it only takes time to program. Probably less than two weeks if we made it priority number one. Let us know if this feature would be important to you by emailing support@bidunity.com.

#### Selecting the Basis of Your Bid

**Selecting Product Validations:** When all qualified product validations load, the least expensive is selected by default, notice the green button that says 'Selected' in the top row of the specification table. You can select a different product validation to use as the basis of your proposal, just click the button that says 'Select System'.

**Choose Components** by clicking on this link in the table heading. It opens a new window which display all of the components available to the product system. Whenever possible, component names correspond to the test report document which forms the basis of the product validation.

Only one component can be selected for each of the required component types. We recognize that it is necessary to allow alternate comonents to be selected, mixed, and matched within elevations and specificaitons. We consider this to be a bug, which limits the usefulness of BidUnity. We plan to support dynamic recombination of components within elevations and specifications in the near future.

**Fine Grained Selection** is possible when you click on the costs displayed for each expense account line item. When you click on the line item costs a complete breakdown is displayed. The breakdown includes everything that contributes costs to that expense type. You can drill in on those cost items further, by clicking on the price. This brings up a list of every possible alernative option. You can select any of the available alternate options in lieu of what was selected by default.

**Doors** deserve further explaination. When you create a door schedule, you specify the character of the components which should be used to make the door. When you build the proposal data, it is very possible that not every supplier has an exact match for what you specified. If BidUnity can not find an exact match because it either doesn't exist or isn't in the database, BidUnity will make a guess as to which available alternate best matches the door schedule.

**Component Match Scores:** When BidUnity builds the doors it also reports how well it thinks the door matches your intent. BidUnity looks to the door schedule' specifications to understand your intent.

Each door component is evaluated individually; if a door has ten different components, each will count for 10% of the component match score.

For example, if your door schedule specifies a 5-6 inch bottom rail and BidUnity found a 5-6 inch bottom rail for the door, BidUnity scores the bottom rail at 100%, an exact match. On the other hand, if a 5-6 in top rail is also specified and BidUnity can only find a 2-3 inch top rail, the top rail is scored at less than 100%. The component match score is the sum of the match scores of all of the door's components.

#### Errors & Unexpected Results

First lets identify that there at two types of errors. The first type of error is what we perceive to be wrong. Sometimes we resolve this by learning and sometimes we resolve it by following the error back to its origin and making a correction. The second type of error happens when BidUnity calculates a result that wouldn't make any kind of sense to you either. When the second type of error happens you will receive a '504' error. In other words, the page will load a message that says '504 Error'. If you experience this, please email support@bidunity.com and include the page address and description of what you were doing when you received the error. We'll be able to track down the problem and fix it. For the rest of this section we discuss the first type of error, why isn't BidUnity doing what I expect?

1. **No Product Systems Found:** We might not have any product systems to return for several reasons.
   * No system types match the product system type, in other words, they haven't been configured by anyone yet.
   * None of your company vendors have systems which match the specification's system type. **Double check your company vendors, make sure that they were not inadvertently de-selected.**
   * None of the systems which are availabe and match the specification's type meet the product approval constraints.
2. **Missing Components** can happen when they don't meet the constraints. If they should meet the constraints check the elevation sizes to make sure that they are correctly recorded and check the components themselves to make sure that constraint information is propoerly associated.
3. **Missing Part Prices** can happen when BidUnity can't find pricing from at least one of your vendors for the part. You can try adding the prices if you have that permission, and if that doesn't work you should check your vendors.
4. _No frame found, check that product validation has a frame configured._ Can happen with the product validation isn't associated with a door frame. Do what it says if you have permission.
5. _No leaf found meeting the door opening size._ Door leaves are constrained to maximum sizes. Are you trying to build a storefront door leaf that is not in your supplier's product catalog or hasn&%39;t been tested to the applicable sizes? Maybe the door is available for purchase, but has not been configured in BidUnity yet? One of the ways that BidUnity protects you is by not returning pricing for things that you can't purchase.

**Reviewing the Parts List**

We provided a way to double check that that part sizes are calculated correctly on this page. We don't view this page as being important to the estimating process, but we recognize the opportunity that it provides for reassuring estimators that everything has been correctly accounted. This is one area of the application where browsers other than Google Chrome are known to have problems. For the purposes of reviewing part sizes, you will probably find it to be more efficient to finalize the proposal and look at the cutting lists.

**Proposal Overhead Expenses**

Here you can add whatever you want to the proposal. We have organized commonly incurred overhead cost items for your review and selection. Hover over the table headings and field labels for specific instruction on the page.

**Finalizing the Proposal Behind the scenes**

After you've made selections and assigned overhead to the proposal you get to review cost budgets and assign a margin as appropriate. Several important things are happening in the background that help explain what you will find on this page.

First, at the top left of the page, you have options. You can either sell materials and labor, which is the default, or you can sell materials only. If you sell material only field labor charges are removed from the proposal's value.

**Sales, Discretionary, and Use Tax Calculation**

**Sales Taxes** are tricky to get perfect because every jurisdiction has different rates and rules. Sales tax rates vary according to each state, county, municipality, and even based on the character of the thing purchased. To make matters more difficult, these rates can change at any time.

Because we want to estimate costs as precisely as possible, we handle sales tax nearly perfectly based on Florida's sales tax laws. BidUnity calculates sales tax in the following way.

1. BidUnity uses the project's address to get the applicable sales tax rate from a tax server, so we start out with exactly the right information.
2. Sales taxes are transaction based. They will apply to each transaction that you have with each vendor independently of other transactions. BidUnity assumes, and we know this is not always true, that each material account represents a single transaction with only one vendor.
3. Based on each expense line item corresponding to a unique transaction, BidUnity calculates the sales taxes which would be due on that transaction.
4. The state sales tax rate is applied to the total value of the expense line item.
5. The same rules apply to shop labor.
6. Field Labor is exempt from sales tax.

If this results in any inaccuracy in your jurisdiction, please let us know by sending email to support@bidunity.com. In the mean time, you can probably compensate for the variance by adjusting your margin now that you understand what BidUnity is doing.

**Assigning Margin** is pretty straight forward as long as you understand how the company margin schedules operates.

**Sending Proposals The Public Proposal**

The public proposal is intended to include all of the information that you would need to gather and submit for projects you take them to contract. You selected the basis of your bid, added indirect expenses, and assigned margins. BidUnity derives complete proposals by relating your selections to what it already knows about the selected items.

We are going to be making some updates to the way that public proposals look. Take a look at an example proposal [here](https://bidunity.com/public/proposals/3c027290-3e5b-4cf5-aa81-0ed6b2e304ea/contract).

