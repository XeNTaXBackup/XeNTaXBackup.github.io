## Post #1
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-05-30T22:56:58+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

Hi,

Is there a way to unpack and repack the .pak file from Hellboy: Asylum Seeker? I am interested in translating this game.
Edit: Here's the file: [https://www.mediafire.com/folder/bnbka7sjs4xms/Hellboy](https://www.mediafire.com/folder/bnbka7sjs4xms/Hellboy)


Thank you.
## Post #2
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-04T16:23:00+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

Anyone?
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-06T06:23:27+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

The format is simple. All the filenames are there and nothing is compressed. Anyone with basic knowledge could be able to repack it.
## Post #4
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-06T13:06:18+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> The format is simple. All the filenames are there and nothing is compressed. Anyone with basic knowledge could be able to repack it.

And how can i do that? My knowledge of unpack/repack is very limited.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-06T14:56:15+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from vitorrs100
>
> And how can i do that? My knowledge of unpack/repack is very limited.

I'm not saying you can do that. Maybe some people here who didn't download your file because its so big will now be willing to help you. I could, but now I don't have time for this, because I'm working with Batman.
## Post #6
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-06T15:02:28+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> 
I'm not saying you can do that. Maybe some people here who didn't download your file because its so big will now be willing to help you. I could, but now I don't have time for this, because I'm working with Batman.

Ah Ok, i misunderstood your comment. My bad.
## Post #7
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-10T12:31:15+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

Anyone?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-10T20:46:13+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

Guess noone. (It's called "The WORST Playstation Game Ever Made", isn't it?  )

Anyway, you'll have to spend more efforts, for example upload a screenshot of the first 1024 bytes of the pak.
And a shoot of the region where the filenames to start.
The filenames and the offsets are required. The offsets often to be found at the beginning of the archive the filenames at the very end (but not always).
## Post #9
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-11T19:22:53+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from shakotay2
>
> Guess noone. (It's called "The WORST Playstation Game Ever Made", isn't it?  )

Anyway, you'll have to spend more efforts, for example upload a screenshot of the first 1024 bytes of the pak.
And a shoot of the region where the filenames to start.
The filenames and the offsets are required. The offsets often to be found at the beginning of the archive the filenames at the very end (but not always).

Ok, i'm not sure if i did it right, but here are the screenshots:

The beginning of the file:


The beginning of the filenames:
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-11T22:26:11+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

thx. Next would be to find the beginning of a file. Since daemon1 said "nothing is compressed" it should not be too hard but you need to be familiar with file types, of course. You know how to identify graphic files from their signature?

If no, try to find a text file. Often script files like lua are in plain ASCII for example. So are most ini and xml files.

We'd need a screenshot from the starting point (address) of such a file again. And it should be the first file of that type counted from the beginning of the archive file.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-12T06:29:50+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

First file (01_small_town_e5.enw) starts from 0x0006BC54 - right after the table. There's no offset pointing to this, as far as I can see. But we have all relative file offsets starting from that point. 

The only thing I can't understand is the meaning of those numbers 0xF83b58 - 0x0107EB18
Seems some sort of a table 1MB in size, but why? Maybe something related to PS, no idea.

p.s. that may be offsets in another file
## Post #12
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-12T14:27:22+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from shakotay2
>
> thx. Next would be to find the beginning of a file. Since daemon1 said "nothing is compressed" it should not be too hard but you need to be familiar with file types, of course. You know how to identify graphic files from their signature?

If no, try to find a text file. Often script files like lua are in plain ASCII for example. So are most ini and xml files.

We'd need a screenshot from the starting point (address) of such a file again. And it should be the first file of that type counted from the beginning of the archive file.

This is the first text file i've found. Apparently it is in data/script folder:



> Reply from daemon1
>
> First file (01_small_town_e5.enw) starts from 0x0006BC54 - right after the table. There's no offset pointing to this, as far as I can see. But we have all relative file offsets starting from that point. 

The only thing I can't understand is the meaning of those numbers 0xF83b58 - 0x0107EB18
Seems some sort of a table 1MB in size, but why? Maybe something related to PS, no idea.

p.s. that may be offsets in another file

These are all the files of the game:
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-12T14:47:43+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from vitorrs100
>
> 
These are all the files of the game:

Very strange indeed. Then I have no idea what these numbers are: 0xF83b58 - 0x0107EB18
And I think they are needed to repack the game.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-14T09:11:10+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

After some analyzing i think this may be a static table inside of .exe containing all references to the resources.

Can you make a dump of the game running?
## Post #15
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-14T11:32:07+00:00
- Post Title: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> After some analyzing i think this may be a static table inside of .exe containing all references to the resources.

Can you make a dump of the game running?

How can i do that? "Create Dump File" in Task Manager?
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-14T11:39:08+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

yes
## Post #17
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-14T11:44:39+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> yes

Ok, uploading.
## Post #18
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-14T12:24:15+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Here it is:
[http://www.mediafire.com/download/mycn7 ... ellboy.rar](http://www.mediafire.com/download/mycn7wxl8v1s1yg/hellboy.rar)
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-14T14:02:05+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Unfortunately, no such table. Can you also upload music.pak so i can compare 2 paks?
## Post #20
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-14T14:14:09+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> Unfortunately, no such table. Can you also upload music.pak so i can compare 2 paks?

Uploading.
## Post #21
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-14T15:15:31+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Done:
[http://www.mediafire.com/download/56mr8 ... /music.rar](http://www.mediafire.com/download/56mr8im8rxhan0f/music.rar)
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-14T16:24:29+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Hmm... Same format, different numbers. No idea what these are. Anyway, we can try and repack the file with these numbers intact. Very strange still.
## Post #23
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-19T15:02:34+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

No news?
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-21T08:32:42+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

No time yet. Also i think before wasting time on repacker we need some experiment to check will it even work. What do you want to replace, sound or text?
## Post #25
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-06-21T11:17:50+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> No time yet. Also i think before wasting time on repacker we need some experiment to check will it even work. What do you want to replace, sound or text?

Text.
## Post #26
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-07-07T19:55:53+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

So... nothing new?
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-11T13:03:31+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

I'm almost finished with batman
## Post #28
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-07-11T13:08:55+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> I'm almost finished with batman

Ok, i'll wait
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-13T19:56:40+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

heres the unpacker, it will unpack all resources, but you see, text is in script files, and they are in some unknown format. I suggest you to just edit the PAK file, not changing the text size.
[Hellboy.rar](https://xentaxbackup.github.io/file/9417_Hellboy.rar)
## Post #30
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-07-16T14:25:01+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> heres the unpacker, it will unpack all resources, but you see, text is in script files, and they are in some unknown format. I suggest you to just edit the PAK file, not changing the text size.

Thanks, i'll take a look.
## Post #31
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-07-16T14:55:56+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

As far as i looked, some texts are graphics and the rest is in dialog.txt.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-16T15:16:44+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Look for example at the file chicken_cooked_use.scw

There's some text and I don't see it in dialog.txt.
## Post #33
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-07-18T13:54:27+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from daemon1
>
> Look for example at the file chicken_cooked_use.scw

There's some text and I don't see it in dialog.txt.

Hmm... i'll see how many of these files have texts.
## Post #34
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2015-08-03T18:52:23+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Sorry for the long silence, a lot of things happened to me recently. Here's all script files that have texts. If anyone mind to take a look.
[HB text.rar](https://xentaxbackup.github.io/file/9480_HB text.rar)
## Post #35
- Username: hellboy4
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 18, 2016 9:12 pm
- Post datetime: 2016-02-18T13:17:14+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

unpacker doesn't work. Foobar displays 

```
"C:\Users\Adrian\Downloads\music\music\dripping_music.wav""
```
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-18T15:35:03+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from hellboy4
>
> unpacker doesn't work.

Unpacker works.

But its only made for main pak file, not music.
## Post #37
- Username: hellboy4
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 18, 2016 9:12 pm
- Post datetime: 2016-05-08T13:25:13+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

sorry, my fault.

So... nothing new? I have soundtrack from Hellboy but in WMA 96kbps from another forum. Unfortunately i don't remember what's the name of this forum was.

It's looks possible, but may be impossible for you guys
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-08T16:45:29+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

its just like nobody needed the music

if I remember correctly, it was all in plain WAV files

and that means you can open them yourself, there's no need to bother with such a simple thing

or just split them with WAV splitter bms script
## Post #39
- Username: hellboy4
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 18, 2016 9:12 pm
- Post datetime: 2016-05-09T07:41:10+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

I found splitter scripts only for Xbox 360 packages on this forum. Dunno what do next.

You trying to say, that's music.pak is one long wav?
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-09T08:03:55+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

> Reply from hellboy4
>
> I found splitter scripts only for Xbox 360 packages on this forum. Dunno what do next.

You trying to say, that's music.pak is one long wav?

No, its many wav files, but you can always open them as one raw file.

And I meant this script:
[viewtopic.php?f=13&p=74664#p74664](http://forum.xentax.com/viewtopic.php?f=13&p=74664#p74664)

Also many tools (vgmtoolbox for example) have WAV splitting function.
## Post #41
- Username: hellboy4
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 18, 2016 9:12 pm
- Post datetime: 2016-11-11T00:35:58+00:00
- Post Title: Re: Hellboy: Asylum Seeker (.pak)

Audio tracks and sounds from Hellboy is fully playable. All we need to do, is import these files in Audacity as RAW Audio with settings below

For music I recommend export all files, combine them into one file and split again.

Gosh, if u guys have problem with understanding me - i'm from Poland 
[untitled.PNG](https://xentaxbackup.github.io/file/11896_untitled.PNG)
