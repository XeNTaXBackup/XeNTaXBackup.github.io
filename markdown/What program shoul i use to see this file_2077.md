## Post #1
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-07T11:44:28+00:00
- Post Title: What program shoul i use to see this file?

I just want to know what program shoul i use to see this file?
.PIC
.IMG
.FLC
I hope you can help me, thanks in advance
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T12:38:58+00:00
- Post Title: What program shoul i use to see this file?

It depends on from what game you ripped them from.

for example ".PIC" can be lots of different pic types.
(same with IMG),  is FLC even used nowadays?

I think flc is an old animation type format.
but if you found that in a game its most probably a false-positive 
detection.

examples? =o...please upload.
## Post #3
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-07T14:48:25+00:00
- Post Title: What program shoul i use to see this file?

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T15:36:36+00:00
- Post Title: What program shoul i use to see this file?

Hi again! =D

ive got bad news and good news. lets start with the bad news.

All of those images are false-positive ones.  (the ripper detected something that looked like that format , but it wasnt, and it ripped it anyway just incase if it really was this format).

However, do not use the "Various Graphics" anymore. its pretty unsafe, sorry
that it isnt mentioned in the program, it will be in next release.

The Good news. the files actually contains graphic data. but i havent found
out in which the REAL format is yet. but it is indeed graphics.
still investigating... =)

when ripping from a PS2 game, try to be more specific with the ripper
and set options with PS2 specific formats. Like VAG, TIM2, maybe even PNG, JPEG. but never use "Various Graphics" these are odd formats, which i may even stop to support, due to the high rate of falseripping.
## Post #5
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-07T15:52:33+00:00
- Post Title: What program shoul i use to see this file?

Thanks for the news , and yes i use Various Graphic because i didnt know.
But i glad that file contain graphic data. i want to rip the sprites.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T15:56:33+00:00
- Post Title: What program shoul i use to see this file?

Here are some raw rips i did from the files.

in the sci_ file i found some 8 bit 256x256 images.

here is an example. (when reading it raw)

the palette is ofcourse wrong as i dont know the colors of it.
but it seems like graphics from the game :X
[found8.jpg](https://xentaxbackup.github.io/file/846_found8.jpg)
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T16:01:13+00:00
- Post Title: What program shoul i use to see this file?

More raw rips.
[found9.jpg](https://xentaxbackup.github.io/file/847_found9.jpg)
## Post #8
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-07T16:05:29+00:00
- Post Title: What program shoul i use to see this file?

Thats fast! and it like a map file.
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T16:15:59+00:00
- Post Title: What program shoul i use to see this file?

Ive found out a way to detect these files properly now. i just have
to get my lazy ass and make a ripper/converter for it.
I will export it as TGA as i have no idea in what format this really is.
but i now see a palette header ontop of the raw data, this will be converted
to 32bit colors when exporting to TGA.

who made this game, what company? =o   *too lazy to google*
## Post #10
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-07T16:29:00+00:00
- Post Title: What program shoul i use to see this file?

Thank you for your work, the company who made this is Nippon Ichi, the one popular from strategy game and funny dialog inside.
They made Disgaea, Disgaea 2 cursed memories, Phantom Brave (i hope all this have same format so i can rip them all)
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T16:51:23+00:00
- Post Title: What program shoul i use to see this file?

A Preliminary exporter is made for this format.

remember to go into options, Enable "NIS-MK Texture" and press save.
this should now export any kinds of these textures to TGA.

[http://jaedernaub.ath.cx/jn191t.zip](http://jaedernaub.ath.cx/jn191t.zip)

There are still some other type of graphics here which i havent figured out yet.  =X

also tell me if this ripper works on the other games you mentioned, that would be good to know.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-07T17:14:28+00:00
- Post Title: What program shoul i use to see this file?

> Reply from Strobe
>
> A Preliminary exporter is made for this format.

remember to go into options, Enable "NIS-MK Texture" and press save.
this should now export any kinds of these textures to TGA.

http://jaedernaub.ath.cx/jn191t.zip

There are still some other type of graphics here which i havent figured out yet.  =X

also tell me if this ripper works on the other games you mentioned, that would be good to know.

Strriiiiiiike! Strobe gets to homebase!
## Post #13
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-07T17:45:42+00:00
- Post Title: What program shoul i use to see this file?

It works so far i rip all the texture for map, but i think the other graphic that havent been figured is the characters sprites and icon.

I test it with La Pucelle and Disgaea they work to, i havent test it with Disgaea 2 and Phantom Brave because my friend still play it.
## Post #14
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-08T04:00:07+00:00
- Post Title: What program shoul i use to see this file?

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-10T14:15:53+00:00
- Post Title: What program shoul i use to see this file?

Downloaded. Investigating :X

for some reason i think of DDS files when i see the graphic data
of the files i cannot read properly. maybe they are just DDS data
with modified headers....

time will tell.....
## Post #16
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-09-22T12:30:56+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: LustD
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 19, 2006 10:21 pm
- Post datetime: 2006-10-03T15:50:49+00:00
- Post Title: 

I try your newer version of Jaeder and try to rip Disgaea 2. thus i found this file most likely this is the charset i want to rip, but the program only manage to rip one file.
I hope you can help me to rip this file.
Do i need to upload the data file to?
[mk_ 24809569_xxxx.rar](https://xentaxbackup.github.io/file/880_mk_ 24809569_xxxx.rar)
