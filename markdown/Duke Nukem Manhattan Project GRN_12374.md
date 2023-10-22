## Post #1
- Username: TheZombieKiller
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 11, 2014 9:48 am
- Post datetime: 2014-12-11T01:54:41+00:00
- Post Title: Duke Nukem Manhattan Project GRN

Hi,

I'm looking for somebody who may be able to crack Duke Nukem Manhattan Project's GRN model format.
I've searched all over for some sort of importer and exporter for the format, but I haven't found much.

Over here are some files that may aid in understanding the format: [https://www.dropbox.com/s/uhwdjrcjpezto ... ystuff.rar](https://www.dropbox.com/s/uhwdjrcjpeztoau/grannystuff.rar)

The farthest I've gotten is getting grn models over to the gr2 format, but even then, grnreader doesn't seem to be able to read the animation files,
so I can only really get static models out. Which still doesn't solve the issue of not being able to get them back into grn format.

Thanks in advance to anyone willing to help/contribute
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-11T18:28:23+00:00
- Post Title: Duke Nukem Manhattan Project GRN

how did you convert duke.grn to duke.gr2?

Your readme.txt says:
"grn2gr2.dll - File that can convert grn files to gr2, could possibly be used by a program to convert models"

Guess, I'd need
Granny Standard Exporter from the SDK? (which is not free?)
## Post #3
- Username: TheZombieKiller
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 11, 2014 9:48 am
- Post datetime: 2014-12-11T23:00:00+00:00
- Post Title: Duke Nukem Manhattan Project GRN

Whoops, forgot to mention how I did that.
I had to use a modified version of the free tool "Granny Viewer" that can read GRN files.
[http://forums.duke4.net/index.php?app=c ... ch_id=7683](http://forums.duke4.net/index.php?app=core&module=attach&section=attach&attach_id=7683)

Just drag the "grn" model of your choice onto the custom version of Granny Viewer, and wait for the model to convert. Then, if you want to convert it to an SMD, close Granny Viewer and open "gr2convert.bat" and type in the original name of the model or any name you want the resulting smd to have, eg, if you're converting "duke.grn", then just type duke and press enter.

Materials don't appear to remain intact.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-12T00:33:05+00:00
- Post Title: Duke Nukem Manhattan Project GRN

well, thx.
I had to use granny2.dll from your opening post, then duke.smd was created
and could be read into a 3D app.

So to sum up:
o you can read static .grn meshes and convert them to SMD

o For animations like duke_cartwheel.grn (0 meshes, 31 bones) grn_viewer.exe doesn't display
an object but creates a grn.gr2 file.

o The bat file doesn't create an SMD from grn.gr2. 
o The grnreader_a.exe creates an empty .ms file
and an SMD like this:
triangles 
end

Did I miss something?

Hopefully there are animations in the grn.gr2 file.
## Post #5
- Username: TheZombieKiller
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 11, 2014 9:48 am
- Post datetime: 2014-12-12T00:36:07+00:00
- Post Title: Duke Nukem Manhattan Project GRN

Nope, you haven't missed anything at all. That's basically all I've managed to do so far.
GrannyViewer seems to be able to convert animations to gr2, but grnreader has trouble converting the resulting gr2 files to smd files.

The goal here is to fix this, and to also get an exporter for the grn format, so that models can be added and/or replaced in the game.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-12T01:02:25+00:00
- Post Title: Duke Nukem Manhattan Project GRN

I'll have to sleep now.  

Don't know whether it will help but I would suggest to add debug lines to the grnreader.cpp
(just logging the addresses processed in the gr2 file.) -> edit: impossible, no access to granny2.dll

Then process duke.gr2 and the cart_wheel.gr2 to get some understanding of their structures.

(It's a static mesh and an animation file, yeah.
But that's the only idea I have atm.)

edit: (log)
duke.gr2
 tex_cnt 2
 mat_cnt 4
skel_cnt 1
vert_cnt 11
TriTop_cnt 11
msh_cnt 11
mod_cnt 1
TrGrp_cnt 1
ani_cnt 1
--------------------
cardwheel.gr2
 tex_cnt 0
 mat_cnt 0
skel_cnt 1
vert_cnt 0
TriTop_cnt 0
msh_cnt 0
mod_cnt 1
TrGrp_cnt 1
ani_cnt 1

I logged the members of t_Animations:

ani_Name: (unnamed)
ani_Duration: -1610612736
ani_TimeStep: -1610612736
ani_TrackGrpsCnt: 0

As you can see Duration and TimeStep are not valid.
(Since most things are hidden in granny2.dll which comes without debug info I'll stop my investigations here.)
