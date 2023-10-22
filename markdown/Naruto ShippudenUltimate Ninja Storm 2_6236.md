## Post #1
- Username: boukistan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 19, 2011 12:46 am
- Post datetime: 2011-03-18T16:57:55+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

hello i downloaded the game for xbox 360 and i wanna know how i could extract model and texture to use thel in maya or 3ds max

thanx
## Post #2
- Username: boukistan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 19, 2011 12:46 am
- Post datetime: 2011-03-18T18:19:10+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

i dont script,  just wanna how to get the characters, but it seems difficult , i think so  u use a different method for a different game ?
anyway help , it l be great

thx
## Post #3
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-19T06:28:26+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

i think its hard to rip the model
## Post #4
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-03-19T07:26:19+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

post the sample files if you now how to get, so someone can help you. 

goodluck man cheers
## Post #5
- Username: boukistan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 19, 2011 12:46 am
- Post datetime: 2011-03-23T18:02:09+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

thx for u feedback, but i really don't know about extracting files methods.

and i don't know what file yout talking about ?

maybe can i upload a screenshot of the DVD
i open it with isobuster 

thx
## Post #6
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-03-24T01:49:13+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-24T02:36:32+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

its compressed with xmem. then they use the NDP3 format.
you need xbedecompress to decompress the file.

```
Magic = readfixedstring f 4
version = readbelong f
null01 = readbelong f
null02 = readbelong f
Unk01 = readbelong f --00 00 2D C4
Unk02 = readbelong f --00 00 00 03
Unk03 = readbelong f --00 79 DC 00
Unk04 = readbelong f --00 00 00 09 Text1 Count
Unk05 = readbelong f --00 00 00 8D Text1 size
Unk06 = readbelong f --00 00 00 0C Text2 Count
Unk07 = readbelong f --00 00 01 20 Text2 Size
Unk08 = readbelong f --00 00 01 3C Text3 Count
Unk09 = readbelong f --00 00 16 6E Text3 Size
Unk10 = readbelong f --00 00 01 4E
Unk11 = readbelong f --00 00 0F A8
Unk12 = readbelong f --00 00 01 76
null03 = readbelong f
--TextStart
--NDP3 Mesh
```

[narutohair.png](https://xentaxbackup.github.io/file/4100_narutohair.png)
## Post #8
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-03-24T03:24:01+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

Well i managed to uncompress them using the method you suggested~


Now.... Whats a NDP3 format? O.o;;;


::edit just saw the picture u posted::

Woah! O.O you have this figured out already!
## Post #9
- Username: boukistan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 19, 2011 12:46 am
- Post datetime: 2011-03-24T18:09:17+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

thx for ur advices guyz !

i'm buzzy with my work but i'll try the chrrox's method
## Post #10
- Username: boukistan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 19, 2011 12:46 am
- Post datetime: 2011-03-26T03:38:00+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

Ok i know that goog is my friend but i dont fond xbedecompress
Anyone could upload it please
## Post #11
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-03-26T06:14:27+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from boukistan
>
> Ok i know that goog is my friend but i dont fond xbedecompress
Anyone could upload it please

As far as I know the tool "xbedecompress" is from the "xbox sdk"... I hope it helps!
## Post #12
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-03-27T20:07:21+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-04-19T09:37:17+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

Hi all. Can anybody write algorithm for full exporting into 3ds Max?
## Post #14
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-04-19T10:01:15+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

Chrrox please help!
## Post #15
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-04-20T12:52:52+00:00
- Post Title: Naruto Shippuden:Ultimate Ninja Storm 2

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2011-04-24T07:07:32+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

How do we import them to 3ds max? how do we decompress .xfbin
## Post #17
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-05-04T09:57:17+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Chrrox!!!! SOS!!!
## Post #18
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-17T06:27:07+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I really want to learn how to import them to 3ds max too..
## Post #19
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-05-27T10:44:14+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Chrrox, please, answer - how to import uncompressed models into 3ds MAX?
## Post #20
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-28T10:00:25+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

maybe sir chrrox will post it some other time.
## Post #21
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-05-28T11:22:15+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

DOTAPRINCE, Slozhny, please give me a super maximporter for all games now. Because I want it, so please make me one.


Guys, it is very annoying to push someone who does so much already for free by spamming a thread with just requesting. I am sure he will post a script when it is done, if it is done.

You are not making it easier by "screaming" and stressing him up guys  Please be patient or do it yourselves, easy options
## Post #22
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-05-28T20:00:35+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from pixellegolas
>
> DOTAPRINCE, Slozhny, please give me a super maximporter for all games now. Because I want it, so please make me one.


Guys, it is very annoying to push someone who does so much already for free by spamming a thread with just requesting. I am sure he will post a script when it is done, if it is done.

You are not making it easier by "screaming" and stressing him up guys  Please be patient or do it yourselves, easy options

On previous page he share screenshot from MAX, then I've try to find any information about NDP3. Может ты, нубяра, знаешь какой импортер юзать? Так подскажи, "не будь очком". Ещё я предполагаю что ты нихера не знаешь русского языка. And now I simply want to ask Chrrox, because he already do it.
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-28T20:36:25+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

The format structure is a pain to work on. I just manually converted that one model.
## Post #24
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-05-28T22:33:57+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from chrrox
>
> The format structure is a pain to work on. I just manually converted that one model.
Oh sorry. I thought you used some standard tool. It sadly (((
## Post #25
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-29T04:39:15+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

i see, how about models from naruto shippuden ultimate ninja 5? are those possible to be converted?
## Post #26
- Username: rhazielz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 31, 2011 3:23 am
- Post datetime: 2011-05-30T19:34:51+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

how do you do a manual convert chrrox
## Post #27
- Username: rhazielz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 31, 2011 3:23 am
- Post datetime: 2011-05-30T19:46:38+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

i dont think it's NDP3 but NTP3, could be wrong
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-30T22:34:11+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

NTP3 is the textures
## Post #29
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2011-05-31T01:26:44+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

so the only way we can get the models is by manually converting them?
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-31T01:27:57+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

why not just convert the wii models they are all brmdl files.
## Post #31
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2011-05-31T01:32:46+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

wait, are we still talking about the Storm 2 models or the wii game??
## Post #32
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-31T02:10:56+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I am saying i am not going to work on the format and the wii models are the same.
so if you want naruto models grab the wii models.
## Post #33
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-05-31T02:47:40+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

in my opinion the naruto from ps2 models like UN5 is better than the wii's..
## Post #34
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-05-31T14:18:43+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from DOTAPRINCE
>
> in my opinion the naruto from ps2 models like UN5 is better than the wii's..
Absolutely right ))) Wii models - original shit (and not only Naruto games)
In Storm 2 best models from all Naruto Game series
## Post #35
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2011-06-02T05:33:05+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

sir chrrox, so your saying i should get the ps2 models instead?
## Post #36
- Username: AvengerSeraphim
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 29, 2011 3:15 am
- Post datetime: 2011-08-07T19:46:20+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Naruto 5 in PS2 is still awesome...But it doesnt have the newest characters like Pain, Hidan etc...
I dont have a clue about those stuff but i hope someone can figure it out!!!
## Post #37
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T19:52:32+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I got the model format figured out but not the material section. without knowing the material section i cant get to the data i need to import.
The only way i can import models is by specifying the offset and that is to complex for people to do on their own to use my script.
## Post #38
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-24T13:58:32+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

At least you're making progress sir chrrox XD
## Post #39
- Username: SAGEMOD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 30, 2011 5:27 am
- Post datetime: 2011-11-04T17:50:31+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

So , has anyone finished converting  storm 2 models ???
I really need them
## Post #40
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-17T11:44:09+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

This converting is so crude.
I have no previous knowledge of convert.
Sorry, it's too difficult to explain,because my English skills are bad.
Here is some convert obj file
[delete](delete)
## Post #41
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-01-17T13:00:57+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

wow ..it's really amazing...i assembled ur obj model and it's really hig poly.
You figured out the vertex data and u convert them in a obj mesh using deep exploration. right?
## Post #42
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-18T02:57:42+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I dunno, at least roughly to complete.


Here is the result file.
[delete](delete)
## Post #43
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-18T11:46:05+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Ares722
>
> wow ..it's really amazing...i assembled ur obj model and it's really hig poly.
You figured out the vertex data and u convert them in a obj mesh using deep exploration. right?

I still have a lot to learn, i'll explain it in simple.
Mind you, i'm a mere beginner in this.

The things that you should personally prepare are as follows.
-Noesis
-Hex Editor

It'll be a very long story if I go into the details
Because my English skills are bad, bad, bad~~~.
Just look at this picture.

Here is ndp3 sample
[delete](delete)
## Post #44
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-01-18T15:26:52+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I have to learn a lot too.   
Thank u soo much for your clear explanation. 
It was really useful for me. thanks again.

EDIT: I didn't know that noesis supports the .ndp3 files.
## Post #45
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-01-19T17:03:19+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Errrmmm... How do I rip the rextures?? Getting the files are a little tedious, but there's no problem.
## Post #46
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-19T17:09:52+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Darko
>
> Errrmmm... How do I rip the rextures?? Getting the files are a little tedious, but there's no problem.
I don't know how to convert nut to dds.
But, please go to link[viewtopic.php?f=18&t=8071](http://forum.xentax.com/viewtopic.php?f=18&t=8071).	
That'd be a some help.
## Post #47
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-21T16:21:20+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

hi and thanks for your method, I tryed it and that's what appear to me:
-I followed your tutorial testing it whit the file '1nrtbod1.xfbin';
-after I saved it like 'naruto.ndp3'
-I opened it with noesis and...
[](http://imageshack.us/photo/my-images/859/immagineyp.png/)


...what's about it? xD
I hope that you can reply to me.

P.S.=can I use this code for other files like '1sskbod1.xfbin'?
[](http://imageshack.us/photo/my-images/221/argv.png/)
## Post #48
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-21T16:32:57+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> hi and thanks for your method, I tryed it and that's what appear to me:
-I followed your tutorial testing it whit the file '1nrtbod1.xfbin';
-after I saved it like 'naruto.ndp3'
-I opened it with noesis and...



...what's about it? xD
I hope that you can reply to me.

P.S.=can I use this code for other files like '1sskbod1.xfbin'?
xfbin contains a lot of ndp3 file.
Please refer to the this file.
[delete](delete)
And the code applies to all ndp3 file
## Post #49
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-21T17:44:52+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

fine, that means I can extract other characters like sasuke.
P.S.= what about textures? how can I found them?
## Post #50
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-21T18:03:52+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> fine, that means I can extract other characters like sasuke.
P.S.= what about textures? how can I found them?
In a similar manner. 
The only difference is search for ntp3.
This method is not be complete.
[viewtopic.php?f=18&t=8071](http://forum.xentax.com/viewtopic.php?f=18&t=8071)
## Post #51
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-21T19:00:42+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

thanks I'll post here for any update!

P.S.=I tryed to import your textured model in 3d studio max but it shows uvw problem that doesn't appear in Noesis...it's the same even if I try to open using milkshape.
## Post #52
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-21T19:04:59+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> thanks I'll post here for any update!

P.S.=I tryed to import your textured model in 3d studio max but it shows uvw problem that doesn't appear in Noesis...it's the same even if I try to open using milkshape.
Sorry, The matter is outside my knowledge.
## Post #53
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-01-22T00:45:28+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> thanks I'll post here for any update!

P.S.=I tryed to import your textured model in 3d studio max but it shows uvw problem that doesn't appear in Noesis...it's the same even if I try to open using milkshape.

Try to rotate or mirror the texure with a graphics software or directly into your 3d application and the problem is solved.

EDIT: did u seclect the flip option when u exported from noesis?
## Post #54
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-01-22T09:58:04+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Why does it look different from how they appear in the game?
## Post #55
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-22T21:44:37+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

The contents of this post was deleted because of possible forum rules violation.
## Post #56
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-23T00:22:40+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from dj082502
>
> I dunno, at least roughly to complete.


Here is the result file.
http://www.mediafire.com/?tqhha860v6tib48

Could you please post another link?  The link you posted before is dead...
## Post #57
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-23T09:39:53+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Rimbros
>
> mmmmm MEGAUPLOAD ITS DEAD.

> Reply from cchuauns1
>
> Could you please post another link?  The link you posted before is dead...
I'm so sorry, Megaupload
[delete](delete)
## Post #58
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-23T13:28:28+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Thanks! I appreciate it!:)
## Post #59
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-24T16:26:03+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

following the same method I extracted from the file '1sskbod1.xfbin' a nut file.
after I opened it in texture viewer 2.0 but it's strange:
[](http://imageshack.us/photo/my-images/201/txture.png/)

I extracted a 3d model too, soon I'll post a pic.
EDIT=in it there was a lot of objects but i added just two:
[](http://imageshack.us/photo/my-images/193/sasukerp.png/)

[](http://imageshack.us/photo/my-images/515/sasuketest.png/)
## Post #60
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-01-24T19:37:40+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> following the same method I extracted from the file '1sskbod1.xfbin' a nut file.
after I opened it in texture viewer 2.0 but it's strange:


I extracted a 3d model too, soon I'll post a pic.
EDIT=in it there was a lot of objects but i added just two:

DXT1 and  your texture is ready, anyways any idea on how to extract textures??
## Post #61
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-24T23:55:07+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Do you think you guys could extract Naruto (Shippuden version) model from the game?  Thanks!
## Post #62
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-25T00:06:15+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from dj082502
>
> I dunno, at least roughly to complete.


Here is the result file.
http://www.mediafire.com/?tqhha860v6tib48

How do you think I could smooth out the model?
## Post #63
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-25T15:28:56+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from cchuauns1
>
> Do you think you guys could extract Naruto (Shippuden version) model from the game?  Thanks!
3D models ripping is possible. 
But my tutorial is annoying and troubling, needs more patience
Xbox360 version the files are compressed[xbdecompress] but in the PS3 version the files are uncompressed.

> Reply from cchuauns1
>
> How do you think I could smooth out the model?
I don't know what you meant.
## Post #64
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-01-25T19:59:11+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from cchuauns1
>
> dj082502 wrote:I dunno, at least roughly to complete.


Here is the result file.
http://www.mediafire.com/?tqhha860v6tib48

How do you think I could smooth out the model?

3dsmax, smooth modifier.
## Post #65
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-26T12:30:24+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Guys, how come when I import the model to 3ds Max, the textures all messed up?
## Post #66
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-26T14:24:24+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Ares722
>
> kuraudo94 wrote:thanks I'll post here for any update!

P.S.=I tryed to import your textured model in 3d studio max but it shows uvw problem that doesn't appear in Noesis...it's the same even if I try to open using milkshape.

EDIT: did u seclect the flip option when u exported from noesis?

thanks it works.
## Post #67
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-27T09:32:41+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> following the same method I extracted from the file '1sskbod1.xfbin' a nut file.
after I opened it in texture viewer 2.0 but it's strange:
If you will be uploading sample file, i'll check it out immediately.
## Post #68
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-27T15:23:01+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

The contents of this post was deleted because of possible forum rules violation.
## Post #69
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-27T15:40:09+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

The contents of this post was deleted because of possible forum rules violation.
## Post #70
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-27T18:16:13+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

it works good, thanks!
## Post #71
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-27T19:04:58+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> it works good, thanks!

The NTP3 are still under research by 0xFAIL
If you wish to have further information, please go here.
[viewtopic.php?f=18&t=8071](http://forum.xentax.com/viewtopic.php?f=18&t=8071)
## Post #72
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2012-01-30T22:11:59+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

hello, for better quality use this settings

[](http://s771.photobucket.com/albums/xx357/hiwap000/?action=view&current=Captura.jpg)

and fot the sharingan Shift= 699

here is the result

[](http://s771.photobucket.com/albums/xx357/hiwap000/?action=view&current=sasuke.jpg)

sry for my bad english I speak spanish   

dj082502 thx for the guide
## Post #73
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-30T22:42:58+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from hiwap
>
> hello, for better quality use this settings



and fot the sharingan Shift= 699

here is the result



sry for my bad english I speak spanish   

dj082502 thx for the guide

WOW! Good Job! You think you could extract Naruto (Shippuden version)?
## Post #74
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2012-01-30T23:07:10+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from cchuauns1
>
> 

WOW! Good Job! You think you could extract Naruto (Shippuden version)?

i dot know what file have "naruto" shippuden version but the file for sannin mode is this "rnrxbod1" (I'm not 100 % sure becouse i dont have the file in the same folder   )


Textures:
[](http://s771.photobucket.com/albums/xx357/hiwap000/?action=view&current=Untitled-1.png)

[](http://s771.photobucket.com/albums/xx357/hiwap000/?action=view&current=Untitled-2.png)

Result:
[](http://s771.photobucket.com/albums/xx357/hiwap000/?action=view&current=naruto.jpg)
## Post #75
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-31T06:22:59+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Hiwap, how do you get these kind of files (rnrxbod1)?  I'm such a noob... Or if your feeling kinda lazy to teach you could just post the link to that sannin Naruto file.
## Post #76
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-01-31T06:31:31+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Another question... hehe  How do you render them to look like how they come out in the game?
## Post #77
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-01-31T16:45:15+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

hey dj082502, do you know where can be the files of this map? [http://www.youtube.com/watch?v=eYJKBdNVUQY](http://www.youtube.com/watch?v=eYJKBdNVUQY)
I was searching in the 'stage' folder but i think there are just the maps of the battle mode. also I was searching in data>interface>map but i don't think it's there because there are just 4 files.xfbin and just one contein '.ndp3' but it's just 7 kbyte and I think the map is more bigger. xD
have you any ideas?
thanks in advance.
## Post #78
- Username: natsuto
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 09, 2012 8:28 am
- Post datetime: 2012-02-10T01:54:56+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I tried to import your texture model in 3D Studio Max, but it shows the problem of UVW will not appear in Noesis.
## Post #79
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-10T02:43:08+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I haven't read a single post in this thread, but just FYI, the format will probably be properly supported in the next version of Noesis. Someone PM'd me about it and it turns out it's basically the same format as was used in Time Crisis: Razing Storm. (potentially plus or minus an offset table at the start)
## Post #80
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2012-02-22T18:54:44+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

That would be pretty sweet, looking forward to that.
## Post #81
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2012-03-05T18:09:24+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Naruto Shippuden Ultimate Ninja Storm Generations

here is the file is fron the PS3-JP version compresed in cpk i dont know how to extrack it. I used BMS CPK script but dont work :S
the file is the data.cpk

[http://www.mediafire.com/?0qy8vl076z0gv0t](http://www.mediafire.com/?0qy8vl076z0gv0t)
[http://www.mediafire.com/?dp1bdb8m1bkvdde](http://www.mediafire.com/?dp1bdb8m1bkvdde)

that one dont have models in it but the other one is 1.35 G here is a part of it is 60MB so you can see the header
[http://www.mediafire.com/?1tiw2h5mhzhacdc](http://www.mediafire.com/?1tiw2h5mhzhacdc)

the file have inside xfbin with "NPD3, NTP3"
## Post #82
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-05T20:46:01+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

That's a new version of CPK tools do not yet supported.
## Post #83
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-07T02:05:10+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Hey Mr Adults, don't forget this game pls
## Post #84
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-07T02:44:57+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I did in fact forget this game, haha. Oops. Looking back over my notes, I think I need a few different character models from it to verify what all the differences are, and whoever it was that sent me an example only seems to have sent one. If someone could PM a link over to a few of them, that would be helpful.
## Post #85
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2012-03-07T03:06:24+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

PM with models send
## Post #86
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-07T03:20:35+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from MrAdults
>
> I did in fact forget this game, haha. Oops. Looking back over my notes, I think I need a few different character models from it to verify what all the differences are, and whoever it was that sent me an example only seems to have sent one. If someone could PM a link over to a few of them, that would be helpful.

Ok, Im gonna send you 2 or 3 rar files with the game's file already uncompressed.
## Post #87
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-07T04:30:14+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Thanks, got plenty of data to work with now.

Edit: Pushed a new build up to load these. As noted in the readme:

> -3.831 - Added crude support for NS:UNS2 models. No skeleton (seems to be in a different file), material assignments are usually off, some meshes are offset, and some meshes just have screwed up verts. Seems like a vertex format or offset issue, haven't looked into it.
Also, I have to say, these models are really bad. I think chrrox was right, seems like they're probably identical to whatever was used in the Wii game.
## Post #88
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2012-03-07T13:27:02+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

thx for adding support for xfbin, the models of ps3/360 are better(make it poly well vertices(?)) and have LODS and with the new game we have More characters
## Post #89
- Username: cchuauns1
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 23, 2011 9:39 pm
- Post datetime: 2012-03-07T16:18:02+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Could anyone post a link for the Shippuden version of Naruto? If it is available... Thanks!
## Post #90
- Username: hiwap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 12, 2011 5:07 am
- Post datetime: 2012-03-09T21:30:11+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from cchuauns1
>
> Could anyone post a link for the Shippuden version of Naruto? If it is available... Thanks!
[http://www.mediafire.com/?5g0hlt7rfnuchnk](http://www.mediafire.com/?5g0hlt7rfnuchnk)

enjoy
## Post #91
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-13T00:31:04+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Dragon Ball Z Burst Limit

I've altered the header, add xfbin header.
## Post #92
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-03-14T10:30:29+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Cool!!...so the method is the same as in Naruto S. Ninja storm2, right?
## Post #93
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-03-21T12:28:34+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

By the way, how do we render them to make it look like the same as how they appear in game?
## Post #94
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-03-22T15:00:36+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from DOTAPRINCE
>
> By the way, how do we render them to make it look like the same as how they appear in game?

Obviosly it depends by your 3d software and your rendering knowledges. 
The cell-shading method of rendering is explained a lot on the web.
There are a lot of good tutorials on the web for most of 3d rendering software like max, blender and so on.
## Post #95
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-03-22T15:08:32+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Ares722
>
> DOTAPRINCE wrote:By the way, how do we render them to make it look like the same as how they appear in game?

Obviosly it depends by your 3d software and your rendering knowledges. 
The cell-shading method of rendering is explained a lot on the web.
There are a lot of good tutorials on the web for most of 3d rendering software like max, blender and so on.
I would like to see a sample then, take a character from Naruto Ultimate ninja storm 2 and make him/her look like how they appear in-game.
## Post #96
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-03-23T11:08:21+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from DOTAPRINCE
>
> Ares722 wrote:DOTAPRINCE wrote:By the way, how do we render them to make it look like the same as how they appear in game?

Obviosly it depends by your 3d software and your rendering knowledges. 
The cell-shading method of rendering is explained a lot on the web.
There are a lot of good tutorials on the web for most of 3d rendering software like max, blender and so on.
I would like to see a sample then, take a character from Naruto Ultimate ninja storm 2 and make him/her look like how they appear in-game.
 ok i will post a render as example  soon.
## Post #97
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-03-23T11:13:08+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Thanks, I'll be expecting it
## Post #98
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-03-26T14:59:39+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

is there any news about the location of the map? (I'm talking about naruto ultimate ninja storm 1, the map of the village).
## Post #99
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-04-08T09:37:12+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

extracting the model of naruto shippuden I saw that there are two models in the same '.xfbin' as you can see here: [http://moddingblog.wordpress.com/2012/0 ... n-andreas/](http://moddingblog.wordpress.com/2012/04/06/naruto-shippuden-ps3-model-in-gta-san-andreas/)
*if there are problem for the link posted I will delete it.
## Post #100
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-12T18:13:28+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I was able to extract the files from Ultimate Storm Generations, but I don't of the files are wrong or just they used another format:

[http://anonym.to/?http://www.mediafire. ... w95j5w15u7](http://anonym.to/?http://www.mediafire.com/?0efxew95j5w15u7)

If anyone is interested.

See ya
## Post #101
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-12T18:17:27+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Darko
>
> I was able to extract the files from Ultimate Storm Generations, but I don't of the files are wrong or just they used another format:

http://anonym.to/?http://www.mediafire. ... w95j5w15u7

If anyone is interested.

See ya
This link appears broken
## Post #102
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-12T18:28:26+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from dj082502
>
> Darko wrote:I was able to extract the files from Ultimate Storm Generations, but I don't of the files are wrong or just they used another format:

http://anonym.to/?http://www.mediafire. ... w95j5w15u7

If anyone is interested.

See ya
This link appears broken

Just copy the mediafire part and paste it in your webbrowser, unless that server is banned in your country.

```
http://www.mediafire.com/?0efxew95j5w15u7
```


I think the code tag is usefull in order to avoid hotlinking (discused in noesis thread).
## Post #103
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-12T18:42:05+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Except for 2skreff1.xfbin, most of the files may have become corrupted.
Your unpacking doesn't seem to be working right.
## Post #104
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-12T20:01:07+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from dj082502
>
> Except for 2skreff1.xfbin, most of the files may have become corrupted.
Your unpacking doesn't seem to be working right.

Yeah, I used a tool posted here. So I'll have to wait.
## Post #105
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-05-30T23:27:23+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

And, Noesis support the Naruto Shippuden:Ultimate Ninja Storm 2 game?
## Post #106
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-05-31T17:29:30+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I download the x360 and the format its the same but Noesis cant read this. hope anyone can explain why.
I see samples posted on this treadh then i post here the links. Also i downloaded the .cpk posted on this treadh, the one with 2 links in mediafire but when i try unpack with Noesis this crash. If somebody can resume in one repply the method to unpack and get the models that can be usefully.

X360 File extracted
[http://www.4shared.com/rar/VkS6bwLk/spc.html](http://www.4shared.com/rar/VkS6bwLk/spc.html)

PS3 File sample downloaded
[http://www.mediafire.com/?5g0hlt7rfnuchnk](http://www.mediafire.com/?5g0hlt7rfnuchnk)
## Post #107
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-08-26T16:24:41+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

I to all.
I'm very intrested in this models and I want to extract them to make a GTA sa mod.
The problem is that I have a slow internet connection and I can't download an ISO, so, can anyone upload the .xfbin files containing the characters?

Maybe you can create a folder in Mediafire and upload the files in it.

I Hope that someone will do what I'm asking.
## Post #108
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-08-26T16:47:18+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from Rimbros
>
> I download the x360 and the format its the same but Noesis cant read this. hope anyone can explain why.
I see samples posted on this treadh then i post here the links. Also i downloaded the .cpk posted on this treadh, the one with 2 links in mediafire but when i try unpack with Noesis this crash. If somebody can resume in one repply the method to unpack and get the models that can be usefully.

X360 File extracted
http://www.4shared.com/rar/VkS6bwLk/spc.html

PS3 File sample downloaded
http://www.mediafire.com/?5g0hlt7rfnuchnk
You can decompress X360 file with xbdecompress.exe.
And, includes NTP3/NDP3 that's the only 2nrteff1.xfbin
## Post #109
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-08-27T13:51:16+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from loriscangini
>
> I to all.
I'm very intrested in this models and I want to extract them to make a GTA sa mod.
The problem is that I have a slow internet connection and I can't download an ISO, so, can anyone upload the .xfbin files containing the characters?

Maybe you can create a folder in Mediafire and upload the files in it.

I Hope that someone will do what I'm asking.

Please, Can someone upload the .xfbin files of the characters from Naruto Ultimate Ninja (1 and/or 2)?
## Post #110
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-08-28T11:28:32+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from loriscangini
>
> I to all.
I'm very intrested in this models and I want to extract them to make a GTA sa mod.
The problem is that I have a slow internet connection and I can't download an ISO, so, can anyone upload the .xfbin files containing the characters?

Maybe you can create a folder in Mediafire and upload the files in it.

I Hope that someone will do what I'm asking.

Please, someone must be able to upload the xfbin files. 
If you don't knows know how to do, follow these instructions: 
Open the iso and search for a folder called rpg, in that folder search for a file called 1nrtbod1.xfbin, if you find the file, the folder is the correct one. 
Once found the folder, pack all the xfbin files in rar or zip archives, possibly in small groups (10-15 xfbin files per archive ) and upload them in mediafire. 

I wait for your help.
## Post #111
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-08-28T16:25:03+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from loriscangini
>
> loriscangini wrote:I to all.
I'm very intrested in this models and I want to extract them to make a GTA sa mod.
The problem is that I have a slow internet connection and I can't download an ISO, so, can anyone upload the .xfbin files containing the characters?

Maybe you can create a folder in Mediafire and upload the files in it.

I Hope that someone will do what I'm asking.

Please, someone must be able to upload the xfbin files. 
If you don't knows know how to do, follow these instructions: 
Open the iso and search for a folder called rpg, in that folder search for a file called 1nrtbod1.xfbin, if you find the file, the folder is the correct one. 
Once found the folder, pack all the xfbin files in rar or zip archives, possibly in small groups (10-15 xfbin files per archive ) and upload them in mediafire. 

I wait for your help.

If someone helps me, I can convert the models to .3ds or .obj and share them to all, but I need someone's help to get the xfbin from the game. 

Please, help me.
## Post #112
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-08-31T18:25:20+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from loriscangini
>
> loriscangini wrote:loriscangini wrote:I to all.
I'm very intrested in this models and I want to extract them to make a GTA sa mod.
The problem is that I have a slow internet connection and I can't download an ISO, so, can anyone upload the .xfbin files containing the characters?

Maybe you can create a folder in Mediafire and upload the files in it.

I Hope that someone will do what I'm asking.

Please, someone must be able to upload the xfbin files. 
If you don't knows know how to do, follow these instructions: 
Open the iso and search for a folder called rpg, in that folder search for a file called 1nrtbod1.xfbin, if you find the file, the folder is the correct one. 
Once found the folder, pack all the xfbin files in rar or zip archives, possibly in small groups (10-15 xfbin files per archive ) and upload them in mediafire. 

I wait for your help.

If someone helps me, I can convert the models to .3ds or .obj and share them to all, but I need someone's help to get the xfbin from the game. 

Please, help me.

Please, I need someone's help, I'm not asking for an impossible thing.
## Post #113
- Username: kuraudo94
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 14, 2010 6:32 pm
- Post datetime: 2012-09-01T11:51:02+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

If you want naruto's models from this series in GTA San Andreas I already did them.
[http://moddingblog.wordpress.com/author/kuraudo94/](http://moddingblog.wordpress.com/author/kuraudo94/)
P.S.= if there are problem with the link I'll delete it.
## Post #114
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-09-04T16:14:05+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from kuraudo94
>
> If you want naruto's models from this series in GTA San Andreas I already did them.
http://moddingblog.wordpress.com/author/kuraudo94/
P.S.= if there are problem with the link I'll delete it.

I want the files from the game, so I can extract the characters I want when I need them.
I already converted Konan, but I need all the others .xfbin character files.

Please, can someone uplaod them??
## Post #115
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-04T21:12:09+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from loriscangini
>
> Please, can someone uplaod them??
Nobody would offer to help u.
It was so big(6Gb) as to upload.
## Post #116
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2012-09-05T18:06:13+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

> Reply from dj082502
>
> loriscangini wrote:Please, can someone uplaod them??
Nobody would offer to help u.
It was so big(6Gb) as to upload.

I don't want the whole ISO, I need only a folder, It's called RPG and it contains all the characters of the game. 
It isn't so difficult to upload that folder, I also wrote the instructions a few posts ago.
## Post #117
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2012-10-30T06:12:04+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

So did anyone ever end up making a script or extraction method for Shippuden Generations? I know this topic was brought up a few times and there was progress made but doesn't seem there was anything definitive.
## Post #118
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2012-11-02T13:53:09+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

Hello

I looking for 3mesh and animation chars of naruto.
if someone has this, PM me... PLZ
## Post #119
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-11-02T23:58:57+00:00
- Post Title: Re: Naruto Shippuden:Ultimate Ninja Storm 2

lol ..it's going from bad to worse.
