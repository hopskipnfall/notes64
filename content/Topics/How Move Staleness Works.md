---
publish: true
---
In an attempt to encourage users to use a variety of attacks, moves get *weakened* immediately after use. As you play, the game scales damage (and also knockback with the exception of throws) for attacks by keeping track of the most recent four that were used per player:

| Staleness Level                                                                                                                                                                                            | Attack                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| Stale 1 (maximum): Scale damage by 0.75^[These scaling constants came from the Smash Wiki article [Stale-move negation](https://www.ssbwiki.com/Stale-move_negation#Calculation_in_Smash_64)] and round up | (most recent attack goes here) |
| Stale 2: Scale damage by 0.82 and round up                                                                                                                                                                 | (second most recent attack)    |
| Stale 3: Scale damage by 0.89 and round up                                                                                                                                                                 | (third most recent attack)     |
| Stale 4: Scale damage by 0.96 and round up                                                                                                                                                                 | (fourth most recent attack)    |
Whenever an attack *does damage*, it goes into the top right box of that table, pushing any other moves down. If the attack is already in the table, it gets moved back up to the top.

Note that because damage is dealt in integers with damage scaling for stale moves rounding up, this means that any move doing 24% or less when fresh will do the same damage at stale 4.
# Practical example
```kotlin
// TODO
```
# Common questions
1. Do throws get stale?
   Yes but knockback is not affected
2. Are forward and back throw considered different moves?
   Yes
3. Do projectiles get stale?
   This is complicated and a little contrived. To answer this we have to break projectiles into two categories: *weapons* and *items*.
   
   *Weapons*: Fox's laser, the RayGun item's laser, fireballs, thunder jolt, fire flower, PK fire, Link's boomerang. These attacks that come from a player or are granted by an item *do stale*.
   
   *Items*: RayGun, Fan, Link's Bomb, shells. Damage done by an item not currently being held (including collision) *does not stale*.
