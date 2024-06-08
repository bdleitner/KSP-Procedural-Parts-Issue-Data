# Issue Description

Prodecural Xenon Tank always has default capacity.

I've observed the following behavior with a procedural xenon tank. This persists even after removing the part from the craft and replacing it with a newly created one:

* In the VAB, the size of the tank is 1.25m diameter and 10m long. It has a capacity of 99664.6 units of Xenon
* The default size for the procedural xenon tank is 0.625m diameter and 0.3m long with a capacity of 747.5 units.  The math for these two capacities is consistent.
* When I launch, the tank shows full, but with a capacity of only "748". Going into the save file it has both `amount` and `maxAmount` equal to 747.5.
* If I revert to VAB, the tank is the same size but now has only 747.5 units out of the 99664.6 capacity.
* If I launch again from there, the tank shows as having 5.61 of the 747.5 (the same ratio as 747.5/99664.6)
* Most bizarrely, editing the save file to change the `amount` and `maxAmount` values doesn't work. When the I save the changes to a new file I can confirm the 99664.6 values are there,
but when I load the game it goes back to 747.5 and a new save has the 747.5 values. The 747.5 value is found nowhere else in the part (though it could be calculated from something else).

I'm not sure if this is caused by another mod interfering, or if there's a bug in the procedural xenon tank when computing capacity outside the VAB such that it always uses the default regardless of tank size.
