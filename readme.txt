## Stack Experience Rebalance Mod 0.9

Stack Experience Rebalance redesigns the bonuses that creature stacks gain through the WoG stack experience system. Instead of using the original progression tables, the mod can apply configurable stat growth and a selected set of experience abilities for WoG creatures and, when the Third Upgrade Mod is active, TUM creatures.

----------------------------------------------------------------------------------------------------------------------
WHAT THE MOD CHANGES
----------------------------------------------------------------------------------------------------------------------

- Replaces the stack experience growth tables for Health, Attack, Defense, minimum and maximum Damage, and Speed.
- Allows the strength of these bonuses to be adjusted through the Difficulty Mod configuration window.
- Can remove the original experience abilities and replace them with a targeted ability set for supported WoG and Third Upgrade Mod creatures.
- Gives each supported WoG and TUM neutral creature one targeted stack-experience ability through separate configuration switches.
- Adds or updates creature specialty descriptions for affected TUM creatures.
- Includes optional native creature configuration files for supported TUM creatures.

The mod changes the bonuses earned from stack experience. It does not replace the underlying WoG stack experience system.

----------------------------------------------------------------------------------------------------------------------
CONFIGURABLE STAT GROWTH
----------------------------------------------------------------------------------------------------------------------

The configuration offers separate values for:

- Health: 0 to 200 percent total growth.
- Attack and Defense: 0 to 20 points of total growth.
- Minimum and maximum Damage: 0 to 200 percent total growth.
- Speed: 0 to 200 percent total growth.

The selected total is distributed across the ten stack experience ranks. Changes to the progression tables are applied when the game is entered or loaded.

Three quick presets are available by clicking the creature portraits at the top of the configuration window:

- Low: 50% Health, +5 Attack and Defense, 50% Damage, 0% Speed.
- Medium: 100% Health, +10 Attack and Defense, 100% Damage, 10% Speed. This is the recommended default.
- High: 150% Health, +15 Attack and Defense, 150% Damage, 20% Speed.

The preset names describe stack-experience growth, not game difficulty. Every value can still be adjusted separately with the arrow buttons. Clicking Medium restores the recommended default values.

----------------------------------------------------------------------------------------------------------------------
REBALANCED STACK EXPERIENCE ABILITIES
----------------------------------------------------------------------------------------------------------------------

When a corresponding ability option is active, supported creatures receive a selected ability as their stack experience increases. WoG faction creatures and both neutral packages receive exactly one targeted ability per creature. The TUM faction package retains its more extensive rebalanced selections. Examples include:

- Permanent combat enchantments such as Prayer, Stone Skin, Air Shield, Fortune, Mirth and elemental protection.
- Additional retaliations, double attacks, no-retaliation attacks and ranged-attack improvements.
- Spell immunity, magic resistance and damage reduction.
- Regeneration, summoning, spellcasting, Death Blow, Deflect and defense reduction.

The exact ability and its strength depend on the creature and its stack experience rank.

----------------------------------------------------------------------------------------------------------------------
REQUIREMENTS AND CURRENT INTEGRATION
----------------------------------------------------------------------------------------------------------------------

- Heroes of Might and Magic III with ERA 3 and the WoG stack experience system.
- Era Erm Framework is required.
- Difficulty Mod is optional and provides an additional entry to open the configuration window.
- Third Upgrade Mod is optional, but is required for the TUM creature stats and ability package.

The configuration window, default values and persistent settings are owned by this mod. Editable defaults are stored in `Lang/configuration.json`. Confirmed in-game settings are saved to `Runtime/stack experience rebalance.ini` and take precedence over the JSON defaults. Delete that INI to apply changed JSON defaults again. Difficulty Mod only provides an optional menu entry.

When TUM is not active, its section is marked as unavailable and its switches cannot be changed. Legacy of the Silence uses overlapping creature IDs; when it is detected, the TUM section is marked as blocked and all TUM-specific switches are disabled automatically.

----------------------------------------------------------------------------------------------------------------------
COMPATIBILITY NOTES
----------------------------------------------------------------------------------------------------------------------

When TUM rebalance options are enabled, the script obtains the current maximum creature ID and processes the supported TUM range beginning at ID 197. WoG's Dracolich at ID 196 remains part of the WoG neutral package. Other mods that reuse TUM IDs may have their stack experience tables changed or cleared. Legacy of the Silence is detected and automatically disables the TUM-specific switches. Test other creature packs with overlapping IDs carefully.

The optional native ability overrides are stored in `Data/disabled/Creatures`. ERA loads creature CFG files independently of the in-game options, so they are disabled by default. Move this folder to `Data/Creatures` only when TUM is active and no mod with overlapping creature IDs is enabled. If ACM is used, give ACM priority over TUM.

All four ability switches are functional. WoG faction creatures, WoG neutral creatures, TUM faction creatures, and TUM neutral creatures each receive one selected stack-experience ability when their corresponding option is enabled.

----------------------------------------------------------------------------------------------------------------------
INSTALLATION
----------------------------------------------------------------------------------------------------------------------

1. Copy the `Stack-Exp-Rebalance` folder into the ERA `Mods` directory.
2. Enable the mod in the ERA Mod Manager.
3. Enable the WoG stack experience option.
4. Optional: configure the rebalance through Difficulty Mod or edit `Lang/configuration.json` before starting a scenario.
5. Optional: activate the native TUM ability overrides as described under Compatibility Notes.

----------------------------------------------------------------------------------------------------------------------
LATEST CHANGELOG
----------------------------------------------------------------------------------------------------------------------

Version 0.9

- Made the mod independent from Difficulty Mod by moving loading and saving into the Stack Experience Rebalance scripts.
- Reloaded Runtime settings after map initialization or savegame loading so restored map variables cannot overwrite them.
- Added `Lang/configuration.json` with editable default values.
- Added one-time migration of existing Stack Experience settings from `Runtime/difficulty mod.ini`.
- Renamed the three quick selections to Low, Medium and High because they control stack-experience growth rather than game difficulty.
- Added functional Low, Medium and High presets, exact-preset highlighting and Medium as the recommended reset/default.
- Added translated section headings, clearer option names and mouse-over hints for presets, settings, values and controls.
- Added visible handling for an inactive Third Upgrade Mod and for Legacy of the Silence ID conflicts.
- Changed invalid or uninitialized progression values to the recommended Medium defaults.
- Confirming the configuration now explicitly activates the mod, including when the window is opened through Difficulty Mod or Ingame Menu.

- Moved native creature CFG overrides to the disabled folder so they are no longer loaded regardless of the selected options.
- Limited TUM table processing to the highest creature ID supported by this version instead of every registered creature.
- Added validation for all configurable progression values.
- Restored the original configuration dialogue element structure and corrected its declared element count.
- Made Cancel restore the complete configuration that was active before opening the window.
- Added a translated configuration title and completed the Russian creature descriptions.
- Updated option descriptions, compatibility notes and installation instructions.
- Added separate neutral-creature lists for WoG and TUM and assigned one targeted stack-experience ability to every supported neutral creature.
- Enabled the WoG and TUM neutral-creature configuration switches.
- Enabled the WoG faction-ability switch and assigned one targeted stack-experience ability to all 137 supported WoG faction creatures, including the nine level-8 creatures.
- Organized the WoG ability package into a dispatcher and separate, documented functions for every faction and the level-8 creatures.

Version 0.5 - Development version

- Added configurable stack experience growth for combat statistics.
- Added rebalanced experience abilities for supported Third Upgrade Mod creatures.
- Added compatibility handling for Legacy of the Silence creature-ID conflicts.
- Added creature configuration and specialty-description support.

----------------------------------------------------------------------------------------------------------------------
FEEDBACK
----------------------------------------------------------------------------------------------------------------------

For feedback, balance suggestions and bug reports, join the HoMM 3.5 ERA Mods Discord server:
https://discord.gg/hCTMfVq6w5

Stack Experience Rebalance Mod by PerryR.
