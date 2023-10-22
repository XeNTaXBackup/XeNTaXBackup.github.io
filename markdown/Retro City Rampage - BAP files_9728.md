## Post #1
- Username: LuigiBlood
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 29, 2010 5:26 am
- Post datetime: 2012-10-11T19:58:05+00:00
- Post Title: Retro City Rampage - BAP files

So... I gotta admit, those files got my attention as I want the songs.

But I found out those are pretty much made for music. I mean, apparently, it has "IT" and WAV files inside (from the file list included), with 50% of the file being unsigned 8-bit samples.

Though I can't seem to figure it out. I'd like to get those songs as they are some pretty cool NES-styled music.

The file type is called "Brian's Audio Pack".
My source is official, as I asked him directly:
[https://twitter.com/LuigiBlood/status/2 ... 7404790784](https://twitter.com/LuigiBlood/status/255967637404790784)
## Post #2
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2012-12-26T17:29:34+00:00
- Post Title: Retro City Rampage - BAP files

I want too!

I would expect that they are impulse tracker ".it" files right? Maybe if we can find the specs for that format anywhere, we can scan the binary contents of audio_music_W32.bap to see if the tracks are in there unencrypted.
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-30T11:13:22+00:00
- Post Title: Retro City Rampage - BAP files

Apparently he made his own tracker format as well. Files start off with a "BTRK" header, so I'm not sure what's up with the .it and .wav filenames.
## Post #4
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2014-11-30T22:43:43+00:00
- Post Title: Retro City Rampage - BAP files

> Reply from barti
>
> Apparently he made his own tracker format as well. Files start off with a "BTRK" header, so I'm not sure what's up with the .it and .wav filenames.What files?
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-01T20:29:35+00:00
- Post Title: Retro City Rampage - BAP files

> Reply from Nerd42
>
> What files?

Files inside the .BAP containers.
## Post #6
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2014-12-03T22:46:51+00:00
- Post Title: Retro City Rampage - BAP files

> Reply from barti
>
> Nerd42 wrote:What files?

Files inside the .BAP containers.How'd you get into them?
## Post #7
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-03T23:38:45+00:00
- Post Title: Retro City Rampage - BAP files

I've tried to reverse the format myself and make a QuickBMS script (which isn't really useful in its current state):

```

idstring "BAP0"
get VERSION short
get FILES0  short
get FILES1  short
get FILES2  short
get FILES1OFF long
get FILES2OFF long
get NAMEOFF long
math NAMEOFF += 1

getdstring COMMENT 24

for i = 0 < FILES0
get OFFSET long
get SIZE   long
get DUMMY  long
get NAME   long
math NAME += NAMEOFF

savepos TMP
goto NAME
get NAME string
goto TMP

log NAME OFFSET SIZE
next i

#for i = 0 < FILES1
#get OFFSET long
#log "" OFFSET 500
#next i

#for i = 0 < FILES2
#get OFFSET long
#log "" OFFSET 500
#next i
```


The files look like they're separated somehow. I'm guessing files0 are "BTRK" headers, files1 are PCM samples and files2 are the track patterns or something like that (I'm not very familiar with tracker formats).
