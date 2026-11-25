> Mirror of [iceanimations/loader](https://github.com/iceanimations/loader), published by the studio under
> EPL 2.0. Kept here for reference; the original repository is the canonical one.

# loader

The Pipeline ToolBox: the Ice Scripts menu that every artist had in Maya, and the command library behind
it.

`icemenu.py` builds the menu from a config file, `command/command.py` wires each entry to the MEL or
Python that implements it, and the commands themselves live in `command/mel` (71 scripts) and
`command/libmel` (18 reusable procedures). `client/iceSetup.mel` and `client/userSetup.mel` are what put
it in front of an artist on login.

It is the repository the public [Pipeline ToolBox manual](https://github.com/iceanimations/PipelineTooBoxManual)
documents, which is why it is here.

## What is in it

- **The pivot toolbox**, a family of `ptb*` procedures in `libmel`: fit, centre, average, unify, display
  and group at pivots, with local axis handling. Small commands, used constantly.
- **Animation and character tools**: `poseMan.mel` (107 KB), `kk_controllers.mel` (65 KB), `CharSet`,
  `AnimClip`.
- **Farm and render**: `SubmitJobToDeadline.mel` (61 KB), `Ice_Render_GUI.mel`, `ICE_playBlast`,
  `ICE_quickTime`.
- **Scene and naming**: `ICE_removeNameSpace`, `ICE_copyObjNames`, `ICE_copyGrpNames`,
  `ICE_findPolyIntersections`, the curve and camera toolboxes, `ICE_LightTransaltor`.

71 of the 93 MEL files are menu commands, 18 are shared procedures, and the rest is setup.

## Dependencies

Maya, and TACTIC login for the entries that need a session. It is MEL and Python 2 of its era, and it is
not a package anybody can pip install; `deployer/` is how it reached artist machines.

## Authorship

125 commits between 2015 and 2021:

| Author | Commits |
|---|---|
| Qurban Ali | 81 |
| Talha Ahmed | 43 |
| unattributed | 1 |

The command library grew out of the team's needs, and Qurban Ali wrote the larger share of these
scripts, including the pivot toolbox and `poseMan`. I wrote part of the set and built the menu and
deployment around it. The commit log shows the split.

LICENSE
=======

Copyright 2021. Talha Ahmed. All rights reserved.

This work is licensed under the terms of Eclipse Public License - v 2.0.
For a copy see https://www.eclipse.org/org/documents/epl-2.0/EPL-2.0.txt
