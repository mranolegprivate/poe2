# poe2 loot filter END GAME

#===============================================================================================================
# sajanXgame Loot Filter - for Path of Exile 2
#===============================================================================================================
# VERSION:  0.0.1
# TYPE:     1 - END GAME
# STYLE:    DEFAULT
# AUTHOR:   sajanXgame
#------------------------------------
# DISCORD: https://discord.gg/Dxj7BXz6dS
# TWITTER: @sajanXgame
# TWITCH:  https://www.twitch.tv/sajanXgame
# GITHUB:  sajanXgame

#===============================================================================================================
# [WELCOME] TABLE OF CONTENTS + QUICKJUMP TABLE
#===============================================================================================================
# [[0100]] OVERRIDE AREA 1 - Override ALL rules here
# [[0100]] Gold
# [[0200]] Exotic Bases
# [[0300]] Exotic Item States
# [[0400]] Chancing Bases and Economy Selected Bases
#   [0401] Crafting and Chancing Bases
# [[0500]] Endgame Flasks
# [[0600]] Endgame Charms
# [[0700]] Salvagables
# [[0800]] Normal and Magic Crafting bases
#   [0801] Hide Crafting Bases
#   [0802] Normal, Magic Crafting Decorators
#   [0803] Normal, Magic Crafting: Level 82+
#   [0804] Normal, Magic Crafting: Optional Rules
#   [0805] Normal, Magic Crafting: Endgame Progression
#   [0806] Normal, Magic Crafting: Rings+Amulets
#   [0807] Normal, Magic Crafting: Belts
#   [0808] Normal, Magic Crafting: Decorator Removers
# [[0900]] Hide Layer 1 - Normal and Magic Endgame Gear
# [[1000]] Rare Item Decorators
# [[1100]] Endgame - Conditional Hide Layers
# [[1200]] Endgame - Rare - Jewellery
# [[1300]] Endgame - Rare - Gear - Droplevel Hiding
# [[1400]] Endgame - Rare - Gear
# [[1500]] Untiered Rare Catcher
# [[1600]] Hide Layer 2 - Rare Gear
# [[1700]] Socketables - Runes and Soul Cores
# [[1800]] Jewels
# [[1900]] Relics
# [[2000]] Gems and Uncut Gems
# [[2100]] Waystones
# [[2200]] Normal Waystone Progression
#   [2201] Generic Decorators
#   [2202] Special Maps
#   [2203] Waystone progression
# [[2300]] Currency - Exceptions - Leveling Currencies
# [[2400]] Currency - Regular Currency Tiering
# [[2500]] Currency - SPECIAL
#   [2501] Distilled Emotions (Delirium)
#   [2502] Catalysts (breach)
#   [2503] Essences
#   [2504] Omen (ritual)
# [[2600]] Misc Map Like
# [[2700]] Splinters, Tablets, Fragments
# [[2800]] Misc Map Items
# [[2900]] Remaining Currency
# [[3000]] Uniques
#   [3001] Exceptions #1
#   [3002] Tier 1 and 2 uniques
#   [3003] Multi-Unique bases.
#   [3004] Low tier exceptions
#   [3005] Tier 3 uniques 
#   [3006] Tier 4 uniques
# [[3100]] Leveling - Salvagable
# [[3200]] Leveling - Hide outdated leveling flasks
# [[3300]] Leveling - Life Mana Flasks
#   [3301] Life flasks
#   [3302] Mana flasks
#   [3303] Charms
# [[3400]] Leveling - Rules
#   [3401] Rares - Decorators
#   [3402] Rares - Universal
#   [3403] Rares - Other
# [[3500]] Leveling - Useful magic and normal items
#   [3501] Decorators
#   [3502] Purpose Picked Items
#   [3503] Conditional Rules
#   [3504] Others
#   [3505] Hide All known Section
#   [3506] Show All unknown Section

#===============================================================================================================
# [[0100]] Gold
#===============================================================================================================
# !! Waypoint c0.start : "Start - Override ALL rules"

Show # $type->gold $tier->stack3
	StackSize >= 5000
	BaseType == "Gold"
	SetFontSize 40
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 20 20 0 255
	PlayEffect Orange
	MinimapIcon 1 Yellow Cross

Show # $type->gold $tier->stack2
	StackSize >= 2500
	BaseType == "Gold"
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	PlayEffect Orange Temp
	MinimapIcon 1 White Cross

Show # %H5 $type->gold $tier->stack1
	StackSize >= 500
	BaseType == "Gold"
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	PlayEffect Orange Temp

Show # %H5 $type->gold $tier->stack1lvl
	StackSize >= 250
	BaseType == "Gold"
	AreaLevel < 65
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	PlayEffect Orange Temp

Hide # %H3 $type->gold $tier->any
	BaseType == "Gold"
	SetTextColor 180 180 180
	SetBorderColor 0 0 0 255
	SetBackgroundColor 20 20 0 180

#===============================================================================================================
# [[0200]] Exotic Bases
#===============================================================================================================
# !! Waypoint c2.exotic.all : "Exotic Items - Breach Rings, Fishing Rods, Quest Items"
# These bases don't usually drop during normal gameplay and are usually only acquired form certain sources

# Currently contains mostly undroppable bases

Show # $type->exoticbases $tier->superexoticbases
	Rarity Normal Magic Rare
	BaseType == "Diamond" "Time-Lost Diamond"
	SetFontSize 42
	SetTextColor 0 240 190 255
	SetBorderColor 0 240 190 255
	SetBackgroundColor 0 75 30 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 0 Blue Diamond

# Currently contains breach rings

Show # %D6 $type->exoticbases $tier->commonexoticbaseshigh
	ItemLevel >= 82
	Rarity Normal Magic
	BaseType == "Breach Ring"
	SetFontSize 42
	SetTextColor 0 70 255 255
	SetBorderColor 0 70 255 255
	SetBackgroundColor 30 0 70 255
	PlayAlertSound 2 300
	PlayEffect Blue
	MinimapIcon 1 Blue Diamond

Show # %D4 $type->exoticbases $tier->commonexoticbases
	Rarity Normal Magic
	BaseType == "Breach Ring"
	SetFontSize 38
	SetTextColor 0 70 255 255
	SetBorderColor 0 70 255 255
	PlayEffect Blue Temp
	MinimapIcon 2 Blue Diamond

# Sanctum keys

Show # $type->questlikeexception $tier->questlike
	BaseType == "Bronze Key" "Gold Key" "Silver Key"
	SetFontSize 42
	SetTextColor 74 230 58 255
	PlayAlertSound 3 300
	PlayEffect Green
	MinimapIcon 0 Green Pentagon

Show # $type->questlikeexception $tier->questitems
	Class == "Quest Items"
	SetFontSize 42
	SetTextColor 74 230 58 255
	PlayAlertSound 3 300
	PlayEffect Green
	MinimapIcon 0 Green Pentagon

Show # $type->artifact $tier->fishingrod
	Rarity Normal Magic Rare
	Class == "Fishing Rods"
	SetFontSize 42
	SetTextColor 240 0 0 255
	SetBorderColor 240 0 0 255
	SetBackgroundColor 70 0 20 255
	PlayAlertSound 3 300
	PlayEffect Orange
	MinimapIcon 0 Orange Pentagon

#===============================================================================================================
# [[0300]] Exotic Item States
#===============================================================================================================
# !! Waypoint c3.exotic.state.all : "Exotic State - Double Corrupted, Overquality"

Show # $type->exotic->others $tier->overqualityany
	Corrupted False
	Quality >= 21
	Rarity Normal Magic Rare
	SetFontSize 42
	SetTextColor 0 240 190 255
	SetBorderColor 0 240 190 255
	SetBackgroundColor 0 75 30 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 0 Blue Diamond

#===============================================================================================================
# [[0400]] Chancing Bases and Economy Selected Bases
#===============================================================================================================
#------------------------------------
#   [0401] Crafting and Chancing Bases
#------------------------------------
# !! Waypoint c3.gear.chancing : "Chancing bases"

Show # $type->chancing $tier->any
	Mirrored False
	Corrupted False
	Rarity Normal
	BaseType == "Sapphire Ring" "Stellar Amulet"
	SetFontSize 40
	SetBorderColor 0 200 95
	PlayAlertSound 3 300
	PlayEffect Green Temp
	MinimapIcon 1 Green Diamond

#===============================================================================================================
# [[0500]] Endgame Flasks
#===============================================================================================================
# !! Waypoint c3.flasks.endgame : "Flasks (Endgame)"

Show # %D5 $type->endgame->flasks $tier->toplevelqualityflasks
	Mirrored False
	Corrupted False
	Quality > 10
	ItemLevel >= 83
	Rarity Normal Magic
	BaseType == "Ultimate Life Flask" "Ultimate Mana Flask"
	AreaLevel >= 65
	SetFontSize 40
	SetBorderColor 245 175 0
	SetBackgroundColor 10 60 40

Show # %D4 $type->endgame->flasks $tier->toplevelflasks
	Mirrored False
	Corrupted False
	ItemLevel >= 83
	Rarity Normal Magic
	BaseType == "Ultimate Life Flask" "Ultimate Mana Flask"
	AreaLevel >= 65
	SetFontSize 40
	SetBorderColor 245 175 0
	SetBackgroundColor 10 60 40

Show # %D4 $type->endgame->flasks $tier->anyhighqualflask
	Mirrored False
	Corrupted False
	Quality >= 15
	Rarity Normal Magic
	BaseType == "Ultimate Life Flask" "Ultimate Mana Flask"
	AreaLevel >= 65
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

#Show # %D2 $type->endgame->flasks $tier->anyqualflask
#	Mirrored False
#	Corrupted False
#	Quality >= 1
#	Rarity Normal Magic
#	BaseType == "Ultimate Life Flask" "Ultimate Mana Flask"
#	AreaLevel >= 65
#	SetFontSize 38
#	SetBorderColor 100 100 100
#	SetBackgroundColor 10 60 40

#Show # %D1 $type->endgame->flasks $tier->earlymappinglifemana
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 65
#	Rarity Normal Magic
#	BaseType == "Ultimate Life Flask" "Ultimate Mana Flask"
#	AreaLevel >= 65
#	AreaLevel <= 67
#	SetFontSize 38
#	SetBorderColor 100 100 100
#	SetBackgroundColor 10 60 40

#===============================================================================================================
# [[0600]] Endgame Charms
#===============================================================================================================
# !! Waypoint c3.charms.endgame : "Charms (Endgame)"

Show # %D6 $type->endgame->charms $tier->topqualitycharms
	Mirrored False
	Corrupted False
	Quality >= 18
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Charms"
	AreaLevel >= 65
	SetFontSize 42
	SetTextColor 0 240 190 255
	SetBorderColor 0 240 190 255
	SetBackgroundColor 0 75 30 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 0 Blue Diamond

Show # %D5 $type->endgame->charms $tier->hight1charms
	Mirrored False
	Corrupted False
	ItemLevel >= 83
	Rarity Normal Magic
	Class == "Charms"
	BaseType == "Amethyst Charm" "Antidote Charm" "Dousing Charm" "Golden Charm" "Grounding Charm" "Stone Charm" "Thawing Charm"
	AreaLevel >= 65
	SetFontSize 40
	SetBorderColor 245 175 0
	SetBackgroundColor 10 60 40

Show # %D4 $type->endgame->charms $tier->highothercharms
	Mirrored False
	Corrupted False
	ItemLevel >= 83
	Rarity Normal Magic
	Class == "Charms"
	BaseType == "Amethyst Charm" "Antidote Charm" "Dousing Charm" "Golden Charm" "Grounding Charm" "Ruby Charm" "Sapphire Charm" "Silver Charm" "Staunching Charm" "Stone Charm" "Thawing Charm" "Topaz Charm"
	AreaLevel >= 65
	SetFontSize 40
	SetBorderColor 245 175 0
	SetBackgroundColor 10 60 40

#Show # %D3 $type->endgame->charms $tier->qualitycharms
#	Mirrored False
#	Corrupted False
#	Quality > 0
#	Rarity Normal Magic
#	Class == "Charms"
#	AreaLevel >= 65
#	SetFontSize 40
#	SetBorderColor 100 100 100
#	SetBackgroundColor 10 60 40

Show # %D4 $type->endgame->charms $tier->earlymappingcharms
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Charms"
	BaseType == "Amethyst Charm" "Antidote Charm" "Dousing Charm" "Golden Charm" "Grounding Charm" "Stone Charm" "Thawing Charm"
	AreaLevel >= 65
	AreaLevel <= 70
	SetFontSize 38
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

#Show # %D2 $type->endgame->charms $tier->anycharm
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Charms"
#	AreaLevel >= 65
#	SetFontSize 38
#	SetBorderColor 100 100 100
#	SetBackgroundColor 10 60 40

#===============================================================================================================
# [[0700]] Salvagables
#===============================================================================================================
# !! Waypoint c4.gear.salvagable : "Salvagable bases (Endgame)"

# Double Quality Currencies

#Show # %D3 $type->endgame->salvagable $tier->quality2martialany
#	Quality >= 10
#	Rarity Normal Magic
#	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Two Hand Maces"
#	AreaLevel >= 65
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D3 $type->endgame->salvagable $tier->quality2casterany
#	Quality >= 10
#	Rarity Normal Magic
#	Class == "Sceptres" "Staves" "Wands"
#	AreaLevel >= 65
#	SetFontSize 38
#	SetBorderColor 180 180 180

Show # %D4 $type->endgame->salvagable $tier->quality2armorany
	Quality >= 10
	Rarity Normal Magic
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel >= 65
	SetFontSize 38
	SetBorderColor 180 180 180

# Single Quality Currencies

#Show # %D2 $type->endgame->salvagable $tier->qualitymartialany
#	Quality >= 1
#	Rarity Normal Magic
#	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Two Hand Maces"
#	AreaLevel >= 65
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D2 $type->endgame->salvagable $tier->qualitycasterany
#	Quality >= 1
#	Rarity Normal Magic
#	Class == "Sceptres" "Staves" "Wands"
#	AreaLevel >= 65
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D3 $type->endgame->salvagable $tier->qualityarmorany
#	Quality >= 1
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 35
#	SetBorderColor 127 127 127

# Artificer Scraps

#Show # %D1 $type->endgame->salvagable $tier->socketslarge
#	Sockets > 0
#	Height >= 3
#	Rarity Normal Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D2 $type->endgame->salvagable $tier->socketssmall
#	Sockets > 0
#	Height < 3
#	Rarity Normal Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	SetFontSize 35
#	SetBorderColor 127 127 127

#===============================================================================================================
# [[0800]] Normal and Magic Crafting bases
#===============================================================================================================

#------------------------------------
#   [0801] Hide Crafting Bases
#------------------------------------

#Hide # $type->endgame->conditionalhiders->crafting $tier->hideweaponsbytype
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->crafting $tier->arhider
#	Mirrored False
#	Corrupted False
#	BaseEnergyShield 0
#	BaseEvasion 0
#	BaseArmour > 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->crafting $tier->evhider
#	Mirrored False
#	Corrupted False
#	BaseEnergyShield 0
#	BaseEvasion > 0
#	BaseArmour 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->crafting $tier->eshider
#	Mirrored False
#	Corrupted False
#	BaseEnergyShield > 0
#	BaseEvasion 0
#	BaseArmour 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->crafting $tier->arevhider
#	Mirrored False
#	Corrupted False
#	BaseEnergyShield 0
#	BaseEvasion > 0
#	BaseArmour > 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->crafting $tier->areshider
#	Mirrored False
#	Corrupted False
#	BaseEnergyShield > 0
#	BaseEvasion 0
#	BaseArmour > 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->crafting $tier->eveshider
#	Mirrored False
#	Corrupted False
#	BaseEnergyShield > 0
#	BaseEvasion > 0
#	BaseArmour 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	AreaLevel >= 65
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#------------------------------------
#   [0802] Normal, Magic Crafting Decorators
#------------------------------------
# !! Waypoint c4.gear.crafting.decorators : "Crafting Decorators - Visual override for crafting items"

Show # $type->endgame->normalcraft->decorator $tier->regulargeardecorator
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetBorderColor 0 0 0 255
	SetBackgroundColor 20 20 0 230
	Continue

#Show # $type->endgame->normalcraft->decorator $tier->normal80
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 80
#	Rarity Normal Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	Continue

Show # $type->endgame->normalcraft->decorator $tier->normal82
	Mirrored False
	Corrupted False
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetBorderColor 122 87 0
	Continue

Show # $type->endgame->normalcraft->decorator $tier->qualitydecorator1
	Mirrored False
	Corrupted False
	Quality >= 10
	Rarity Normal Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetFontSize 38
	SetBorderColor 180 180 180
	Continue

Show # $type->endgame->normalcraft->decorator $tier->qualitydecorator2
	Mirrored False
	Corrupted False
	Quality >= 1
	Rarity Normal Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetFontSize 35
	SetBorderColor 127 127 127
	Continue

Show # $type->endgame->normalcraft->decorator $tier->normaldecoratorjwlry
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Amulets" "Rings"
	AreaLevel >= 65
	Continue

#------------------------------------
#   [0803] Normal, Magic Crafting: Level 82+
#------------------------------------
# !! Waypoint c4.gear.crafting.all : "Crafting Bases - Handpicked Magic and Normal Bases"

# Best itemlevel bases (82)

Show # %D4 $type->endgame->normalcraft->any $tier->t1ideallevel
	Mirrored False
	Corrupted False
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Attuned Wand" "Chiming Staff" "Expert Altar Robe" "Expert Barrier Quarterstaff" "Expert Bombard Crossbow" "Expert Brigand Mace" "Expert Cloaked Mail" "Expert Doubled Gauntlets" "Expert Dualstring Bow" "Expert Edged Buckler" "Expert Elite Greathelm" "Expert Feathered Sandals" "Expert Feathered Targe" "Expert Feathered Tiara" "Expert Forlorn Crossbow" "Expert Goldcast Cuffs" "Expert Heavy Crown" "Expert Hexer's Robe" "Expert Hunter Hood" "Expert Hunting Shoes" "Expert Intricate Gloves" "Expert Iron Cuirass" "Expert Keth Raiment" "Expert Leaden Greathammer" "Expert Lizardscale Boots" "Expert Moulded Mitts" "Expert Omen Crest Shield" "Expert Pathfinder Coat" "Expert Pelt Leggings" "Expert Pelt Mantle" "Expert Plumed Focus" "Expert Rogue Armour" "Expert Sacrificial Mantle" "Expert Scale Mail" "Expert Scalper's Jacket" "Expert Serpentscale Coat" "Expert Shaman Mantle" "Expert Shielded Helm" "Expert Slicing Quarterstaff" "Expert Spined Bracers" "Expert Spiral Wraps" "Expert Stacked Sabatons" "Expert Steel Plate" "Expert Stone Greaves" "Expert Stone Tower Shield" "Expert Studded Vest" "Expert Tribal Mask" "Expert Vaal Cuirass" "Expert Waxed Jacket" "Expert Wayfarer Jacket" "Omen Sceptre" "Primed Quiver" "Rattling Sceptre" "Siphoning Wand" "Voltaic Staff"

#Show # %D2 $type->endgame->normalcraft->any $tier->t2ideallevel
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 82
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Altar Robe" "Advanced Sacrificial Mantle" "Advanced Scale Mail" "Advanced Scalper's Jacket" "Advanced Serpentscale Coat" "Advanced Vaal Cuirass" "Expert Aged Cuffs" "Expert Antler Focus" "Expert Bolstered Mitts" "Expert Braced Sabatons" "Expert Braced Tower Shield" "Expert Chain Tiara" "Expert Construct Hammer" "Expert Cowled Helm" "Expert Crescent Quarterstaff" "Expert Crescent Targe" "Expert Crystal Focus" "Expert Cultist Greathammer" "Expert Dyad Crossbow" "Expert Face Mask" "Expert Felt Cap" "Expert Firm Bracers" "Expert Frayed Shoes" "Expert Gauze Wraps" "Expert Guarded Helm" "Expert Horned Crown" "Expert Iron Greaves" "Expert Jewelled Gloves" "Expert Jingling Crest Shield" "Expert Laced Boots" "Expert Layered Gauntlets" "Expert Linen Wraps" "Expert Long Quarterstaff" "Expert Mail Sabatons" "Expert Martyr Crown" "Expert Oak Greathammer" "Expert Padded Leggings" "Expert Pelage Targe" "Expert Plated Buckler" "Expert Rampart Tower Shield" "Expert Ringmail Gauntlets" "Expert Riveted Mitts" "Expert Rope Cuffs" "Expert Sectioned Bracers" "Expert Secured Leggings" "Expert Sigil Crest Shield" "Expert Silk Slippers" "Expert Soldier Greathelm" "Expert Sombre Gloves" "Expert Spiked Buckler" "Expert Spired Greathelm" "Expert Steeltoe Boots" "Expert Swathed Cap" "Expert Tense Crossbow" "Expert Threaded Shoes" "Expert Trimmed Greaves" "Expert Veiled Mask" "Expert Warden Bow" "Expert Warpick" "Expert Wicker Tiara" "Expert Wrapped Sandals" "Expert Zealot Bow" "Gelid Staff" "Penetrating Quiver" "Pyrophyte Staff" "Stoic Sceptre" "Visceral Quiver" "Volant Quiver" "Volatile Wand" "Withered Wand"

#Show # $type->endgame->normalcraft->any $tier->t3ideallevel
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 82
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Aged Cuffs" "Advanced Anchorite Garb" "Advanced Barrier Quarterstaff" "Advanced Bolstered Mitts" "Advanced Bombard Crossbow" "Advanced Braced Sabatons" "Advanced Chain Tiara" "Advanced Doubled Gauntlets" "Advanced Dualstring Bow" "Advanced Edged Buckler" "Advanced Elite Greathelm" "Advanced Explorer Armour" "Advanced Feathered Sandals" "Advanced Feathered Targe" "Advanced Feathered Tiara" "Advanced Full Plate" "Advanced Goldcast Cuffs" "Advanced Heavy Crown" "Advanced Heraldric Tower Shield" "Advanced Hunter Hood" "Advanced Hunting Shoes" "Advanced Intricate Gloves" "Advanced Ironclad Vestments" "Advanced Jewelled Gloves" "Advanced Layered Gauntlets" "Advanced Linen Wraps" "Advanced Lizardscale Boots" "Advanced Moulded Mitts" "Advanced Omen Crest Shield" "Advanced Pelt Leggings" "Advanced Plumed Focus" "Advanced Ringed Buckler" "Advanced Scout's Vest" "Advanced Sectioned Bracers" "Advanced Secured Leggings" "Advanced Shielded Helm" "Advanced Silk Slippers" "Advanced Spined Bracers" "Advanced Spiral Wraps" "Advanced Spired Greathelm" "Advanced Stacked Sabatons" "Advanced Steeltoe Boots" "Advanced Stone Greaves" "Advanced Stone Tower Shield" "Advanced Swathed Cap" "Advanced Threaded Shoes" "Advanced Tribal Mask" "Advanced Trimmed Greaves" "Advanced Voodoo Focus" "Advanced Votive Raiment" "Ashen Staff" "Bone Wand" "Expert Composite Bow" "Expert Crackling Quarterstaff" "Expert Crumbling Maul" "Expert Cultist Bow" "Expert Forge Maul" "Expert Gothic Quarterstaff" "Expert Plated Mace" "Expert Shortbow" "Expert Slim Mace" "Expert Smithing Hammer" "Expert Sturdy Crossbow" "Expert Temple Maul" "Expert Varnished Crossbow" "Shrine Sceptre" "Toxic Quiver" "Two-Point Quiver"

#------------------------------------
#   [0804] Normal, Magic Crafting: Optional Rules
#------------------------------------
# Matrix pauses: Optional: highlight +5minion bases for sumonners (81)

#Show # $type->endgame->normalcraft->any $tier->minionsceptresoptional
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 81
#	Rarity Normal Magic
#	Class == "Sceptres"
#	SetBorderColor 122 87 0

Show # %D4 $type->endgame->normalcraft->any $tier->craftingwands
	Mirrored False
	Corrupted False
	ItemLevel >= 81
	Rarity Normal Magic
	BaseType == "Attuned Wand" "Siphoning Wand"
	SetBorderColor 122 87 0

#------------------------------------
#   [0805] Normal, Magic Crafting: Endgame Progression
#------------------------------------
# Matrix proceeds here. Best available bases

Show # %D4 $type->endgame->normalcraft->any $tier->t1
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Attuned Wand" "Chiming Staff" "Expert Altar Robe" "Expert Barrier Quarterstaff" "Expert Bombard Crossbow" "Expert Brigand Mace" "Expert Cloaked Mail" "Expert Doubled Gauntlets" "Expert Dualstring Bow" "Expert Edged Buckler" "Expert Elite Greathelm" "Expert Feathered Sandals" "Expert Feathered Targe" "Expert Feathered Tiara" "Expert Forlorn Crossbow" "Expert Goldcast Cuffs" "Expert Heavy Crown" "Expert Hexer's Robe" "Expert Hunter Hood" "Expert Hunting Shoes" "Expert Intricate Gloves" "Expert Iron Cuirass" "Expert Keth Raiment" "Expert Leaden Greathammer" "Expert Lizardscale Boots" "Expert Moulded Mitts" "Expert Omen Crest Shield" "Expert Pathfinder Coat" "Expert Pelt Leggings" "Expert Pelt Mantle" "Expert Plumed Focus" "Expert Rogue Armour" "Expert Sacrificial Mantle" "Expert Scale Mail" "Expert Scalper's Jacket" "Expert Serpentscale Coat" "Expert Shaman Mantle" "Expert Shielded Helm" "Expert Slicing Quarterstaff" "Expert Spined Bracers" "Expert Spiral Wraps" "Expert Stacked Sabatons" "Expert Steel Plate" "Expert Stone Greaves" "Expert Stone Tower Shield" "Expert Studded Vest" "Expert Tribal Mask" "Expert Vaal Cuirass" "Expert Waxed Jacket" "Expert Wayfarer Jacket" "Omen Sceptre" "Primed Quiver" "Rattling Sceptre" "Siphoning Wand" "Voltaic Staff"
	AreaLevel >= 65

#Show # %D3 $type->endgame->normalcraft->any $tier->t2onlevel
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Altar Robe" "Advanced Sacrificial Mantle" "Advanced Scale Mail" "Advanced Scalper's Jacket" "Advanced Serpentscale Coat" "Advanced Vaal Cuirass" "Expert Aged Cuffs" "Expert Antler Focus" "Expert Bolstered Mitts" "Expert Braced Sabatons" "Expert Braced Tower Shield" "Expert Chain Tiara" "Expert Construct Hammer" "Expert Cowled Helm" "Expert Crescent Quarterstaff" "Expert Crescent Targe" "Expert Crystal Focus" "Expert Cultist Greathammer" "Expert Dyad Crossbow" "Expert Face Mask" "Expert Felt Cap" "Expert Firm Bracers" "Expert Frayed Shoes" "Expert Gauze Wraps" "Expert Guarded Helm" "Expert Horned Crown" "Expert Iron Greaves" "Expert Jewelled Gloves" "Expert Jingling Crest Shield" "Expert Laced Boots" "Expert Layered Gauntlets" "Expert Linen Wraps" "Expert Long Quarterstaff" "Expert Mail Sabatons" "Expert Martyr Crown" "Expert Oak Greathammer" "Expert Padded Leggings" "Expert Pelage Targe" "Expert Plated Buckler" "Expert Rampart Tower Shield" "Expert Ringmail Gauntlets" "Expert Riveted Mitts" "Expert Rope Cuffs" "Expert Sectioned Bracers" "Expert Secured Leggings" "Expert Sigil Crest Shield" "Expert Silk Slippers" "Expert Soldier Greathelm" "Expert Sombre Gloves" "Expert Spiked Buckler" "Expert Spired Greathelm" "Expert Steeltoe Boots" "Expert Swathed Cap" "Expert Tense Crossbow" "Expert Threaded Shoes" "Expert Trimmed Greaves" "Expert Veiled Mask" "Expert Warden Bow" "Expert Warpick" "Expert Wicker Tiara" "Expert Wrapped Sandals" "Expert Zealot Bow" "Gelid Staff" "Penetrating Quiver" "Pyrophyte Staff" "Stoic Sceptre" "Visceral Quiver" "Volant Quiver" "Volatile Wand" "Withered Wand"
#	AreaLevel >= 65
#	AreaLevel <= 75

#Show # %D2 $type->endgame->normalcraft->any $tier->t3onlevel
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Aged Cuffs" "Advanced Anchorite Garb" "Advanced Barrier Quarterstaff" "Advanced Bolstered Mitts" "Advanced Bombard Crossbow" "Advanced Braced Sabatons" "Advanced Chain Tiara" "Advanced Doubled Gauntlets" "Advanced Dualstring Bow" "Advanced Edged Buckler" "Advanced Elite Greathelm" "Advanced Explorer Armour" "Advanced Feathered Sandals" "Advanced Feathered Targe" "Advanced Feathered Tiara" "Advanced Full Plate" "Advanced Goldcast Cuffs" "Advanced Heavy Crown" "Advanced Heraldric Tower Shield" "Advanced Hunter Hood" "Advanced Hunting Shoes" "Advanced Intricate Gloves" "Advanced Ironclad Vestments" "Advanced Jewelled Gloves" "Advanced Layered Gauntlets" "Advanced Linen Wraps" "Advanced Lizardscale Boots" "Advanced Moulded Mitts" "Advanced Omen Crest Shield" "Advanced Pelt Leggings" "Advanced Plumed Focus" "Advanced Ringed Buckler" "Advanced Scout's Vest" "Advanced Sectioned Bracers" "Advanced Secured Leggings" "Advanced Shielded Helm" "Advanced Silk Slippers" "Advanced Spined Bracers" "Advanced Spiral Wraps" "Advanced Spired Greathelm" "Advanced Stacked Sabatons" "Advanced Steeltoe Boots" "Advanced Stone Greaves" "Advanced Stone Tower Shield" "Advanced Swathed Cap" "Advanced Threaded Shoes" "Advanced Tribal Mask" "Advanced Trimmed Greaves" "Advanced Voodoo Focus" "Advanced Votive Raiment" "Ashen Staff" "Bone Wand" "Expert Composite Bow" "Expert Crackling Quarterstaff" "Expert Crumbling Maul" "Expert Cultist Bow" "Expert Forge Maul" "Expert Gothic Quarterstaff" "Expert Plated Mace" "Expert Shortbow" "Expert Slim Mace" "Expert Smithing Hammer" "Expert Sturdy Crossbow" "Expert Temple Maul" "Expert Varnished Crossbow" "Shrine Sceptre" "Toxic Quiver" "Two-Point Quiver"
#	AreaLevel >= 65
#	AreaLevel <= 70

#------------------------------------
#   [0806] Normal, Magic Crafting: Rings+Amulets
#------------------------------------
# !! Waypoint c4.gear.jewellery : "Jewellery - Endgame Magic&Normal"

Show # %D6 $type->endgame->jewellery $tier->ringamut1ideallevel
	Mirrored False
	Corrupted False
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Amulets" "Rings"
	BaseType == "Amethyst Ring" "Breach Ring" "Prismatic Ring" "Solar Amulet"
	AreaLevel >= 65
	SetFontSize 42
	SetBackgroundColor 30 0 70 255

Show # %D5 $type->endgame->jewellery $tier->ringamut2ideallevel
	Mirrored False
	Corrupted False
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Amulets" "Rings"
	BaseType == "Amber Amulet" "Azure Amulet" "Bloodstone Amulet" "Gold Amulet" "Gold Ring" "Jade Amulet" "Lapis Amulet" "Lazuli Ring" "Lunar Amulet" "Pearl Ring" "Ruby Ring" "Sapphire Ring" "Stellar Amulet" "Topaz Ring" "Unset Ring"
	AreaLevel >= 65
	SetFontSize 42
	SetBackgroundColor 30 0 70 255

#Show # %D3 $type->endgame->jewellery $tier->ringamut3ideallevel
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 82
#	Rarity Normal Magic
#	Class == "Amulets" "Rings"
#	BaseType == "Crimson Amulet" "Emerald Ring" "Iron Ring"
#	AreaLevel >= 65
#	SetFontSize 40

Show # %D5 $type->endgame->jewellery $tier->ringamut1
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Amulets" "Rings"
	BaseType == "Amethyst Ring" "Breach Ring" "Prismatic Ring" "Solar Amulet"
	AreaLevel >= 65
	SetFontSize 40
	SetBackgroundColor 30 0 70 255

Show # %D5 $type->endgame->jewellery $tier->ringamut2
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Amulets" "Rings"
	BaseType == "Amber Amulet" "Azure Amulet" "Bloodstone Amulet" "Gold Amulet" "Gold Ring" "Jade Amulet" "Lapis Amulet" "Lazuli Ring" "Lunar Amulet" "Pearl Ring" "Ruby Ring" "Sapphire Ring" "Stellar Amulet" "Topaz Ring" "Unset Ring"
	AreaLevel >= 65
	SetFontSize 40
	SetBackgroundColor 30 0 70 255

#Show # %D3 $type->endgame->jewellery $tier->ringamut3
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Amulets" "Rings"
#	BaseType == "Crimson Amulet" "Emerald Ring" "Iron Ring"
#	AreaLevel >= 65
#	SetFontSize 38

#------------------------------------
#   [0807] Normal, Magic Crafting: Belts
#------------------------------------

Show # %D5 $type->endgame->jewellery $tier->beltst1ideallevel
	Mirrored False
	Corrupted False
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Belts"
	BaseType == "Plate Belt" "Utility Belt"
	AreaLevel >= 65
	SetFontSize 40
	SetBackgroundColor 30 0 70 255

Show # %D5 $type->endgame->jewellery $tier->beltst2ideallevel
	Mirrored False
	Corrupted False
	ItemLevel >= 82
	Rarity Normal Magic
	Class == "Belts"
	BaseType == "Double Belt" "Fine Belt" "Linen Belt" "Long Belt" "Mail Belt" "Ornate Belt" "Rawhide Belt" "Wide Belt"
	AreaLevel >= 65
	SetFontSize 40

#Show # %D4 $type->endgame->jewellery $tier->beltst3ideallevel
#	Mirrored False
#	Corrupted False
#	ItemLevel >= 82
#	Rarity Normal Magic
#	Class == "Belts"
#	AreaLevel >= 65
#	SetFontSize 38

Show # %D4 $type->endgame->jewellery $tier->beltst1
	Mirrored False
	Corrupted False
	Rarity Normal Magic
	Class == "Belts"
	BaseType == "Plate Belt" "Utility Belt"
	AreaLevel >= 65
	SetFontSize 40
	SetBackgroundColor 30 0 70 255

#Show # %D3 $type->endgame->jewellery $tier->beltst2
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Belts"
#	BaseType == "Double Belt" "Fine Belt" "Linen Belt" "Long Belt" "Mail Belt" "Ornate Belt" "Rawhide Belt" "Wide Belt"
#	AreaLevel >= 65
#	SetFontSize 38

#Show # %D2 $type->endgame->jewellery $tier->beltst3
#	Mirrored False
#	Corrupted False
#	Rarity Normal Magic
#	Class == "Belts"
#	AreaLevel >= 65
#	SetFontSize 38

#------------------------------------
#   [0808] Normal, Magic Crafting: Decorator Removers
#------------------------------------

Show # $type->endgame->normalcraft->decorator $tier->magicdecoratorremover
	Mirrored False
	Corrupted False
	Rarity Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetFontSize 32
	SetTextColor 136 136 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 20 20 0 240
	Continue

Show # $type->endgame->normalcraft->decorator $tier->normaldecoratorremover
	Mirrored False
	Corrupted False
	Rarity Normal
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetFontSize 32
	SetTextColor 200 200 200
	SetBorderColor 0 0 0 255
	SetBackgroundColor 20 20 0 240
	Continue

#===============================================================================================================
# [[0900]] Hide Layer 1 - Normal and Magic Endgame Gear
#===============================================================================================================
# !! Waypoint c5.hidelayer.normalmagic : "HIDELAYER - All other endgame equipment normal&magic items"

#Show # %D0 $type->lowstrictnessshowlayer $tier->normalmagicendgameany
#	Rarity Normal Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Charms" "Crossbows" "Foci" "Gloves" "Helmets" "Life Flasks" "Mana Flasks" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	SetFontSize 26
#	SetBorderColor 0 0 0 0
#	SetBackgroundColor 20 20 0 140
#	DisableDropSound True

Hide # $type->hidelayer $tier->normalmagicendgame
	Rarity Normal Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Charms" "Crossbows" "Foci" "Gloves" "Helmets" "Life Flasks" "Mana Flasks" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

#===============================================================================================================
# [[1000]] Rare Item Decorators
#===============================================================================================================
# !! Waypoint c6.rare.decorator.all : "Rare Endgame Items - Decorators"

Show # $type->decorators->rareeg $tier->basicraredecorator
	Rarity Rare
	AreaLevel >= 65
	SetBorderColor 0 0 0 255
	Continue

#Show # $type->decorators->rareeg $tier->largerares
#	Width >= 2
#	Height >= 3
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	Continue

#Show # $type->decorators->rareeg $tier->mediumrares1
#	Width 1
#	Height >= 3
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	Continue

#Show # $type->decorators->rareeg $tier->mediumrares2
#	Width 2
#	Height 2
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	Continue

Show # $type->decorators->rareeg $tier->tinyrares
	Width <= 2
	Height 1
	Rarity Rare
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetBorderColor 220 220 0
	Continue

#Show # $type->decorators->rareeg $tier->ilvl80
#	ItemLevel >= 80
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	Continue

Show # $type->decorators->rareeg $tier->ilvl82
	ItemLevel >= 82
	Rarity Rare
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetTextColor 245 175 0
	Continue

# Optional: caster weapons get their most important mods on 81

#Show # %D0 $type->decorators->rareeg $tier->ilvl81caster
#	ItemLevel >= 81
#	Rarity Rare
#	Class == "Sceptres" "Staves" "Wands"
#	AreaLevel >= 65
#	SetTextColor 245 175 0
#	Continue

Show # $type->decorators->rareeg $tier->corruptedrares
	AnyEnchantment False
	Corrupted True
	Rarity Rare
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetBorderColor 120 0 0 240
	Continue

Show # $type->decorators->rareeg $tier->corruptedraresimplicit
	AnyEnchantment True
	Corrupted True
	Rarity Rare
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetBorderColor 250 0 0 255
	Continue

#===============================================================================================================
# [[1100]] Endgame - Conditional Hide Layers
#===============================================================================================================
# !! Waypoint c6.rare.optionalhide : "Rare Endgame Items - (Optional) Hiding Corrupted and Mirrored Items"

#Hide # $type->conditionalhide $tier->idhider
#	Identified True
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->conditionalhide $tier->corruptedrares
#	AnyEnchantment False
#	Corrupted True
#	Identified False
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#===============================================================================================================
# [[1200]] Endgame - Rare - Jewellery
#===============================================================================================================
# !! Waypoint c6.rare.jewellery.all : "Rare Endgame Items - Amulets, Rings"

Show # %D6 $type->rr->amuringeg $tier->t1
	ItemLevel >= 82
	Rarity Rare
	Class == "Amulets" "Rings"
	BaseType == "Amethyst Ring" "Breach Ring" "Prismatic Ring" "Solar Amulet"
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D6 $type->rr->amuringeg $tier->t2
	ItemLevel >= 82
	Rarity Rare
	Class == "Amulets" "Rings"
	BaseType == "Amber Amulet" "Azure Amulet" "Bloodstone Amulet" "Gold Amulet" "Gold Ring" "Jade Amulet" "Lapis Amulet" "Lazuli Ring" "Lunar Amulet" "Pearl Ring" "Ruby Ring" "Sapphire Ring" "Stellar Amulet" "Topaz Ring" "Unset Ring"
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D4 $type->rr->amuringeg $tier->t3
	ItemLevel >= 82
	Rarity Rare
	Class == "Amulets" "Rings"
	BaseType == "Crimson Amulet" "Emerald Ring" "Iron Ring"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D6 $type->rr->amuring $tier->t1
	ItemLevel >= 65
	Rarity Rare
	Class == "Amulets" "Rings"
	BaseType == "Amethyst Ring" "Breach Ring" "Prismatic Ring" "Solar Amulet"
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D5 $type->rr->amuring $tier->t2
	ItemLevel >= 65
	Rarity Rare
	Class == "Amulets" "Rings"
	BaseType == "Amber Amulet" "Azure Amulet" "Bloodstone Amulet" "Gold Amulet" "Gold Ring" "Jade Amulet" "Lapis Amulet" "Lazuli Ring" "Lunar Amulet" "Pearl Ring" "Ruby Ring" "Sapphire Ring" "Stellar Amulet" "Topaz Ring" "Unset Ring"
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D4 $type->rr->amuring $tier->t3
	ItemLevel >= 65
	Rarity Rare
	Class == "Amulets" "Rings"
	BaseType == "Crimson Amulet" "Emerald Ring" "Iron Ring"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

# !! Waypoint c6.rare.belts.all : "Rare Endgame Items - Belts"

Show # %D6 $type->rr->beltseg $tier->t1
	ItemLevel >= 82
	Rarity Rare
	Class == "Belts"
	BaseType == "Plate Belt" "Utility Belt"
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D5 $type->rr->beltseg $tier->t2
	ItemLevel >= 82
	Rarity Rare
	Class == "Belts"
	BaseType == "Double Belt" "Fine Belt" "Linen Belt" "Long Belt" "Mail Belt" "Ornate Belt" "Rawhide Belt" "Wide Belt"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

#Show # %D4 $type->rr->beltseg $tier->t3
#	ItemLevel >= 82
#	Rarity Rare
#	Class == "Belts"
#	SetFontSize 38
#	SetBackgroundColor 20 20 0 255

Show # %D5 $type->rr->belts $tier->t1
	ItemLevel >= 65
	Rarity Rare
	Class == "Belts"
	BaseType == "Plate Belt" "Utility Belt"
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

Show # %D4 $type->rr->belts $tier->t2
	ItemLevel >= 65
	Rarity Rare
	Class == "Belts"
	BaseType == "Double Belt" "Fine Belt" "Linen Belt" "Long Belt" "Mail Belt" "Ornate Belt" "Rawhide Belt" "Wide Belt"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

#Show # %D4 $type->rr->belts $tier->t3
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Belts"
#	SetFontSize 38
#	SetBackgroundColor 20 20 0 255

#===============================================================================================================
# [[1300]] Endgame - Rare - Gear - Droplevel Hiding
#===============================================================================================================
# !! Waypoint c6.rare.drophiders : "Rare Endgame Items - Hide low items on high levels"

#Hide # $type->endgame->conditionalhiders->rare $tier->hideweaponsbytype
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->rare $tier->arhider
#	ItemLevel >= 65
#	BaseEnergyShield 0
#	BaseEvasion 0
#	BaseArmour > 0
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->rare $tier->evhider
#	ItemLevel >= 65
#	BaseEnergyShield 0
#	BaseEvasion > 0
#	BaseArmour 0
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->rare $tier->eshider
#	ItemLevel >= 65
#	BaseEnergyShield > 0
#	BaseEvasion 0
#	BaseArmour 0
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->rare $tier->arevhider
#	ItemLevel >= 65
#	BaseEnergyShield 0
#	BaseEvasion > 0
#	BaseArmour > 0
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->rare $tier->areshider
#	ItemLevel >= 65
#	BaseEnergyShield > 0
#	BaseEvasion 0
#	BaseArmour > 0
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->endgame->conditionalhiders->rare $tier->eveshider
#	ItemLevel >= 65
#	BaseEnergyShield > 0
#	BaseEvasion > 0
#	BaseArmour 0
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#===============================================================================================================
# [[1400]] Endgame - Rare - Gear
#===============================================================================================================
# !! Waypoint c6.rare.t1.all : "Rare Endgame Items - T1 (75ish+ gear)

# T1 rares

Show # %D5 $type->rr $tier->t1_top
	ItemLevel >= 82
	Rarity Rare
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Attuned Wand" "Chiming Staff" "Expert Altar Robe" "Expert Barrier Quarterstaff" "Expert Bombard Crossbow" "Expert Brigand Mace" "Expert Cloaked Mail" "Expert Doubled Gauntlets" "Expert Dualstring Bow" "Expert Edged Buckler" "Expert Elite Greathelm" "Expert Feathered Sandals" "Expert Feathered Targe" "Expert Feathered Tiara" "Expert Forlorn Crossbow" "Expert Goldcast Cuffs" "Expert Heavy Crown" "Expert Hexer's Robe" "Expert Hunter Hood" "Expert Hunting Shoes" "Expert Intricate Gloves" "Expert Iron Cuirass" "Expert Keth Raiment" "Expert Leaden Greathammer" "Expert Lizardscale Boots" "Expert Moulded Mitts" "Expert Omen Crest Shield" "Expert Pathfinder Coat" "Expert Pelt Leggings" "Expert Pelt Mantle" "Expert Plumed Focus" "Expert Rogue Armour" "Expert Sacrificial Mantle" "Expert Scale Mail" "Expert Scalper's Jacket" "Expert Serpentscale Coat" "Expert Shaman Mantle" "Expert Shielded Helm" "Expert Slicing Quarterstaff" "Expert Spined Bracers" "Expert Spiral Wraps" "Expert Stacked Sabatons" "Expert Steel Plate" "Expert Stone Greaves" "Expert Stone Tower Shield" "Expert Studded Vest" "Expert Tribal Mask" "Expert Vaal Cuirass" "Expert Waxed Jacket" "Expert Wayfarer Jacket" "Omen Sceptre" "Primed Quiver" "Rattling Sceptre" "Siphoning Wand" "Voltaic Staff"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->rr $tier->t1_other
	ItemLevel >= 65
	ItemLevel <= 81
	Rarity Rare
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Attuned Wand" "Chiming Staff" "Expert Altar Robe" "Expert Barrier Quarterstaff" "Expert Bombard Crossbow" "Expert Brigand Mace" "Expert Cloaked Mail" "Expert Doubled Gauntlets" "Expert Dualstring Bow" "Expert Edged Buckler" "Expert Elite Greathelm" "Expert Feathered Sandals" "Expert Feathered Targe" "Expert Feathered Tiara" "Expert Forlorn Crossbow" "Expert Goldcast Cuffs" "Expert Heavy Crown" "Expert Hexer's Robe" "Expert Hunter Hood" "Expert Hunting Shoes" "Expert Intricate Gloves" "Expert Iron Cuirass" "Expert Keth Raiment" "Expert Leaden Greathammer" "Expert Lizardscale Boots" "Expert Moulded Mitts" "Expert Omen Crest Shield" "Expert Pathfinder Coat" "Expert Pelt Leggings" "Expert Pelt Mantle" "Expert Plumed Focus" "Expert Rogue Armour" "Expert Sacrificial Mantle" "Expert Scale Mail" "Expert Scalper's Jacket" "Expert Serpentscale Coat" "Expert Shaman Mantle" "Expert Shielded Helm" "Expert Slicing Quarterstaff" "Expert Spined Bracers" "Expert Spiral Wraps" "Expert Stacked Sabatons" "Expert Steel Plate" "Expert Stone Greaves" "Expert Stone Tower Shield" "Expert Studded Vest" "Expert Tribal Mask" "Expert Vaal Cuirass" "Expert Waxed Jacket" "Expert Wayfarer Jacket" "Omen Sceptre" "Primed Quiver" "Rattling Sceptre" "Siphoning Wand" "Voltaic Staff"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

# !! Waypoint c6.rare.t2.all : "Rare Endgame Items - T2 (70ish+ gear)

Show # %D4 $type->rr $tier->t2_top
	ItemLevel >= 82
	Rarity Rare
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Advanced Altar Robe" "Advanced Sacrificial Mantle" "Advanced Scale Mail" "Advanced Scalper's Jacket" "Advanced Serpentscale Coat" "Advanced Vaal Cuirass" "Expert Aged Cuffs" "Expert Antler Focus" "Expert Bolstered Mitts" "Expert Braced Sabatons" "Expert Braced Tower Shield" "Expert Chain Tiara" "Expert Construct Hammer" "Expert Cowled Helm" "Expert Crescent Quarterstaff" "Expert Crescent Targe" "Expert Crystal Focus" "Expert Cultist Greathammer" "Expert Dyad Crossbow" "Expert Face Mask" "Expert Felt Cap" "Expert Firm Bracers" "Expert Frayed Shoes" "Expert Gauze Wraps" "Expert Guarded Helm" "Expert Horned Crown" "Expert Iron Greaves" "Expert Jewelled Gloves" "Expert Jingling Crest Shield" "Expert Laced Boots" "Expert Layered Gauntlets" "Expert Linen Wraps" "Expert Long Quarterstaff" "Expert Mail Sabatons" "Expert Martyr Crown" "Expert Oak Greathammer" "Expert Padded Leggings" "Expert Pelage Targe" "Expert Plated Buckler" "Expert Rampart Tower Shield" "Expert Ringmail Gauntlets" "Expert Riveted Mitts" "Expert Rope Cuffs" "Expert Sectioned Bracers" "Expert Secured Leggings" "Expert Sigil Crest Shield" "Expert Silk Slippers" "Expert Soldier Greathelm" "Expert Sombre Gloves" "Expert Spiked Buckler" "Expert Spired Greathelm" "Expert Steeltoe Boots" "Expert Swathed Cap" "Expert Tense Crossbow" "Expert Threaded Shoes" "Expert Trimmed Greaves" "Expert Veiled Mask" "Expert Warden Bow" "Expert Warpick" "Expert Wicker Tiara" "Expert Wrapped Sandals" "Expert Zealot Bow" "Gelid Staff" "Penetrating Quiver" "Pyrophyte Staff" "Stoic Sceptre" "Visceral Quiver" "Volant Quiver" "Volatile Wand" "Withered Wand"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

#Show # %D3 $type->rr $tier->t2_a1
#	ItemLevel >= 75
#	ItemLevel <= 81
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Altar Robe" "Advanced Sacrificial Mantle" "Advanced Scale Mail" "Advanced Scalper's Jacket" "Advanced Serpentscale Coat" "Advanced Vaal Cuirass" "Expert Aged Cuffs" "Expert Antler Focus" "Expert Bolstered Mitts" "Expert Braced Sabatons" "Expert Braced Tower Shield" "Expert Chain Tiara" "Expert Construct Hammer" "Expert Cowled Helm" "Expert Crescent Quarterstaff" "Expert Crescent Targe" "Expert Crystal Focus" "Expert Cultist Greathammer" "Expert Dyad Crossbow" "Expert Face Mask" "Expert Felt Cap" "Expert Firm Bracers" "Expert Frayed Shoes" "Expert Gauze Wraps" "Expert Guarded Helm" "Expert Horned Crown" "Expert Iron Greaves" "Expert Jewelled Gloves" "Expert Jingling Crest Shield" "Expert Laced Boots" "Expert Layered Gauntlets" "Expert Linen Wraps" "Expert Long Quarterstaff" "Expert Mail Sabatons" "Expert Martyr Crown" "Expert Oak Greathammer" "Expert Padded Leggings" "Expert Pelage Targe" "Expert Plated Buckler" "Expert Rampart Tower Shield" "Expert Ringmail Gauntlets" "Expert Riveted Mitts" "Expert Rope Cuffs" "Expert Sectioned Bracers" "Expert Secured Leggings" "Expert Sigil Crest Shield" "Expert Silk Slippers" "Expert Soldier Greathelm" "Expert Sombre Gloves" "Expert Spiked Buckler" "Expert Spired Greathelm" "Expert Steeltoe Boots" "Expert Swathed Cap" "Expert Tense Crossbow" "Expert Threaded Shoes" "Expert Trimmed Greaves" "Expert Veiled Mask" "Expert Warden Bow" "Expert Warpick" "Expert Wicker Tiara" "Expert Wrapped Sandals" "Expert Zealot Bow" "Gelid Staff" "Penetrating Quiver" "Pyrophyte Staff" "Stoic Sceptre" "Visceral Quiver" "Volant Quiver" "Volatile Wand" "Withered Wand"
#	SetFontSize 38
#	SetBackgroundColor 35 35 35 240

Show # %D4 $type->rr $tier->t2_other
	ItemLevel >= 65
	ItemLevel <= 74
	Rarity Rare
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Advanced Altar Robe" "Advanced Sacrificial Mantle" "Advanced Scale Mail" "Advanced Scalper's Jacket" "Advanced Serpentscale Coat" "Advanced Vaal Cuirass" "Expert Aged Cuffs" "Expert Antler Focus" "Expert Bolstered Mitts" "Expert Braced Sabatons" "Expert Braced Tower Shield" "Expert Chain Tiara" "Expert Construct Hammer" "Expert Cowled Helm" "Expert Crescent Quarterstaff" "Expert Crescent Targe" "Expert Crystal Focus" "Expert Cultist Greathammer" "Expert Dyad Crossbow" "Expert Face Mask" "Expert Felt Cap" "Expert Firm Bracers" "Expert Frayed Shoes" "Expert Gauze Wraps" "Expert Guarded Helm" "Expert Horned Crown" "Expert Iron Greaves" "Expert Jewelled Gloves" "Expert Jingling Crest Shield" "Expert Laced Boots" "Expert Layered Gauntlets" "Expert Linen Wraps" "Expert Long Quarterstaff" "Expert Mail Sabatons" "Expert Martyr Crown" "Expert Oak Greathammer" "Expert Padded Leggings" "Expert Pelage Targe" "Expert Plated Buckler" "Expert Rampart Tower Shield" "Expert Ringmail Gauntlets" "Expert Riveted Mitts" "Expert Rope Cuffs" "Expert Sectioned Bracers" "Expert Secured Leggings" "Expert Sigil Crest Shield" "Expert Silk Slippers" "Expert Soldier Greathelm" "Expert Sombre Gloves" "Expert Spiked Buckler" "Expert Spired Greathelm" "Expert Steeltoe Boots" "Expert Swathed Cap" "Expert Tense Crossbow" "Expert Threaded Shoes" "Expert Trimmed Greaves" "Expert Veiled Mask" "Expert Warden Bow" "Expert Warpick" "Expert Wicker Tiara" "Expert Wrapped Sandals" "Expert Zealot Bow" "Gelid Staff" "Penetrating Quiver" "Pyrophyte Staff" "Stoic Sceptre" "Visceral Quiver" "Volant Quiver" "Volatile Wand" "Withered Wand"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

# !! Waypoint c6.rare.t3.all : "Rare Endgame Items - T3 (65ish+ gear)

#Show # %D3 $type->rr $tier->t3_top
#	ItemLevel >= 82
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Aged Cuffs" "Advanced Anchorite Garb" "Advanced Barrier Quarterstaff" "Advanced Bolstered Mitts" "Advanced Bombard Crossbow" "Advanced Braced Sabatons" "Advanced Chain Tiara" "Advanced Doubled Gauntlets" "Advanced Dualstring Bow" "Advanced Edged Buckler" "Advanced Elite Greathelm" "Advanced Explorer Armour" "Advanced Feathered Sandals" "Advanced Feathered Targe" "Advanced Feathered Tiara" "Advanced Full Plate" "Advanced Goldcast Cuffs" "Advanced Heavy Crown" "Advanced Heraldric Tower Shield" "Advanced Hunter Hood" "Advanced Hunting Shoes" "Advanced Intricate Gloves" "Advanced Ironclad Vestments" "Advanced Jewelled Gloves" "Advanced Layered Gauntlets" "Advanced Linen Wraps" "Advanced Lizardscale Boots" "Advanced Moulded Mitts" "Advanced Omen Crest Shield" "Advanced Pelt Leggings" "Advanced Plumed Focus" "Advanced Ringed Buckler" "Advanced Scout's Vest" "Advanced Sectioned Bracers" "Advanced Secured Leggings" "Advanced Shielded Helm" "Advanced Silk Slippers" "Advanced Spined Bracers" "Advanced Spiral Wraps" "Advanced Spired Greathelm" "Advanced Stacked Sabatons" "Advanced Steeltoe Boots" "Advanced Stone Greaves" "Advanced Stone Tower Shield" "Advanced Swathed Cap" "Advanced Threaded Shoes" "Advanced Tribal Mask" "Advanced Trimmed Greaves" "Advanced Voodoo Focus" "Advanced Votive Raiment" "Ashen Staff" "Bone Wand" "Expert Composite Bow" "Expert Crackling Quarterstaff" "Expert Crumbling Maul" "Expert Cultist Bow" "Expert Forge Maul" "Expert Gothic Quarterstaff" "Expert Plated Mace" "Expert Shortbow" "Expert Slim Mace" "Expert Smithing Hammer" "Expert Sturdy Crossbow" "Expert Temple Maul" "Expert Varnished Crossbow" "Shrine Sceptre" "Toxic Quiver" "Two-Point Quiver"
#	SetFontSize 38
#	SetBackgroundColor 35 35 35 240

#Show # %D2 $type->rr $tier->t3_a1
#	ItemLevel >= 75
#	ItemLevel <= 81
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Aged Cuffs" "Advanced Anchorite Garb" "Advanced Barrier Quarterstaff" "Advanced Bolstered Mitts" "Advanced Bombard Crossbow" "Advanced Braced Sabatons" "Advanced Chain Tiara" "Advanced Doubled Gauntlets" "Advanced Dualstring Bow" "Advanced Edged Buckler" "Advanced Elite Greathelm" "Advanced Explorer Armour" "Advanced Feathered Sandals" "Advanced Feathered Targe" "Advanced Feathered Tiara" "Advanced Full Plate" "Advanced Goldcast Cuffs" "Advanced Heavy Crown" "Advanced Heraldric Tower Shield" "Advanced Hunter Hood" "Advanced Hunting Shoes" "Advanced Intricate Gloves" "Advanced Ironclad Vestments" "Advanced Jewelled Gloves" "Advanced Layered Gauntlets" "Advanced Linen Wraps" "Advanced Lizardscale Boots" "Advanced Moulded Mitts" "Advanced Omen Crest Shield" "Advanced Pelt Leggings" "Advanced Plumed Focus" "Advanced Ringed Buckler" "Advanced Scout's Vest" "Advanced Sectioned Bracers" "Advanced Secured Leggings" "Advanced Shielded Helm" "Advanced Silk Slippers" "Advanced Spined Bracers" "Advanced Spiral Wraps" "Advanced Spired Greathelm" "Advanced Stacked Sabatons" "Advanced Steeltoe Boots" "Advanced Stone Greaves" "Advanced Stone Tower Shield" "Advanced Swathed Cap" "Advanced Threaded Shoes" "Advanced Tribal Mask" "Advanced Trimmed Greaves" "Advanced Voodoo Focus" "Advanced Votive Raiment" "Ashen Staff" "Bone Wand" "Expert Composite Bow" "Expert Crackling Quarterstaff" "Expert Crumbling Maul" "Expert Cultist Bow" "Expert Forge Maul" "Expert Gothic Quarterstaff" "Expert Plated Mace" "Expert Shortbow" "Expert Slim Mace" "Expert Smithing Hammer" "Expert Sturdy Crossbow" "Expert Temple Maul" "Expert Varnished Crossbow" "Shrine Sceptre" "Toxic Quiver" "Two-Point Quiver"
#	SetFontSize 35
#	SetBackgroundColor 80 80 80 190

#Show # %D3 $type->rr $tier->t3_a2
#	ItemLevel >= 70
#	ItemLevel <= 74
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Aged Cuffs" "Advanced Anchorite Garb" "Advanced Barrier Quarterstaff" "Advanced Bolstered Mitts" "Advanced Bombard Crossbow" "Advanced Braced Sabatons" "Advanced Chain Tiara" "Advanced Doubled Gauntlets" "Advanced Dualstring Bow" "Advanced Edged Buckler" "Advanced Elite Greathelm" "Advanced Explorer Armour" "Advanced Feathered Sandals" "Advanced Feathered Targe" "Advanced Feathered Tiara" "Advanced Full Plate" "Advanced Goldcast Cuffs" "Advanced Heavy Crown" "Advanced Heraldric Tower Shield" "Advanced Hunter Hood" "Advanced Hunting Shoes" "Advanced Intricate Gloves" "Advanced Ironclad Vestments" "Advanced Jewelled Gloves" "Advanced Layered Gauntlets" "Advanced Linen Wraps" "Advanced Lizardscale Boots" "Advanced Moulded Mitts" "Advanced Omen Crest Shield" "Advanced Pelt Leggings" "Advanced Plumed Focus" "Advanced Ringed Buckler" "Advanced Scout's Vest" "Advanced Sectioned Bracers" "Advanced Secured Leggings" "Advanced Shielded Helm" "Advanced Silk Slippers" "Advanced Spined Bracers" "Advanced Spiral Wraps" "Advanced Spired Greathelm" "Advanced Stacked Sabatons" "Advanced Steeltoe Boots" "Advanced Stone Greaves" "Advanced Stone Tower Shield" "Advanced Swathed Cap" "Advanced Threaded Shoes" "Advanced Tribal Mask" "Advanced Trimmed Greaves" "Advanced Voodoo Focus" "Advanced Votive Raiment" "Ashen Staff" "Bone Wand" "Expert Composite Bow" "Expert Crackling Quarterstaff" "Expert Crumbling Maul" "Expert Cultist Bow" "Expert Forge Maul" "Expert Gothic Quarterstaff" "Expert Plated Mace" "Expert Shortbow" "Expert Slim Mace" "Expert Smithing Hammer" "Expert Sturdy Crossbow" "Expert Temple Maul" "Expert Varnished Crossbow" "Shrine Sceptre" "Toxic Quiver" "Two-Point Quiver"
#	SetFontSize 38
#	SetBackgroundColor 35 35 35 240

Show # %D4 $type->rr $tier->t3_other
	ItemLevel >= 65
	ItemLevel <= 69
	Rarity Rare
	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	BaseType == "Advanced Aged Cuffs" "Advanced Anchorite Garb" "Advanced Barrier Quarterstaff" "Advanced Bolstered Mitts" "Advanced Bombard Crossbow" "Advanced Braced Sabatons" "Advanced Chain Tiara" "Advanced Doubled Gauntlets" "Advanced Dualstring Bow" "Advanced Edged Buckler" "Advanced Elite Greathelm" "Advanced Explorer Armour" "Advanced Feathered Sandals" "Advanced Feathered Targe" "Advanced Feathered Tiara" "Advanced Full Plate" "Advanced Goldcast Cuffs" "Advanced Heavy Crown" "Advanced Heraldric Tower Shield" "Advanced Hunter Hood" "Advanced Hunting Shoes" "Advanced Intricate Gloves" "Advanced Ironclad Vestments" "Advanced Jewelled Gloves" "Advanced Layered Gauntlets" "Advanced Linen Wraps" "Advanced Lizardscale Boots" "Advanced Moulded Mitts" "Advanced Omen Crest Shield" "Advanced Pelt Leggings" "Advanced Plumed Focus" "Advanced Ringed Buckler" "Advanced Scout's Vest" "Advanced Sectioned Bracers" "Advanced Secured Leggings" "Advanced Shielded Helm" "Advanced Silk Slippers" "Advanced Spined Bracers" "Advanced Spiral Wraps" "Advanced Spired Greathelm" "Advanced Stacked Sabatons" "Advanced Steeltoe Boots" "Advanced Stone Greaves" "Advanced Stone Tower Shield" "Advanced Swathed Cap" "Advanced Threaded Shoes" "Advanced Tribal Mask" "Advanced Trimmed Greaves" "Advanced Voodoo Focus" "Advanced Votive Raiment" "Ashen Staff" "Bone Wand" "Expert Composite Bow" "Expert Crackling Quarterstaff" "Expert Crumbling Maul" "Expert Cultist Bow" "Expert Forge Maul" "Expert Gothic Quarterstaff" "Expert Plated Mace" "Expert Shortbow" "Expert Slim Mace" "Expert Smithing Hammer" "Expert Sturdy Crossbow" "Expert Temple Maul" "Expert Varnished Crossbow" "Shrine Sceptre" "Toxic Quiver" "Two-Point Quiver"
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

# !! Waypoint c6.rare.t4.all : "Rare Endgame Items - T4 (55ish+ gear)

#Show # %D1 $type->rr $tier->t4_a1
#	ItemLevel >= 75
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Beaded Circlet" "Advanced Bound Bracers" "Advanced Brigand Mace" "Advanced Bronze Greaves" "Advanced Chiseled Targe" "Advanced Cloaked Mail" "Advanced Composite Bow" "Advanced Construct Hammer" "Advanced Cowled Helm" "Advanced Crescent Quarterstaff" "Advanced Crumbling Maul" "Advanced Crystal Focus" "Advanced Cultist Crown" "Advanced Dyad Crossbow" "Advanced Embossed Boots" "Advanced Felt Cap" "Advanced Firm Bracers" "Advanced Forlorn Crossbow" "Advanced Frayed Shoes" "Advanced Gauze Wraps" "Advanced Hooded Mask" "Advanced Iron Greaves" "Advanced Keth Raiment" "Advanced Lace Hood" "Advanced Laced Boots" "Advanced Lattice Sandals" "Advanced Leaden Greathammer" "Advanced Mail Sabatons" "Advanced Maraketh Cuirass" "Advanced Martyr Crown" "Advanced Padded Leggings" "Advanced Plated Mace" "Advanced Rampart Tower Shield" "Advanced Rhoahide Coat" "Advanced Ringmail Gauntlets" "Advanced Riveted Mitts" "Advanced Rope Cuffs" "Advanced Sectarian Crest Shield" "Advanced Shaman Mantle" "Advanced Silk Robe" "Advanced Slicing Quarterstaff" "Advanced Soldier Greathelm" "Advanced Sombre Gloves" "Advanced Spiked Buckler" "Advanced Steel Plate" "Advanced Stitched Gloves" "Advanced Studded Vest" "Advanced Tempered Mitts" "Advanced Veiled Mask" "Advanced Visored Helm" "Advanced Warden Bow" "Advanced Wayfarer Jacket" "Advanced Wicker Tiara" "Advanced Wrapped Greathelm" "Advanced Wrapped Sandals" "Advanced Zealot Bow"
#	SetFontSize 35
#	SetBackgroundColor 80 80 80 190

#Show # %D2 $type->rr $tier->t4_a2
#	ItemLevel >= 70
#	ItemLevel <= 74
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Beaded Circlet" "Advanced Bound Bracers" "Advanced Brigand Mace" "Advanced Bronze Greaves" "Advanced Chiseled Targe" "Advanced Cloaked Mail" "Advanced Composite Bow" "Advanced Construct Hammer" "Advanced Cowled Helm" "Advanced Crescent Quarterstaff" "Advanced Crumbling Maul" "Advanced Crystal Focus" "Advanced Cultist Crown" "Advanced Dyad Crossbow" "Advanced Embossed Boots" "Advanced Felt Cap" "Advanced Firm Bracers" "Advanced Forlorn Crossbow" "Advanced Frayed Shoes" "Advanced Gauze Wraps" "Advanced Hooded Mask" "Advanced Iron Greaves" "Advanced Keth Raiment" "Advanced Lace Hood" "Advanced Laced Boots" "Advanced Lattice Sandals" "Advanced Leaden Greathammer" "Advanced Mail Sabatons" "Advanced Maraketh Cuirass" "Advanced Martyr Crown" "Advanced Padded Leggings" "Advanced Plated Mace" "Advanced Rampart Tower Shield" "Advanced Rhoahide Coat" "Advanced Ringmail Gauntlets" "Advanced Riveted Mitts" "Advanced Rope Cuffs" "Advanced Sectarian Crest Shield" "Advanced Shaman Mantle" "Advanced Silk Robe" "Advanced Slicing Quarterstaff" "Advanced Soldier Greathelm" "Advanced Sombre Gloves" "Advanced Spiked Buckler" "Advanced Steel Plate" "Advanced Stitched Gloves" "Advanced Studded Vest" "Advanced Tempered Mitts" "Advanced Veiled Mask" "Advanced Visored Helm" "Advanced Warden Bow" "Advanced Wayfarer Jacket" "Advanced Wicker Tiara" "Advanced Wrapped Greathelm" "Advanced Wrapped Sandals" "Advanced Zealot Bow"
#	SetFontSize 38
#	SetBackgroundColor 35 35 35 240

#Show # %D3 $type->rr $tier->t4_other
#	ItemLevel >= 65
#	ItemLevel <= 69
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	BaseType == "Advanced Beaded Circlet" "Advanced Bound Bracers" "Advanced Brigand Mace" "Advanced Bronze Greaves" "Advanced Chiseled Targe" "Advanced Cloaked Mail" "Advanced Composite Bow" "Advanced Construct Hammer" "Advanced Cowled Helm" "Advanced Crescent Quarterstaff" "Advanced Crumbling Maul" "Advanced Crystal Focus" "Advanced Cultist Crown" "Advanced Dyad Crossbow" "Advanced Embossed Boots" "Advanced Felt Cap" "Advanced Firm Bracers" "Advanced Forlorn Crossbow" "Advanced Frayed Shoes" "Advanced Gauze Wraps" "Advanced Hooded Mask" "Advanced Iron Greaves" "Advanced Keth Raiment" "Advanced Lace Hood" "Advanced Laced Boots" "Advanced Lattice Sandals" "Advanced Leaden Greathammer" "Advanced Mail Sabatons" "Advanced Maraketh Cuirass" "Advanced Martyr Crown" "Advanced Padded Leggings" "Advanced Plated Mace" "Advanced Rampart Tower Shield" "Advanced Rhoahide Coat" "Advanced Ringmail Gauntlets" "Advanced Riveted Mitts" "Advanced Rope Cuffs" "Advanced Sectarian Crest Shield" "Advanced Shaman Mantle" "Advanced Silk Robe" "Advanced Slicing Quarterstaff" "Advanced Soldier Greathelm" "Advanced Sombre Gloves" "Advanced Spiked Buckler" "Advanced Steel Plate" "Advanced Stitched Gloves" "Advanced Studded Vest" "Advanced Tempered Mitts" "Advanced Veiled Mask" "Advanced Visored Helm" "Advanced Warden Bow" "Advanced Wayfarer Jacket" "Advanced Wicker Tiara" "Advanced Wrapped Greathelm" "Advanced Wrapped Sandals" "Advanced Zealot Bow"
#	SetFontSize 38
#	SetBackgroundColor 35 35 35 240

# !! Waypoint c6.rare.t5.all : "Rare Endgame Items - T5 (lower)

#Show # %D1 $type->rr $tier->t5_a1
#	ItemLevel >= 75
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 35
#	SetBackgroundColor 80 80 80 190

#Show # %D2 $type->rr $tier->t5_a2
#	ItemLevel >= 70
#	ItemLevel <= 74
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 35
#	SetBackgroundColor 80 80 80 190

#Show # %D3 $type->rr $tier->t5_other
#	ItemLevel >= 65
#	ItemLevel <= 69
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 38
#	SetBackgroundColor 35 35 35 240

#===============================================================================================================
# [[1500]] Untiered Rare Catcher
#===============================================================================================================
# !! Waypoint c6.rare.rest : "Rare Endgame Items - Others, Salvagable bases"

# Double Quality Currencies

#Show # %D3 $type->rare->salvagable $tier->quality2martialany
#	Quality >= 10
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Two Hand Maces"
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D3 $type->rare->salvagable $tier->quality2casterany
#	Quality >= 10
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Sceptres" "Staves" "Wands"
#	SetFontSize 38
#	SetBorderColor 180 180 180

Show # %D4 $type->rare->salvagable $tier->quality2armorany
	Quality >= 10
	ItemLevel >= 65
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	SetFontSize 38
	SetBorderColor 180 180 180

# Single Quality Currencies

#Show # %D2 $type->rare->salvagable $tier->qualitymartialany
#	Quality >= 1
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Two Hand Maces"
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D2 $type->rare->salvagable $tier->qualitycasterany
#	Quality >= 1
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Sceptres" "Staves" "Wands"
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D3 $type->rare->salvagable $tier->qualityarmorany
#	Quality >= 1
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
#	SetFontSize 35
#	SetBorderColor 127 127 127

# Artificer Scraps

#Show # %D1 $type->rare->salvagable $tier->socketslarge
#	Sockets > 0
#	Height >= 3
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 35
#	SetBorderColor 127 127 127

#Show # %D2 $type->rare->salvagable $tier->socketssmall
#	Sockets > 0
#	Height < 3
#	ItemLevel >= 65
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 35
#	SetBorderColor 127 127 127

#===============================================================================================================
# [[1600]] Hide Layer 2 - Rare Gear
#===============================================================================================================

#Show # %D0 $type->lowstrictnessshowlayer $tier->raresendgameany
#	Rarity Rare
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 65
#	SetFontSize 26
#	SetBorderColor 0 0 0 0
#	SetBackgroundColor 20 20 0 140
#	DisableDropSound True

Hide # $type->hidelayer $tier->raresendgame
	Rarity Rare
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 65
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

#===============================================================================================================
# [[1700]] Socketables - Runes and Soul Cores
#===============================================================================================================
# !! Waypoint c7.miscgear.socketables : "Socketables - Runes and Soul Cores"

# Highlight lower runes while leveling as well

Show # %H4 $type->sockets->runes $tier->levelingrunes
	Class == "Socketable"
	BaseType == "Body Rune" "Desert Rune" "Glacial Rune" "Inspiration Rune" "Mind Rune" "Rebirth Rune" "Stone Rune" "Storm Rune" "Vision Rune"
	AreaLevel < 65
	SetFontSize 38
	SetTextColor 220 175 132
	SetBorderColor 220 175 132

#Show # %H6 $type->sockets->runes $tier->t1
#	Class == "Socketable"
#	SetFontSize 42
#	SetTextColor 0 0 0 255
#	SetBorderColor 0 0 0 255
#	SetBackgroundColor 245 139 87 255
#	PlayAlertSound 2 300
#	PlayEffect White
#	MinimapIcon 1 Yellow Circle

Show # %H5 $type->sockets->runes $tier->t2
	Class == "Socketable"
	BaseType == "Iron Rune"
	SetFontSize 40
	SetTextColor 240 207 132
	SetBorderColor 240 207 132
	SetBackgroundColor 76 51 12
	PlayEffect Yellow Temp

Hide # %H3 $type->sockets->runes $tier->t3
	Class == "Socketable"
	BaseType == "Desert Rune" "Glacial Rune" "Inspiration Rune" "Storm Rune"
	SetFontSize 38
	SetTextColor 220 175 132
	SetBorderColor 220 175 132

Hide # %H2 $type->sockets->runes $tier->t4
	Class == "Socketable"
	BaseType == "Body Rune" "Mind Rune" "Rebirth Rune" "Stone Rune" "Vision Rune"
	SetFontSize 38
	SetTextColor 170 158 130
	SetBorderColor 170 158 130

Hide # $type->sockets->runes $tier->exhide
	Class == "Socketable"
	BaseType == "Body Rune" "Desert Rune" "Glacial Rune" "Inspiration Rune" "Iron Rune" "Mind Rune" "Rebirth Rune" "Stone Rune" "Storm Rune" "Vision Rune"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->sockets->runes $tier->restex
	Class == "Socketable"
	BaseType "Rune"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

Show # $type->sockets->cores $tier->s
	Class == "Socketable"
	BaseType == "Soul Core of Azcapa"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->sockets->cores $tier->a
	Class == "Socketable"
	BaseType == "Soul Core of Citaqualotl" "Soul Core of Zalatl"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Circle

Show # $type->sockets->cores $tier->b
	Class == "Socketable"
	BaseType == "Soul Core of Jiquani" "Soul Core of Opiloti" "Soul Core of Puhuarte" "Soul Core of Quipolatl" "Soul Core of Tacati" "Soul Core of Ticaba" "Soul Core of Topotante" "Soul Core of Tzamoto" "Soul Core of Xopec"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 2 300
	PlayEffect Yellow
	MinimapIcon 1 Yellow Circle

Show # %H6 $type->sockets->cores $tier->c
	Class == "Socketable"
	BaseType == "Soul Core of Atmohua" "Soul Core of Cholotl" "Soul Core of Zantipi"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 139 87 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 1 Yellow Circle

#Show # %H5 $type->sockets->cores $tier->d
#	Class == "Socketable"
#	SetFontSize 40
#	SetTextColor 0 0 0 255
#	SetBorderColor 0 0 0 255
#	SetBackgroundColor 240 180 100 255
#	PlayAlertSound 2 300
#	PlayEffect White
#	MinimapIcon 2 White Circle

#Show # %H3 $type->sockets->cores $tier->e
#	Class == "Socketable"
#	SetFontSize 40
#	SetTextColor 240 207 132
#	SetBorderColor 240 207 132
#	PlayEffect White Temp
#	MinimapIcon 2 Grey Circle

Hide # $type->sockets->cores $tier->exhide
	Class == "Socketable"
	BaseType == "Soul Core of Atmohua" "Soul Core of Cholotl" "Soul Core of Jiquani" "Soul Core of Opiloti" "Soul Core of Puhuarte" "Soul Core of Quipolatl" "Soul Core of Tacati" "Soul Core of Ticaba" "Soul Core of Topotante" "Soul Core of Tzamoto" "Soul Core of Xopec" "Soul Core of Zantipi"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->sockets->cores $tier->restex
	Class == "Socketable"
	BaseType "Soul Core"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#===============================================================================================================
# [[1800]] Jewels
#===============================================================================================================
# !! Waypoint c7.jewels.generic.all : "Jewels"

Show # $type->jewels->generic $tier->anytimeless
	Rarity Normal Magic Rare
	Class "Jewel"
	BaseType == "Time-Lost Emerald" "Time-Lost Ruby" "Time-Lost Sapphire"
	SetFontSize 42
	SetTextColor 0 240 190 255
	SetBorderColor 0 240 190 255
	SetBackgroundColor 0 75 30 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 0 Blue Diamond

Show # $type->jewels->generic $tier->anycorruptedmod
	AnyEnchantment True
	Corrupted True
	Rarity Normal Magic Rare
	Class "Jewel"
	SetFontSize 42
	SetTextColor 0 240 190 255
	SetBorderColor 0 240 190 255
	SetBackgroundColor 0 75 30 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 0 Blue Diamond

Show # $type->jewels->generic $tier->any5modded
	Corrupted True
	Rarity Normal Magic Rare
	Class "Jewel"
	HasExplicitMod >=5 "a" "o" "e" "u" "i" "y"
	SetFontSize 42
	SetTextColor 0 240 190 255
	SetBorderColor 0 240 190 255
	SetBackgroundColor 0 75 30 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 0 Blue Diamond

Show # $type->jewels->generic $tier->anyrare
	Rarity Rare
	Class "Jewel"
	BaseType == "Emerald" "Ruby" "Sapphire"
	SetFontSize 42
	SetTextColor 220 220 0
	SetBorderColor 220 220 0
	SetBackgroundColor 75 75 0
	PlayAlertSound 2 300
	PlayEffect Yellow
	MinimapIcon 1 Yellow Diamond

Show # %H5 $type->jewels->generic $tier->anymagic
	Rarity Normal Magic
	Class "Jewel"
	BaseType == "Emerald" "Ruby" "Sapphire"
	SetFontSize 42
	SetTextColor 0 70 255 255
	SetBorderColor 0 70 255 255
	SetBackgroundColor 30 0 70 255
	PlayAlertSound 2 300
	PlayEffect Blue
	MinimapIcon 1 Blue Diamond

#===============================================================================================================
# [[1900]] Relics
#===============================================================================================================
# !! Waypoint c7.relics.generic.all : "Relics (Trial of the Sekhema)"
# Relics currently are not hidable, due to an ingame limitation.

Show # $type->relics->generic $tier->any
	Rarity Normal Magic
	BaseType == "Amphora Relic" "Coffer Relic" "Incense Relic" "Seal Relic" "Tapestry Relic" "Urn Relic" "Vase Relic"
	SetFontSize 40
	SetTextColor 0 240 190 255
	PlayAlertSound 3 300
	PlayEffect Blue Temp

#===============================================================================================================
# [[2000]] Gems and Uncut Gems
#===============================================================================================================
# !! Waypoint c8.gems.uncut : "Gems - Uncut"

# Level20

Show # $type->gems->uncut $tier->spirit20
	ItemLevel >= 20
	BaseType == "Uncut Spirit Gem"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->gems->uncut $tier->skill20
	ItemLevel >= 20
	BaseType == "Uncut Skill Gem"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

# Level19

Show # %H5 $type->gems->uncut $tier->spirit19
	ItemLevel 19
	BaseType == "Uncut Spirit Gem"
	SetFontSize 42
	SetTextColor 20 240 240
	SetBorderColor 20 240 240
	SetBackgroundColor 6 0 60
	PlayAlertSound 2 300
	PlayEffect Cyan
	MinimapIcon 1 Cyan Triangle

Show # %H5 $type->gems->uncut $tier->skill19
	ItemLevel 19
	BaseType == "Uncut Skill Gem"
	SetFontSize 42
	SetTextColor 20 240 240
	SetBorderColor 20 240 240
	SetBackgroundColor 6 0 60
	PlayAlertSound 2 300
	PlayEffect Cyan
	MinimapIcon 1 Cyan Triangle

# All gems during campaign with sounds

Show # %H5 $type->gems->uncut $tier->spiritcampaign
	BaseType == "Uncut Spirit Gem"
	AreaLevel < 65
	SetFontSize 42
	SetTextColor 20 240 240
	SetBorderColor 20 240 240
	PlayAlertSound 2 300
	PlayEffect Cyan
	MinimapIcon 1 Cyan Triangle

Show # %H5 $type->gems->uncut $tier->skillcampaign
	BaseType == "Uncut Skill Gem"
	AreaLevel < 65
	SetFontSize 42
	SetTextColor 20 240 240
	SetBorderColor 20 240 240
	PlayAlertSound 2 300
	PlayEffect Cyan
	MinimapIcon 1 Cyan Triangle

Show # %H5 $type->gems->uncut $tier->supportcampaign
	BaseType == "Uncut Support Gem"
	AreaLevel < 65
	SetFontSize 42
	SetTextColor 20 240 240
	SetBorderColor 20 240 240
	PlayAlertSound 2 300
	PlayEffect Cyan
	MinimapIcon 1 Cyan Triangle

# Lower highlight for lower level gems in maps

Hide # %H3 $type->gems->uncut $tier->otherspiriteg
	BaseType == "Uncut Spirit Gem"
	AreaLevel >= 65
	SetFontSize 35
	SetTextColor 20 240 240
	SetBorderColor 20 240 240

Hide # %H3 $type->gems->uncut $tier->otherskilleg
	BaseType == "Uncut Skill Gem"
	AreaLevel >= 65
	SetFontSize 35
	SetTextColor 20 240 240
	SetBorderColor 20 240 240

Hide # %H3 $type->gems->uncut $tier->othersupporteg
	BaseType == "Uncut Support Gem"
	AreaLevel >= 65
	SetFontSize 35
	SetTextColor 20 240 240
	SetBorderColor 20 240 240

# Hider for filterblade

Hide # $type->gems->uncut $tier->exhide
	BaseType == "Uncut Skill Gem" "Uncut Spirit Gem" "Uncut Support Gem"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

# !! Waypoint c8.gems.others : "Gems - Specific"

Show # $type->gems $tier->any
	Class == "Skill Gems" "Support Gems"
	SetFontSize 42
	SetTextColor 20 240 240
	SetBorderColor 20 240 240
	PlayAlertSound 2 300
	PlayEffect Cyan
	MinimapIcon 1 Cyan Triangle

#===============================================================================================================
# [[2100]] Waystones
#===============================================================================================================
# !! Waypoint c9.waystones.all : "Waystones - Override All"

#===============================================================================================================
# [[2200]] Normal Waystone Progression
#===============================================================================================================
# !! Waypoint c9.waystone.special : "Waystones - Override Hider Rules"

#Hide # $type->waystone->hiders $tier->corruptedmaphider
#	Corrupted True
#	Rarity Normal Magic
#	Class == "Waystones"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # $type->waystone->hiders $tier->mirroredmaphider
#	Mirrored True
#	Rarity Normal Magic
#	Class == "Waystones"
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#------------------------------------
#   [2201] Generic Decorators
#------------------------------------
# !! Waypoint c9.waystone.decorators.all : "Waystones - Decorators"

Show # $type->waystones $tier->decomap1
	WaystoneTier >= 15
	Class == "Waystones"
	SetFontSize 42
	SetBorderColor 0 0 0 255
	Continue

Show # $type->waystones $tier->decomap2
	WaystoneTier >= 12
	WaystoneTier <= 14
	Class == "Waystones"
	SetFontSize 40
	SetBorderColor 0 0 0 255
	Continue

Show # $type->waystones $tier->decomap3
	WaystoneTier >= 6
	WaystoneTier <= 11
	Class == "Waystones"
	SetFontSize 40
	SetBorderColor 200 200 200 255
	Continue

Show # $type->waystones $tier->decomap4
	WaystoneTier >= 1
	WaystoneTier <= 5
	Class == "Waystones"
	SetFontSize 40
	SetBorderColor 200 200 200 255
	Continue

Show # $type->waystones $tier->deco_wsup_t16
	WaystoneTier >= 16
	Class == "Waystones"
	AreaLevel < 80
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t15
	WaystoneTier >= 15
	Class == "Waystones"
	AreaLevel < 79
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t14
	WaystoneTier >= 14
	Class == "Waystones"
	AreaLevel < 78
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t13
	WaystoneTier >= 13
	Class == "Waystones"
	AreaLevel < 76
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t12
	WaystoneTier >= 12
	Class == "Waystones"
	AreaLevel < 75
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t11
	WaystoneTier >= 11
	Class == "Waystones"
	AreaLevel < 74
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t10
	WaystoneTier >= 10
	Class == "Waystones"
	AreaLevel < 73
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t9
	WaystoneTier >= 9
	Class == "Waystones"
	AreaLevel < 72
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t8
	WaystoneTier >= 8
	Class == "Waystones"
	AreaLevel < 72
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t7
	WaystoneTier >= 7
	Class == "Waystones"
	AreaLevel < 71
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t6
	WaystoneTier >= 6
	Class == "Waystones"
	AreaLevel < 70
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t5
	WaystoneTier >= 5
	Class == "Waystones"
	AreaLevel < 69
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t4
	WaystoneTier >= 4
	Class == "Waystones"
	AreaLevel < 68
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t3
	WaystoneTier >= 3
	Class == "Waystones"
	AreaLevel < 67
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t2
	WaystoneTier >= 2
	Class == "Waystones"
	AreaLevel < 66
	SetBorderColor 220 50 0 255
	Continue

Show # $type->waystones $tier->deco_wsup_t1
	WaystoneTier >= 1
	Class == "Waystones"
	AreaLevel < 65
	SetBorderColor 220 50 0 255
	Continue

#Show # $type->waystones $tier->decomap1overleveled
#	WaystoneTier >= 1
#	WaystoneTier <= 11
#	Class == "Waystones"
#	AreaLevel >= 78
#	SetFontSize 38
#	SetBorderColor 200 200 200 255
#	Continue

#Show # $type->waystones $tier->decomap2overleveled
#	WaystoneTier >= 1
#	WaystoneTier <= 8
#	Class == "Waystones"
#	AreaLevel >= 76
#	SetFontSize 38
#	SetBorderColor 200 200 200 255
#	Continue

#Show # $type->waystones $tier->decomap3overleveled
#	WaystoneTier >= 1
#	WaystoneTier <= 6
#	Class == "Waystones"
#	AreaLevel >= 74
#	SetFontSize 38
#	SetBorderColor 200 200 200 255
#	Continue

#Show # $type->waystones $tier->decomap4overleveled
#	WaystoneTier >= 1
#	WaystoneTier <= 3
#	Class == "Waystones"
#	AreaLevel >= 72
#	SetFontSize 38
#	SetBorderColor 200 200 200 255
#	Continue

# semi-strict, currently: t14 map, find: t1 map, shown based on t1

Show # $type->waystones $tier->deco_corruptedmod
	AnyEnchantment True
	Class == "Waystones"
	SetBorderColor 250 0 0 255
	Continue

#------------------------------------
#   [2202] Special Maps
#------------------------------------

Show # $type->waystones $tier->enchanted
	AnyEnchantment True
	Class == "Waystones"
	SetBorderColor 250 0 0 255

Show # $type->waystones $tier->corrupted8
	Corrupted True
	Class == "Waystones"
	HasExplicitMod >=7 "a" "o" "e" "u" "i" "y"
	SetBorderColor 250 0 0 255

#------------------------------------
#   [2203] Waystone progression
#------------------------------------
# !! Waypoint c9.waystone.generic.t16 : "Waystones - t15-t16"

Show # $type->waystones $tier->waystone_t16
	WaystoneTier >= 16
	Class == "Waystones"
	SetTextColor 0 0 0 255
	SetBackgroundColor 235 235 235 255
	PlayAlertSound 5 300
	PlayEffect Yellow
	MinimapIcon 1 Red Square

Show # $type->waystones $tier->waystone_t15
	WaystoneTier 15
	Class == "Waystones"
	SetTextColor 0 0 0 255
	SetBackgroundColor 235 235 235 255
	PlayAlertSound 5 300
	PlayEffect Yellow
	MinimapIcon 1 Red Square

# !! Waypoint c9.waystone.generic.t14 : "Waystones - t12-t14"

Show # %H5 $type->waystones $tier->waystone_t14
	WaystoneTier 14
	Class == "Waystones"
	SetTextColor 0 0 0 255
	SetBackgroundColor 200 200 200 255
	PlayAlertSound 4 300
	PlayEffect Yellow Temp
	MinimapIcon 1 Yellow Square

Hide # %HS3 $type->waystones $tier->waystone_t13
	WaystoneTier 13
	Class == "Waystones"
	SetTextColor 0 0 0 255
	SetBackgroundColor 200 200 200 255

Hide # %HS3 $type->waystones $tier->waystone_t12
	WaystoneTier 12
	Class == "Waystones"
	SetTextColor 0 0 0 255
	SetBackgroundColor 200 200 200 255

# !! Waypoint c9.waystone.generic.t11 : "Waystones - t7-t11"

Hide # %HS3 $type->waystones $tier->waystone_t11
	WaystoneTier 11
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS3 $type->waystones $tier->waystone_t10
	WaystoneTier 10
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS3 $type->waystones $tier->waystone_t9
	WaystoneTier 9
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS3 $type->waystones $tier->waystone_t8
	WaystoneTier 8
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS3 $type->waystones $tier->waystone_t7
	WaystoneTier 7
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

# !! Waypoint c9.waystone.generic.t6 : "Waystones - T1-T6"

Hide # %HS2 $type->waystones $tier->waystone_t6
	WaystoneTier 6
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS2 $type->waystones $tier->waystone_t5
	WaystoneTier 5
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS2 $type->waystones $tier->waystone_t4
	WaystoneTier 4
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS2 $type->waystones $tier->waystone_t3
	WaystoneTier 3
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS2 $type->waystones $tier->waystone_t2
	WaystoneTier 2
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Hide # %HS2 $type->waystones $tier->waystone_t1
	WaystoneTier 1
	Class == "Waystones"
	SetTextColor 255 255 255 255
	SetBackgroundColor 20 20 0 255

Show # $type->waystones $tier->restex
	Class == "Waystones"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#===============================================================================================================
# [[2300]] Currency - Exceptions - Leveling Currencies
#===============================================================================================================
# !! Waypoint c9.currency.leveling.nonstacked : "Tierlist - Currency - Leveling Currency"

Show # %H5 $type->currency->leveling $tier->rare
	Class == "Stackable Currency"
	BaseType == "Artificer's Orb" "Lesser Jeweller's Orb" "Regal Orb"
	AreaLevel < 65
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 240 180 100 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 2 White Circle

Show # %H4 $type->currency->leveling $tier->magic
	Class == "Stackable Currency"
	BaseType == "Orb of Augmentation" "Orb of Transmutation"
	AreaLevel < 65
	SetFontSize 42
	SetTextColor 220 175 132
	SetBorderColor 220 175 132

Hide # %H3 $type->currency->leveling $tier->wisdomstart
	Class == "Stackable Currency"
	BaseType == "Scroll of Wisdom"
	AreaLevel < 17
	SetFontSize 40
	SetTextColor 170 158 130
	SetBorderColor 170 158 130

Hide # %H3 $type->currency->leveling $tier->wisdom
	Class == "Stackable Currency"
	BaseType == "Scroll of Wisdom"
	AreaLevel < 65
	SetFontSize 35
	SetTextColor 170 158 130

#===============================================================================================================
# [[2400]] Currency - Regular Currency Tiering
#===============================================================================================================
# !! Waypoint c9.currency.single : "Tierlist - Currency - General"

Show # $type->currency $tier->s
	Class == "Stackable Currency"
	BaseType == "Albino Rhoa Feather" "Divine Orb" "Mirror of Kalandra" "Perfect Jeweller's Orb"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->currency $tier->a
	Class == "Stackable Currency"
	BaseType == "Greater Jeweller's Orb" "Orb of Annulment" "Orb of Chance"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 2 White Circle

Show # $type->currency $tier->b
	Class == "Stackable Currency"
	BaseType == "Chaos Orb" "Exotic Coinage" "Gemcutter's Prism"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 2 300
	PlayEffect Yellow
	MinimapIcon 1 Yellow Circle

Show # $type->currency $tier->c
	Class == "Stackable Currency"
	BaseType == "Exalted Orb" "Glassblower's Bauble"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 139 87 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 1 Yellow Circle

Show # %H5 $type->currency $tier->d
	Class == "Stackable Currency"
	BaseType == "Armourer's Scrap" "Artificer's Orb" "Chance Shard" "Lesser Jeweller's Orb" "Orb of Alchemy" "Regal Orb" "Vaal Orb"
	SetFontSize 40
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 240 180 100 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 2 White Circle

Hide # %H3 $type->currency $tier->e
	Class == "Stackable Currency"
	BaseType == "Arcanist's Etcher" "Blacksmith's Whetstone"
	SetFontSize 40
	SetTextColor 240 207 132
	SetBorderColor 240 207 132

# Artifacts and special drops

Show # $type->currency $tier->artifactlike
	Class == "Stackable Currency"
	BaseType == "Black Scythe Artifact" "Broken Circle Artifact" "Order Artifact" "Sun Artifact"
	SetFontSize 40
	SetTextColor 240 207 132
	SetBorderColor 240 207 132
	SetBackgroundColor 76 51 12
	PlayAlertSound 2 300
	PlayEffect Yellow Temp
	MinimapIcon 1 White Kite

Hide # %H3 $type->currency $tier->supplymagic
	Class == "Stackable Currency"
	BaseType == "Alchemy Shard" "Artificer's Shard" "Orb of Augmentation" "Orb of Transmutation" "Regal Shard"
	SetFontSize 38
	SetTextColor 220 175 132
	SetBorderColor 220 175 132

Hide # %H1 $type->currency $tier->supplieslow
	Class == "Stackable Currency"
	BaseType == "Scroll of Wisdom" "Transmutation Shard"
	SetFontSize 35
	SetTextColor 170 158 130

Hide # $type->currency $tier->exhide
	Class == "Stackable Currency"
	BaseType == "Alchemy Shard" "Arcanist's Etcher" "Armourer's Scrap" "Artificer's Orb" "Artificer's Shard" "Black Scythe Artifact" "Blacksmith's Whetstone" "Broken Circle Artifact" "Chance Shard" "Chaos Orb" "Exalted Orb" "Exotic Coinage" "Gemcutter's Prism" "Glassblower's Bauble" "Lesser Jeweller's Orb" "Orb of Alchemy" "Orb of Augmentation" "Orb of Transmutation" "Order Artifact" "Regal Orb" "Regal Shard" "Scroll of Wisdom" "Sun Artifact" "Transmutation Shard" "Vaal Orb"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

#===============================================================================================================
# [[2500]] Currency - SPECIAL
#===============================================================================================================
#------------------------------------
#   [2501] Distilled Emotions (Delirium)
#------------------------------------
# !! Waypoint c9.currency.emotions.all : "Tierlist - Distilled Emotions (Delirium)"

Show # $type->currency->emotions $tier->s
	Class == "Stackable Currency"
	BaseType == "Distilled Isolation" "Distilled Suffering"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->currency->emotions $tier->a
	Class == "Stackable Currency"
	BaseType == "Distilled Despair" "Distilled Fear"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Circle

Show # $type->currency->emotions $tier->b
	Class == "Stackable Currency"
	BaseType == "Distilled Disgust" "Distilled Envy"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 2 300
	PlayEffect Yellow
	MinimapIcon 1 Yellow Circle

Show # %H6 $type->currency->emotions $tier->c
	Class == "Stackable Currency"
	BaseType == "Distilled Greed" "Distilled Paranoia"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 139 87 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 1 Yellow Circle

Show # %H5 $type->currency->emotions $tier->d
	Class == "Stackable Currency"
	BaseType == "Distilled Guilt" "Distilled Ire"
	SetFontSize 40
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 240 180 100 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 2 White Circle

#Show # %H4 $type->currency->emotions $tier->e
#	Class == "Stackable Currency"
#	SetFontSize 40
#	SetTextColor 240 207 132
#	SetBorderColor 240 207 132
#	PlayEffect White Temp
#	MinimapIcon 2 Grey Circle

Hide # $type->currency->emotions $tier->exhide
	Class == "Stackable Currency"
	BaseType == "Distilled Disgust" "Distilled Envy" "Distilled Greed" "Distilled Guilt" "Distilled Ire" "Distilled Paranoia"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->currency->emotions $tier->restex
	Class == "Stackable Currency"
	BaseType "Distilled "
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#------------------------------------
#   [2502] Catalysts (breach)
#------------------------------------
# !! Waypoint c9.currency.catalysts.all : "Tierlist - Catalysts (Breach)"

#Show # $type->currency->catalysts $tier->s
#	Class == "Stackable Currency"
#	SetFontSize 45
#	SetTextColor 255 0 0 255
#	SetBorderColor 255 0 0 255
#	SetBackgroundColor 255 255 255 255
#	PlayAlertSound 6 300
#	PlayEffect Red
#	MinimapIcon 0 Red Star

#Show # $type->currency->catalysts $tier->a
#	Class == "Stackable Currency"
#	SetFontSize 45
#	SetTextColor 255 255 255 255
#	SetBorderColor 255 255 255 255
#	SetBackgroundColor 245 105 90 255
#	PlayAlertSound 1 300
#	PlayEffect Red
#	MinimapIcon 0 Red Circle

#Show # $type->currency->catalysts $tier->b
#	Class == "Stackable Currency"
#	SetFontSize 42
#	SetTextColor 0 0 0 255
#	SetBorderColor 0 0 0 255
#	SetBackgroundColor 245 105 90 255
#	PlayAlertSound 2 300
#	PlayEffect Yellow
#	MinimapIcon 1 Yellow Circle

#Show # %H6 $type->currency->catalysts $tier->c
#	Class == "Stackable Currency"
#	SetFontSize 42
#	SetTextColor 0 0 0 255
#	SetBorderColor 0 0 0 255
#	SetBackgroundColor 245 139 87 255
#	PlayAlertSound 2 300
#	PlayEffect White
#	MinimapIcon 1 Yellow Circle

Show # %HS4 $type->currency->catalysts $tier->d
	Class == "Stackable Currency"
	BaseType == "Adaptive Catalyst" "Neural Catalyst"
	SetFontSize 40
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 240 180 100 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 2 White Circle

Hide # %HS2 $type->currency->catalysts $tier->e
	Class == "Stackable Currency"
	BaseType == "Carapace Catalyst" "Chayula's Catalyst" "Esh's Catalyst" "Flesh Catalyst" "Reaver Catalyst" "Sibilant Catalyst" "Skittering Catalyst" "Tul's Catalyst" "Uul-Netol's Catalyst" "Xoph's Catalyst"
	SetFontSize 40
	SetTextColor 240 207 132
	SetBorderColor 240 207 132

Hide # $type->currency->catalysts $tier->exhide
	Class == "Stackable Currency"
	BaseType == "Adaptive Catalyst" "Carapace Catalyst" "Chayula's Catalyst" "Esh's Catalyst" "Flesh Catalyst" "Neural Catalyst" "Reaver Catalyst" "Sibilant Catalyst" "Skittering Catalyst" "Tul's Catalyst" "Uul-Netol's Catalyst" "Xoph's Catalyst"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->currency->catalysts $tier->restex
	Class == "Stackable Currency"
	BaseType "Catalyst"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#------------------------------------
#   [2503] Essences
#------------------------------------
# !! Waypoint c9.currency.essences.all : "Tierlist - Essences"

Show # $type->currency->essence $tier->s
	Class == "Stackable Currency"
	BaseType == "Greater Essence of Haste" "Greater Essence of Sorcery" "Greater Essence of the Infinite"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->currency->essence $tier->a
	Class == "Stackable Currency"
	BaseType == "Greater Essence of Electricity" "Greater Essence of Enhancement" "Greater Essence of Ruin" "Greater Essence of the Mind" "Greater Essence of Torment"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Circle

Show # $type->currency->essence $tier->b
	Class == "Stackable Currency"
	BaseType == "Essence of Electricity" "Greater Essence of Battle" "Greater Essence of Flames" "Greater Essence of Ice" "Greater Essence of the Body"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 2 300
	PlayEffect Yellow
	MinimapIcon 1 Yellow Circle

Show # $type->currency->essence $tier->c
	Class == "Stackable Currency"
	BaseType == "Essence of Haste" "Essence of Torment"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 139 87 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 1 Yellow Circle

Show # %H6 $type->currency->essence $tier->d
	Class == "Stackable Currency"
	BaseType == "Essence of Battle" "Essence of Enhancement" "Essence of Flames" "Essence of Ice" "Essence of Ruin" "Essence of Sorcery" "Essence of the Body" "Essence of the Infinite" "Essence of the Mind"
	SetFontSize 40
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 240 180 100 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 2 White Circle

#Show # %H5 $type->currency->essence $tier->e
#	Class == "Stackable Currency"
#	SetFontSize 40
#	SetTextColor 240 207 132
#	SetBorderColor 240 207 132
#	PlayEffect White Temp
#	MinimapIcon 2 Grey Circle

Hide # $type->currency->essence $tier->exhide
	Class == "Stackable Currency"
	BaseType == "Essence of Battle" "Essence of Electricity" "Essence of Enhancement" "Essence of Flames" "Essence of Haste" "Essence of Ice" "Essence of Ruin" "Essence of Sorcery" "Essence of the Body" "Essence of the Infinite" "Essence of the Mind" "Essence of Torment" "Greater Essence of Battle" "Greater Essence of Flames" "Greater Essence of Ice" "Greater Essence of the Body"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->currency->essence $tier->restex
	Class == "Stackable Currency"
	BaseType "Essence"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#------------------------------------
#   [2504] Omen (ritual)
#------------------------------------
# !! Waypoint c9.currency.omen.all : "Tierlist - Omen (Ritual)"

Show # $type->currency->omen $tier->s
	Class == "Omen"
	BaseType == "Omen of Corruption" "Omen of Dextral Annulment" "Omen of Dextral Erasure" "Omen of Sinistral Annulment" "Omen of Sinistral Erasure" "Omen of Whittling"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->currency->omen $tier->a
	Class == "Omen"
	BaseType == "Omen of Amelioration"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Circle

Show # $type->currency->omen $tier->b
	Class == "Omen"
	BaseType == "Omen of Greater Annulment" "Omen of Resurgence" "Omen of Sinistral Alchemy" "Omen of Sinistral Coronation" "Omen of Sinistral Exaltation"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 105 90 255
	PlayAlertSound 2 300
	PlayEffect Yellow
	MinimapIcon 1 Yellow Circle

Show # $type->currency->omen $tier->c
	Class == "Omen"
	BaseType == "Omen of Dextral Alchemy" "Omen of Dextral Coronation" "Omen of Dextral Exaltation" "Omen of Greater Exaltation" "Omen of Refreshment"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 245 139 87 255
	PlayAlertSound 2 300
	PlayEffect White
	MinimapIcon 1 Yellow Circle

#Show # $type->currency->omen $tier->d
#	Class == "Omen"
#	SetFontSize 40
#	SetTextColor 0 0 0 255
#	SetBorderColor 0 0 0 255
#	SetBackgroundColor 240 180 100 255
#	PlayAlertSound 2 300
#	PlayEffect White
#	MinimapIcon 2 White Circle

#Show # %H5 $type->currency->omen $tier->e
#	Class == "Omen"
#	SetFontSize 40
#	SetTextColor 240 207 132
#	SetBorderColor 240 207 132
#	PlayEffect White Temp
#	MinimapIcon 2 Grey Circle

Hide # $type->currency->omen $tier->exhide
	Class == "Omen"
	BaseType == "Omen of Dextral Alchemy" "Omen of Dextral Coronation" "Omen of Dextral Exaltation" "Omen of Greater Annulment" "Omen of Greater Exaltation" "Omen of Refreshment" "Omen of Resurgence" "Omen of Sinistral Alchemy" "Omen of Sinistral Coronation" "Omen of Sinistral Exaltation"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->currency->omen $tier->restex
	Class == "Omen"
	BaseType "Omen "
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#===============================================================================================================
# [[2600]] Misc Map Like
#===============================================================================================================
# !! Waypoint c10.fragments.special : "Special Keys - Pinnacle, Logbook"

Show # $type->maplike->special $tier->superkeys
	Class == "Pinnacle Keys"
	SetFontSize 42
	SetTextColor 240 0 0 255
	SetBorderColor 240 0 0 255
	SetBackgroundColor 70 0 20 255
	PlayAlertSound 3 300
	PlayEffect Orange
	MinimapIcon 0 Orange Pentagon

Show # $type->maplike->special $tier->logbooks
	Class "Logbook"
	SetFontSize 42
	SetTextColor 240 0 0 255
	SetBorderColor 240 0 0 255
	SetBackgroundColor 70 0 20 255
	PlayAlertSound 3 300
	PlayEffect Orange
	MinimapIcon 0 Orange Pentagon

#===============================================================================================================
# [[2700]] Splinters, Tablets, Fragments
#===============================================================================================================
# !! Waypoint c10.fragments.most : "Fragments and Splinters"

Show # $type->currency->splinter $tier->t1
	StackSize >= 25
	Class == "Stackable Currency"
	BaseType == "Breach Splinter" "Simulacrum Splinter"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 220 0 255 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Kite

Show # $type->currency->splinter $tier->t2
	StackSize >= 10
	Class == "Stackable Currency"
	BaseType == "Breach Splinter" "Simulacrum Splinter"
	SetFontSize 45
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 220 0 255 255
	PlayAlertSound 2 300
	PlayEffect Purple
	MinimapIcon 0 Red Kite

Show # $type->currency->splinter $tier->t3
	StackSize >= 5
	Class == "Stackable Currency"
	BaseType == "Breach Splinter" "Simulacrum Splinter"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 180 75 225 255
	PlayAlertSound 2 300
	PlayEffect Purple
	MinimapIcon 1 Orange Kite

Show # $type->currency->splinter $tier->t4
	StackSize >= 2
	Class == "Stackable Currency"
	BaseType == "Breach Splinter" "Simulacrum Splinter"
	SetFontSize 40
	SetTextColor 200 75 200 255
	SetBorderColor 200 75 200 255
	SetBackgroundColor 50 0 75
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 Yellow Kite

Show # $type->currency->splinter $tier->t5
	Class == "Stackable Currency"
	BaseType == "Breach Splinter" "Simulacrum Splinter"
	SetFontSize 38
	SetTextColor 200 75 200 255
	SetBorderColor 200 75 200 255
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 White Kite

Show # $type->fragments->generic $tier->s
	BaseType == "An Audience with the King" "Breachstone" "Simulacrum"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->fragments->generic $tier->a
	BaseType == "Cowardly Fate" "Deadly Fate" "Victorious Fate"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 220 0 255 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Hexagon

Show # $type->fragments->generic $tier->b
	BaseType == "Ritual Precursor Tablet"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 220 0 255 255
	PlayAlertSound 2 300
	PlayEffect Purple
	MinimapIcon 1 Yellow Hexagon

Show # $type->fragments->generic $tier->c
	BaseType == "Breach Precursor Tablet" "Delirium Precursor Tablet" "Expedition Precursor Tablet"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 180 75 225 255
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 White Hexagon

Show # $type->fragments->generic $tier->d
	BaseType == "Precursor Tablet"
	SetFontSize 40
	SetTextColor 200 75 200 255
	SetBorderColor 200 75 200 255
	SetBackgroundColor 50 0 75
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 2 White Hexagon

#Show # $type->fragments->generic $tier->e
#	SetFontSize 38
#	SetTextColor 180 75 225 255
#	PlayEffect Purple Temp
#	MinimapIcon 2 Grey Hexagon

Hide # $type->fragments->generic $tier->exhide
	BaseType == "Breach Precursor Tablet" "Delirium Precursor Tablet" "Expedition Precursor Tablet" "Precursor Tablet" "Ritual Precursor Tablet"
	SetFontSize 18
	SetBackgroundColor 20 20 0 0

Show # $type->fragments->generic $tier->restex
	Class "Map Fragments" "Tablet"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#===============================================================================================================
# [[2800]] Misc Map Items
#===============================================================================================================
# !! Waypoint c10.ascendancy.all : "Trial Keys"

Show # $type->miscmapitemsextra $tier->trialkeyultimatumreward
	Rarity Magic Rare Unique
	BaseType == "Inscribed Ultimatum"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 220 0 255 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Red Hexagon

Show # %HS4 $type->miscmapitemsextra $tier->trialkeysanctumtop
	ItemLevel >= 80
	BaseType == "Djinn Barya" "Test of Cunning Barya" "Test of Strength Barya" "Test of Time Barya" "Test of Will Barya"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 180 75 225 255
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 White Hexagon

Show # %H4 $type->miscmapitemsextra $tier->trialkeysanctumhigh
	ItemLevel >= 75
	ItemLevel <= 79
	BaseType == "Djinn Barya" "Test of Cunning Barya" "Test of Strength Barya" "Test of Time Barya" "Test of Will Barya"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 180 75 225 255
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 White Hexagon

Hide # %H3 $type->miscmapitemsextra $tier->trialkeysanctumlow
	ItemLevel <= 74
	BaseType == "Djinn Barya" "Test of Cunning Barya" "Test of Strength Barya" "Test of Time Barya" "Test of Will Barya"
	SetFontSize 40
	SetTextColor 200 75 200 255
	SetBorderColor 200 75 200 255
	SetBackgroundColor 50 0 75

Show # %HS4 $type->miscmapitemsextra $tier->trialkeyultimatumtop
	ItemLevel >= 80
	BaseType == "Inscribed Ultimatum"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 180 75 225 255
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 White Hexagon

Show # %H4 $type->miscmapitemsextra $tier->trialkeyultimatumhigh
	ItemLevel >= 75
	ItemLevel <= 79
	BaseType == "Inscribed Ultimatum"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 180 75 225 255
	PlayAlertSound 2 300
	PlayEffect Purple Temp
	MinimapIcon 1 White Hexagon

Hide # %H3 $type->miscmapitemsextra $tier->trialkeyultimatumlow
	ItemLevel <= 74
	BaseType == "Inscribed Ultimatum"
	SetFontSize 40
	SetTextColor 200 75 200 255
	SetBorderColor 200 75 200 255
	SetBackgroundColor 50 0 75

Show # $type->miscmapitemsextra $tier->relickeyssafe
	Class == "Vault Keys"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

#===============================================================================================================
# [[2900]] Remaining Currency
#===============================================================================================================

Show # $type->currency $tier->restex
	Class == "Stackable Currency"
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#===============================================================================================================
# [[3000]] Uniques
#===============================================================================================================
# !! Waypoint c11.uniques.all : "Tierlist - Uniques - All"

#------------------------------------
#   [3001] Exceptions #1
#------------------------------------

Show # $type->uniques $tier->sekhemaring
	Sockets > 0
	Rarity Unique
	BaseType == "Ring"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 188 96 37 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Yellow Star

#------------------------------------
#   [3002] Tier 1 and 2 uniques
#------------------------------------
# !! Waypoint c11.uniques.t1 : "Tierlist - Uniques - T1, T2"

Show # $type->uniques $tier->t1
	Rarity Unique
	BaseType == "Armoured Cap" "Emerald" "Furtive Wraps" "Incense Relic" "Ornate Belt" "Ring" "Ruby" "Sapphire" "Smuggler Coat" "Stone Tower Shield" "Timeless Jewel" "Time-Lost Diamond" "Ultimate Life Flask" "Ultimate Mana Flask" "Utility Belt" "Vase Relic"
	SetFontSize 45
	SetTextColor 255 0 0 255
	SetBorderColor 255 0 0 255
	SetBackgroundColor 255 255 255 255
	PlayAlertSound 6 300
	PlayEffect Red
	MinimapIcon 0 Red Star

Show # $type->uniques $tier->t2
	Rarity Unique
	BaseType == "Altar Robe" "Burnished Gauntlets" "Conqueror Plate" "Crucible Tower Shield" "Diamond" "Feathered Tiara" "Fine Bracers" "Gold Amulet" "Grand Regalia" "Grand Visage" "Heavy Crown" "Wyrm Quarterstaff"
	SetFontSize 45
	SetTextColor 255 255 255 255
	SetBorderColor 255 255 255 255
	SetBackgroundColor 188 96 37 255
	PlayAlertSound 1 300
	PlayEffect Red
	MinimapIcon 0 Yellow Star

#------------------------------------
#   [3003] Multi-Unique bases.
#------------------------------------

Show # $type->uniques $tier->multispecialhigh
	Rarity Unique
	BaseType == "Amethyst Ring" "Sapphire Ring" "Stellar Amulet"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 188 96 37 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 1 Blue Star

Show # $type->uniques $tier->multispecial
	Rarity Unique
	BaseType == "Amber Amulet" "Azure Amulet" "Crimson Amulet" "Emerald Ring" "Gold Ring" "Jade Amulet" "Lazuli Ring" "Moulded Mitts" "Pearl Ring" "Solar Amulet" "Spiked Club" "Tribal Mask"
	SetFontSize 42
	SetTextColor 0 0 0 255
	SetBorderColor 0 0 0 255
	SetBackgroundColor 188 96 37 255
	PlayAlertSound 3 300
	PlayEffect Blue
	MinimapIcon 1 Blue Star

#------------------------------------
#   [3004] Low tier exceptions
#------------------------------------
# !! Waypoint c11.uniques.t1 : "Tierlist - Uniques - Low Tier Uniques"

#Show # $type->uniques $tier->earlyleague
#	Rarity Unique
#	SetFontSize 42
#	SetTextColor 188 96 37 255
#	SetBorderColor 188 96 37 255
#	SetBackgroundColor 53 13 13 255
#	PlayAlertSound 3 300
#	PlayEffect Brown
#	MinimapIcon 1 Brown Star

Show # $type->uniques $tier->corrupteduniques
	AnyEnchantment True
	Corrupted True
	Rarity Unique
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	SetFontSize 42
	SetTextColor 188 96 37 255
	SetBorderColor 250 0 0 255
	SetBackgroundColor 53 13 13 255
	PlayAlertSound 3 300
	PlayEffect Brown
	MinimapIcon 1 Brown Star

#------------------------------------
#   [3005] Tier 3 uniques 
#------------------------------------

Show # %H5 $type->uniques $tier->t3boss
	Rarity Unique
	BaseType == "Chain Tiara" "Explorer Armour" "Omen Crest Shield" "Shrine Sceptre" "Silk Robe"
	SetFontSize 42
	SetTextColor 188 96 37 255
	SetBorderColor 188 96 37 255
	SetBackgroundColor 53 13 13 255
	PlayAlertSound 3 300
	PlayEffect Brown
	MinimapIcon 2 Blue Star

Show # %H5 $type->uniques $tier->t3
	Rarity Unique
	BaseType == "Amphora Relic" "Bloodstone Amulet" "Brimmed Helm" "Champion Cuirass" "Chiming Staff" "Closed Helm" "Coffer Relic" "Crescent Quarterstaff" "Crude Bow" "Dualstring Bow" "Felt Cap" "Gold Circlet" "Grand Cuisses" "Grand Manchettes" "Iron Ring" "Knight Armour" "Lapis Amulet" "Lattice Sandals" "Linen Wraps" "Long Quarterstaff" "Lunar Amulet" "Pilgrim Vestments" "Rawhide Belt" "Ruby Ring" "Seal Relic" "Shortbow" "Sigil Crest Shield" "Solid Mask" "Spined Bracers" "Spired Greathelm" "Tapestry Relic" "Threaded Shoes" "Topaz Ring" "Torment Club" "Vaal Cuirass" "Velour Shoes" "Volatile Wand" "Wrapped Greathelm"
	SetFontSize 42
	SetTextColor 188 96 37 255
	SetBorderColor 188 96 37 255
	SetBackgroundColor 53 13 13 255
	PlayAlertSound 3 300
	PlayEffect Brown
	MinimapIcon 1 Brown Star

#------------------------------------
#   [3006] Tier 4 uniques
#------------------------------------

Show # %H4 $type->uniques $tier->hideable
	Rarity Unique
	BaseType == "Aged Cuffs" "Anchorite Garb" "Ashen Staff" "Attuned Wand" "Beaded Circlet" "Blazon Crest Shield" "Bone Raiment" "Bone Wand" "Braced Sabatons" "Braced Tower Shield" "Broadhead Quiver" "Bronze Greaves" "Chain Mail" "Cloaked Mail" "Covert Hood" "Cowled Helm" "Crescent Targe" "Crumbling Maul" "Crystal Focus" "Cultist Crown" "Doubled Gauntlets" "Effigial Tower Shield" "Elite Greathelm" "Emblem Crest Shield" "Embossed Boots" "Engraved Focus" "Face Mask" "Feathered Robe" "Feathered Sandals" "Felled Greatclub" "Fine Belt" "Fire Quiver" "Firm Bracers" "Forge Maul" "Full Plate" "Fur Plate" "Garment" "Gauze Wraps" "Gelid Staff" "Gilded Vestments" "Goldcast Cuffs" "Gothic Quarterstaff" "Guarded Helm" "Hardwood Targe" "Hermit Garb" "Hewn Mask" "Hexer's Robe" "Hooded Mask" "Horned Crown" "Hunter Hood" "Hunting Shoes" "Intricate Gloves" "Iron Crown" "Iron Cuirass" "Iron Greaves" "Ironclad Vestments" "Jewelled Gloves" "Jingling Crest Shield" "Keth Raiment" "Lace Hood" "Laced Boots" "Layered Gauntlets" "Leaden Greathammer" "Leather Vest" "Linen Belt" "Lizardscale Boots" "Long Belt" "Mail Belt" "Mail Sabatons" "Mail Vestments" "Makeshift Crossbow" "Marabout Garb" "Maraketh Cuirass" "Martyr Crown" "Oak Greathammer" "Omen Sceptre" "Painted Tower Shield" "Pathfinder Coat" "Pelage Targe" "Plate Belt" "Plated Mace" "Pyrophyte Staff" "Quilted Vest" "Raider Plate" "Rampart Tower Shield" "Rattling Sceptre" "Recurve Bow" "Rhoahide Coat" "Ringmail Gauntlets" "Riveted Mitts" "Rogue Armour" "Rope Cuffs" "Rough Greaves" "Rusted Cuirass" "Rusted Greathelm" "Scale Mail" "Scout's Vest" "Sectioned Bracers" "Secured Leggings" "Serpentscale Coat" "Shabby Hood" "Shaman Mantle" "Shielded Helm" "Silk Slippers" "Slim Mace" "Smithing Hammer" "Soldier Greathelm" "Sombre Gloves" "Spiritbone Crown" "Splintered Tower Shield" "Stacked Sabatons" "Steel Plate" "Steelpoint Quarterstaff" "Steeltoe Boots" "Stitched Gloves" "Stone Greaves" "Straw Sandals" "Studded Greatclub" "Studded Vest" "Suede Bracers" "Tattered Robe" "Tempered Mitts" "Tense Crossbow" "Tonal Focus" "Torn Gloves" "Trimmed Greaves" "Twig Circlet" "Twig Focus" "Vagabond Armour" "Veiled Mask" "Visceral Quiver" "Visored Helm" "Voltaic Staff" "Votive Raiment" "Warrior Greathelm" "Waxed Jacket" "Wayfarer Jacket" "Wicker Tiara" "Wide Belt" "Wooden Club" "Woven Focus" "Wrapped Quarterstaff" "Wrapped Sandals"
	SetFontSize 40
	SetTextColor 188 96 37 255
	PlayAlertSound 3 300
	PlayEffect Brown
	MinimapIcon 2 Brown Star

Show # $type->uniques $tier->restex
	Rarity Unique
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon

#===============================================================================================================
# [[3100]] Leveling - Salvagable
#===============================================================================================================
# !! Waypoint c20.leveling.salvagable.all: "Leveling - Salvagable bases"

# Double Quality Currencies

Show # %D4 $type->leveling->salvagable $tier->quality2martialany
	Quality >= 10
	Rarity Normal Magic
	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Two Hand Maces"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 180 180 180

Show # %D4 $type->leveling->salvagable $tier->quality2casterany
	Quality >= 10
	Rarity Normal Magic
	Class == "Sceptres" "Staves" "Wands"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 180 180 180

Show # %D5 $type->leveling->salvagable $tier->quality2armorany
	Quality >= 10
	Rarity Normal Magic
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 180 180 180

# Single Quality Currencies

Show # %D4 $type->leveling->salvagable $tier->qualitymartialany
	Quality >= 1
	Rarity Normal Magic
	Class == "Bows" "Crossbows" "One Hand Maces" "Quarterstaves" "Two Hand Maces"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 180 180 180

Show # %D4 $type->leveling->salvagable $tier->qualitycasterany
	Quality >= 1
	Rarity Normal Magic
	Class == "Sceptres" "Staves" "Wands"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 180 180 180

Show # %D4 $type->leveling->salvagable $tier->qualityarmorany
	Quality >= 1
	Rarity Normal Magic
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 180 180 180

# Artificer Scraps

#Show # %D3 $type->leveling->salvagable $tier->socketslarge
#	Sockets > 0
#	Height >= 3
#	Rarity Normal Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel < 65
#	SetFontSize 40
#	SetBorderColor 127 127 127

#Show # %D3 $type->leveling->salvagable $tier->socketssmall
#	Sockets > 0
#	Height < 3
#	Rarity Normal Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel < 65
#	SetFontSize 40
#	SetBorderColor 180 180 180

#===============================================================================================================
# [[3200]] Leveling - Hide outdated leveling flasks
#===============================================================================================================
# !! Waypoint c20.leveling.flasks.hidelayer : "Leveling - All flask rules"

Hide # %H0 $type->hidelayer $tier->outdatedlevelflaska
	Quality 0
	Class == "Life Flasks" "Mana Flasks"
	BaseType "Lesser" "Medium"
	AreaLevel >= 15
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

Hide # %H0 $type->hidelayer $tier->outdatedlevelflaskb
	Quality 0
	Class == "Life Flasks" "Mana Flasks"
	BaseType "Grand" "Greater"
	AreaLevel >= 30
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

Hide # %H0 $type->hidelayer $tier->outdatedlevelflaskc
	Quality 0
	Class == "Life Flasks" "Mana Flasks"
	BaseType "Colossal" "Giant"
	AreaLevel >= 42
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

Hide # %H0 $type->hidelayer $tier->outdatedlevelflaskd
	Quality 0
	Class == "Life Flasks" "Mana Flasks"
	BaseType "Gargantuan"
	AreaLevel >= 52
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

Hide # %H0 $type->hidelayer $tier->outdatedlevelflaske
	Quality 0
	Class == "Life Flasks" "Mana Flasks"
	BaseType "Transcendent"
	AreaLevel >= 62
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

#===============================================================================================================
# [[3300]] Leveling - Life Mana Flasks
#===============================================================================================================
# !! Waypoint c20.leveling.flasks.qual : "Leveling - Quality Flasks"

Show # %D5 $type->leveling->flasks->quality $tier->max
	Quality >= 20
	Rarity Normal Magic
	Class == "Charms" "Life Flasks" "Mana Flasks"
	SetFontSize 38
	SetBorderColor 180 180 180
	SetBackgroundColor 10 60 40

Show # %D4 $type->leveling->flasks->quality $tier->high
	Quality >= 14
	Rarity Normal Magic
	Class == "Charms" "Life Flasks" "Mana Flasks"
	SetFontSize 38
	SetBorderColor 180 180 180
	SetBackgroundColor 10 60 40

#Show # %D3 $type->leveling->flasks->quality $tier->any
#	Quality >= 1
#	Rarity Normal Magic
#	Class == "Charms" "Life Flasks" "Mana Flasks"
#	SetFontSize 38
#	SetBorderColor 100 100 100
#	SetBackgroundColor 10 60 40

#------------------------------------
#   [3301] Life flasks
#------------------------------------
# !! Waypoint c20.leveling.flasks.progression : "Leveling - Flask Progression"

Show # $type->leveling->flasks->life $tier->t1
	Class == "Life Flasks"
	BaseType "Medium"
	AreaLevel <= 8
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t2
	Class == "Life Flasks"
	BaseType "Greater"
	AreaLevel <= 15
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t3
	Class == "Life Flasks"
	BaseType "Grand"
	AreaLevel <= 22
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t4
	Class == "Life Flasks"
	BaseType "Giant"
	AreaLevel <= 29
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t5
	Class == "Life Flasks"
	BaseType "Colossal"
	AreaLevel <= 39
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t6
	Class == "Life Flasks"
	BaseType "Gargantuan"
	AreaLevel <= 49
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t7
	Class == "Life Flasks"
	BaseType "Transcendent"
	AreaLevel <= 59
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->life $tier->t8
	Class == "Life Flasks"
	BaseType "Ultimate"
	AreaLevel <= 65
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

#------------------------------------
#   [3302] Mana flasks
#------------------------------------

Show # $type->leveling->flasks->mana $tier->t1
	Class == "Mana Flasks"
	BaseType "Medium"
	AreaLevel <= 8
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t2
	Class == "Mana Flasks"
	BaseType "Greater"
	AreaLevel <= 15
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t3
	Class == "Mana Flasks"
	BaseType "Grand"
	AreaLevel <= 22
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t4
	Class == "Mana Flasks"
	BaseType "Giant"
	AreaLevel <= 29
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t5
	Class == "Mana Flasks"
	BaseType "Colossal"
	AreaLevel <= 39
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t6
	Class == "Mana Flasks"
	BaseType "Gargantuan"
	AreaLevel <= 49
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t7
	Class == "Mana Flasks"
	BaseType "Transcendent"
	AreaLevel <= 59
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

Show # $type->leveling->flasks->mana $tier->t8
	Class == "Mana Flasks"
	BaseType "Ultimate"
	AreaLevel <= 65
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

#------------------------------------
#   [3303] Charms
#------------------------------------

Show # %D4 $type->leveling->charms $tier->selected
	Rarity Normal Magic
	BaseType == "Amethyst Charm" "Antidote Charm" "Dousing Charm" "Golden Charm" "Grounding Charm" "Stone Charm" "Thawing Charm"
	AreaLevel < 65
	SetFontSize 40
	SetBorderColor 100 100 100
	SetBackgroundColor 10 60 40

#Show # %D2 $type->leveling->charms $tier->any
#	Rarity Normal Magic
#	Class == "Charms"
#	AreaLevel < 65
#	SetFontSize 40
#	SetBorderColor 100 100 100
#	SetBackgroundColor 10 60 40

#===============================================================================================================
# [[3400]] Leveling - Rules
#===============================================================================================================
# !! Waypoint c21.leveling.gear.all : "Leveling - Gear - All"
#------------------------------------
#   [3401] Rares - Decorators
#------------------------------------
# !! Waypoint c21.leveling.decorators.all : "Leveling - Rares - Decorators"

#Show # $type->leveling->decorators->rare $tier->largerares
#	Width >= 2
#	Height >= 3
#	Rarity Rare
#	AreaLevel < 65
#	Continue

#Show # $type->leveling->decorators->rare $tier->mediumrares1
#	Width 1
#	Height >= 3
#	Rarity Rare
#	AreaLevel < 65
#	Continue

#Show # $type->leveling->decorators->rare $tier->mediumrares2
#	Width 2
#	Height 2
#	Rarity Rare
#	AreaLevel < 65
#	Continue

Show # $type->leveling->decorators->rare $tier->tinyrares
	Width <= 2
	Height 1
	Rarity Rare
	AreaLevel < 65
	SetBorderColor 220 220 0
	Continue

#------------------------------------
#   [3402] Rares - Universal
#------------------------------------

# !! Waypoint c21.leveling.rares.jewellery : "Leveling - Rares - Belts, Rings, Amulets"

Show # %D6 $type->leveling->rare->universal $tier->jewellery
	Rarity Rare
	Class == "Amulets" "Belts" "Rings"
	AreaLevel < 65
	SetFontSize 42
	SetBackgroundColor 75 75 0
	PlayEffect Yellow
	MinimapIcon 1 White Diamond

# !! Waypoint c21.leveling.rares.armors : "Leveling - Rares - Armour Pieces"

Show # %D4 $type->leveling->rare->armours $tier->ar
	BaseEnergyShield 0
	BaseEvasion 0
	BaseArmour > 0
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->armours $tier->ev
	BaseEnergyShield 0
	BaseEvasion > 0
	BaseArmour 0
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->armours $tier->es
	BaseEnergyShield > 0
	BaseEvasion 0
	BaseArmour 0
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->armours $tier->arev
	BaseEnergyShield 0
	BaseEvasion > 0
	BaseArmour > 0
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->armours $tier->ares
	BaseEnergyShield > 0
	BaseEvasion 0
	BaseArmour > 0
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->armours $tier->eves
	BaseEnergyShield > 0
	BaseEvasion > 0
	BaseArmour 0
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %H5 $type->leveling->rare->armours $tier->anythingearly
	Rarity Rare
	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"
	AreaLevel < 16
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->wands
	Rarity Rare
	Class == "Wands"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->sceptres
	Rarity Rare
	Class == "Sceptres"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->staves
	Rarity Rare
	Class == "Staves"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->bowsquivers
	Rarity Rare
	Class == "Bows" "Quivers"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->crossbows
	Rarity Rare
	Class == "Crossbows"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->onehandmaces
	Rarity Rare
	Class == "One Hand Maces"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->twohandmaces
	Rarity Rare
	Class == "Two Hand Maces"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

Show # %D4 $type->leveling->rare->weapons $tier->quarterstaves
	Rarity Rare
	Class == "Quarterstaves"
	AreaLevel < 65
	SetFontSize 40
	SetBackgroundColor 20 20 0 255

#------------------------------------
#   [3403] Rares - Other
#------------------------------------
# !! Waypoint c21.leveling.rares.low : "Leveling - Gear - Low Tier"

Hide # %H3 $type->leveling->rare->remaining $tier->any class == "body armours" "gloves" "boots" "helmets" "shields" "foci" "staves" "sceptres" "wands" "one hand maces" "quarterstaves" "two hand maces" "bows" "crossbows" "quivers" "amulets" "belts" "rings"
	Rarity Rare
	AreaLevel < 65
	SetFontSize 38
	SetBackgroundColor 35 35 35 240

#===============================================================================================================
# [[3500]] Leveling - Useful magic and normal items
#===============================================================================================================
#------------------------------------
#   [3501] Decorators
#------------------------------------
# !! Waypoint c21.leveling.magicvendor.all : "Leveling - Normal and Magic - Magic Vendor Items"

Show # $type->decorators->leveling->magic $tier->largemagic
	Width >= 2
	Height >= 3
	Rarity Magic
	AreaLevel < 65
	SetFontSize 38
	Continue

Show # $type->decorators->leveling->magic $tier->medium1
	Width 1
	Height >= 3
	Rarity Magic
	AreaLevel < 65
	SetFontSize 38
	Continue

Show # $type->decorators->leveling->magic $tier->medium2
	Width 2
	Height 2
	Rarity Magic
	AreaLevel < 65
	SetFontSize 38
	Continue

Show # $type->decorators->leveling->magic $tier->noticeearly
	Rarity Magic
	AreaLevel <= 9
	SetFontSize 40
	Continue

Show # $type->decorators->leveling->magic $tier->tiny
	Width <= 2
	Height 1
	Rarity Magic
	AreaLevel < 65
	SetFontSize 40
	Continue

#------------------------------------
#   [3502] Purpose Picked Items
#------------------------------------

# !! Waypoint c21.leveling.normalmagic : "Leveling - Remarkable Normal and Magic Gear"

Show # %D4 $type->leveling->normalmagicremarkable $tier->jewellery
	Rarity Normal Magic
	Class == "Amulets" "Belts" "Rings"
	SetFontSize 42
	SetBackgroundColor 30 0 70 255

Show # %D5 $type->leveling->normalmagicremarkable $tier->earlyboots
	Rarity Magic
	Class == "Boots"
	AreaLevel <= 32
	SetFontSize 40
	SetBackgroundColor 30 0 70 255

#------------------------------------
#   [3503] Conditional Rules
#------------------------------------
# !! Waypoint c21.leveling.firstlevels.all : "Leveling - Normal and Magic - First Levels"

#Hide # %RH1 $type->leveling->progressivehide $tier->normal1
#	DropLevel < 8
#	Rarity Normal
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 22
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH1 $type->leveling->progressivehide $tier->normal2
#	DropLevel < 16
#	Rarity Normal
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 30
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH1 $type->leveling->progressivehide $tier->normal3
#	DropLevel < 24
#	Rarity Normal
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 40
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH1 $type->leveling->progressivehide $tier->normal4
#	DropLevel < 32
#	Rarity Normal
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 48
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH1 $type->leveling->progressivehide $tier->normal5
#	DropLevel < 40
#	Rarity Normal
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 56
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH1 $type->leveling->progressivehide $tier->normal6
#	DropLevel < 44
#	Rarity Normal
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 60
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH2 $type->leveling->progressivehide $tier->magic1
#	DropLevel < 8
#	Rarity Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 22
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH2 $type->leveling->progressivehide $tier->magic2
#	DropLevel < 16
#	Rarity Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 30
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH2 $type->leveling->progressivehide $tier->magic3
#	DropLevel < 24
#	Rarity Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 40
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH2 $type->leveling->progressivehide $tier->magic4
#	DropLevel < 32
#	Rarity Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 48
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH2 $type->leveling->progressivehide $tier->magic5
#	DropLevel < 40
#	Rarity Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 56
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Hide # %RH2 $type->leveling->progressivehide $tier->magic6
#	DropLevel < 44
#	Rarity Magic
#	Class == "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Shields" "Two Hand Maces"
#	AreaLevel >= 60
#	SetFontSize 18
#	SetBackgroundColor 20 20 0 0

#Show # %D3 $type->leveling->normalmagic->armours $tier->ar
#	BaseEnergyShield 0
#	BaseEvasion 0
#	BaseArmour > 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"

#Show # %D3 $type->leveling->normalmagic->armours $tier->ev
#	BaseEnergyShield 0
#	BaseEvasion > 0
#	BaseArmour 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"

#Show # %D3 $type->leveling->normalmagic->armours $tier->es
#	BaseEnergyShield > 0
#	BaseEvasion 0
#	BaseArmour 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"

#Show # %D3 $type->leveling->normalmagic->armours $tier->arev
#	BaseEnergyShield 0
#	BaseEvasion > 0
#	BaseArmour > 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"

#Show # %D3 $type->leveling->normalmagic->armours $tier->ares
#	BaseEnergyShield > 0
#	BaseEvasion 0
#	BaseArmour > 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"

#Show # %D3 $type->leveling->normalmagic->armours $tier->eves
#	BaseEnergyShield > 0
#	BaseEvasion > 0
#	BaseArmour 0
#	Rarity Normal Magic
#	Class == "Body Armours" "Boots" "Foci" "Gloves" "Helmets" "Shields"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->wands
#	Rarity Normal Magic
#	Class == "Wands"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->sceptres
#	Rarity Normal Magic
#	Class == "Sceptres"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->staves
#	Rarity Normal Magic
#	Class == "Staves"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->bowsquivers
#	Rarity Normal Magic
#	Class == "Bows" "Quivers"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->crossbows
#	Rarity Normal Magic
#	Class == "Crossbows"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->onehandmaces
#	Rarity Normal Magic
#	Class == "One Hand Maces"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->twohandmaces
#	Rarity Normal Magic
#	Class == "Two Hand Maces"

#Show # %D3 $type->leveling->normalmagic->weapons $tier->quarterstaves
#	Rarity Normal Magic
#	Class == "Quarterstaves"

#------------------------------------
#   [3504] Others
#------------------------------------

Show # %D5 $type->leveling->firstlevels $tier->firstareasmagic
	Rarity Magic
	AreaLevel <= 3
	SetFontSize 38

Show # %D5 $type->leveling->firstlevels $tier->firstareasnormal
	Rarity Normal
	AreaLevel <= 3
	SetFontSize 38

#Show # %D2 $type->leveling->magic->remaining $tier->rest
#	Rarity Magic
#	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	AreaLevel >= 24
#	AreaLevel <= 65

Show # %D4 $type->leveling->magic->remaining $tier->act2
	Rarity Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 16
	AreaLevel <= 24

Show # %D4 $type->leveling->magic->remaining $tier->act1
	Rarity Magic
	Class == "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Crossbows" "Foci" "Gloves" "Helmets" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	AreaLevel >= 9
	AreaLevel <= 16

# !! Waypoint c22.hide.all : "HIDELAYER - Hide all known untiered items"
#------------------------------------
#   [3505] Hide All known Section
#------------------------------------

#Show # %D0 $type->lowstrictnessshowlayer $tier->anyfinal
#	Class "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Charms" "Crossbows" "Foci" "Gloves" "Helmets" "Jewels" "Life Flasks" "Mana Flasks" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
#	SetFontSize 18
#	SetBorderColor 0 0 0 0
#	SetBackgroundColor 20 20 0 0
#	DisableDropSound True

Hide # $type->hidelayer $tier->final
	Class "Amulets" "Belts" "Body Armours" "Boots" "Bows" "Charms" "Crossbows" "Foci" "Gloves" "Helmets" "Jewels" "Life Flasks" "Mana Flasks" "One Hand Maces" "Quarterstaves" "Quivers" "Rings" "Sceptres" "Shields" "Staves" "Two Hand Maces" "Wands"
	SetFontSize 18
	SetBorderColor 0 0 0 0
	SetBackgroundColor 20 20 0 0
	DisableDropSound True

#------------------------------------
#   [3506] Show All unknown Section
#------------------------------------
# !! Waypoint c22.show.all : "SAFETYLAYER - Show all unknown items"
# THIS ENTRY IS CAUGHT IN 3 CASES:
# 1) YOUR FILTER IS OUT OF DATE!
# 2) YOU DID SOMETHING SILLY WHEN EDITING THE FILTER
# 3) YOU ENCOUNTERED A PREVIOUSLY UNKNOWN ITEM (VERY UNLIKELY)

Show # $type->anyremaining $tier->restex
	SetFontSize 45
	SetTextColor 0 255 255 255
	SetBorderColor 0 255 255 255
	SetBackgroundColor 255 0 255 255
	PlayAlertSound 3 300
	PlayEffect Pink
	MinimapIcon 0 Pink Pentagon
