:title: XO Laptop Lemonade Stand slides re-structured-text
:author: Fernando Ellis, Ian Furry, Ryan Stush, David Wilson
:description: Flock presentation slides
:keywords: presentation, XO Badges, Lemonade

----

Playtesting
===========

First we playtested Lemonade Stand to see what it was like.
Then we had children who fit the age group it was designed
for test it at different events we participated in.

We discoverd that some parts of the game were hard to underdatnd
and that some of games freatures where a bit too easy.

----

.. image:: images/lemonade-trillion.png

----

Balancing problems
==================

When we first started working with Lemonade Stand the game was too easy.

- Players could gain money way too fast.
- When players had lots of items events did nothing.

While we were changing Lemonade Stand  we often made the game too hard and
had to tone down the difficulty.

- ingredients cost more then selling price
- negative events could blitz the player into being stuck.

----

Balancing Fixes
===============

Balancing was a tricky dance.
We had to offer the player a challenge without being overwheliming.

To balance the game we gave everything numerical values.
Then created equations for each element being balance.
Results equaled planed scaled value based on dificulty selection.

----

Rewroking Random Events
=======================

Originaly
- All the events were in one array and chosen with a random number generator
- If random number went beyond array then there was no event.
- Events only had static effects.

Now
- Events seperated into two Arrays, one for positve events and one for negative.
- Events chosen with a weighted system that adjusts to difficulty
- Some of the rare events scale effect to progress of the player.

----

Recipes
=======

With more ingredients the ability to choose between multiple recipes
and for the player to be able to make their own became obvious. 

However since we haven't designed a good way to graphically choose
recipes, the code is in the game but currently unused.

----

Ingredients
===========

When we were creating different versions of stands it some the other stands seemed
like it would be more fun if there was wider verity of ingredients to use.

This required the way ingredients are called to be made more flexable.
