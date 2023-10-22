## Post #1
- Username: kawayide
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-26T02:34:34+00:00
- Post Title: Idolm@ster

Ill post the converter when i have it more complete but hear is a teaser.
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-07-26T03:56:53+00:00
- Post Title: Idolm@ster

you know what would make a killing, idolmaster desktop. just have these girls dance around while you place music.. I wonder why there arent too many desktop interactive software out there.. well aside from the Windows widget

anyway cant wait to see more of them models. great work man
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-27T01:26:49+00:00
- Post Title: Idolm@ster

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-07-27T09:46:56+00:00
- Post Title: Idolm@ster

That so great chrrox!! your work is amazing, thanks alot i will wait your converter   Did you use the idolmaster xbox 360 ??
## Post #5
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-07-27T13:05:17+00:00
- Post Title: Idolm@ster

i'm guessing that it's from 360, that game kinda remind me of mikumikudance

anyway good work so far sir chrrox, keep it up
## Post #6
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-07-27T13:19:28+00:00
- Post Title: Idolm@ster

Yay its aweeeeeeeeeeesome chrrox
That is amazing
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-29T17:19:07+00:00
- Post Title: Idolm@ster

I will post the converter this weekend with or without bones if me and my friends can get the format done then ill support them otherwise its mesh only.
here is an attempt at me doing a toon render in max.
## Post #8
- Username: med2392
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-30T16:39:40+00:00
- Post Title: Idolm@ster

Here are the steps to extract and convert the textures
1st extract the bna files with this bms script.
[viewtopic.php?f=10&t=4812](http://forum.xentax.com/viewtopic.php?f=10&t=4812)

then use this script to extract the .nut files

```
endian big
get version short
get files short
goto 0x10
for i = 0 < files
savepos offset
get size long
get name basename
string name + i
string name + .dds
log name offset size
math offset + size
goto offset
next i

```


now use this bms script to convert those dds files to normal textures.

```
endian big
get size long
getdstring null 0xF
get type byte
get width1 byte
get width2 byte
get height1 byte
get height2 byte
if type == 1
putVarChr MEMORY_FILE 0x57 0x33
endif
if type == 0
putVarChr MEMORY_FILE 0x57 0x31
endif
putVarChr MEMORY_FILE 0x11 width1 byte
putVarChr MEMORY_FILE 0x10 width2 byte
putVarChr MEMORY_FILE 0xD height1 byte
putVarChr MEMORY_FILE 0xC height2 byte
get name filename
append
math size - 0x50
log MEMORY_FILE 0x50 SIZE
append
set count size
math count / 2
goto 0x80 MEMORY_FILE
for i = 0 < count
savepos start MEMORY_FILE
endian little
get num short MEMORY_FILE
endian big
putVarChr MEMORY_FILE start num short
next i
endian little
math SIZE += 0x80
log NAME 0 SIZE MEMORY_FILE


```


I will post the model converter soon and some model samples.
## Post #9
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-07-30T22:00:28+00:00
- Post Title: Idolm@ster

Thanks for the script "bro" 

Is it the script for the "The Idolm@ster: Live For You!" or for "The idolm@ster" game?

OFFTOPIC: Any body have a torrent o DL of the game because here is hard found a original game like that
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-30T22:42:21+00:00
- Post Title: Idolm@ster

I bought a copy on playasia and dumped it myself.
[http://www.play-asia.com/paOS-13-71-br- ... -2b5d.html](http://www.play-asia.com/paOS-13-71-br-49-en-70-2b5d.html)
## Post #11
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-07-30T23:01:32+00:00
- Post Title: Idolm@ster

> Reply from chrrox
>
> I bought a copy on playasia and dumped it myself.
http://www.play-asia.com/paOS-13-71-br- ... -2b5d.html

Thanks a lot for the info chrrox, i will try to search here, keep up the your good work
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-31T18:49:07+00:00
- Post Title: Idolm@ster

The contents of this post was deleted because of possible forum rules violation.
[max.rar](https://xentaxbackup.github.io/file/3282_max.rar)
## Post #13
- Username: luciasil
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 24, 2010 9:48 am
- Post datetime: 2010-07-31T22:29:17+00:00
- Post Title: Idolm@ster

very nice
thx
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-01T22:39:56+00:00
- Post Title: Idolm@ster

i am getting close


[](http://img213.imageshack.us/img213/849/bonesh.png)

here is the updated bone code if anyone can help with what i did wrong
[gmw.rar](https://xentaxbackup.github.io/file/3288_gmw.rar)
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-10T23:12:31+00:00
- Post Title: Idolm@ster

got it working 
[](http://img713.imageshack.us/img713/359/idolmasterbones.png)
## Post #16
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-08-11T00:31:42+00:00
- Post Title: Re: Idolm@ster

wow its awesome chrrox
## Post #17
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-11T01:26:04+00:00
- Post Title: Re: Idolm@ster

Sorry for not be so helpfull i don't know so much about code but that's a "amazing work bro ;D"
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-11T02:17:30+00:00
- Post Title: Re: Idolm@ster

just need to get textures auto assigned but this will do the job
run bones 1 then bones 2 then the mesh.
I should be able to get animations also for the game.

This was made possible with the help of my friends also without them i would of never done this.
I hope to have something like this soon
[http://www.youtube.com/watch?v=PHmXDfmQbsw](http://www.youtube.com/watch?v=PHmXDfmQbsw)
[Scripts.rar](https://xentaxbackup.github.io/file/3308_Scripts.rar)
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-08-11T11:09:44+00:00
- Post Title: Re: Idolm@ster

uploaded scripts
## Post #20
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-11T14:39:11+00:00
- Post Title: Re: Idolm@ster

Thanks "bro" your job is amazing
## Post #21
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-08-11T14:56:39+00:00
- Post Title: Re: Idolm@ster

> Reply from chrrox
>
> just need to get textures auto assigned but this will do the job
run bones 1 then bones 2 then the mesh.
I should be able to get animations also for the game.

This was made possible with the help of my friends also without them i would of never done this.
I hope to have something like this soon
http://www.youtube.com/watch?v=PHmXDfmQbsw

I hope do the same but  with the dream c club models
## Post #22
- Username: med2392
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 05, 2010 8:12 pm
- Post datetime: 2011-12-21T20:58:14+00:00
- Post Title: Re: Idolm@ster

any update for idolm@ster 2     , thx
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-21T21:35:07+00:00
- Post Title: Re: Idolm@ster

its the same format but its filesystem is encrypted.
## Post #24
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2012-01-04T16:34:23+00:00
- Post Title: Re: Idolm@ster

new The Idolm@ster: Gravure For You! Vol. 3 for ps3 exploracion is .tsk
## Post #25
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-04T16:48:19+00:00
- Post Title: Re: Idolm@ster

all the files are identical to the first game except they encrypted them.
## Post #26
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-05-08T16:26:49+00:00
- Post Title: Re: Idolm@ster

wow It looks great!
## Post #27
- Username: HatsuneMiku15
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 07, 2012 7:13 pm
- Post datetime: 2012-05-08T18:50:29+00:00
- Post Title: Re: Idolm@ster

Nice one!

I was also wondering if the Noire one is fixed already ;w;
## Post #28
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-06-06T09:02:50+00:00
- Post Title: Re: Idolm@ster

hi chrrox,i look at motion anime file(not bind pose motion). i'm sure one song has multiple motion files, and, divides to three group: left(file name with letter 'l'), center(with letter 'c'), right(with letter 'r'), corresponding to 3 dancers in game: left, center, right.
each group usually has 6 files: non-loop, xxloopxx, xxHANDLxx, xxHANDRxx....

these motion files are different from bind pose motion file, a strenge format:
usually only 9 to 25 channels in a file(but bones over 200)
each keyframe only 3 short value. I think they are just rotations. no scale and translation.

Do you know how channels are set to bones? And how to convert the keyframes?
## Post #29
- Username: hanable132
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 14, 2012 2:06 am
- Post datetime: 2012-08-02T18:53:29+00:00
- Post Title: Re: Idolm@ster

Sorry for the necro.

In case you are still wondering, it isn't that much different from the bind pose file.
So there are 25 3-tuple.
The first 2 short tuple are all 0 (which i guess you could say if for bone 0 and 1) the next short tuple is the the position(for bone 0 or 1?) 
the next 22 tuple are rotation corresponding  to bone 2 to 24.

for hand its all rotation where bone 24-39 is for the right and 40-54 is for the left.

So one line is one frame, where one frame is 1/60th of a second, so there is no keyframes.

On a side note I really can't' figure out imas2, if its encrypted or compressed, cause I can't tell the difference. However the s2d (bg2d) and nub2(sounds) files seems to have some kind of a pattern.
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-02T22:26:18+00:00
- Post Title: Re: Idolm@ster

they are encrypted based on file names.
best bet is to dump it from 360's ram.
that is what one guy did to extract the models and anims from it.
## Post #31
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2012-08-24T13:51:19+00:00
- Post Title: Re: Idolm@ster

> Reply from hanable132
>
> Sorry for the necro.

In case you are still wondering, it isn't that much different from the bind pose file.
So there are 25 3-tuple.
The first 2 short tuple are all 0 (which i guess you could say if for bone 0 and 1) the next short tuple is the the position(for bone 0 or 1?) 
the next 22 tuple are rotation corresponding  to bone 2 to 24.

for hand its all rotation where bone 24-39 is for the right and 40-54 is for the left.

So one line is one frame, where one frame is 1/60th of a second, so there is no keyframes.

On a side note I really can't' figure out imas2, if its encrypted or compressed, cause I can't tell the difference. However the s2d (bg2d) and nub2(sounds) files seems to have some kind of a pattern.
finally, I got it working with help of this thread.
shame that I did no crack but just begging for answer.
## Post #32
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2012-12-11T00:02:56+00:00
- Post Title: Re: Idolm@ster

the polycount for the girls in this game is it around 17000?
## Post #33
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-09-17T17:22:38+00:00
- Post Title: Re: Idolm@ster

Are there any news on decryption for PS3 or X360 ver?
## Post #34
- Username: TeridaxXD001
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 28, 2015 12:12 am
- Post datetime: 2016-02-06T22:40:55+00:00
- Post Title: Re: Idolm@ster

> Reply from chrrox
>
> just need to get textures auto assigned but this will do the job
run bones 1 then bones 2 then the mesh.
I should be able to get animations also for the game.

This was made possible with the help of my friends also without them i would of never done this.
I hope to have something like this soon
http://www.youtube.com/watch?v=PHmXDfmQbsw

I get an error any time I try to run any of these.

Error: invalid command "fname" or arguments -1 at line 5
## Post #35
- Username: NeonZed
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 09, 2015 11:15 pm
- Post datetime: 2016-09-27T04:02:21+00:00
- Post Title: Re: Idolm@ster

I know its too late for ask but, any news for Idolmaster 2? It would be great because the 2nd one has different models.
## Post #36
- Username: TeridaxXD001
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 28, 2015 12:12 am
- Post datetime: 2017-11-02T05:37:50+00:00
- Post Title: Re: Idolm@ster

The texture script works fine, but I still can't get the mesh or bones scripts to work for the life of me.
## Post #37
- Username: spiral6
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 30, 2019 3:03 pm
- Post datetime: 2019-11-30T07:06:42+00:00
- Post Title: Re: Idolm@ster

Still no luck with Idolmaster 2. Still encrypted and unable to extract archives for data.
## Post #38
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-11-30T14:06:37+00:00
- Post Title: Re: Idolm@ster

> Reply from spiral6 ↑Sat Nov 30, 2019 3:06 pm at Sat Nov 30, 2019 3:06 pm
>
> 
Still no luck with Idolmaster 2. Still encrypted and unable to extract archives for data.
[viewtopic.php?t=19105](https://forum.xentax.com/viewtopic.php?t=19105)
## Post #39
- Username: spiral6
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 30, 2019 3:03 pm
- Post datetime: 2019-12-02T10:30:02+00:00
- Post Title: Re: Idolm@ster

> Reply from chrrox ↑Sat Nov 30, 2019 10:06 pm at Sat Nov 30, 2019 10:06 pm
>
> 
spiral6 wrote: ↑Sat Nov 30, 2019 3:06 pm
Still no luck with Idolmaster 2. Still encrypted and unable to extract archives for data.

viewtopic.php?t=19105

I'm not entirely certain what this script is supposed to do. It does not decrypt the .scb files in the /resource/gscript folder, nor does it do anything for the .mpc, .nub2, .tsk or any other files...
## Post #40
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-12-02T10:39:41+00:00
- Post Title: Re: Idolm@ster

Your files must be bad then.
Just go download the original tool I mentioned if quickbms does not work for you.
## Post #41
- Username: spiral6
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 30, 2019 3:03 pm
- Post datetime: 2019-12-02T10:41:51+00:00
- Post Title: Re: Idolm@ster

And this should be working for the extracted data from the Xbox 360 version (ideally, an Xbox 360 iso backed up into .xex and folders?)

In addition to that, if there was a tool posted, was it deleted? There are a few forum posts that state that "The contents of this post was deleted because of possible forum rules violation."
## Post #42
- Username: spiral6
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 30, 2019 3:03 pm
- Post datetime: 2019-12-02T10:47:51+00:00
- Post Title: Re: Idolm@ster

New error. Seems like the script is recognizing the correct version of the file (which is to say, the platform it originated from), but is running into some sort of issue that is preventing it from working. 

```
--------------------------------------
Version: Xbox 360

Error: [myfseek] offset 0x000001a8 in file -2 can't be reached

Last script line before the error or that produced the error:
  84  goto TMP2 memory_file2
```
## Post #43
- Username: spiral6
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 30, 2019 3:03 pm
- Post datetime: 2019-12-02T10:58:26+00:00
- Post Title: Re: Idolm@ster

And the last thing to mention. If something were changed in the file, be it dialogue in the gscript files or textures from the game, would they require re-encryption on loading them into the game, and if so, how would I begin to re-encrypt them?

Sorry for all of these posts. The only reason I am attempting this is to try and start the translation of the game itself. Thank you.
## Post #44
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-12-02T14:09:38+00:00
- Post Title: Re: Idolm@ster

[https://mega.nz/#!Lvw0XAoY!CxB0H1SFtki1 ... ry6ode6wHc](https://mega.nz/#!Lvw0XAoY!CxB0H1SFtki1zzzNUXu5KVjEkDfCq2oGdry6ode6wHc)
## Post #45
- Username: spiral6
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 30, 2019 3:03 pm
- Post datetime: 2019-12-02T19:49:11+00:00
- Post Title: Re: Idolm@ster

Thank you for the programs. The decryption program works fine, the files are decrypted and encoded in Unicode 16 Big Endian. I assume that the imas2cs could possibly re-encrypt the files? If not, is there a way to re-encrypt them? 

Looking at the gscript files, they are indeed dialogue for the game, but they seem to have some sort of pointer/script to them in that they load scenes, reference other dialogue files, and so on. There will be some reverse engineering required for this.
## Post #46
- Username: erutorius
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 27, 2020 11:36 am
- Post datetime: 2020-01-28T12:43:32+00:00
- Post Title: Re: Idolm@ster

Hello I would like to edit a model and use it in the original game, is there a way to export or convert the edited model to ". nud" file after editing it using this 3DS MAX script?
I tried exporting it to ".obj" and then I converted it to ". nud" using Smash-Forge, but it doesn't work well probably because of the file format.
Please tell me if there is any good way.
## Post #47
- Username: kmbx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 27, 2018 8:06 pm
- Post datetime: 2020-04-21T16:09:21+00:00
- Post Title: Re: Idolm@ster

Hi, I'm looking to get some models from IDOLM@STER2 for PS3.
I was trying to extract  these 3Dmodels  with reference to this thread, but when .tsk file becomes .dec file using a Chrrox's tool, I got stuck.
How do i extract .xmb file, .nub file ,etc from this .dec file?
