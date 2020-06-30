Claiming
========

Claiming in PiggyFactions is essentially identical to `MassiveCraft's Factions`_ plugin on Java Edition.

Claim System
------------
A chunk is defined as a ``16 x 16 x 256`` segment of land, and cannot be modified. You can use ``/f seechunks`` or ``/f sc`` to get a pseudo-visualization of the chunk boundaries. You should have your particle effects enabled. By default, each claim will cost the faction ``1`` power. This value can be modified in the configuration under ``factions.claims.cost``. Factions should use their power for claims sparingly, or they risk being `overclaimed`_.

In comparison, `FactionsPro`_ used an area-based claiming system that claims a ``25 x 25 x 256`` segment of land. The area-based system was not adopted because the implementation of a chunk-based system was far simpler.

Overclaiming
------------
Overclaiming is when a faction claims over an existing claim that belonged to another faction. A faction's land can only be overclaimed if the faction's total land claims exceeds that of their current power.

* To overclaim a faction's land...

  * Create a claim of your own right at the edge of their territory.
  * From that claim you just created, walk into their territory and claim again.
  * You can continue overclaiming until their power and land have reached equilibrium.

.. image:: /_static/img/piggyfactions/overclaiming.gif
    :align: center
    :alt: overclaiming gif

.. _MassiveCraft's Factions: https://www.massivecraft.com/factions
.. _overclaimed: /plugins/piggyfactions/docs/functionality/claiming.html#overclaiming
.. _FactionsPro: https://poggit.pmmp.io/p/FactionsPro/1.3.11-6