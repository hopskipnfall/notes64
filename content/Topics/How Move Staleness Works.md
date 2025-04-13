In an attempt to prevent players from abusing a few strong moves, moves get *weakened* immediately after use.

The game keeps track of 4 moves 

# Example scenario

You hit with a back air

The game keeps a list of your last 3 moves for staleness purposes. 

To prevent players from abusing a single move, 

The game keeps track of your last 3 unique moves when calculating staleness.

Throws *do* get stale, but unlike other moves it does not affect knockback.

- Whiffed moves do not count for staleness
- [ ] Do moves that hit on invincible characters count for staleness?
- [ ] Do moves that hit on invulnerable characters count for staleness?
- [ ] How do multi-move moves work?
- [ ] Projectiles?

[Smash Wiki Article](https://www.ssbwiki.com/Stale-move_negation#Calculation_in_Smash_64)
