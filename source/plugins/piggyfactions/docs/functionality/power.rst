Power
=====

Player
------

Player Power
~~~~~~~~~~~~

Player Power is the power that each player has. You can see your own, or others, power with ``/f player <player>``

* When a new player joins the server, the player will start off with ``0`` power.
* Players will passively gain ``2`` power per hour **while the player is online**.

  * No power is gained while the player is offline.
* An easy way to gain power is by killing other players, which gives ``1`` power per kill.

  * On the contrary, each death reduces the player's power by ``2``.
* Players can hold up to ``10`` power maximum and cannot go lower than ``0`` power unless changed.

To configure the power values for players, please refer to `Further Configuration#Power`_.

Player Power Boost
~~~~~~~~~~~~~~~~~~

Player Power Boost increases the maximum power which a player can hold.

Faction
-------

Faction Power
~~~~~~~~~~~~~

Faction Power is the power that each faction has. You can see your own, or others, power with ``/f info <faction>``

* Faction Power can be split up into two parts: current and maximum power.

  * Current Power: The cumulative CURRENT power of all players in the faction.

    * Current Power is important to keep in mind while claiming.
    * If your total land claims exceeds that of your current power, your land can be overclaimed by other factions.
  * Maximum Power: The cumulative MAXIMUM power of all players in the faction.

* Unlike FactionsPro,

  * Allying factions will not give additional power.
  * There is no minimum player requirement in order to claim land.
  * Creating a faction home does not require power.

Faction Power Boost
~~~~~~~~~~~~~~~~~~~

Faction Power Boost adds to both the current and maximum power of the faction.

.. _Further Configuration#Power: /plugins/piggyfactions/docs/further-configuration#Power