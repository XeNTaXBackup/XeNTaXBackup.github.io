## Post #1
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2016-11-18T00:52:59+00:00
- Post Title: 7,62 High Calibre .ACT files

Hey everyone,

I'm looking to import and export .ACT files from the game 7,62 High Calibre. There's a few ways to do it, but I was hoping to have a script to import and export these static models in 3DS Max 2010.

The current method is using either an old version of Blender or Milkshape to import them as a .x file and export them as something generic, such as .obj. Then whenever you're ready to export them, use Blender 2.69 and a python script to export them. 
The issue is, I highly prefer using 3DS Max and I was hoping for a more streamlined workflow because while this fairly long process of Blender 2.49b -> 3DS Max -> Blender 2.69 is manageable for one or two models, adding quite a few models at a time makes this extremely tedious.

I've attached a sample model and texture, along with the python script for Blender, and I was really hoping for a script to import these .ACT files and export them in Max. I don't think this is anything particularly complicated, as it's easy to import in other programs and there's already an export script here for a different program working. It's an old game with a small community, but this would be a pretty great step in making the modding process for this game much more user-friendly.

Thanks so much for reading, I'll answer any other questions that might help you guys as well of course.
[762 high calibre sample.zip](https://xentaxbackup.github.io/file/11928_762 high calibre sample.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-18T08:39:10+00:00
- Post Title: 7,62 High Calibre .ACT files

looks like your sample is just a directx .x model, you should be able to change the extension from act to x
and import it directly to 3ds max. there is a older .x import plugin for 3ds max here that might work for you
[http://www.maxplugins.de/r2_files/alf/dximport.zip](http://www.maxplugins.de/r2_files/alf/dximport.zip)
found that link here
[http://answers.unity3d.com/questions/43 ... 3dmax.html](http://answers.unity3d.com/questions/43444/how-to-import-x-file-in-3dmax.html)

looks like there was another newer one released at some point here but the links are dead
[https://www.youtube.com/watch?v=V5wVAYlW-pU](https://www.youtube.com/watch?v=V5wVAYlW-pU)
the files were "kwxport.dle" and "max2k14ximport.dli"
maybe you can ask the guy if he can upload it again

you might at least be able to cut your steps in half if it can import your sample.
## Post #3
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2016-11-18T12:17:37+00:00
- Post Title: 7,62 High Calibre .ACT files

Ahh, you're a real hero! So the importer didn't seem to work, and the link for the exporter was dead, but...

This works as an importer: [http://mofo.pns.to/wibs/#5](http://mofo.pns.to/wibs/#5)

And I found a cached copy of the exporter!: [https://web.archive.org/web/20110726085 ... xport.org/](https://web.archive.org/web/20110726085410/http://kwxport.org/)

It imports properly it seems, and I haven't quite tested the exporter but I'm sure that should work just fine. If I have any issues I'll let you know but thanks SO MUCH!
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-18T13:07:58+00:00
- Post Title: 7,62 High Calibre .ACT files

> Reply from mouzerball1000
>
> This works as an importer: http://mofo.pns.to/wibs/#5
nice find! that should cover your *.x import/export needs
## Post #5
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2016-11-18T13:37:16+00:00
- Post Title: 7,62 High Calibre .ACT files

Well, I've hit another wall here. So it seems to import fine, and exporting works, but the model doesn't load in the game. I opened it up, and it seems like i'm just using the wrong export options. I've tried a few different combinations and can't seem to figure it out. 

I've attached a sample. The original.act is a base model in the game. You can open it in notepad if you want.
exported.act is what happens when I take that model and export it using the above exporter. I have pictures in there of my exporter settings as well in there.

They're both in plain text, but you can see when I export it... it's not quite the same. There's a lot of additional templates and a few missing that seem to show as corrupted in the game. Any idea what I've got wrong here?

If the exporter just won't work for this case, if anyone can somehow convert the python script in the OP to maxscript, that would be ideal if this doesn't seem to work out.
[ACT file comparison.zip](https://xentaxbackup.github.io/file/11931_ACT file comparison.zip)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-18T14:54:41+00:00
- Post Title: 7,62 High Calibre .ACT files

> Reply from mouzerball1000
>
> So it seems to import fine, and exporting works, but the model doesn't load in the game.
yeah importing is one thing but exporting has to be done a certain
way so your game can read the file data properly.
you will have to use Blender and that python script until a maxscript
solution comes along because it writes the header and data out in a way
the game expects to read it.
## Post #7
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2016-11-18T15:44:03+00:00
- Post Title: 7,62 High Calibre .ACT files

Yeah, I figured as much. Dang, it's such a shame because if you compare the files, they're so close. Ah well, if I have to just export in Blender it's like you said, just one less step. I'm hoping that maybe that python script might give someone enough of a head start to write an equivalent in max script. I know I'm expecting a little bit of a miracle since it's an old game with a minimal community but... Fingers crossed!

Really, really stupid question, but I wouldn't be able to run this python script in 3DS Max somehow, would I?
