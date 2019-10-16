# Roguelike #

This week we're doing a dungeons and dragons style combat game. 

Initial requirements are below. 

- The game consists of a series of battles between the player and an opponent. A battle lasts until either the player or
  the opponent is reduced to zero hit points. 
    - If the player is reduced to zero hit points then the game is lost 
    - If the opponent is reduced to zero hit points then the player wins and will loot the corpse for treasure as a
      reward, and can then choose to either exit the dungeon with all the treasure collected so far, or to proceed to
      fight the next opponent
- Random number generation should simulate dice rolls, so 3d6 is three D6 (1-6) rolls added together, not one a 3-36
  random number
- The are three races:
    - Human
        - Hit points: 16
        - Armour class: 13
        - Weapon: Axe (+5 to hit, 1d12 damage) 
    - Goblin
        - Hit points: 4
        - Armour class: 10
        - Weapon: Scimitar (+4 to hit, 1d6+2 damage)
    - Hobgoblin
        - Hit points: 6
        - Armour class: 10
        - Weapon: Short sword (+5 to hit, 1d6+3 damage)
- The player is always human, while opponents are randomly selected as either a Goblin or a Hobgoblin
- Attacking works as follows:
    - The player always attacks first, then the opponent attacks
    - The attacker rolls 1d20 to hit and adds any modifiers. If the roll exceeds the defenders armour class then the
      defender takes damage according to the weapon damage
- When looting a corpse the player receives 1d3 gold pieces

Additional requirements -- feel free to add these incrementally! Trying to do all these from the outset would probably
be painful.

- Health potions
    - Players now start the fight with a potion of healing, which will restore all hit points if used
    - Players can heal between fights but cannot heal during a fight
- There is now a new race which the player may fight
    - Orc
        - Hit points: 8
        - Armour class: 12
        - Weapon: Sword (+5 to hit, 1d6+4 damage)
- Randomised health
    - Opponents now have randomised health
        - Goblin: 1d4
        - Hobgoblin: 1d6
        - Orc: 1d10
- Looting the corpse of an Orc gives a 25% of finding a potion of healing
- Weapon enchantment
    - Weapons can now be created as blessed, unenchanted, or cursed
    - Weapon enchantment is displayed as part of the name, so an opponent might wield a "Blessed Axe", an "Axe", or a "Cursed Axe"
    - Weapons have a 25% chance of being created blessed, which gives +1 to hit
    - Weapons have a 25% chance of being created cursed, which gives -1 to hit
- Weapon looting
    - When looting a corpse, the player can choose to replace their weapon with the one of the defeated opponent
- Weapon status effects
    - Weapons can now cause status effects on hit in addition to causing damage
    - Weapons have a 10% chance of being created with fire elemental effects
        - Fire weapons have a 25% chance of setting an opponent on fire, causing 1d3 damage each turn for the next two turns
    - Weapons have a 10% chance of being created with ice elemental effects
        - Ice weapons have a 25% chance of freezing an opponent, causing an additional 1d3 damage on hit
    - Weapons have a 10% chance of being created with thunder elemental effects
        - Thunder weapons have a 25% chance of shocking an opponent, causing the opponent to miss their next attack
    - Weapon status effects are displayed as part of the name, so an opponent might wield a "Blessed Axe of Thunder", or
      an "Axe of Fire"
- Intrinsic elemental affinities
    - Creatures can now be created with an intrinsic elemental affinity
        - Creatures have a 25% chance of being created with ice intrinsic
            - Ice creatures take 50% less damage from ice weapons, but double damage from fire weapons
        - Creatures have a 25% chance of being created with fire intrinsic
            - Fire creatures take 50% less damage from fire weapons, but double damage from ice weapons
    - A creature's intrinsic elemental affinity is displayed as part of its race, so an opponent might be a "Fire Orc"
      or an "Ice Goblin"

