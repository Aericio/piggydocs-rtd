Further Configuration
=====================

This page will cover extra configuration settings that were not covered in the `Quick Start`_ guide.

.. contents:: Table of Contents

Databases
---------

+----------+-------------------------------------------------+
| database |                                                 |
+==========+==============+============+=====================+
|          | type         | ``sqlite`` |                     |
|          +--------------+------------+---------------------+
|          | **sqlite**   |                                  |
|          |              +------------+---------------------+
|          |              | file       | "factions.sqlite"   |
|          +--------------+------------+---------------------+
|          | **mysql**    |                                  |
|          |              +------------+---------------------+
|          |              | host       | ``localhost``       |
|          |              +------------+---------------------+
|          |              | username   | ``root``            |
|          |              +------------+---------------------+
|          |              | password   | ``""``              |
|          |              +------------+---------------------+
|          |              | schema     | ``"piggyfactions"`` |
|          +--------------+------------+---------------------+
|          | worker-limit | ``1``      |                     |
+----------+--------------+------------+---------------------+

.. databases

:type:
    Determines which database provider to use.

    Available Types: ``sqlite``, ``mysql``

:sqlite:
    This section lists the settings for the ``sqlite`` database provider.

    :file: The file name of the database in the plugin data folder. You can also put an absolute path here.

:mysql:
    This section lists the settings for the ``mysql`` database provider.

    :host: Your MySQL database's host address.

    :username: Your MySQL username. Avoid using the ``root`` user for security reasons.

    :password: Your MySQL user's password.

    :schema: The schema that PiggyFactions should use. The schema should be empty and created beforehand.

:worker-limit:
    Sets the maximum number of simultaneous SQL queries.

    libasynql's documentation recommends the limit to be set to ``1`` for ``sqlite`` and ``2`` for ``mysql``.
    If you are using MySQL, you may want to further increase this value if your MySQL connection is very slow.

Economy
-------

+---------+----------------------------------------------+
| economy |                                              |
+=========+==================+================+==========+
|         | enabled          | ``false``      |          |
|         +------------------+----------------+----------+
|         | provider         | ``economyapi`` |          |
|         +------------------+----------------+----------+
|         | **faction-bank** |                           |
|         |                  +----------------+----------+
|         |                  | enabled        | ``true`` |
+---------+------------------+----------------+----------+

.. economy

:enabled:
    Determines whether to enable economy features or not.

    Options: ``false``, ``true``

:provider:
    Determines which economy provider to use.

    Options: ``economyapi``, ``multieconomy``, ``xp``

:faction-bank:
    This section lists the settings for the faction bank.

    :enabled:
        Determines whether to enable faction bank or not.

        Options: ``true``, ``false``

Factions
--------

General
~~~~~~~

+----------+----------------------------+
| factions |                            |
+==========+===================+========+
|          | blacklisted-names | ``[]`` |
|          +-------------------+--------+
|          | max-name-length   | ``16`` |
|          +-------------------+--------+
|          | max-players       | ``50`` |
+----------+-------------------+--------+

:blacklisted-names:
    Determines which faction names should be prevented from being created.

    Example: ``["Owners", "Admins", "Pigs"]``

:max-name-length:
    Determines the maximum length of a faction's name.

:max-players:
    Determines the maximum amount of players that can be in a faction.

PVP
~~~

+--------------+--------------------------------+
| factions.pvp |                                |
+==============+=====================+==========+
|              | factionless         | ``true`` |
|              +---------------------+----------+
|              | between-factionless | ``true`` |
+--------------+---------------------+----------+

.. factions.pvp

:factionless:
    Whether to allow factionless players to attack players in factions.

    Options: ``true``, ``false``

:between-factionless:
    Whether to allow factionless players to attack other factionless players.

    Options: ``true``, ``false``

Power
~~~~~

+----------------+---------------------------+
| factions.power |                           |
+================+=========+========+========+
|                | default | ``0``  |        |
|                +---------+--------+--------+
|                | min     | ``0``  |        |
|                +---------+--------+--------+
|                | max     | ``10`` |        |
|                +---------+--------+--------+
|                | **per** |                 |
|                +---------+--------+--------+
|                |         | death  | ``-2`` |
|                |         +--------+--------+
|                |         | kill   | ``1``  |
|                |         +--------+--------+
|                |         | hour   | ``2``  |
+----------------+---------+--------+--------+

.. factions.power

:default: A player's default power when they first join the server.

:min: The minimum amount of power a player can have. Negative power is supported.

:max: The maximum amount of power a player can have.

:per:
    This section lists what should happen per...

    :death: The amount of power that should be deducted each death.

    :kill: The amount of power that should be gained each kill.

    :hour: The total amount of power that should be passively gained per hour.

Homes
~~~~~

+----------------+------------------------------+
| factions.homes |                              |
+================+===================+==========+
|                | within-territory  | ``true`` |
|                +-------------------+----------+
|                | teleport-on-death | ``true`` |
+----------------+-------------------+----------+

.. factions.homes

:within-territory:
    Whether to disallow ``/f sethome`` from being set outside of faction territory.

    Options: ``true``, ``false``

:teleport-on-death:
    Whether to teleport players to faction's home upon death.

    Options: ``true``, ``false``

Claims
~~~~~~

+-----------------+-----------------------------------------+
| factions.claims |                                         |
+=================+=====================+==========+========+
|                 | blacklisted-worlds  | ``[]``   |        |
|                 +---------------------+----------+--------+
|                 | **denied-commands** |                   |
|                 +---------------------+----------+--------+
|                 |                     | enemy    | ``[]`` |
|                 |                     +----------+--------+
|                 |                     | none     | ``[]`` |
|                 |                     +----------+--------+
|                 |                     | truce    | ``[]`` |
|                 |                     +----------+--------+
|                 |                     | ally     | ``[]`` |
|                 +---------------------+----------+--------+
|                 | overclaim           | ``true`` |        |
|                 +---------------------+----------+--------+
|                 | cost                | ``1``    |        |
|                 +---------------------+----------+--------+
|                 | max                 | ``-1``   |        |
|                 +---------------------+----------+--------+
|                 | shield-factor       | ``0.1``  |        |
+-----------------+---------------------+----------+--------+

.. factions.claims

:blacklisted-worlds:
    Determines which worlds should have claiming disabled in.

    Example: ``["hub", "shop", "plots"]``

:denied-commands:
    This section details what commands should be denied to the following relations when they are in a faction's territory:

    :enemy:
        Commands listed here will prevent **enemy** factions from using commands in a faction's territory.

        Example: ``["home", "spawn", "hub"]``

    :none: Commands listed here will prevent **factionless** players from using commands in a faction's territory.

    :truce: Commands listed here will prevent **truced** factions from using commands in a faction's territory.

    :ally: Commands listed here will prevent **allied** factions from using commands in a faction's territory.

:overclaim:
    Determines whether overclaiming is enabled or not. See `Claiming`_ for how overclaiming works in comparison to FactionsPro.

    Options: ``true``, ``false``

:cost: Determines the amount of power required per claim.

:max: Determines the max amount of claims which a faction can have. A value of ``-1`` means unlimited.

:shield-factor: Determines the damage reduction when a player gets attacked in their territory.

Languages
---------

+-----------+-------------------------+
| languages |                         |
+===========+=========+===============+
|           | default | ``"english"`` |
+-----------+---------+---------------+

.. factions.languages

:default:
    The default language that is set for all players.

    Available Languages: ``english``, ``chinese_simplified``, ``chinese_traditional``, ``german``, ``indonesian``, ``serbian``, ``spanish``

Symbols
-------

General
~~~~~~~

+---------+-----------------------+
| symbols |                       |
+=========+=============+=========+
|         | factionless | ``""``  |
|         +-------------+---------+
|         | powerless   | ``"0"`` |
+---------+-------------+---------+

.. symbols

:factionless: Symbol that is shown if the player is factionless.

:powerless: Symbol that is shown if the player is powerless.

Relation Colors
~~~~~~~~~~~~~~~

+--------------------------+---------------------------------+
| symbols.colors.relations |                                 |
+==========================+==========+======================+
|                          | member   | ``"{GREEN}"``        |
|                          +----------+----------------------+
|                          | ally     | ``"{DARK_PURPLE}"``  |
|                          +----------+----------------------+
|                          | truce    | ``"{LIGHT_PURPLE}"`` |
|                          +----------+----------------------+
|                          | neutral  | ``"{WHITE}"``        |
|                          +----------+----------------------+
|                          | enemy    | ``"{RED}"``          |
|                          +----------+----------------------+
|                          | safezone | ``"{GOLD}"``         |
|                          +----------+----------------------+
|                          | warzone  | ``"{DARK_RED}"``     |
+--------------------------+----------+----------------------+

.. symbols.colors.relations

:member: The relationship color for Members of your faction.

:ally: The relationship color for allied factions.

:truce: The relationship color for truced factions.

:neutral: The relationship color for neutral factions.

:enemy: The relationship color for enemy factions.

:safezone: The relationship color of the Safezone faction.

:warzone: The relationship color of the Warzone faction.

Ranks
~~~~~

+---------------+-------------------+
| symbols.ranks |                   |
+===============+=========+=========+
|               | leader  | ``"^"`` |
|               +---------+---------+
|               | officer | ``"*"`` |
|               +---------+---------+
|               | member  | ``"+"`` |
|               +---------+---------+
|               | recruit | ``"-"`` |
|               +---------+---------+
|               | none    | ``""``  |
+---------------+---------+---------+

.. symbols.ranks

:leader: The rank symbol for Leaders.

:officer: The rank symbol for Officers.

:member: The rank symbol for Members.

:recruit: The rank symbol for Recruits.

:none: The rank symbol for factionless players.

Forms
-----

.. forms

:forms:
    Whether to enable Forms or not.

    Options: ``true``, ``false``

.. _Quick Start: /plugins/piggyfactions/docs/quickstart.html
.. _Claiming: /plugins/piggyfactions/docs/functionality/claiming.rst