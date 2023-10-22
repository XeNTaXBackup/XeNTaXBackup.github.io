## Post #1
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-14T15:54:02+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Needs to be fixed.  They export gibberish, but what appears to be an accurate file structure.  However, neither psp or photoshop will open the pcx's or tga's the archives contain, and the config files are filled with the random characters of death.

I am extremely interesting in getting this to work if you guys can do that.

Please let me know.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-15T14:55:44+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

OK, I will take a look at this as soon as possible - just need to get the demo or something so I have some files to work with.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-16T06:43:22+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Thanks much
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-16T13:43:16+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Hi again,

Yep, I downloaded the demo and fixed up the bugs in the Game Extractor plugins. The plugins will work with the Full Version of Game Extractor (they are in the latest update) and they *may* work with the basic version too. However, repacking the archives will definately only work in the full version.

For more information of Game Extractor - [http://www.watto.org/extract](http://www.watto.org/extract)

Attached below are the updated plugins - you can try them in the basic version by unzipping the attached file into your plugins/ directory.

Good luck. If you want something updated for MexCom, let us know too hey.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)

PS - Mr Mouse, I have more-or-less finished my contribution to the wiki, and have also updated the Hostile Waters specs to the correct ones.
[HostileWatersPlugins.zip](https://xentaxbackup.github.io/file/225_HostileWatersPlugins.zip)
## Post #5
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T04:14:10+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Doesn't appear to work in the basic.

I guess i'll have to wait til i can get 5 bucks into paypal before i can really test em on the full version, but oh well... its at least hope.
## Post #6
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T04:20:21+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Ah, yeah... if you can make one for MexCom, that'd be kewl... might work.

I have both, just not the full versions.  I got them both to see if either would work, and neither did... though to be honest the Game Extractor worked better... lil less gibberish
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-17T04:29:23+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

I will take a look to see if I can make one for the basic version for you if you want - send me an email so I don't forget.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-17T07:09:17+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

> Reply from Vagamus
>
> Ah, yeah... if you can make one for MexCom, that'd be kewl... might work.

I have both, just not the full versions.  I got them both to see if either would work, and neither did... though to be honest the Game Extractor worked better... lil less gibberish

Really? What gibberish?
## Post #9
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T08:18:24+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

This gibberish...

in the default.cfg file, from the game.mng archive of Hostile Waters:

xÅ“uÂ
## Post #10
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T08:22:31+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Oh, but the upside is, the structures appear to be correct.

Using the structure and file names i took from MexCom and GE, i was able to mod in some replacement sounds for a few weapons.

Bout the most i can do until i can see config files and such, but its still a nice step
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-17T08:51:06+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

You have pointed out an interesting phenomenon. The Hostile Waters script was converted from the old 16-bit version script, and probably not confirmed. 

Indeed, it was not confirmed. ( [viewtopic.php?t=631&start=0](http://forum.xentax.com/viewtopic.php?t=631&start=0) )

I have looked at it, and the MBX was screwed. The converter started the new script with the command "CleanExit" which causes the process to be abandoned even before it was started! I will have to fix that some time. 

As for the MNG, the files were extracted in compressed form. 

Here's a new script you can use that will extract everything correctly. 

```
ComType ZLib1 ;
IDString 0 ZGWH ;
Get FILECNTL Long 0 ;
For T = 1 to FILECNTL ;
Get FILENAME String 0 ;
SavePos CSO 0 ;
Get CS Long 0 ;
SavePos UCSO 0 ;
Get UCS Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FILESTART 0 ;
CLog FILENAME FO CS FOO CSO UCS UCSO ;
Next T ;

```


Or get the zipped BMS file. You will need the registered version to use it in the "Run custom script on..." function.
[MNG.zip](https://xentaxbackup.github.io/file/227_MNG.zip)
## Post #12
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T12:42:47+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

yargh. same result as with game extractor, i'm gonna have to wait to donate to test any of this.
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-17T13:45:10+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

OK well here is a plugin for Game Extractor (Basic) for the *.mng archives - I have tested it here at home successfully using the Basic version so it should be OK. However, I will not be able to add repack support to the Basic version because the archvie uses ZLib compression and there are bugs in the Basic version that prevent it from working. The full version, however, does do the repacking properly.

Unzip the attached file into your plugins/ directory, and run Game Extractor.

Good Luck! I could probably fix the dat/mbx plugin for the basic version if you want that as well - i didn't do it initially because you said that the mng archives were priority.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_MNG_ZGWH_Basic.zip](https://xentaxbackup.github.io/file/228_Plugin_MNG_ZGWH_Basic.zip)
## Post #14
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T15:51:34+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

Works brilliantly :p

I found only one problem so far... 

The PCX's are inverted looking (it looks like the TGA's are fine), i dunno whats up with that.  if you have psp or somethat that can view them, go look at them sometime.

All the text files, which i really wanted, seem to have come out perfectly... this is a big success 

The sounds from the audio.mng also appear to work perfectly 

The only fault i could find were the pcx's.

If i find anything else i will make it public here.

If nothing else, I owe both of you my full testing of this format, so you can make your programs both accurate and comprehensive.
## Post #15
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T15:53:17+00:00
- Post Title: Hostile Waters: Antaeus Rising; MNG and MBX file extraction

crap, also forgot... yes, yes... i would love a plug in for the mbx's and dats if you can make one.  no rush on them at this point hehe... i just figure the more complete the support the better eh?
## Post #16
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-17T16:17:04+00:00
- Post Title: 

Ok, theres another thing i'm noticing, i'm not sure if this is a fault or the way the file is... but the values.txt out of the games.mng (tree: \config\) ends like  so:

; Mortar / Bombs info

LobberSpeed = 0.01
LobberRange = 24000.0

ChopperLobberDamage = 50.0
ChopperLobberRange = 1500.0

JetLobberDamage = 60.0
JetLobberRange = 2000.0

SuperChopperLobberDamage = 90.0
SuperChopperLobberRange = 1500.0

BuggyLobberDamage = 10.0
BuggyLobberRange = 500.0

HoverLobberDamage = 20.0
HoverLobberRange = 1500.0

SuperHoverLobberDamage = 22.5
SuperHoverLobber


Its that last part that worries me, see how it says that but fails to define a value?  Seems like a cut off... tis strange.

Also, with the sound files, i'm noticing that they begin about 1/3rd into what they're supposed to, and end with their beginnings... and in loops there are long pauses at the ends.  I have never seen a game developer make a loop with any lag at the end... so this was a red flag to me.

Let me know if ya figure anything out and i'll be glad to put it through its paces.
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-18T07:04:58+00:00
- Post Title: 

1. If you are previewing the files in Game Extractor, it won't show the full text file if it is too long. This could explain the cutting off of the end of the text file. However, extracting the file will give you the full file.
2. There is no way that the files could be starting or stopping half way through unless that is what it programmed in the archive. The files are all compressed, which means that you must start at the beginning of the file when trying to read it, otherwise the file could not be decompressed. In other words, if Game Extractor was not starting at the beginning of the file when trying to do the decompression, it would not decompress the file and it would not be readable.
3.T he inverted pcx images must be the way the game reads them. All BMP iamges are stored upside down, so chances are the game also stores the PCX images upside down for consistent reading. There is not much that can be done about this unless we re-write the wrole image the correct way up. It would be easier to change the image in photoshop then to convert it in Game Extractor.

I hope that answers all your questions. I will also try to get a new plugin for the other MBX files to you when I get home.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-18T12:50:28+00:00
- Post Title: 

Well, i wasn't previewing the file.  That was a clipping from the file as it extracted.

If the file was stopping half way through, and this is impossible as it wouldn't be readable... why was it somewhat readable and mostly not the first times around?  I dunno, it just seems suspect, if you can agree, that a file defining the values for things would simply cut out on declaring a variable where it had just defined a whole set of them.  If the variable was unused (which is not the case with this one, i can confirm its linked to a unit in the game) i would have thought it would be commented out at some point.

I also find it suspect that the wav files, when ya open em up in anything, they display the wave forms as previously mentioned.

Again, i don't know if thats how they're meant to be or not, but it all seems like its incorrect somewhere.

The sounds that display and play improperly for me in sound forge and winamp, play perfectly and fully in the game.

Timed them, found the difference is the full sounds in the game seem to be longer than those extracted.  Pitch is the same, i'm sure of that as a large difference of pitch would be required to alter a sample by (in some cases) 2 seconds.

It just seems to me, that all the anomalies must lead to some problem with extracting the archives... but i, of course, can't be sure about that.

Through toying i don't know what could be wrong, but those are my observations.
## Post #19
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-18T12:54:30+00:00
- Post Title: 

Oh, and what i mean by that bit about the archives reading was that wouldn't it be possible, if improbable, that the routine to extract or preview the file was truncating part of it?  Might that be something that would constitute a possible bug?
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-18T12:55:30+00:00
- Post Title: 

Like Watto explained, he extracted them using a decompression method that would not allow one to start anywhere else than at the beginning of the file. 

The programmers may, for some reason, have intended it that way. The fact that they play well in the game, does not mean the programmers don't mess with it first to get the sound allright.
## Post #21
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-18T14:42:20+00:00
- Post Title: 

Hi again,

Hmm, well there is a possibility that there is a bug in the basic version with the decompression (ie cutting off the end) but I wasn't aware of the bug. I know the bug is not in the full version, if it is a bug, so I may look into it and try to fix up the basic version alittle?

However, if the file starts at the wrong spot, that is definately not a bug and it is correct in that way.

Anyway, I have attached a plugin for the *.mbx/*.dat files that works with the basic version. To use it, you tell Game Extractor to open the *.mbx files, NOT the *.dat files! I did this because I expect that people would more naturally try to open the big files rather than the small ones, therefore it is more probable that they open an *.mbx rather than a *.dat file. Anyway, same as before, unzip it into your plugins directory.


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_DAT_2_Basic.zip](https://xentaxbackup.github.io/file/229_Plugin_DAT_2_Basic.zip)
## Post #22
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-18T15:07:31+00:00
- Post Title: 

OK, well yes it does appear as though there was a decompression bug in the basic version which prevented it from writing the complete file. It isn't really a decompression bug, its just that at the time I wrote the basic version I had only just made my own file buffers, and it seems as though I hadn't remembered to flush out the buffer before writing the file.

Anyway, the good news though is that the full version does not have this problem, i repaired the bug somewhere between verison 0.94 (basic) and 1.02 (full).

Thanks mate!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #23
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-18T19:32:53+00:00
- Post Title: 

See bud, i thought something was off hehe.

In the meantime, i guess i'll continue seein if i can pull a few favors and get your full version (I don't have a paypal acct anymore)... unless you fix the bug in the basic one before i do this... either way, i'll be donating to both of you in the near future.

All of this has made me really happy 



So ya see, my persistence in this matter i see as mutually beneficial; i get to write off a cause of a problem and look elsewhere, or you get to find a bug somewhere to fix.  Not tryin to be an ass and go off on a rant about about your programs
## Post #24
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-19T15:20:49+00:00
- Post Title: 

Hi mate,

Yes thanks for your help - it really does make a difference even if it is just picking out faults in the program 

I don't really want to fix the bug in the basic version, mostly because I am currently trying to build a newer basic version off the full version code - thus the bug will have already been fixed. However, I have attached some code which *may* solve the problem - I just stole the code from the full version that I think was causing the problems.

Unzip the attachment INTO THE MAIN DIRECTORY - not the plugins directory. It should be ok because I designed this code to be backwards compatable, but you just never know. If it doesn't work, you will just have to re-install Game Extractor over the top of it 

Good luck - hope it works.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Repairs.zip](https://xentaxbackup.github.io/file/239_Repairs.zip)
## Post #25
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-19T22:44:32+00:00
- Post Title: 

Yeah, doesn't start anymore :\

But i'll wait for your newer version or get the full one soon as i can, its all good hehe.
## Post #26
- Username: Vagamus
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 14, 2005 11:50 pm
- Post datetime: 2005-05-28T07:38:52+00:00
- Post Title: 

Ok, so in testing of the dat/mbx decompression, i've found that it doesn't appear to even get the structure right, its all "fileXXXX" (where x's are numbers) and uniform sizes.  Doesn't seem to be able to extract anything i can read either... tis strange.

If ya get some time, please do look into this.
## Post #27
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-29T13:01:09+00:00
- Post Title: 

OK, first make sure you are opening the *.mbx files, not the *.dat files . Game Extractor won't use the right plugin if you try to open the *.dat file

Secondly, the files won't have proper names - they are not stored in the archives. Therefore, it is perfectly legitimate for the files to have the names File XXXX. 

Thirdly, it may be possible that all the files are similar sized, and unreadable - in fact most files used in games are unreadable. Thats because game makers develop their own files for use in-game, just as they make their own archive formats.


So from what you have mentioned here, i cant say either way whether it works or not, however I did test it on some of the archives from the demo without a problem so my assumption at this point in time is that the plugin is working correctly.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #28
- Username: Valor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 24, 2012 6:22 pm
- Post datetime: 2016-11-08T10:30:36+00:00
- Post Title: 

Hi!

Is there any way to open the model files inside the MNG? If I'm correct I should open the bin_* files.

Thanks?
## Post #29
- Username: Valor
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 24, 2012 6:22 pm
- Post datetime: 2016-11-08T19:53:24+00:00
- Post Title: 

> Reply from Valor
>
> Hi!

Is there any way to open the model files inside the MNG? If I'm correct I should open the bin_* files.

Thanks?

I've figured out that the bin_* files are binary files and I don't know the specification. What I know:
1. the files starts with BS09 string: 4 bytes
2. zero: 4 bytes
3. length of the object path, int: 4 bytes
4. object path string, length: see 3. point

But the remaining content is unknown. Strange thing is that there are other model files in plain texts like Way point.s01.

Object : way point crystal
Matrix : 1.000000, 0.000000, 0.000000, 0.000000, 1.000000, 0.000000, 0.000000, 0.000000, 1.000000, 0.000000, 0.000000, 0.000000
Verts (6)
{
 0.000000, -0.000000, 526.959045
 198.813004, -0.000004, 364.078979
 -0.073382, 187.846893, 364.078949
 -198.959763, -0.000017, 364.078949
 -0.073362, -187.846893, 364.078979
 0.000000, -0.000000, 0.000000
}
Texture Verts (9)
{
 0.908626, 0.952917
 0.953331, 0.908213
 0.908643, 0.908213
 0.863922, 0.908213
 0.908626, 0.863508
 0.908643, 0.908258
 0.908625, 0.908213
 0.908643, 0.908167
 0.908661, 0.908213
}
Quads (0)
{
}
Tris (8)
{
 2, 1, 0
 Texture : 'scanner unit.tif' 0, 1, 2
  Opacity : Filter 0.500000
 Normals : 0.526252, 0.557179, 0.642348, 0.633738, 0.000000, 0.773547, 0.633738, 0.000000, 0.773547
 3, 2, 0
 Texture : 'scanner unit.tif' 3, 0, 2
  Opacity : Filter 0.500000
 Normals : -0.633459, 0.000000, 0.773777, -0.526092, 0.557009, 0.642626, -0.633459, 0.000000, 0.773777
 4, 3, 0
 Texture : 'scanner unit.tif' 4, 3, 2
  Opacity : Filter 0.500000
 Normals : -0.526091, -0.557009, 0.642626, -0.633459, 0.000000, 0.773777, -0.633459, 0.000000, 0.773777
 1, 4, 0
 Texture : 'scanner unit.tif' 1, 4, 2
  Opacity : Filter 0.500000
 Normals : 0.633738, 0.000000, 0.773547, 0.526252, -0.557179, 0.642348, 0.633738, 0.000000, 0.773547
 2, 5, 1
 Texture : 'scanner unit.tif' 0, 5, 1
  Opacity : Filter 0.500000
 Normals : 0.642933, 0.680717, -0.351087, 0.877668, 0.000000, -0.479269, 0.877668, 0.000000, -0.479269
 3, 5, 2
 Texture : 'scanner unit.tif' 3, 6, 0
  Opacity : Filter 0.500000
 Normals : -0.877519, -0.000000, -0.479542, -0.877519, -0.000000, -0.479542, -0.642874, 0.680655, -0.351314
 4, 5, 3
 Texture : 'scanner unit.tif' 4, 7, 3
  Opacity : Filter 0.500000
 Normals : -0.642874, -0.680655, -0.351314, -0.877519, -0.000000, -0.479542, -0.877519, -0.000000, -0.479542
 1, 5, 4
 Texture : 'scanner unit.tif' 1, 8, 4
  Opacity : Filter 0.500000
 Normals : 0.877668, 0.000000, -0.479269, 0.877668, 0.000000, -0.479269, 0.642933, -0.680717, -0.351087
}

...

I think the bin_* files are the same but binary formatted. End of the files I located the texture files too like in the example above.

Could someone help me decoding the model files?
