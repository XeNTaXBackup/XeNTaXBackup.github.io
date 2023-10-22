## Post #1
- Username: tempesttime
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 14, 2010 2:48 am
- Post datetime: 2010-09-14T20:57:07+00:00
- Post Title: Request: Persona 3 and 4 Models

Hello everyone.
For a while now I have been attempting to rip models from Persona 3 and 4. I managed to rip some *.GMO's from Persona 3 Portable, however even after enlisting the much appreciated help of a few people, the textures I ripped don't line up and the *.3ds model file I created from the file has errors of it's own.
I decided to start over again, this time by using the models from Persona 3 and 4 on the PS2 which, from the looks of it, use the same format to contain their models. This format is called an *.RMD file. I was hoping that someone might be able to help me, even if it means a simple program or Quickbms script, all help will be appreciated.
Thank you all so much.
## Post #2
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-09-22T00:14:23+00:00
- Post Title: Request: Persona 3 and 4 Models

Im very interested to this
## Post #3
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-11-22T05:35:38+00:00
- Post Title: Request: Persona 3 and 4 Models

Any lock on this subject?
I have seen some files and it seems compressed because I can not find any valid integer array or float array for 3d mesh data.
Also it seems like a archive because very different pattern is contained in a single file. which means may be texture and mesh are included in single file?
[N1_1.rar](https://xentaxbackup.github.io/file/3632_N1_1.rar)
## Post #4
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2010-12-09T20:18:28+00:00
- Post Title: Request: Persona 3 and 4 Models

I posted details on the format 2 years ago here
[viewtopic.php?f=16&t=3163&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=3163&start=15)

I attached a converted version of the RMD file you posted in object wavefront format with the textures

post a reply if you need more intel on how to rip the models
[N1_1.rar](https://xentaxbackup.github.io/file/3681_N1_1.rar)
## Post #5
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-12-09T23:55:01+00:00
- Post Title: Request: Persona 3 and 4 Models

@prototypesky
Wow you're awesome,If you don't mind can you please tell me how to rip the model 
Oh yeah also is it possible to extract digital devil saga and other shin megami tensei model from ps 2 game
## Post #6
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-12-16T01:23:20+00:00
- Post Title: Request: Persona 3 and 4 Models

I didn't check the files of the game yet... but looks like prototypesky already cracked this format...
## Post #7
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-12-17T02:08:44+00:00
- Post Title: Request: Persona 3 and 4 Models

Some random noobs test max script with the prototypesky info about the file and the bluearms file sample

```
*/

myfile="C:\\Documents and Settings\\Administrator\\Desktop\\N1_1\\N1_1.RMD"
f = fopen myfile "rb"

fseek f 720 #seek_set

read=readlong f

vertsArray=#()
tvertArray=#()
facesArray=#()

for a = 1 to 100 do (
vx = readfloat f
vy = readfloat f
vz = readfloat f
append vertsArray[vx,vz,vy]
append tvertArray[0,0,0]
)


msh = mesh vertices:vertsArray faces:facesArray
msh.numTVerts = tvertArray.count
buildTVFaces msh
convertTo msh PolyMeshObject

print read

gc()
fclose f
```


I just started with this and yeah the scripts fails   ...
## Post #8
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2011-01-01T18:47:58+00:00
- Post Title: Request: Persona 3 and 4 Models

Here is the rmd viewer use the cursor keys to rotate and scale the models
[RMDViewer.rar](https://xentaxbackup.github.io/file/3757_RMDViewer.rar)
## Post #9
- Username: Servizio
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 15, 2010 4:04 pm
- Post datetime: 2011-01-22T14:01:11+00:00
- Post Title: Request: Persona 3 and 4 Models

Apologies if this is the wrong place to ask, but is there a model viewer for Nocturne's .pb files? And better still, maybe a way to export models?

It seems like there might be one

[viewtopic.php?f=16&t=3163&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=3163&start=15)

in this thread, but cippyboy hasn't posted in two years.
## Post #10
- Username: sonia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 19, 2011 1:24 pm
- Post datetime: 2011-01-23T03:47:11+00:00
- Post Title: Request: Persona 3 and 4 Models

i think its hard to extract the model
## Post #11
- Username: feareffectinferno
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 13, 2011 1:43 am
- Post datetime: 2011-11-12T19:44:11+00:00
- Post Title: Request: Persona 3 and 4 Models

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-13T11:15:35+00:00
- Post Title: Request: Persona 3 and 4 Models

Don't think the Fear Effect models are related. This is Persona 3 and 4, by Atlus. Though I'd love to see support for Megaten titles, may not be very possible yet to convert them.
## Post #13
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-11-13T12:56:46+00:00
- Post Title: Request: Persona 3 and 4 Models

I'd love to see p3 and p4 model too for noesis since the rmd viewer can't export them with bones.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-11-14T04:48:20+00:00
- Post Title: Request: Persona 3 and 4 Models

Yeah, that is a major bummer I must say. Though animations and such may be hard. Head rotation, for example, is separate and seems to have its own thing.
## Post #15
- Username: feareffectinferno
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 13, 2011 1:43 am
- Post datetime: 2014-05-06T05:39:05+00:00
- Post Title: Request: Persona 3 and 4 Models

Hi.

I've extracted Fear Effect .WAD files, and I found a .RMD

But the RMD viewer can't open it.
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2014-05-06T19:05:41+00:00
- Post Title: Re: Request: Persona 3 and 4 Models

They are not the same format. Two completely different games, from different developers, in different periods.
## Post #17
- Username: prototypesky
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Oct 07, 2008 5:10 am
- Post datetime: 2015-01-02T02:13:47+00:00
- Post Title: Re: Request: Persona 3 and 4 Models

I believe a totally different developer from Atlus worked on Fear Effect they just happened to use the same extension name for 3d models I guess.
