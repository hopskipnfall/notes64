---
publish: true
---
In an attempt to encourage players to use a variety of attacks, moves get *weakened* immediately after use. As you play, the game scales damage and knockback (with the exception of throws) for attacks by keeping track of the most recent four that were used per player.

| Staleness Level                                             | Attack                         |
| ----------------------------------------------------------- | ------------------------------ |
| Stale 1 (maximum): Multiply damage by 0.75 and round up[^1] | (most recent attack goes here) |
| Stale 2: Multiply damage by 0.82 and round up               | (second most recent attack)    |
| Stale 3: Multiply damage by 0.89 and round up               | (third most recent attack)     |
| Stale 4: Multiply damage by 0.96 and round up               | (fourth most recent attack)    |

The game has a copy of this table for each player, and it describes how the attack's damage and knockback will change the next time it is used.

When an attack *does damage*, it goes into the top right box of that table, pushing any other moves down. If the attack is already in the table, it gets moved back up to the top. If an attack is in the "stale 4" slot and gets shifted down, it is removed from the staleness table and is no longer stale.

Note that because damage is dealt in integers with damage scaling for stale moves rounding up, this means that any move doing less than 25% damage when fresh will do the same damage at stale 4:

$$
\lceil 24 \cdot 0.96 \rceil = 24
$$

Since this describes almost all moves in the game, you can just remember this as a rule of thumb:

> After you hit someone with an attack, that attack is now maximum stale. Attack with *three different moves* to un-stale the first attack.
# Practical example
```kotlin
// TODO
```
# Projectiles
Link's boomerang gets stale, but not his bomb. How does projectile staling work?

This is complicated and a little contrived. To answer this we have to break projectiles into two categories: *weapons* and *items*.

*Weapons*: Fox's laser, the RayGun item's laser, fireballs, thunder jolt, fire flower, PK fire, Link's boomerang. These attacks that come from a player or are granted by an item *do stale*.

*Items*: RayGun, Fan, Link's Bomb, shells. Damage done by an item not currently being held (including collision) *does not stale*.
# Random facts
1. Throws do stale, but knockback is not affected.
2. Forward and back throws count as different moves.

[^1]: These scaling constants came from the Smash Wiki article [Stale-move negation](https://www.ssbwiki.com/Stale-move_negation#Calculation_in_Smash_64)
