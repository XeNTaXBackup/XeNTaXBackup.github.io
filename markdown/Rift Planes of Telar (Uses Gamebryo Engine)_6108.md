## Post #1
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2011-02-20T10:39:28+00:00
- Post Title: Rift: Planes of Telar (Uses Gamebryo Engine)

Hi

There is new MMORPG - Rift: Planes of Telar, and it uses Gamebryo Engine and have nice models. So, i tried to use nif tools to import models, so i got to import some of the static meshes from Geometry .pak files, but the Nif files from Character .pak don't seem to import (I am interesting in import monster models). Did someone got to import them?. Or have some clues, why does it not importing?
## Post #2
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-02-26T05:48:47+00:00
- Post Title: Rift: Planes of Telar (Uses Gamebryo Engine)

Rift use version of Gamebryo Engine:

> Gamebryo File Format, Version 20.6.0.0
which currently unsupported by NIFSkope and NIFImporter (newest supported version 20.2.x.x). Try to use latest Blender-scripts for import those NIFs.
