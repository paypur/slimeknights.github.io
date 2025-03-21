---
layout: page
title: Fuel Recipes
description: Fuel recipes are used to define valid fluids in the melter, alloyer, smeltery, and foundry in Tinkers' Construct since 1.16.
---
{{page.description}}

The rate of fuel consumption varies based on the usage. For the melter and alloyer, 1 fuel "duration" is consumed every 4 ticks, or 1/5 of a second. For the smeltery and foundry, multiple "duration" may will be consumed based on the size of the structure, causing the fuel to not exactly map to seconds.

## Fuel

<div class="treeview" markdown=1>
* {% include field.html type="object" %} The recipe object.
    * {% include field.html name="type" type="resource location" %} Always `tconstruct:melting_fuel`.
    * {% include field.html name="fluid" type="fluid ingredient" %} Fluid ingredient matching the fuel. Amount determines how much fuel is consumed per operation.
    * {% include field.html name="duration" type="integer" %} Amount of "fuel units" produced per operation. The exact amount of units consumed is based on the structure size.
    * {% include field.html name="temperature" type="temperature" %} Fuel temperature value, used for gating [melting](../item-melting) and [alloying](../alloying) recipes. Additionally, before 1.20 acts as a multiplier on the rate items melt, with 1000 being the baseline.
    * {% include field.html name="rate" type="integer" version="since 1.20.1" %} How quickly items are heated up using this fuel. 10 is a typical baseline (visualized in JEI as 1.0x).
</div>

### Solid Fuel
<div class="hatnote">Since 1.20.1</div>

In the next 1.20 update, creating a fuel instance without setting `fluid` and `duration` will cause that temperature and rate to be used for solid fuel in the heater. Only a single recipe should be provided to set solid fuel properties, which is provided by Tinkers' Construct; modify that recipe if you wish to change it in a modpack.

## Temperature

Fuel temperature is often used as a gating mechanism for recipes. The following fuel temperatures are defined in the base mod:

* Soild fuel has a temperature of 800 degrees.
* Lava has a temperature of 1000 degrees.
* Blazing Blood has a temperature of 1500 degrees.