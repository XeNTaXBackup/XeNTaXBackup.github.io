## Post #1
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-11-24T17:49:58+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Hi guys, I decided to try out this game. But first, the Sounds. After poking around a little, I found these archives here:


These got to be the game's core files. Their format .Arch04 seemed very familiar to me, and that's because F.E.A.R. 2 used .Arch01.
Here is a sample of the new archive.

I tried to simply change the 04 to 01 and try to open it.
So, using F.E.A.R. 2 TOOLS made by Crypton I was able to extract the archieve's content.
This action rewarded me with a lot of .bndl files. Which I thought was cool, because now I can use Crypton's BNDL Extractor to unpack them. But I had no luck with it. And that's where you come in. Please take a look at the samples above. Or at the .BNDL File that I already extracted. I'm not quite sure it is a sound file.

I'd be very grateful if someone would please check this out. Any help is appreciated in here.
Thanks in advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-25T00:26:15+00:00
- Post Title: Guardians of Middle-Earth .Arch04

> Reply from Luriam
>
> I'm not quite sure it is a sound file.Then why not use a hex editor to have a look at it?
Looks like a text resource.
Just copy the data from 0x15E1E to 0x113EF5 into a txt file.
If you replace the 00 00 at 0x15E1E by 0xFF 0xFE before 
you'll get a UNICODE txt file to be opened by notepad.

In the remaining non unicode text from 0x113F00 up to the end you can replace every 00 00 by 0x0D 0x0A
(and the remaining 00s by 0D 0A)
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-11-25T08:57:13+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Quickbms script for unpack

```
get version long
get nametablesz long
get nametablesz2 long
get null longlong
get files long
savepos offset
log MEMORY_FILE offset nametablesz
math offset += nametablesz2
for i = 0 < files
goto offset
get nameoff long
get size long
savepos offset
goto nameoff MEMORY_FILE
get name string MEMORY_FILE
log name offset size
math offset += size
next i
```
## Post #4
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-11-25T16:42:06+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Thanks shakotay2, but I could never think of such a thing, because I'm fairly new at this. 
But I appreciate your patience and your contribution.


Thanks a lot for the script swuforce! It worked nice and easy. 
After successfully unpacking the .BNDL file, I got some other kind of archive. This time it's .bnk
I have tried several methods of unpacking/extracting it's contents. But I have failed. Again.
I thought I got something for a little while, when I tried using ww2ogg, but the file was so distorted and "broken" that revorb was just crashing when used.

Anyway, here is a sample of the .BNK container.
Thanks for your help! I hope you can help me get this figured out.
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-11-26T09:09:44+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Use AlphaTwentyThree's script on bnk: [viewtopic.php?f=13&t=4450&p=89662#p89662](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=89662#p89662)
## Post #6
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-11-26T17:23:16+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Thanks again swuforce! Also props to AlphaTwentyThree for the script!

But, once again... *sigh* hopefully the last time, I need your help.
Id did extracted the sounds, but they are .wwise.
I tried all sorts of ww2ogg but no luck there.

Here's a sample of the file.
Guardians of Middle-Earth .wwise Sample

I appreciate your support guys. Thanks!
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-11-26T18:32:58+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Use this command: ww2ogg.exe filename.wwise --pcb packed_codebooks_aoTuV_603.bin
Then use revorb.
## Post #8
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-11-26T19:24:47+00:00
- Post Title: Guardians of Middle-Earth .Arch04

It worked like a charm! I feel so indebted to you. 
Endless kudos to you swuforce.
I am really grateful for what you did here. 
Thanks for sticking around.
## Post #9
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-03-20T04:43:06+00:00
- Post Title: Guardians of Middle-Earth .Arch04

The tools always crash for me when using them, and that script gives an error on BNDL files as well...is there any reliable method by which to extract the models?
[https://www.dropbox.com/s/g2kslkiihu8dr ... hirez.bndl](https://www.dropbox.com/s/g2kslkiihu8drml/champ_sauron_hirez.bndl)
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-03-20T09:57:59+00:00
- Post Title: Guardians of Middle-Earth .Arch04

regarding the arch* archives you can ever use my fear.bms script, it's still the same format:
[http://aluigi.org/papers/bms/fear.bms](http://aluigi.org/papers/bms/fear.bms)

while for this BNDL format I made this script:
[http://aluigi.org/papers/bms/others/bndl_4.bms](http://aluigi.org/papers/bms/others/bndl_4.bms)
## Post #11
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-03-20T13:35:32+00:00
- Post Title: Guardians of Middle-Earth .Arch04

Luigi, my good fellow, you are an embodiment of awesome. Thank you so much!

Only issue now is the fact they unpack to MESH files. Any way to view or convert these?

[https://www.dropbox.com/s/oyhwno2o726he ... auron.mesh](https://www.dropbox.com/s/oyhwno2o726hekt/champ_enchanter_sauron.mesh)
