## Post #1
- Username: FauxBestaan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 09, 2009 2:37 am
- Post datetime: 2014-01-24T15:03:00+00:00
- Post Title: Cabal Online - EBM/ECH Import/Export scripts for 3ds Max

Downloads:

import_ebm_cabal.ms
export_ebm_cabal.ms
ui_ebm_cabal.ms
forge_small.png

Installation instructions:

Download "import_ebm_cabal.ms" and "export_ebm_cabal.ms" and put them in: YOUR_ACCOUNT_NAME\AppData\Local\Autodesk\3dsMax\YOUR_MAX_VERSION\ENU\scripts\
Download "ui_ebm_cabal.ms" and "forge_small.png" and put them in: YOUR_ACCOUNT_NAME\AppData\Local\Autodesk\3dsMax\YOUR_MAX_VERSION\ENU\scripts\startup\

Requirements:

3ds Max 2010 or newer.

Unsupported features:

Animations for models with magic key of 0x3EF03 or higher.  The animation list will still be populated, but no keys will be generated.
Animation exporting works, but it's just a tiny bit funky.  I'll look into why the animations are a little different and will fix it soon.

Usage notes:

To import an EBM/ECH, click the "Open..." button in the EBM properties panel (the one docked to the right with the Forge logo at the top).
To export an EBM/ECH, click the "Save..." button in the EBM properties panel.
You must complete all of the header information displayed in the EBM properties panel.  You will get an error when exporting if you don't provide values for each attribute, or you provide an incorrect value (ie. not adding a '%' after the scale).
If your model contains bones, they MUST be assigned to a "Skin" modifier attached to at least the first mesh in your scene.  The importer will automatically create this modifier and the exporter will read from this modifier if it exists.
If you want custom normals for your model, you need to add an "Edit Normals" modifier and store the normals there.  The importer will automatically create this modifier and the exporter will read from this modifier if it exists.
All meshes need to be of the Editable_Mesh type.  If your meshes aren't in this format, just select each mesh in turn, right-click the viewport, go to "Convert to:" and select "Convert to Editable Mesh".
Check "Export only mesh?" in the EBM options of the Forge toolbox in 3dsMax to only export the currently-selected mesh.  This is useful if you want to create or share custom armour.  The resulting .cmesh file can then be added directly to any ECH, or used to replace an existing piece of armour.
Cabal uses a different coordinate system from 3ds Max.  To see how you need to orient your models, use existing Cabal models as references.

If you have any issues with or suggestions for these scripts, feel free to reply to this thread.
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-02-21T05:49:58+00:00
- Post Title: Cabal Online - EBM/ECH Import/Export scripts for 3ds Max

good job dude, really you done, we still waiting for news about animations, thanks again for all.
## Post #3
- Username: FauxBestaan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 09, 2009 2:37 am
- Post datetime: 2014-02-23T11:22:41+00:00
- Post Title: Cabal Online - EBM/ECH Import/Export scripts for 3ds Max

I haven't done any work on this for a little while as I've had some other things to take care of, but I'll get back on it as soon as possible.
## Post #4
- Username: mm497905573
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 20, 2014 4:53 pm
- Post datetime: 2014-03-23T03:20:32+00:00
- Post Title: Cabal Online - EBM/ECH Import/Export scripts for 3ds Max

good job~Looking animated feature！
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-08T19:55:46+00:00
- Post Title: Cabal Online - EBM/ECH Import/Export scripts for 3ds Max

I don't really care for this game, so I was led to this thread by chance.
Nethertheless just a remark which should apply to some other threads in this forum, too:

As you may have noticed the thread is about 2 years old and its author provided his scripts via dropbox (thx, FauxBestaan   ).

>>> It's to be expected that such links will "expire" sooner or later.
The weeping will be great then.  

So it would be nice if we had people in this forum who felt obliged to care for such - for example by archiving those ms scripts in some way.

Another solution would be to ask authors "just in time" whether they agree to have their scripts "saved in the thread" via code tags or as an appended zip in case the scripts are too big.
