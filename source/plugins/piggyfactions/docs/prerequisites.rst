Prerequisites
=============

Requirements
------------

* `PocketMine-MP`_: 3.13.0+
* mysql or sqlite3 PHP extensions

  * These should already be installed in your PocketMine-MP PHP binaries.
  * If not, download your operating system's version at `jenkins.pmmp.io`_.
* Virions (pre-bundled in Poggit builds):

  * `DaPigGuy/libPiggyEconomy`_: 2.0.0+
  * `ParoxityTeam/Commando`_: 2.1.0+
  * `poggit/libasynql`_: 3.3.0+
  * `jojoe77777/FormAPI`_: 1.3+

Soft Dependencies
-----------------

* `PiggyCustomEnchants`_: 2.1.1+
* `HRKChat`_: 1.1.1+
* `PureChat`_: :download:`PR-15 <https://poggit.pmmp.io/r/88189/PureChat_pr-15.phar>`

.. note::
    You **must** use Poggit-CI :guilabel:`PR-15` build for PureChat support and set ``default-factions-plugin`` to ``PiggyFactions``.
    All other syntax remains the same. You can modify the rank symbols in PiggyFaction's ``config.yml``.

.. note::
    PiggyFactions is **NOT** compatible with FactionsPro's or FactionPE's database schemas.

.. _PocketMine-MP: https://github.com/pmmp/PocketMine-MP
.. _jenkins.pmmp.io: https://jenkins.pmmp.io/job/PHP-7.3-Aggregate
.. _DaPigGuy/libPiggyEconomy: https://github.com/DaPigGuy/libPiggyEconomy
.. _ParoxityTeam/Commando: https://github.com/ParoxityTeam/Commando
.. _poggit/libasynql: https://github.com/poggit/libasynql
.. _jojoe77777/FormAPI: https://github.com/jojoe77777/FormAPI
.. _PiggyCustomEnchants: https://poggit.pmmp.io/p/PiggyCustomEnchants
.. _HRKChat: https://github.com/CortexPE/HRKChat
.. _PureChat: https://github.com/Heisenburger69/PureChat