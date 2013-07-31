:title: XO Laptop Lemonade Stand slides re-structured-text
:author: Fernando Ellis, Ian Furry, Ryan Stush, David Wilson
:description: Flock presentation slides
:keywords: presentation, XO Badges, Lemonade, impress.js
:css: flock-slides.css

----

Mozilla Open Badges and XO Laptops
===================================

Fernando Ellis, Ian Furry, Ryan Stush, David Wilson
FOSS@RIT SURF

----

Outline
=========

- Mission Statement
    - OLPC
        -Deployments
    - Badges
        - Mozilla Open Badges
            - HASTAC
            - MacArthur Foundation
            - Anatomy of a badge
            - Backpack
    - Activities
        - Lemonade Stand
        - Sash
    - Challenges/Limitations
        - Datastore
        - School server
    - Localization
        - Gettext
        - Stand customization (ice cream, etc..)
    - Next Time...
        - Stable school server
        - Pushing badges to backpack
        - Additional challenges and badges
Acknowledgements


----

Mission Statement
==================

- To connect the Mozilla open badges infrastructure to XO Laptops to supply all children using the laptop with access to the skills and learning recognition provided by the program.

----

Mozilla Open Badges
======================

- Badges are a digital representation of skills learned outside the classroom

- Four examples of emerging learners that could benefit from badges

    - Kareem the High school student who applies himself to extracurriculars instead of rigid school system

    - Sarah the freelance programmer who has been coding since middle school and now feels a college degree has nothing more to offer her

    - Jin the aspiring artist who has grown a stable following within her community but wishes to move to a new city

    - Antony the middle aged worker who has to find a new job in a field that has greatly changed from when he entered it

- Juan Carlos the peruvian student who has been given an XO Laptop from his school in his village in the mountains and aspires to learn and share all technology has to offer

----

HASTAC & MacArthur Foundation
==============================

- Founding Partners of Mozilla Open Badges

- Both work towards increasing technological literacy in a digital age

    - MacArthur-Foundation_ believes educational equality to be a human right

    - HASTAC_ bridging the disconnect between technology and the humanities

.. _MacArthur-Foundation: http://www.macfound.org/about/

.. _HASTAC: http://www.hastac.org/about

- Differences:
    
    -MacArthur Foundation is an international foundation that raises money to invest in programs for human rights, international justice, peace and security, etc.

    -HASTAC is essentially an open-sourced attempt at having the people of all backgounds work together to supplement education with technology or search for ways to interconnect the two

----

Anatomy of a Badge 
====================

- Badges are stored on one's backpack at backpack.openbadges.org

- Issuer Details
    
    - Name

    - URL

    - Organization

- Badge Details

    - Name

    - Description

    - Criteria

----

.. image:: images/backpack-screenshot.png
   :width: 786px
   :height: 432px

----

School servers
=================

- Potential Benefits

    - Teachers could create badges easily accessed by all children in the school
    - Would an ideal world have internet everywhere? 

    - Effecient means of uploading/downloading badges 

- Difficulties
    
    - Not all XO deployments have internet

    - RIT's automatic de-authentication

    - Most recent release wasn't stable

    - install file configurations


----

Playtesting
=============

First we playtested Lemonade Stand to see what it was like.
Then we had children who fit the age group it was designed
for test it at different events we participated in.

We discoverd that some parts of the game were hard to underdatnd
and that some of games freatures where a bit too easy.

----

A New UI
==========

#. Old interface was too clunky
#. Poor readability and usability

----

.. image:: images/old-ui.png
    :width: 600px
    :height: 375px

.. image:: images/new-ui.png
    :width: 600px
    :height: 375px

----

.. image:: images/new-ui-profit.png
    :width: 800px
    :height: 600px

----

New Selections
=================

#. Language selection
#. Menu screen
#. Difficulty selection


----

.. image:: images/new-ui-selection.png
    :width: 800px
    :height: 600px

----

Balancing problems
=====================

When we first started working with Lemonade Stand the game was too easy.

- Players could gain money way too fast.
- When players had lots of items events did nothing.

While we were changing Lemonade Stand  we often made the game too hard and
had to tone down the difficulty.

- ingredients cost more then selling price
- negative events could blitz the player into being stuck.

----

.. image:: images/lemonade-trillion.png
    :width: 600px
    :height: 375px

----

Balancing Fixes
==================

Balancing was a tricky dance.
We had to offer the player a challenge without being overwheliming.

To balance the game we gave everything numerical values.
Then created equations for each element being balance.
Results equaled planed scaled value based on dificulty selection.

----

Reworking Random Events
==========================

Originaly
- All the events were in one array and chosen with a random number generator
- If random number went beyond array then there was no event.
- Events only had static effects.

Now
- Events seperated into two Arrays, one for positve events and one for negative.
- Events chosen with a weighted system that adjusts to difficulty
- Some of the rare events scale effect to progress of the player.

----

Sash
========

#. Activity for displaying the user's badges
#. Reads datastore object for badge information
#. Generates a badge from information received from DS object
#. Displays badge(s) onto the window
#. Tooltips provide useful information about the badges

----

.. image:: images/sash-ui.png
    :width: 800px
    :height: 600px

----

How does Sash work?
=======================

#. Activities that award badges use a badges library
#. Badges lib creates a DS object with a specific property: has_badges
#. Sash finds any DS object that has property 'has_badges: True'
#. Sash checks if that activity has awarded the user any badges
#. If so, Sash reads a symbolic link of the badge images that the badges lib created
#. Badges are then displayed in Sash with tooltip information such as the name, criteria, data acquired, etc.

----

Customization
=================

#. Don't like running a lemonade stand but wish you could make your own? ok, that's a thing.
#. Ability to create other types of stands. ex: Ice Cream Stand!
#. Users are able to load in their own sets of images to generate that new stand

----

.. image:: images/icecream-shop.png
    :width: 600px
    :height: 375px

.. image:: images/icecream-log.png
    :width: 600px
    :height: 375px

----

Ingredients
===============

When we were creating different versions of stands it some the other stands seemed
like it would be more fun if there was wider verity of ingredients to use.

This required the way ingredients are called to be made more flexable.

----

Recipes
============

With more ingredients the ability to choose between multiple recipes
and for the player to be able to make their own became obvious. 

However since we haven't designed a good way to graphically choose
recipes, the code is in the game but currently unused.

----

Localization
================

#. Created a Spanish translation for the game
#. Able to efficently generate any translation and get it working on the XO
#. Other project SkyTime has English, Spanish, and French.
#. Used gettext for translations

----

How to get translations to work
=================================

#. $python setup.py genpot
#. Generates a po/ directory with a <bundle_name>.pot file (rename to <bundle_name.po)
#. Edit the .po file and add your translations
#. $python setup.py dist_xo
#. Generates the locale/ directory where it stores the new .mo file
#. Add these next two lines of code at the beginning of the program
#. import gettext
#. lang = gettext.translation(<bundle_id>, 'locale/', languages=[<name_of_mo_file>])
#. _ = lang.ugettext
#. Every word you want translated, change it to _(<string>)

----

Acknowledgements
===================

- SURF at RIT
- FOSS@RIT
- Remy Decausemaker
- Professor Stephen Jacobs
- Ronald McNair Program

----

Questions
==============
????????????
