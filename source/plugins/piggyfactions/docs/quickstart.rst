Quick Start Guide
=================

.. contents:: Table of Contents

Installation
------------

#. Download the plugin from `Poggit`_, or click :download:`PiggyFactions <https://poggit.pmmp.io/get/PiggyFactions>`.
#. Install the plugin by placing it in the ``plugins/`` directory.
#. Start your server to generate the configuration files, then stop the server.

Configuration
-------------

#. Navigate to ``plugins/PiggyFactions/``
#. Open ``config.yml``

   #. Setup the data provider that PiggyFactions will be using.

      #. By default, PiggyFactions will use SQLite3. No additional setup is required. (RECOMMENDED)
      #. Optionally, PiggyFactions can also use MySQL:

         #. Change ``database.type`` from ``sqlite`` to ``mysql``.
         #. Enter your MySQL credentials in the ``database.mysql`` field.
         #. Change ``worker-limit`` from ``1`` to ``2``.
   #. Changing Languages

      #. Navigate to ``lang/``
      #. Available languages are shown in this folder.

         #. To change the default language, simply change ``languages.default`` to the language's file name.
         #. A player can change their own language with ``/f language <language>``.
   #. Toggle whether or not you want to enable forms with commands.

      * By default, this option is enabled. You can still run commands normally, or through a form.

Setting up your Chat Provider
-----------------------------

Currently, only `HRKChat`_ and `PureChat`_ :guilabel:`PR-17` supports PiggyFactions.

HRKChat
~~~~~~~

.. table::
    :align: center

    +------------------------------+-------------------------------+
    | Tag Name                     | Description                   |
    +==============================+===============================+
    | ``piggyfacs.name``           | Player's faction name         |
    +------------------------------+-------------------------------+
    | ``piggyfacs.power``          | Player's faction power        |
    +------------------------------+-------------------------------+
    | ``piggyfacs.rank.name``      | Your Faction's rank name      |
    +------------------------------+-------------------------------+
    | ``piggyfacs.rank.symbol``    | Your Faction's rank symbol    |
    +------------------------------+-------------------------------+
    | ``piggyfacs.members.all``    | Faction's total member count  |
    +------------------------------+-------------------------------+
    | ``piggyfacs.members.online`` | Faction's online member count |
    +------------------------------+-------------------------------+

.. code-block:: yaml
    :caption: A sample chat and nametag format for HRKChat.

    chatFormat:
      1: "&6{{piggyfacs.rank.symbol}}{{piggyfacs.name}} &r&7{{hrk.displayName}}&r: {{msg}}"
    nameTagFormat:
      1: "&6{{piggyfacs.rank.symbol}}{{piggyfacs.name}} &r&7{{hrk.displayName}}"

PureChat
~~~~~~~~

.. table::
    :align: center

    +------------------------------+------------------------------+
    | Tag Name                     | Description                  |
    +==============================+==============================+
    | ``{fac_name}``               | Player's faction name        |
    +------------------------------+------------------------------+
    | ``{fac_rank}``               | Player's faction rank symbol |
    +------------------------------+------------------------------+

.. code-block:: yaml
    :caption: A sample chat and nametag format for PureChat.

    groups:
      Guest:
        chat: '&7[Guest] &6{fac_rank}{fac_name} &r&7{display_name}&r: {msg}'
        nametag: '&7[Guest] &6{fac_rank}{fac_name} &f{display_name}'
        worlds: []

.. warning::
    You **must** use Poggit-CI :download:`PR-17 <https://poggit.pmmp.io/r/95436/PureChat_pr-17.phar>` build for PureChat support and set ``default-factions-plugin`` to ``PiggyFactions``.
    All other syntax remains the same. You can modify the rank symbols in PiggyFaction's ``config.yml``.

Setting up Safezones / Warzones
-------------------------------

#. Run the command ``/f admin``. This will allow you to bypass faction permissions.
#. Create a Safezone faction with ``/f create <name>``.
#. Flag the faction as a Safezone with ``/f flag <safezone|warzone>``.

   * This will remove the faction from ``/f top`` and prevent other factions from claiming the area.
   * Furthermore, the ``safezone`` flag will prevent combat.
#. Claim Safezone chunks with ``/f claim <auto|square|circle> <radius>``.
#. While you're still in admin mode, use ``/f leave`` to leave the faction.

   * This will allow you to leave the faction without disbanding it.
#. Run the command ``/f admin`` to exit admin mode.

.. note::
    You'll have to repeat this process twice: once for Safezone, once for Warzone.

You're done!
------------

* PiggyFactions is now setup.

  * For further configuration, see `Advanced Configuration`_.
  * For a list of Commands & Permissions, see `Commands and Permissions`_.

.. _Poggit: https://poggit.pmmp.io/p/PiggyFactions
.. _HRKChat: https://github.com/CortexPE/HRKChat
.. _PureChat: https://github.com/Heisenburger69/PureChat
.. _Advanced Configuration: /plugins/piggyfactions/docs/advanced-configuration.html
.. _Commands and Permissions: /plugins/piggyfactions/docs/commands-and-permissions.html