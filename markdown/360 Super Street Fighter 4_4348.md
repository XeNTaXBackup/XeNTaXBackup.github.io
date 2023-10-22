## Post #1
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-04-18T19:41:45+00:00
- Post Title: 360 Super Street Fighter 4

battle.eaf Archive file 2.61GB

It include models, sound, texture, etc

Super Street Fighter 4 has locked dlc costume.

I want change Orignal costume to locked costume. Is that possible??
[3.png](https://xentaxbackup.github.io/file/2955_3.png)
## Post #2
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-04-18T19:43:19+00:00
- Post Title: 360 Super Street Fighter 4

+
[4.png](https://xentaxbackup.github.io/file/2956_4.png)
## Post #3
- Username: rickfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 20, 2010 6:46 pm
- Post datetime: 2010-04-20T21:43:20+00:00
- Post Title: 360 Super Street Fighter 4

It also would be great to port some files from SuperSFIV-360 to SFIV-PC. If we could extract the content from battle.eaf, we'll be able to include colours 11 & 12, new BGMs and (maybe) alternate costumes. 

I've just found some information about .eaf files:
[http://www.lat-mpi.eu/tools/elan/manual/ch04s01.html](http://www.lat-mpi.eu/tools/elan/manual/ch04s01.html)

I've tested ELAN 3.8.1, but when I open battle.eaf it only appears a super long (but empty) media. Can anybody help? Thx, hope we decode these file!! There are some real masters in this forum, so I'm sure they'll do it!!
## Post #4
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-04-20T21:52:32+00:00
- Post Title: 360 Super Street Fighter 4

Upload a file.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-04-21T00:30:47+00:00
- Post Title: 360 Super Street Fighter 4

Here's a quickbms script
[http://hcs64.com/files/eaf03.bms](http://hcs64.com/files/eaf03.bms)

(someone had been asking and [posted a sample](http://hcs64.com/mboard/forum.php?showthread=19223))
## Post #6
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-04-21T00:34:49+00:00
- Post Title: 360 Super Street Fighter 4

> Reply from Caboose
>
> Upload a file.

Let me do it in weekend when I have finished downloading the game.
## Post #7
- Username: rickfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 20, 2010 6:46 pm
- Post datetime: 2010-04-21T12:22:54+00:00
- Post Title: 360 Super Street Fighter 4

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-04-21T20:52:26+00:00
- Post Title: 360 Super Street Fighter 4

The contents of this post was deleted because of possible forum rules violation.
[1.png](https://xentaxbackup.github.io/file/2963_1.png)
## Post #9
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-04-21T20:56:30+00:00
- Post Title: 360 Super Street Fighter 4

I've got bad news : piecemonteeSF4explorer  doest work anymore .
## Post #10
- Username: rickfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 20, 2010 6:46 pm
- Post datetime: 2010-04-21T21:00:16+00:00
- Post Title: 360 Super Street Fighter 4

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-22T02:04:48+00:00
- Post Title: 360 Super Street Fighter 4

the quickbms script posted here decompresses everything fine.
they used the same compression.
all he has to do to make his program work with these models is swap how he reads the endian of the files.
## Post #12
- Username: rickfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 20, 2010 6:46 pm
- Post datetime: 2010-04-22T02:41:09+00:00
- Post Title: 360 Super Street Fighter 4

Great find!! Could someone upload "BGM_MKT_2CH.csb" ?? I need this BGM, but I can't extract the file!! (i've extracted other Bgms, but can't decode this one!). Don't know if it's my fault, but there isn't an UTF head when I open it with SuperEditPadPro, so csb_extract can't do anything. That's what happens to me from "BGM_JRI_4CH.csb" to the end of the directory ("BGM_ZGF_4CH.csb"). Can you extract these files?
## Post #13
- Username: Daewa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 19, 2010 3:33 pm
- Post datetime: 2010-04-22T07:56:20+00:00
- Post Title: 360 Super Street Fighter 4

I don't get how to extract textures and models from those emb files, can someone tell how to do it please?
I understand I have to tweak the script, something about endian, what do I need to change?
## Post #14
- Username: rickfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 20, 2010 6:46 pm
- Post datetime: 2010-04-22T09:47:36+00:00
- Post Title: 360 Super Street Fighter 4

Use offzip. It contains 2 files, copy and paste them in the directory where you wanna extract. For example, in ....\chara\RYU you copy these 2 files (offzip.exe & offzip.exe) and then, in a dos window you tap:
offzip.exe -m 16 -a -z -15 RYU_03_01.col.emb ryu_alpha 0

ryu_alpha is a new directory that you have to create before, and where you'll find 0000001.dat. 
And then, dragon unpacker, etc
## Post #15
- Username: Daewa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 19, 2010 3:33 pm
- Post datetime: 2010-04-22T10:14:27+00:00
- Post Title: 360 Super Street Fighter 4

thanks,

Now if only we could use piecemonteeSF4explorer
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-22T10:35:30+00:00
- Post Title: Re: 360 Super Street Fighter 4

the bms script posted here does not need any change its the model viewer program you mentioned he has to makea small adjustment to make it read 360 files as they are in the reverse endian order compared to the pc files.
## Post #17
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-04-30T16:23:27+00:00
- Post Title: Re: 360 Super Street Fighter 4

or convert the 360 files to litlle edian and use piecemontee
also you need to know each file structure to convert them...
## Post #18
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-05-01T20:58:13+00:00
- Post Title: Re: 360 Super Street Fighter 4

I've managed to extract the stuff from the battle.eaf thanks to the quickBMS script.

But I'm wondering, how would I go about repacking the file?
## Post #19
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-05-09T02:45:10+00:00
- Post Title: Re: 360 Super Street Fighter 4

I've managed to inject the files back into the battle.eaf using infuser and it works fine, but I've noticed that the compression used by the costumes seems different this time around.

I suck at this stuff, does anyone else know how to recompress the costumes?
## Post #20
- Username: dknlght
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 30, 2010 12:05 pm
- Post datetime: 2010-05-14T02:44:52+00:00
- Post Title: Re: 360 Super Street Fighter 4

you mentioned you used infuser to inject the file back into the battle.eaf and it works. Does that mean the game still loads and saw the new costume? if you used infuser how did you know which position to inject the files back into the battle.eaf? also did inject the files back uncompress or compressed? if you inject it back uncompress would it have corrupted the battle.eaf?
## Post #21
- Username: kensou
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 11, 2009 5:20 am
- Post datetime: 2010-05-14T20:57:57+00:00
- Post Title: Re: 360 Super Street Fighter 4

guy 



.jpg (106.35 KiB) Viewed 667 times
## Post #22
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-05-15T02:13:03+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from dknlght
>
> you mentioned you used infuser to inject the file back into the battle.eaf and it works. Does that mean the game still loads and saw the new costume? if you used infuser how did you know which position to inject the files back into the battle.eaf? also did inject the files back uncompress or compressed? if you inject it back uncompress would it have corrupted the battle.eaf?

I made a .bat file that made the quickbms script write a log. The log has the offsets. Using the offsets and number of the file, I managed to use infuser to inject the file back into the .eaf.

I can't test if it works, tho, because I don't know how to RECOMPRESS the costumes. The compression seems to be different.

I probably suck at explaining, so tell me if you didn't understand what I just said :U
## Post #23
- Username: dknlght
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 30, 2010 12:05 pm
- Post datetime: 2010-05-15T06:52:10+00:00
- Post Title: Re: 360 Super Street Fighter 4

actually I do follow you, can you post your quickbms script that logs the offset? I'm going to use the same compression I used on the original street fighter 4 xbox game and see if it actually works. 
thanks
## Post #24
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-05-15T11:52:40+00:00
- Post Title: Re: 360 Super Street Fighter 4

I just put this into a .bat file.

```
quickbms.exe <EAF Script's location here> <Battle.eaf's location here> <Output folder> > battle.eaf.extractionlog.txt
```


Just replace the things with your own locations for the files. 

Here's the quickbms script if you don't have it: [http://hcs64.com/files/eaf03.bms](http://hcs64.com/files/eaf03.bms)

The offsets are off by 10 when I did it, so I had to remove that 10 to inject correctly (or atleast what seems to be correctly). Like, 00133b10 becomes 00133b00.

And I think that when using SF4's compression, the filesize ends up being way bigger, that would cause the battle.eaf to corrupt. You should test anyway, maybe I did it wrong.

I have to say, tho, that the script seemed to decompress the files inside the battle.eaf after it extracted them, which would fuck it all up. I used sora3087's tool for actual extraction. Only really used the script to get a list of the offsets.
## Post #25
- Username: dknlght
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 30, 2010 12:05 pm
- Post datetime: 2010-05-26T04:55:55+00:00
- Post Title: Re: 360 Super Street Fighter 4

Finally had some time to test the procedure in which you used infuser to put the extract files back into the battle.eaf and I'd like to confirm that it works.  Using infuser and the offset generated by quickbms script -10 (as you indicate) does generate a valid battle.eaf file. I did two test. first re-insert an unmodified costume file just to see if the insertion process produced a valid battle.eaf file. Second decompress and re-compress a costume file and re-insert it back. The first test worked i inserted the files extracted using sora's app back into the battle.eaf place the battle.eaf back into the iso and was still able play as the characters I modified but it seems that compression for SF4 doesn't work for SSf4. I manage to compress BSN costume file smaller than the original using the same SF4 compression tool but it still locked up when I loaded the character.  So we just need to figure out which compression would be compatible with SSF4.
## Post #26
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-05-26T12:05:51+00:00
- Post Title: Re: 360 Super Street Fighter 4

Make sure you have theese 4 files:



Copy them and create a new folder to make the things easier, and then paste them there.

In the rar I uploaded we have 2 folders:



SF4 and SF4newtool. First we need to open SF4 folder, and create 2 folders called: emz and emb. After that we're gonna open SF4tool.exe:



So we're gonna uncompress the files we copied before. To do that just drag and drop in the square saying emz decompress:



The uncompressed files are gonna be stored in the emz folder we created before:



Erase the .emb extensions to get this:



Now get out of the sf4 folder and open sf4toolnew and open sf4toolnew.exe:



We're gonna drag and drop pne of the new files, and if the files is correct, a button will appear:

 

Click on the button and repeat it with all the files to get this:



Erase the old files and keep the new files. Erase the newpack extension, and at this rate the file we need to get the model is ready. If you want to replace a sfiv character with a ssfiv one, first we need to rename the files for one of sfiv characters. Open piecemontee and open a sfiv character file, in this case i'm gonna choose chunli:



Under the emb subtree, we see 4 files, so we're gonna rename our Juli files:



After that, in you sf4tool.exe where we decompressed the files, there is a white square text with two buttons and an exporer above it. Choose the emz folder and press the first button, and something like this has to appear in the square text:



After that just select the text and press the second button to get an emz file:



And rename it with the file's name you want to replace.

This is what we get:



Hope someone is interested to write a proper converter for the models we got from all this process.
## Post #27
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-05-26T19:56:41+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from dknlght
>
> Finally had some time to test the procedure in which you used infuser to put the extract files back into the battle.eaf and I'd like to confirm that it works.  Using infuser and the offset generated by quickbms script -10 (as you indicate) does generate a valid battle.eaf file. I did two test. first re-insert an unmodified costume file just to see if the insertion process produced a valid battle.eaf file. Second decompress and re-compress a costume file and re-insert it back. The first test worked i inserted the files extracted using sora's app back into the battle.eaf place the battle.eaf back into the iso and was still able play as the characters I modified but it seems that compression for SF4 doesn't work for SSf4. I manage to compress BSN costume file smaller than the original using the same SF4 compression tool but it still locked up when I loaded the character.  So we just need to figure out which compression would be compatible with SSF4.

Awesome stuff.
## Post #28
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-06T18:45:30+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from Darko
>
> So we're gonna uncompress the files we copied before. To do that just drag and drop in the square saying emz decompress:

I drag'n'droping my file on square emz decompress -> "window with ok" shows up, but files in my emz folder don't creating.

why?
## Post #29
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-06-08T00:49:57+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from Tosyk
>
> Darko wrote:So we're gonna uncompress the files we copied before. To do that just drag and drop in the square saying emz decompress:



I drag'n'droping my file on square emz decompress -> "window with ok" shows up, but files in my emz folder don't creating.

why?

If the program doesn't decompress the files, just use the bms scrypt that come in the rar.
## Post #30
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-06-08T17:21:04+00:00
- Post Title: Re: 360 Super Street Fighter 4

Has any progress been made when it comes to recompressing the costumes themselves, to make skins, you know?

I haven't been able to come up with anything
## Post #31
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-07-04T03:33:02+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from DerMeister
>
> Has any progress been made when it comes to recompressing the costumes themselves, to make skins, you know?

I haven't been able to come up with anything

Seriously, it's like it just died. Come on people, someone that knows this shit help us, pleeeeeeaseeeeee!
## Post #32
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-07-10T04:13:32+00:00
- Post Title: Re: 360 Super Street Fighter 4

bumping!
## Post #33
- Username: dknlght
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 30, 2010 12:05 pm
- Post datetime: 2010-07-15T01:59:27+00:00
- Post Title: Re: 360 Super Street Fighter 4

Well I did try but haven't found the right way to compress the files back made a lot of coasters lol. Unfortunately I don't have a JTAG xbox otherwise it would have been easier to do some more testing. But From what I've read the extra costumes that you downloaded from xbox live for SF4 should still work for SSF4 therefore wouldn't those costume still work with the old compression? This means that you should still be able to mod the add-ons if you had the JTAG xbox. Unfortunately I can't verify that. Can someone with a JTAG xbox mod the 2nd costumes for SF4 and see if it works for SSF4?
## Post #34
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-07-16T15:16:36+00:00
- Post Title: Re: 360 Super Street Fighter 4

Just asking in the possibility for a model converter. Hope someone is interested enough to try it.
## Post #35
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-07-18T17:32:19+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from dknlght
>
> Well I did try but haven't found the right way to compress the files back made a lot of coasters lol. Unfortunately I don't have a JTAG xbox otherwise it would have been easier to do some more testing. But From what I've read the extra costumes that you downloaded from xbox live for SF4 should still work for SSF4 therefore wouldn't those costume still work with the old compression? This means that you should still be able to mod the add-ons if you had the JTAG xbox. Unfortunately I can't verify that. Can someone with a JTAG xbox mod the 2nd costumes for SF4 and see if it works for SSF4?

From what I've seen, SSF4 has the DLC files in the disc. Both the old ones with the new format and the new ones. AFAIK, the DLC pretty much just unlocks the content for use.
## Post #36
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-07-29T02:28:15+00:00
- Post Title: Re: 360 Super Street Fighter 4

buuuuuuump, still wondering how to recompress that stuff D:
## Post #37
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-10T20:43:21+00:00
- Post Title: Re: 360 Super Street Fighter 4

Hi, I cannot update SF4 viewer but I released the sources ([https://sourceforge.net/projects/sf4viewer/](https://sourceforge.net/projects/sf4viewer/)), I hope it may help.
## Post #38
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-08-12T03:37:28+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from piecemontee
>
> Hi, I cannot update SF4 viewer but I released the sources (https://sourceforge.net/projects/sf4viewer/), I hope it may help.

Awesome! Hopefully someone updates it with SSF4 support.
## Post #39
- Username: amandabyyy
- Rank: beginner
- Number of posts: 22
- Joined date: Mon May 31, 2010 3:08 pm
- Post datetime: 2010-08-16T08:31:37+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from piecemontee
>
> Hi, I cannot update SF4 viewer but I released the sources (https://sourceforge.net/projects/sf4viewer/), I hope it may help.

EDIT: Nevermind, finally found it.  Thanks!

Hey piecemontee.  I checked in the directory and only see the executables.  I can't seem to find the source code to anything.  Am I just stupid and not looking in the right place or did I misunderstand what you meant by sources?  (I did find some of the EMA code in one of the zips).

Thanks!
## Post #40
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-25T21:25:51+00:00
- Post Title: Re: 360 Super Street Fighter 4

Could not help trying stuff, my wife will kill me   
Made some progess on Big Endian handling.

Guys, we cannot magically reverse the whole file endianness like I read on some posts!

I have to process field by field to check alignment :some field where not the size I thought, reversing the endianness messes up a lot of values!
we often have data like 20 00 00 00 and we thought it was a 2 byte offset (20 00 ) and another 2 bytes value always 00 00 
WRONG! when reading a console file we find 00 00 00 20 so we put 00 00 in the offset and 20 00 in the dummy value   ... a lot of adjustment are needed.
At least fields we'll be known for sure when done / finished

Furthermore faces indices management looks different from PC version but it may be endianness again.

And I skip the C++ programming tweaks to handle structures (I did not read field by field but struct as a whole) and both little endian and big endian in the same code!

But the harder the better we feel when it works   



[https://sourceforge.net/project/screens ... sid=135251](https://sourceforge.net/project/screenshots.php?group_id=341623&ssid=135251)

P.S. does the term "endianness" really exist ? EDIT: ah, yes it does ([http://en.wikipedia.org/wiki/Endianness](http://en.wikipedia.org/wiki/Endianness))

EDIT2: links updated
## Post #41
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-08-26T01:49:45+00:00
- Post Title: Re: 360 Super Street Fighter 4

Thank you   But when i open your URL on sourceforge i get error:
There was an error processing your request ...
## Post #42
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-30T22:25:10+00:00
- Post Title: Re: 360 Super Street Fighter 4

VICTORY!
(may only satisfy myself though.... sorry  )

Console files triangles are not stripped!

If did not find the flag location yet (although there is a suspect field going from 0 to 1 ...)
[ryu3.JPG](https://xentaxbackup.github.io/file/3388_ryu3.JPG)
## Post #43
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-08-30T22:53:26+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from piecemontee
>
> VICTORY!
(may only satisfy myself though.... sorry  )

Console files triangles are not stripped!

If did not find the flag location yet (although there is a suspect field going from 0 to 1 ...)

Lol, When are you going to release the viewer with ssf4 support??
## Post #44
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-30T23:04:27+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from Darko
>
> Lol, When are you going to release the viewer with ssf4 support??

now!, head over [http://sf4viewer.sourceforge.net/](http://sf4viewer.sourceforge.net/)
## Post #45
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-08-31T00:04:26+00:00
- Post Title: Re: 360 Super Street Fighter 4

When I try to open a model I get invalid 3dcall.
## Post #46
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-31T17:08:07+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from Darko
>
> When I try to open a model I get invalid 3dcall.

- Did previous version work?
- Did you try with d3dx9_38.dll along the exe?
https://sourceforge.net/projects/sf4vie ... p/download
- What are you're system specs (OS, GPU) ?
## Post #47
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-08-31T18:02:19+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from piecemontee
>
> Darko wrote:When I try to open a model I get invalid 3dcall.

- Did previous version work?
- Did you try with d3dx9_38.dll along the exe?
https://sourceforge.net/projects/sf4vie ... p/download
- What are you're system specs (OS, GPU) ?

The vo.33 worked fine for me, later versions had problems in my pc.

System specs:

P4 2.93 GHz , winxp service pack 3/win7 gpu geforce 5400fx (yes too low maybe).

And yes, I already had that d3dx9_38.dll.
## Post #48
- Username: piecemontee
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Aug 04, 2009 4:34 am
- Post datetime: 2010-08-31T19:14:19+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from Darko
>
> piecemontee wrote:Darko wrote:When I try to open a model I get invalid 3dcall.

- Did previous version work?
- Did you try with d3dx9_38.dll along the exe?
https://sourceforge.net/projects/sf4vie ... p/download
- What are you're system specs (OS, GPU) ?


The vo.33 worked fine for me, later versions had problems in my pc.

System specs:

P4 2.93 GHz , winxp service pack 3/win7 gpu geforce 5400fx (yes too low maybe).

And yes, I already had that d3dx9_38.dll.

Please try this [https://sourceforge.net/projects/sf4vie ... e/download](https://sourceforge.net/projects/sf4viewer/files/0.37%20%28Console%20files%20format%20support%20-%20SuperSF4%29/piecemonteeSF4explorerV0.37b.exe/download)

OK, I'll check the difs with 0.33.
Does it work if you only click on DDS textures and EMG sub models in the tree ?
## Post #49
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2010-08-31T23:41:47+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from piecemontee
>
> The vo.33 worked fine for me, later versions had problems in my pc.

System specs:

P4 2.93 GHz , winxp service pack 3/win7 gpu geforce 5400fx (yes too low maybe).

And yes, I already had that d3dx9_38.dll.

Please try this [https://sourceforge.net/projects/sf4vie ... e/download](https://sourceforge.net/projects/sf4viewer/files/0.37%20%28Console%20files%20format%20support%20-%20SuperSF4%29/piecemonteeSF4explorerV0.37b.exe/download)

OK, I'll check the difs with 0.33.
Does it work if you only click on DDS textures and EMG sub models in the tree ?[/quote]

Yep, It works only with textures but not displaying the model.
## Post #50
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2010-09-03T15:14:03+00:00
- Post Title: Re: 360 Super Street Fighter 4

Hi guys!

I am trying to take ssf4 characters into the PC version.
I followed as the way Darko did and able to take the model into the PC. (Thank Darko)
However, when I try to combi the color files, its keep chashing the game at loading screen after character selecting screen. The same thing happen when I try on the move set files.

The way I did the color file is:
I take the JRI_03_01.col.emb and JRI_03_01.obj.emm then decompress its with the bms as Darko said on some post.
next, I put those file through sf4toolnew.exe and rename both of them before repack it with sf4tool.exe
when I use the file, it chashing at loading screen after character selecting screen.

I am wonder if I need to add or missing or need not to do something with my step to make this work.
I saw that kensou had posted a pictuer of RYU that been replace by GUY. It seen that kensou had replace the model, color and move set. I wonder if kensou did used the same tools and/or the same ways.

Thank u all
## Post #51
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-09-05T06:04:29+00:00
- Post Title: Re: 360 Super Street Fighter 4

Yo, Pieceemontee, awesome stuff!

Works fine for me, so far. This does work to inject things back and stuff, right? I will try to test changing stuff and see if it works in-game if so! (I just wanna make sure)
## Post #52
- Username: Piuma84
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 07, 2010 2:13 am
- Post datetime: 2010-09-07T04:00:23+00:00
- Post Title: Re: 360 Super Street Fighter 4

[http://www.youtube.com/watch?v=z7wRQ_A9nCM](http://www.youtube.com/watch?v=z7wRQ_A9nCM)
## Post #53
- Username: gloom
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 13, 2010 11:01 pm
- Post datetime: 2010-09-13T15:09:19+00:00
- Post Title: Re: 360 Super Street Fighter 4

This is just wonderful. Thank you so much for your efforts.
I was wondering how come there are no problems loading the new costumes.
I heared somewhere that if you increase the amount of availble vertexes the model won`t load.
I don`t know if this is right or wrong but don`t the new costumes have a different vertex count?
I really have no idea what i am actually talking about. It`s just fantastic to see that you got the new alternate costumes to work.
## Post #54
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2010-09-13T15:49:01+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from gloom
>
> This is just wonderful. Thank you so much for your efforts.
I was wondering how come there are no problems loading the new costumes.
I heared somewhere that if you increase the amount of availble vertexes the model won`t load.
I don`t know if this is right or wrong but don`t the new costumes have a different vertex count?
I really have no idea what i am actually talking about. It`s just fantastic to see that you got the new alternate costumes to work.

if you extract a model from a character you can't change the vertex count or you won't be able to inject it back into the character.
## Post #55
- Username: gloom
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 13, 2010 11:01 pm
- Post datetime: 2010-09-13T18:31:26+00:00
- Post Title: Re: 360 Super Street Fighter 4

So the problem applies to the alternative costumes too?
## Post #56
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2010-09-14T02:19:02+00:00
- Post Title: Re: 360 Super Street Fighter 4

It doesn't matter with console files because injection doesn't work for them yet, but the vertex thing goes for everything.
## Post #57
- Username: Piuma84
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 07, 2010 2:13 am
- Post datetime: 2010-09-14T22:52:43+00:00
- Post Title: Re: 360 Super Street Fighter 4

this isn't correct. Injection works with backported model with piecemonte asset explorer 0.37b

The problem of vertex amount is a problem of the single model.

If you do a correct conversion of a model the game will load the model (if you convert with an hex editor a RUFUS model to use with the RYU moveset it worls - the same for the backported models from ssf4).

The problem of the vertex amount appears when you try to modify an .obj part from a model changing its vertex amount and then try to reinject it.

In other words, the backported models works like the original sf4 models, having the same restriction about vertex amount.

> Reply from jooped
>
> It doesn't matter with console files because injection doesn't work for them yet, but the vertex thing goes for everything.
## Post #58
- Username: gloom
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 13, 2010 11:01 pm
- Post datetime: 2010-09-15T04:25:40+00:00
- Post Title: Re: 360 Super Street Fighter 4

I see. Thanks for backporting/backengineering Piuma.
## Post #59
- Username: dknlght
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 30, 2010 12:05 pm
- Post datetime: 2010-09-19T05:00:46+00:00
- Post Title: Re: 360 Super Street Fighter 4

Piuma84 so is the video your posting evidence of a successful mod of Super Street Fighter 4? Sorry if it sounds like a stupid question because I can't tell if that SSF4 or SF4. If it is SSF4 how did you manage to re-compress the files back to a compatible format? I just quickly played with piecemonteeSF4explorerV0.37b and the injection process only injects the DDS back into the uncompress version of the original file. I've also went back and re-read Darko's post about sf4tool but maybe I'm missing something but that seems to be instructions on how to extract the character Model so that you can modify it but I didn't see him mentioning re-compressing the file there either.
## Post #60
- Username: Piuma84
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 07, 2010 2:13 am
- Post datetime: 2010-09-20T10:15:05+00:00
- Post Title: Re: 360 Super Street Fighter 4

no, it shows a successfull backport from 360 super to vanilla pc.

> Reply from dknlght
>
> Piuma84 so is the video your posting evidence of a successful mod of Super Street Fighter 4? Sorry if it sounds like a stupid question because I can't tell if that SSF4 or SF4. If it is SSF4 how did you manage to re-compress the files back to a compatible format? I just quickly played with piecemonteeSF4explorerV0.37b and the injection process only injects the DDS back into the uncompress version of the original file. I've also went back and re-read Darko's post about sf4tool but maybe I'm missing something but that seems to be instructions on how to extract the character Model so that you can modify it but I didn't see him mentioning re-compressing the file there either.
## Post #61
- Username: gloom
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 13, 2010 11:01 pm
- Post datetime: 2010-10-07T12:10:25+00:00
- Post Title: Re: 360 Super Street Fighter 4

Thank you piuma and sensibeat for giving us all the new alternate costumes for SFIV. You guys rock. Btw depending if i prefer my original compared to my first official alt. Can i rename the files to replace my official alts instead of the originals? Also i was wondering if there is any way to add the costume sounds to the alts. Like Cammy's metel boot walk sounds on the ssfiv alts.
## Post #62
- Username: yohansm1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 06, 2010 5:15 am
- Post datetime: 2010-10-07T17:45:52+00:00
- Post Title: Re: 360 Super Street Fighter 4

hey did anyone figure out how to repack the files back to battle.eaf and test the game and see if  it works with the custom costumes
## Post #63
- Username: gloom
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 13, 2010 11:01 pm
- Post datetime: 2010-10-20T14:04:58+00:00
- Post Title: Re: 360 Super Street Fighter 4

Just wanted to ask again if its possible to rename the files to overwrite the alternative costumes instead of the standard ones.
## Post #64
- Username: hunterk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 05, 2010 1:11 am
- Post datetime: 2010-10-27T01:09:54+00:00
- Post Title: Re: 360 Super Street Fighter 4

@gloom
yes, just rename it to ***_02.cos.emz then open it with a hex editor, scroll all the way to the bottom of the file and change all of the filename references there to 02 instead of 01.
## Post #65
- Username: bigdave629
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 31, 2010 12:29 am
- Post datetime: 2010-10-31T20:46:50+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from DerMeister
>
> I just put this into a .bat file.
Code: Select allquickbms.exe <EAF Script's location here> <Battle.eaf's location here> <Output folder> > battle.eaf.extractionlog.txt

Just replace the things with your own locations for the files. 

Here's the quickbms script if you don't have it: http://hcs64.com/files/eaf03.bms

The offsets are off by 10 when I did it, so I had to remove that 10 to inject correctly (or atleast what seems to be correctly). Like, 00133b10 becomes 00133b00.

And I think that when using SF4's compression, the filesize ends up being way bigger, that would cause the battle.eaf to corrupt. You should test anyway, maybe I did it wrong.

I have to say, tho, that the script seemed to decompress the files inside the battle.eaf after it extracted them, which would fuck it all up. I used sora3087's tool for actual extraction. Only really used the script to get a list of the offsets.

I am trying to get PC mods on SSF4 with my jtag. I wanted to if I could get the offsets and file numbers so I could try and inject them. I have modded a few skins but don't think I have the right numbers. For some reason I can't get my batch file to work. Also is this how you set yours up 0af74c10#infuser#1398320

I also wanted to know if anyone here still had Sora's tool?
## Post #66
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2010-11-15T14:43:44+00:00
- Post Title: Re: 360 Super Street Fighter 4

SF4explorerV0.37b.exe won't display stage models correctly, not on xbox360 version or pc versions.
[](http://img181.imageshack.us/i/afr02pcsf4explorerv037b.jpg/)

SF4explorerV0.33.exe does display stage models properly on pc version.
[](http://img99.imageshack.us/i/afr01pcsf4explorerv033.jpg/)

help please piecemontee!
## Post #67
- Username: Kuroi Kenshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jan 19, 2011 3:58 am
- Post datetime: 2011-01-19T15:59:58+00:00
- Post Title: Re: 360 Super Street Fighter 4

Hello everyone,
I want to change orignal BGM and Texture Of The battle.eaf
I tried with several programs(infuser,quickbms...) and still nothing, if anyone wants to help me please?
## Post #68
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-29T22:35:22+00:00
- Post Title: Re: 360 Super Street Fighter 4

Hey,
I have two problems that came up with the SF4 explorer...
First, when I try to run any of the versions on my computer, I get INVALIDCALL.
I opened it on another computer, using the latest version, and opened a juri PS3-to-PC model. It loaded just fine, and the viewer was fine, but when I exported it to .obj, it came out all damaged, with holes and stretched vertices. This also happened with an ibuki PS3-to-PC model. When loading these two models into 3.33, they showed up in the viewer the way they are showing up in 3ds max. How can I fix this?
Thanks
## Post #69
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-05-06T08:10:07+00:00
- Post Title: Re: 360 Super Street Fighter 4

is there a way to export tha models with bones ?
thanks :3
## Post #70
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-05-14T00:52:42+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from protosk8
>
> is there a way to export tha models with bones ?
thanks :3

yes, there is, but it's a little long ritual xD
## Post #71
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-05-15T14:23:03+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from maniacoloco
>
> protosk8 wrote:is there a way to export tha models with bones ?
thanks :3

yes, there is, but it's a little long ritual xD

same as exporting them with textures :D?
## Post #72
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-05-21T02:34:43+00:00
- Post Title: Re: 360 Super Street Fighter 4

ok, here is the ritual to get fully rigged ssfiv models. Ok, we need:

emotosmd by magnum
kensou's tool
riggomatic by magnum ([http://z6.invisionfree.com/Resident_Evi ... 11075&st=0](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=11075&st=0))
the latest sfiv assets viewer
noesis 

Basically what we're gonna do is to convert a ssfiv emo object file to sfiv obj file with kensou's tool and then convert it to smd with emotosmd. After that, just convert the original emo object to obj and convert that object to smd with noesis. import the boneless smd in max studio and just rotate it to have the same exact position as the "damaged" smd (yes, the smd gotten with the converted edmo). In the last instance what you need to do is to open riggomatick, select the base model where the vertex weights data and bones are gonna be taken, and select the boneless smd where we want to place that data. The result is a correct full rigged smd model.

For how to run the tools, check this forum and that re forum.
## Post #73
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-05-21T04:30:30+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from maniacoloco
>
> ok, here is the ritual to get fully rigged ssfiv models. Ok, we need:

emotosmd by magnum
kensou's tool
riggomatic by magnum (http://z6.invisionfree.com/Resident_Evi ... 11075&st=0)
the latest sfiv assets viewer
noesis 

Basically what we're gonna do is to convert a ssfiv emo object file to sfiv obj file with kensou's tool and then convert it to smd with emotosmd. After that, just convert the original emo object to obj and convert that object to smd with noesis. import the boneless smd in max studio and just rotate it to have the same exact position as the "damaged" smd (yes, the smd gotten with the converted edmo). In the last instance what you need to do is to open riggomatick, select the base model where the vertex weights data and bones are gonna be taken, and select the boneless smd where we want to place that data. The result is a correct full rigged smd model.

For how to run the tools, check this forum and that re forum.

yeahhhhhhhhhhhhh \o/ thanks for tha info lol
## Post #74
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-05-21T20:43:06+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from protosk8
>
> maniacoloco wrote:ok, here is the ritual to get fully rigged ssfiv models. Ok, we need:

emotosmd by magnum
kensou's tool
riggomatic by magnum (http://z6.invisionfree.com/Resident_Evi ... 11075&st=0)
the latest sfiv assets viewer
noesis 

Basically what we're gonna do is to convert a ssfiv emo object file to sfiv obj file with kensou's tool and then convert it to smd with emotosmd. After that, just convert the original emo object to obj and convert that object to smd with noesis. import the boneless smd in max studio and just rotate it to have the same exact position as the "damaged" smd (yes, the smd gotten with the converted edmo). In the last instance what you need to do is to open riggomatick, select the base model where the vertex weights data and bones are gonna be taken, and select the boneless smd where we want to place that data. The result is a correct full rigged smd model.

For how to run the tools, check this forum and that re forum.

yeahhhhhhhhhhhhh \o/ thanks for tha info lol

Hehe no problem and sorry for the delay.
## Post #75
- Username: Gilberd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 10, 2011 2:54 pm
- Post datetime: 2011-06-10T19:35:45+00:00
- Post Title: Re: 360 Super Street Fighter 4

> Reply from DerMeister
>
> I've managed to inject the files back into the battle.eaf using infuser and it works fine, but I've noticed that the compression used by the costumes seems different this time around.

I suck at this stuff, does anyone else know how to recompress the costumes?

you were able to extract and repack the battle.eaf file from ssfiv
i already extracted it but how you repack the files back into the battle.eaf?
also in the files show BGM_GKI_CH2.csb BGM_GKI_CH4.csb and BGM_GKI_EXT.csb
which bgm is which?
i want to change the bgm for gouki and gouken's rival music to their
own theme's
## Post #76
- Username: yohansm1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 06, 2010 5:15 am
- Post datetime: 2011-09-28T14:00:38+00:00
- Post Title: Re: 360 Super Street Fighter 4

ok i was sucessfully able to repack the batlle.eaf with custom textures but when testing the it freezes if you go to the character selection theme. BTW i used the new quick bms tool with the reimport feature using the the ssfiv extract code...............any whos still moding ssfiv should try this and we can hopefully figure out this thing together
## Post #77
- Username: bigdave629
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 31, 2010 12:29 am
- Post datetime: 2012-08-03T02:33:38+00:00
- Post Title: Re: 360 Super Street Fighter 4

you can repack the battle.eaf with padajuans battle.eaf repacker with custom mods. I have been doing alot of mods for ssf4, but I wanted to know if someone could help me get an emo file back in a stage file?
## Post #78
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-22T23:56:24+00:00
- Post Title: Re: 360 Super Street Fighter 4

I know its a bad idea, to revive such an old thread, but any kind soul wouldn't happen to have the riggomatic by magnum
from this post: [viewtopic.php?p=54312#p54312](https://forum.xentax.com/viewtopic.php?p=54312#p54312)

Edit: Never mind.
