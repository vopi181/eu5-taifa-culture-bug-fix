Taifa Culture Fix for Europa Universalis V 1.4.x
=============================================

Requires Across the Pillars and its taifa subject type.

What it does
------------
New taifa subjects keep their primary culture when it matches their overlord
or is considered kindred by the overlord's culture. Otherwise their country
primary culture changes to the overlord's primary culture (normally Andalusi
for Granada). Existing invalid taifas are repaired on their monthly update.

This changes country primary culture only. It does not convert population,
province or character cultures, and adds no bonuses, events or decisions.

Installation
------------
Copy the taifa_culture_fix folder (including its hidden .metadata folder) to:
  %USERPROFILE%\Documents\Paradox Interactive\Europa Universalis V\mod\

The result must contain:
  mod\taifa_culture_fix\.metadata\metadata.json
  mod\taifa_culture_fix\in_game\common\subject_types\zz_taifa_culture_fix.txt

Restart EU5 and enable "Taifa Culture Fix" in the active playset/mod list.
Enable Across the Pillars as well. Load a copy of the campaign and advance
through a monthly tick to repair existing subjects, then inspect their culture.
Release a new taifa from Castilian or Portuguese territory to check new releases.
Matching and kindred cultures should remain unchanged.

Implementation and compatibility
------------------------------
The installed taifa script already sets only_overlord_or_kindred_culture=yes
but has an empty on_enable. This mod injects the culture guard from vanilla
dominion.txt and adds the documented subject on_monthly hook for existing saves.
It does not replace the full taifa definition or modify the game installation.
Other mods changing taifa on_enable/on_monthly may conflict. Recheck after
future game updates, especially once Paradox fixes the original issue.
Disabling the mod stops further corrections; culture changes already saved
remain in the campaign. Keep an unmodified save if you want to undo them.

Bug reports
-----------
https://forum.paradoxplaza.com/forum/threads/taifa-subjects-released-by-granada-use-castilian-portuguese-primary-culture-despite-overlord-or-kindred-culture-restriction.1947583/
https://forum.paradoxplaza.com/forum/threads/released-taifa-subjects-are-not-primary-or-kindred-culture.1947512/

Validation status
-----------------
Metadata parses, script braces balance, and the culture rule and scope links
were checked against the installed 1.4.5 scripts. An independent script review
found no issues. EU5 reached its main menu, but automated UI input did not work,
so mod recognition, actual release and monthly effects remain unverified.
The mod is copied to the local mod folder; enable it in the active playset.
