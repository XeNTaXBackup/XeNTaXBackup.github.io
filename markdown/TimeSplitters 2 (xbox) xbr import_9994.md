## Post #1
- Username: dragbody
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-01T20:40:50+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

Here is a noesis script to import the models and textures from the xbox version of the game.
here is a quickbms script to extract the xbox archives.

```

if ID == "P4CK"
get tableoff long
get files long
math files / 0x3C
goto tableoff
for i = 0 < files
getdstring name 0x30
get offset long
get size long
get null long
log name offset size
next i
endif

if ID == "P8CK"
get tableoff long
get files long
get tableoff2 long
get table2size long
for i = 0 < files
goto tableoff
get nameoff long
get size long
get offset long
savepos tableoff
math nameoff + tableoff2
goto nameoff
get name string
log name offset size
next i
endif
```

This works on stages and character models.
If some of the models don't look perfect in noesis just export them and they will look fine in any 3d modeling program.
Special Thanks to the following people for help.
Mr anon for the face winding formula.
Reveal8n for help with the face winding formula.
Mr Adults for making noesis and helping with the texture swizzle of the xbox textures.

[fmt_ts2_xbr.zip](https://xentaxbackup.github.io/file/6108_fmt_ts2_xbr.zip)
## Post #2
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2013-01-01T20:54:34+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

im really love this game nice work
## Post #3
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2015-12-05T18:59:29+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

may someone make a script like this for the PS2 variant of the game? the results shown look astounding but alas, with an xbox disk i can't find any existence of a ".xbr" file ANYWHERE on the disk.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-12-05T22:33:40+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

> Reply from Reddance
>
> may someone make a script like this for the PS2 variant of the game? the results shown look astounding but alas, with an xbox disk i can't find any existence of a ".xbr" file ANYWHERE on the disk.

Xbox textures are of better quality for all these games.
## Post #5
- Username: FileMan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 06, 2015 8:03 am
- Post datetime: 2015-12-06T00:14:10+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

> Reply from Gh0stBlade
>
> Xbox textures are of better quality for all these games.
That doesn't help him at all. Unless your making the lunatics claim that it can be open with any old image manipulation program.
## Post #6
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2015-12-06T02:11:11+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

I'm not sure if you need a special program to see these files or a modded xbox, it'd be kinda screwed in that regard.. modded xbox wise.
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-12-06T16:42:56+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

> Reply from FileMan
>
> 
That doesn't help him at all.
How do you know it doesn't help him? Are you him? I was simply suggesting that using the PS2 models are not as good. Xbox has assets of higher quality. So how about you speak for yourself?

> Reply from FileMan
>
> 
Unless your making the lunatics claim that it can be open with any old image manipulation program.
First off, it's "you're"...

How dare you suggest I could be making lunatic claims. You must be really retarded... I never said anything of the sort in relation to these files being able to be opened within any image manipulation program.

Don't you dare think you can talk down to me, get some respect!



Don't try it with me!
~Bitch bye
## Post #8
- Username: TheMelonFiler
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 07, 2015 4:21 am
- Post datetime: 2015-12-06T20:51:59+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

Alright, You may be right but about that but this is an Xbox Thread and he's expressed interest in using the script with a Xbox disk, However he seems to be having problems which mean's that he is using the playstation not out of choice.

Textures. He was asking about how you would go about opening or finding the .XB files on an Xbox disk and again implies that he knows about this however that isn't the point he was requesting how to access the files and you've replied with the textures are of better quality and naturally implies that the textures must have something to with viewing theses files because after all this is a linear conversation.

Now. Respect? I really don't know what to say. I think we both know that in the adult world that respect isn't just granted its earn. I don't know you and therefor cannot automatically respect without having some previous interactions to judge your character.

I think that about explains everything and i think its best we get back on topic!
## Post #9
- Username: TheMelonFiler
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-12-06T21:15:46+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

> Reply from TheMelonFiler
>
> 
Textures. He was asking about how you would go about opening or finding the .XB files on an Xbox disk and again implies that he knows about this however that isn't the point he was requesting how to access the files and you've replied with the textures are of better quality and naturally implies that the textures must have something to with viewing theses files because after all this is a linear conversation.
Oh you must be stupid as well..... I let him and others know the assets are of lower quality to add to the fact a PS2 unpacker is not of much use since there's an existing Xbox unpacker. I just felt maybe letting him know would be beneficial to him and save someone the time required of creating a PS2 unpacker+Mesh importer so use your brain. To clarify the Xbox unpacker should work perfectly fine for PS2, format should be the same from my memory!

> Reply from TheMelonFiler
>
> 
Now. Respect? I really don't know what to say. I think we both know that in the adult world that respect isn't just granted its earn. I don't know you and therefor cannot automatically respect without having some previous interactions to judge your character.

I think that about explains everything and i think its best we get back on topic!

Uhm wait... who the hell are you again? That post wasn't even directed at you so keep out of it. The only one who went off topic is the guy who decided to accuse me of potentially posting lunatic claims. You are too ignorant.

I've had enough of you actually...
Don't try it with me.



~Bitch bye
## Post #10
- Username: TheMelonFiler
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 07, 2015 4:21 am
- Post datetime: 2015-12-06T21:24:14+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

Well. That's fairly interesting that the script would work both ways, I always assume that there was a small difference between the pak files from a different console.
## Post #11
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2015-12-07T04:40:24+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

i have the slightest clue as to what the hell just happened lol. all i'm saying is, when the Timesplitters 2 xbox disk is put into my computer. these are the only files that are displayed.



There's no such thing as a .xbr on these xbox disks, haven't got the faintest idea on how chrrox got these ".xbr" files.
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-12-07T10:28:22+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

Use Ultra ISO. It supports Xbox ISO files perfectly.
## Post #13
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2015-12-07T13:22:35+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

> Reply from Gh0stBlade
>
> Use Ultra ISO. It supports Xbox ISO files perfectly.

So if i used that, would i be able to locate these .xbr files?
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-12-07T21:54:04+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

You need a modded xbox or 360 to rip an xbox iso.
or download an iso from the internet.
then you can use programs to extract the files from the iso.
## Post #15
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2015-12-08T09:37:42+00:00
- Post Title: TimeSplitters 2 (xbox) xbr import

> Reply from chrrox
>
> You need a modded xbox or 360 to rip an xbox iso.
or download an iso from the internet.
then you can use programs to extract the files from the iso.

Gotcha, i figured i would have to do that. everything works now
## Post #16
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-07-22T22:39:06+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

this script works perfectly for all the multiplayer character models / levels but, for the main ones, like the story cutscenes; i get this error.





And when i try to export the model i get this error.




Is there any possible way to get these more higher poly models shown in the cutscenes somehow?
## Post #17
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-24T01:21:39+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

That's because the importer unfortunately has some bugs in the code.
## Post #18
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-07-24T18:30:22+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

Damn bummer.
## Post #19
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-07-28T22:13:03+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

Is there any other way to get these models?
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-28T23:26:44+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

you have to upload some non working samples, it may be as simple as adding a new condition to the script or you can always give Hex2obj a try
## Post #21
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-07-29T11:27:52+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

here's some "nonworking" samples that anyone is welcome to take a crack at! 

[https://www.mediafire.com/?xefc9899m2axuzi](https://www.mediafire.com/?xefc9899m2axuzi)
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-30T08:40:50+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

thx - we'd need at least one working (xbox) xbr sample to get a better understanding of the script.



xbr_test.jpg (67.53 KiB) Viewed 141 times
## Post #23
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-07-30T11:49:19+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

Oh.. my lanta.. YOU'VE DONE IT!111   .... Working .XBR RIGHT ' ERE!

[https://www.mediafire.com/?heytt6bcnm73tby](https://www.mediafire.com/?heytt6bcnm73tby)

This may also be just a MASSIVE long shot but, i've also included animations? aswell? that'd just be a godsend if there was some way to get those even REMOTELY working.. seeing as how the character meshes don't have bones for some odd reason
## Post #24
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-08-04T13:00:26+00:00
- Post Title: Re: TimeSplitters 2 (xbox) xbr import

i've actually tampered with the models a bit, making their faces with actual working eyes / mouths   as for the hands, since they only have about 3 fingers, as the others are kinda welded together, i figure i could use the OTHER character "handyman" as he's practically a giant hand with all fingers intact
