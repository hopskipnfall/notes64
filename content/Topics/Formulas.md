Source: https://docs.google.com/document/d/1KPPr9SnpEu0BW6DJjTcx93SpmnFCLO_jEyvd8F597Tc/edit?tab=t.0#heading=h.ipwltvrsqwko

Note: All resulting values will be ​​rounded down.



Hitlag

(Damage of hit / 3 + 5)

For electric attacks* = (Damage of hit / 3 + 5) * 1.5

For crouch cancel (for the character getting hit) = (Damage of hit / 3 + 5) * 0.6666667

For crouch cancel and electric attack* (for the character getting hit) = ((Damage of hit / 3 + 5) * 1.5) * 0.6666667

  

The increased hitlag doesn't apply against shields or hurtboxes with parry.

Hitlag lasts the same amount of frames for the attacker and the attacked character, except when crouch cancel is applied.



Knockback

$$
\lfloor ((1.4 W(0.1 D + 0.05 P D) + 18) S + B) CC \rfloor
$$

(((((D / 10 + (P * D) / 20) * W * 1.4) + 18) * S) + B) * CC

-P is the % of the target, counted after the attack damage is added.

-D is the damage the attack dealt.

-W is the weight of the target.

-S is the attack's knockback scaling, divided by 100.

-B is the attack's base knockback.

-CC is crouch cancel (0.67).

  

Weight list:

1 Donkey Kong: 0.83 

2 Samus: 0.92 

3 Yoshi: 0.93 

4-5 Captain Falcon, Link: 0.96 

6-8 Fox, Luigi, Mario: 1 

9 Ness: 1.1 

10 Pikachu: 1.16 

11 Kirby: 1.19 

12 Jigglypuff: 1.3

  
  
Fixed knockback

((((1 ＋ (10 * (FKV / 20)) * W * 1.4) ＋ 18) * S) + B) * CC  
  
FKV is the fixed knockback value. 

  

Hitstun

Knockback / 1.875

  

Shieldstun

Damage of hit * 1.62 + 4
