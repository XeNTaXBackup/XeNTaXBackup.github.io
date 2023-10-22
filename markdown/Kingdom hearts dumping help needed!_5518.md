## Post #1
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-09T22:50:17+00:00
- Post Title: Kingdom hearts dumping help needed!

now..along time ago i ripped some kh files o.o and it ended up dumping every single file  i ended up dumping everything off of destiny islands..the papou fruit.. the palm trees... even soras room... it was so cool. but... sadly my computer crashed..    and i never saw it again D: im just trying to remember how to do this... D: has anyone else done this? :\ ... help is much appreciated. ^.^
## Post #2
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-10T06:19:20+00:00
- Post Title: Kingdom hearts dumping help needed!

Falo has a dumper tool, but back then Yaz0r's tool was the only available dumper tool. Also, if your hard drive is still intact you can retrieve the files from it one way or another. But although I know you can dump the character models, never have I heard of dumping Sora's room before. Are you sure you dumped Sora's room?

EDIT: I found it. There is a Paopu Tree and other items in the di01.ard file. You need to brute force or name table the ard files out of Falo's KH1 dumper, and unless someone comes out with a tool to extract MDLS files from ard files, you need to hex edit every eight lines before the word MOBJ and save the result as a(n) MDLS file.
## Post #3
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-10T21:12:01+00:00
- Post Title: Kingdom hearts dumping help needed!

ok i hex dumped the models and saved them as mdls but... when i put them in noesis model viewer they dont appear and i cant use Modelviewer WX 0.3 Cause i click it and It says Modelviewer WX 0.3 has stopped working... :\...     wtf?! xD
## Post #4
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T17:16:52+00:00
- Post Title: Kingdom hearts dumping help needed!

Did you make sure you extracted the MDLSs from the ARDs so that the MOBJ header is at the 0x80 mark? And what do you mean by hex dump?
## Post #5
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T17:38:27+00:00
- Post Title: Kingdom hearts dumping help needed!

oh i was using transhextion xD  lol and idk if i made sure XD lol
## Post #6
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T17:40:52+00:00
- Post Title: Kingdom hearts dumping help needed!

Can you post a sample mdls file so that I may see why it's wrong? The last item on it should be _KDN or something like that.
## Post #7
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T17:45:58+00:00
- Post Title: Kingdom hearts dumping help needed!

D: the extension mdls is not allowed DX
## Post #8
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T17:48:53+00:00
- Post Title: Kingdom hearts dumping help needed!

Post it on another site like Brickshelf and then send over the link. or make it a txt file and send that over.
## Post #9
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T17:53:56+00:00
- Post Title: Kingdom hearts dumping help needed!

here it is in text form 

[http://www.brickshelf.com/gallery/murod ... utree.mdls](http://www.brickshelf.com/gallery/murodragon/stuff/papoutree.mdls)
## Post #10
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T18:14:27+00:00
- Post Title: Kingdom hearts dumping help needed!

That's all wrong. Find in an ARD file where it says MOBJ, go back eight lines, and from there copy until you see an end line like _KD5 or something. Your file is way too small to be the paopu tree. I don't have the ARD files on this computer, so unless someone can send me an ARD file, I won't be able to upload what the papou tree should look like until Sunday.
## Post #11
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T18:18:27+00:00
- Post Title: Kingdom hearts dumping help needed!

im going to try to upload one on 4shared right now lol
## Post #12
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T18:24:39+00:00
- Post Title: Kingdom hearts dumping help needed!

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T18:43:06+00:00
- Post Title: Kingdom hearts dumping help needed!

I extracted them successfully.

[http://www.brickshelf.com/gallery/mirro ... utree.mdls](http://www.brickshelf.com/gallery/mirrorman95/Zatth/paoputree.mdls)

[http://www.brickshelf.com/gallery/mirro ... /gate.mdls](http://www.brickshelf.com/gallery/mirrorman95/Zatth/gate.mdls)
## Post #14
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T18:44:04+00:00
- Post Title: Kingdom hearts dumping help needed!

^.^ thanks
## Post #15
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-11T18:46:49+00:00
- Post Title: Kingdom hearts dumping help needed!

You're welcome. Now if anyone came out with an extractor for the ARD MDLSs, that would be something!
## Post #16
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-11T18:47:36+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

lol yeah it would haha
## Post #17
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-12-12T14:07:56+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

Never read this thread until now lol.

Anyway, been extracting some mdls from Di01.ard. Just seems to be random objects rather than maps so far :/
## Post #18
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-12T14:37:14+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

hmmm  i wonder what these are... moa files???.... maybe those are the maps.. xD Idk lol
[moa.jpg](https://xentaxbackup.github.io/file/3687_moa.jpg)
## Post #19
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-12T17:07:21+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

Lol i  found some interesting keywords while looking through the ew01.ard ew stands for end of the world... o.o kairi didnt have a keyblade in kh1..? o.o i wonder what this is lol... maybes it Kairi's lucky charm that appears in one of the cutscenes?
[kairiskey.jpg](https://xentaxbackup.github.io/file/3688_kairiskey.jpg)
## Post #20
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-13T04:32:07+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

anyways im trying to rip some keyblade models but so far has been unsuccessful lol...
## Post #21
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-13T15:06:16+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

[http://www.brickshelf.com/gallery/mirro ... w02.3.mdls](http://www.brickshelf.com/gallery/mirrorman95/Zatth/kairis_keychain_ew02.3.mdls)
This was the keychain of the keyblade in KH1 that represented Kairi, the Oathkeeper, found in the ew02.ard file.
## Post #22
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2010-12-13T19:07:36+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

awsome  haha i found a papou fruit right off the tree...i'll post more objects later.
[papoufruit.jpg](https://xentaxbackup.github.io/file/3691_papoufruit.jpg)
## Post #23
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2011-03-03T10:57:03+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

Why aren't the world objects found through the nametables anway? It's really exhausting to extract them by copy and paste.
## Post #24
- Username: Murodragon
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Nov 22, 2010 7:45 am
- Post datetime: 2011-03-05T21:10:22+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

Yeah i agree 100%
## Post #25
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-05T22:03:50+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

Those entries a few posts up probably are their equivalent of nametables. The KH1Dumper just isn't properly equipped to dump them. Falo or yaz0r could probably fix their dumpers, if either of them has time.
## Post #26
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-06T02:44:45+00:00
- Post Title: Re: Kingdom hearts dumping help needed!

I hope falo gonna fix and release the new dumper soon
