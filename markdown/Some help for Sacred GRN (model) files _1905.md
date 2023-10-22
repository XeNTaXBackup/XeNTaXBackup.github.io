## Post #1
- Username: Paul Siramy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 04, 2005 6:31 pm
- Post datetime: 2006-05-18T09:54:00+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

I'm already able to extract the vertexs (vertices ?)  from any GRN files from Sacred (and Sacred +). I can also extract all textures. But since I'm not very good at 3D, I'm asking for help.

For those who are interested in decoding the Models (not the Motions), I have made [this zip](http://paul.siramy.free.fr/_divers2/sacred_modded/grn_samples.zip) (2.46 MB). It contains :
some GRN (from small to big sizes)
their textures (may help for UV mapping - if any)
images I made, 3 per GRN, showing Face (XY), Up (XZ), and Profile (ZY) view of the vertexs
screenshots of some models in-game
a readme.txt with additional information
The wiki Sacred page is [here](http://wiki.xentax.com/index.php/Sacred_PAK), it may or may not contains useful datas in helping to decode GRN.

I hope these GRN files will be more clear for you than for me. I have made this zip as good as I tought it could help you. If you need, I can provide you with any (all) GRN of the game, textures...

By the look of it, the GRN structure is very simple... But 3D is really not my cup of tea.
## Post #2
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-06-13T11:44:30+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

Tip: Take a look at the Iris2 project. They managed it to fully load/display *.grn (V1) files from Ultima Online:AOS+.

SVN is official. Sacred *.grn are little bit newer but are also V1 Grannys.
## Post #3
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-06-14T09:33:14+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

Yep. yesterday i checked Sacred *.grn models with our loader and they are working. Only scaling is a bit too big.

greetings.
## Post #4
- Username: jaycenornin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2007 7:07 am
- Post datetime: 2007-10-28T22:26:26+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

> Reply from Paul Siramy
>
> I'm already able to extract the vertexs (vertices ?)  from any GRN files from Sacred (and Sacred +). I can also extract all textures. But since I'm not very good at 3D, I'm asking for help.

For those who are interested in decoding the Models (not the Motions), I have made this zip (2.46 MB). It contains :
some GRN (from small to big sizes)
their textures (may help for UV mapping - if any)
images I made, 3 per GRN, showing Face (XY), Up (XZ), and Profile (ZY) view of the vertexs
screenshots of some models in-game
a readme.txt with additional information
The wiki Sacred page is here, it may or may not contains useful datas in helping to decode GRN.

I hope these GRN files will be more clear for you than for me. I have made this zip as good as I tought it could help you. If you need, I can provide you with any (all) GRN of the game, textures...

By the look of it, the GRN structure is very simple... But 3D is really not my cup of tea.

Are you still working on this at all? How far have you gotten? If you're still pursuing this I'd be willing to offer my assistance where I can. With the progress you've already made and some help from the IRIS2 source code I think it may be possible to write an import script for Blender.

I'm still trying to get the .pak files open, none of the extractors I've gotten are working - Game Extractor and MEX Commander don't seem to work for me.
## Post #5
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-11-06T09:22:41+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

You should try this tools:

[http://ingame.ingame.de//filebase/index ... ry&cid=321](http://ingame.ingame.de//filebase/index.php/?action=category&cid=321)
## Post #6
- Username: jaycenornin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2007 7:07 am
- Post datetime: 2007-11-12T08:46:04+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

> Reply from SiENcE
>
> You should try this tools:

http://ingame.ingame.de//filebase/index ... ry&cid=321

Thanks a million! That model extractor worked great. Now to get that into blender....
## Post #7
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2007-11-12T11:06:43+00:00
- Post Title: Some help for "Sacred" GRN (model) files ?

You can try our very old Grannyviewer for Granny Meshes v1. I think sacred's grn files are v1 files.

Get this Framework (it's for iris but grannyviewer is included):
[http://download.berlios.de/iris/Iris_De ... rk-0.4.zip](http://download.berlios.de/iris/Iris_Developer-Framework-0.4.zip)

I think you also need a Ultima Online Version to test this tool. Later you can reference to sacred models. But it's a bit tricky...so get an UO client first.

You also have to edit the /xml/config.xml file to setup the path to UO.

Then you can export a *.grn mesh to *.SMD fileformat. This you can load with blender.

Our Grannyviewer is a nice tool to see all animations and play around with textures.  Maximize the screenwindow to see all 3 controlsections on the left side. You can register and color clothes as well.

Sourcecode is also available via SVN.

[http://svn.berlios.de/svnroot/repos/iri ... nnyViewer/](http://svn.berlios.de/svnroot/repos/iris/developertools/GrannyViewer/)

or via svn-webbrowser:
[http://svn.berlios.de/wsvn/iris/develop ... rev=0&sc=0](http://svn.berlios.de/wsvn/iris/developertools/GrannyViewer/?rev=0&sc=0)
