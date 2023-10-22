## Post #1
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-13T14:12:19+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

Hi, i have extracted these files from Urban Chaos ps2 

how to explore or extract ent files
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-14T18:50:44+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

First, how did you extract these files?  I only ask because the file sizes shown on your list look incorrect.  For example, 1-01.ENT should be 7,206,912 bytes.

The files have a simple file table structure, and all the data is zlib compressed.  I couldn't find a BMS script online, but it should be easy enough to come up with one to extract and decompress them.
## Post #3
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T04:57:05+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

i have used this script

[http://aluigi.org/bms/urban_chaos_ps2.bms](http://aluigi.org/bms/urban_chaos_ps2.bms)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-15T10:48:06+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

I tried that script and it didn't seem to work properly for me with the European version.  Maybe different releases have different files?

I've attached my BMS scripts - one for the main GAME.DIR archives and one for the ENT/GEO files.

Let me know if they work ok for you.
[Urban Chaos PS2.zip](https://xentaxbackup.github.io/file/16353_Urban Chaos PS2.zip)
## Post #5
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T10:55:27+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

none of them works
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-15T11:05:55+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

What errors are you getting?

Can you upload the GAME.DIR file so I can see if it's the same as mine?

Thanks.
## Post #7
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T11:20:30+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

my goal is to get the game original soundtracks, idk is that possible or not 

here is game.dir
[GAME.rar](https://xentaxbackup.github.io/file/16354_GAME.rar)
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-15T11:49:43+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

I can see the problem now.  You do have a different version to me.  You maybe have the USA release?

Your GAME.DIR file is different to mine - the filenames are in a slightly different order and the file offsets and sizes are different values.

The audio is all in the .SAF files as far as I can tell, so you need to be able to extract them properly first.  The .SAF files are all headerless standard Playstation 4-bit audio, which PSound can read.

I'll have a look at your GAME.DIR file and investigate further.
## Post #9
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T11:52:34+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

if i donwload usa release i can use ur scripts to extract it ?
## Post #10
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T11:53:28+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

or yo send me your version link. i mean the game link
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-15T12:09:21+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

I have the European disc, so my GAME.DIR file proably wouldn't work for you - and I'd probably need your whole disc to see how the files are stored.

If you get the European version, my scripts will work.
## Post #12
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T12:11:28+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

im on it, im downloading it now, shall i keep you posted if i get any error ?
## Post #13
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T12:33:27+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

i'm getting this error
[Screenshot_1.png](https://xentaxbackup.github.io/file/16356_Screenshot_1.png)
## Post #14
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T13:11:02+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

it worked, thanks m8
## Post #15
- Username: wesername
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jun 13, 2019 10:10 pm
- Post datetime: 2019-06-15T13:31:50+00:00
- Post Title: how to extract this file? [Urban Chaos PS2 .ent]

and i wanna learn create scripts like this, do you have any pdf or online source ?
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-15T16:44:32+00:00
- Post Title: Re: how to extract this file? [Urban Chaos PS2 .ent]

Glad you got sorted!

I don't know anything further about how to get the sounds - it's a project to work on when I get the time.

If you want to learn more about creating these, you could start with the Quickbms website: [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm) - a lot of good information and examples on there to get started with.

Good luck!
