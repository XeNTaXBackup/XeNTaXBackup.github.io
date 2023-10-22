## Post #1
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2012-03-06T05:52:51+00:00
- Post Title: Blacklight: Retribution .bnk(BKHD) & RIFF wavefmt

Howdy. While there are many tools for these formats, I've only been able to churn out unplayable files from this. 

The steps I've taken seem to extract the files okay, but when converting them from an unplayable.wav to .ogg with ww2ogg, it never comes out correctly.

I've uploaded the .bnk in question, as well as a sample .wav output by bnkextr.

[http://filesmelt.com/dl/SB_WeaponBank_bnk.rar](http://filesmelt.com/dl/SB_WeaponBank_bnk.rar)

[http://filesmelt.com/dl/SB_WeaponBank.001_.wav](http://filesmelt.com/dl/SB_WeaponBank.001_.wav)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-06T17:13:15+00:00
- Post Title: Blacklight: Retribution .bnk(BKHD) & RIFF wavefmt

This uses the new encoder (aoTuV 6.03), ww2ogg by default uses the packed codebooks for the reference encoder (libvorbis).  Support for using other files was added in ww2ogg 0.18.

Make sure you get 0.18 or later (newest is 0.19 and I'd recommend that), unzip the packed_codebooks_aoTuV_603.bin as well as the ww2ogg.exe, and run it like this on the .wavs:

ww2ogg --pcb packed_codebooks_aoTuV_603.bin BLAH.wav

One other note: In general you should use revorb ( [http://www.hydrogenaudio.org/forums/lof ... 64328.html](http://www.hydrogenaudio.org/forums/lofiversion/index.php/t64328.html) ) to fix up the granulepos in the files ww2ogg outputs.  This is particularly important with short samples like this, otherwise decoders will make the wrong assumptions about the latency and cut off some of the first milliseconds.  This is something ww2ogg should be able to do, but it has to handle so many different versions of WWise that it'd take a bit of work, and revorb already exists.
## Post #3
- Username: ShinobiMao
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Sep 07, 2010 11:41 pm
- Post datetime: 2012-03-06T18:34:03+00:00
- Post Title: Blacklight: Retribution .bnk(BKHD) & RIFF wavefmt

Thanks! I knew if it were you who replied that a solution would definitely be found. Everything worked perfectly and now I'm able to browse through the files with ease. 
For anyone else who'd stumble across this post, you can make and run a .bat file to make it easier. Here's what I did:

```
del "%%a" )
for %%a in (*.ogg) do revorb "%%a"
```


After the .bnk is extracted of course. I used [bnkextr](http://narod.yandex.ru/100.xhtml?ctpax-cheater.narod.ru/personal/bnkextr.zip).
## Post #4
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-10-21T08:55:54+00:00
- Post Title: Blacklight: Retribution .bnk(BKHD) & RIFF wavefmt

I'm stuck at extracting BNK step. bnk files from Zone of the Enders HD Collection. Using bnkextr.exe and nothing happens. I'm doing it with 360 and PS3 version and nothing. I tried drag & drop and command line. 

Maybe it's a different type of bnk? Please advice. Here are a couple of samples: 

[https://mega.co.nz/#!L0NERTKC!nxexgFYg1 ... ab6aug05ss](https://mega.co.nz/#!L0NERTKC!nxexgFYg1Q9rLwpqT4-h-QPbAcdvypnq_ab6aug05ss)
## Post #5
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-11-04T11:46:25+00:00
- Post Title: Blacklight: Retribution .bnk(BKHD) & RIFF wavefmt

> Reply from MiLØ
>
> I'm stuck at extracting BNK step. bnk files from Zone of the Enders HD Collection. Using bnkextr.exe and nothing happens. I'm doing it with 360 and PS3 version and nothing. I tried drag & drop and command line. 

Maybe it's a different type of bnk? Please advice. Here are a couple of samples: 

https://mega.co.nz/#!L0NERTKC!nxexgFYg1 ... ab6aug05ss

I tested on global_sfx.bnk and it worked (222 sound files).

Just put that in the batch file: 

```
bnkextr.exe global_sfx.bnk /swap
```


It's not a different type of .bnk archive 'cause the header is correct and the STID not screwed. The byte order is just originally swapped so you got to swap it back to extract it.

Cordialy.
