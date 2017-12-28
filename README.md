HarnMaster Roll20 Character Sheet
=================================

This is a charactersheet for the [HarnMaster](http://columbiagames.com/cgi-bin/query/cfg/zoom.cfg?product_id=4001) RPG for use in the [Roll20](https://roll20.net/) Virtual Tabletop service.


Creating Mooks
--------------

Mooks are NPCs used in the game may use the character sheet but mostly derive rolls from scripted abilities that reference some values off of the character sheet.  Mooks can be setup any number of ways in different campaigns.  I am detailing here a method I use that draws from some basic abilities on the character sheet, works with a value in the token bar to represent penalties, and uses abilities to roll outcomes.

### Setting up Tokens
To setup a token to represent a Mooks:
* Drag a token onto the play space.
* Make sure it is not marked as 'is drawing' by right clicking on token and checking under advaned.  (if it is you wont get the bars when you select it)
* Double Click the icon to bring up the 'edit token' window.
* Select the appropriate NPC character under 'Represents Character'
* Make sure appropriate Name is entered.
* Make sure you do NOT assign a bar to any trait (this keeps each token independent)
* Open the NPC character you want to assign the token to.
* With the appropriate token selected, click edit in the character window and assign it the selected token.

### Setting Up Abilities
Each ability should be setup different as needed for the particular Mook you're building.  Some abilities are common across most Mooks however, with DODGE, INITIATIVE and SHOCK being the most common.  Most abilities setup will need to have a the appropriate penalty from wounds or fatigue applied (encumberance is usually already included in NPC stats).  These are kept track of in Bar 3 of the token and can be setup to be included in the rolls as in the examples below.

*Note*: click the 'show as token action' to have these appear as button options when the token is selected on the mamp.

To work with base abilities, add the values to the character sheet.  I often add at STR, STA, WIL, Initiative ML, Dodge ML.  Weapons, special abilities and more I add as individual ability macros.

#### Example Abilities

##### Dodge
```
&{template:default} {{name=@{character_name} Dodges}} {{ML=[[@{COMBAT_DODGE} - [[@{selected|bar3}*5]]]]}} {{Roll=[[1d100cs5cs10cs15cs20cs25cs30cs35cs40cs45cs50cs55cs60cs65cs70cs75cs80cs85cs90cs95cs10]]}}
```

##### Shock
```
&{template:default} {{name=@{character_name} Shock Roll}} {{END=@{COMBAT_ENDURANCE}}} {{Roll=@{selected|bar3}d6
 = [[@{selected|bar3}d6]]}}
```

##### Bit Attack (one example of an attack)
```
&{template:default} {{name=@{character_name} Bites}} {{ML=[[52 - [[@{selected|bar3} * 5]]]]}} {{Roll=[[1d100cs5cs10cs15cs20cs25cs30cs35cs40cs45cs50cs55cs60cs65cs70cs75cs80cs85cs90cs95cs10]]}} {{Note=4P}}
```