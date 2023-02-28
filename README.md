# PCB best practices
## rationale
in the interest of keeping everyones visual pattern matching algorithms firing on all cylenders as well as avoiding common or hard to diagnose pitfalls we have created these rules and best paractices. 

## schemetic
### libraries
Symbol and footprint libraries that ship with KiCad can be expected, all other libraries should be linked with relative paths to local libraries (use git submodules for reuse).
### part numbers
Sometimes a specific part is specified with a specific part number and sometimes a group of possible parts are specified with constraints (for example capacitors and rsistors).
#### specific part numbers
The 'value' field of the component should be used to express the most recognisable property of the component, 1k, 100uF, LM339 as examples. Use the field named ```MPN``` to specify the exact part, RMCP2010FT1K00, CL32A107MQVNNWE, LM339APWR for the above examples. It is also often a good idea to include a ```Digi-Key_PN``` field with the exact part numbers RMCP2010FT1K00CT-ND, 1276-3366-1-ND, 296-18454-1-ND.
#### catagory constraints
Passive components often do not need to be specified down to the exact part number, a resistor from stackpole is functionally equivalent to a resistor from vishay in many use cases and a 0.5% value can always be used where 1% is specified. Use the following field names to constrain the catagory of components which can be used. 
 - ```voltage``` voltage constraint on capacitors, if no voltage field is specified 6.3V or higher can be assumed
 - ```precision``` to constrain the precision of resistors to 0.1% or capacitors to 10% for example. If no value is specified assume 1% for resistors and 20% for capacitors
 - ```dielectric``` for dilectric class codes like X5R or C0G. if nothing is specified any class can be used.
 - ```power``` for power specification. Assume 100mW for resistors if not otherwise specified.
### unit naming conventions
Values ought to be represented as 1.7k or 2.2uF. Do not use other notations than these. Also use the following unit notations:
 - R Ohms
 - k kilo ohms
 - M megaohms
 - mF millifarad
 - uF microfarad
 - nF nannofarad
 - pF picofarad
 - H henry 
 - mH millihenry
 - uH microhenry
 - W watt
 - mW milliwatt
 - V volt
 - mV millivolt
 - uV microvolt
 - A amp
 - mA milliamp
 - uA microamp
 
 ## layout
 ### 3d models
 It is strongly recommended that all footprints have a 3d model associated with them. Relative paths must be used to reference 3d models.

