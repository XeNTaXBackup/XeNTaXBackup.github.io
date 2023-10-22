## Post #1
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-04-07T18:32:30+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

hi there as a fan of bleach i need to work on this one ^^

so :
- "btlIchigoDokuro.spk" contain the mesh :
 vertex indices for tristrip, vertex array as vec3 then seems the normals etc.. are also in separated arrays
-"btlIchigoDokuroImg.spk" contain the mesh textures (dds, not found the header specs actually)

here are sample files:
-- removed --

help would be apprecied

edit : here is the alpha tool i was working on : it extract data from spk textures and mesh blocks as splitted object files, it is still not finished as i am too busy currently)
i suggest you create a folder and put each spk and *img.spk files in it then put the exe and drop the files on it to export it the raw way...

[http://www.mediafire.com/?forg5icg91bm55x](http://www.mediafire.com/?forg5icg91bm55x) (executable)
[http://www.mediafire.com/?1qcz0y7h7cqz716](http://www.mediafire.com/?1qcz0y7h7cqz716) (dll file to put with the exe)

(also if mr adult want to add support to this one in noesis i can send him the file specs to add this format support, just drop me a pm)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-07T20:31:11+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

quickbms

```
print "%start%"

goto start
endian big
set i 0
for i
savepos offset
get name basename
string name + _
string name + i
string name + .unk
getdstring one 0x14
get size long
math size + 0x20
log name offset size
math offset + size
goto offset
next i
```
## Post #3
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-04-08T17:07:49+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

finished texture extractor   



3dmodel sample :


the file format is quite easy as it seems to use some ps2 like viftags before each data block ...
## Post #4
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-07-05T12:42:52+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

some good news today i got some free time to work on this format quickly:
the good news :
- bms script no more needed to extract the mesh
- faces are now fixed, no more degenerated ones :op

the bad news :
- one obj is exported for each extracted part so you need to merge the obj together to get the full mesh
- still no skeleton and normals
- materials need to be manually assignated
- i need time to work on this grrrr
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-05T12:53:35+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

> one obj is exported for each extracted part so you need to merge the obj together to get the full mesh

That doesn't sound too bad, unless there are more complications involved when everything is in pieces lol
## Post #6
- Username: Pokegear
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 02, 2011 1:01 pm
- Post datetime: 2011-08-02T12:52:12+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

What did you use to extract the .spk files?
## Post #7
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-08-02T13:10:16+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

> Reply from Pokegear
>
> What did you use to extract the .spk files?

Here[viewtopic.php?f=16&t=6373&p=52389#p52389](http://forum.xentax.com/viewtopic.php?f=16&t=6373&p=52389#p52389)
That is a script for QuickBMS.
[http://aluigi.org/quickbms.htm](http://aluigi.org/quickbms.htm)
## Post #8
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-02T13:56:46+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

> Reply from shadowmoy
>
> finished texture extractor   



3dmodel sample :


the file format is quite easy as it seems to use some ps2 like viftags before each data block ...
That under the detailed methodology
## Post #9
- Username: Pokegear
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 02, 2011 1:01 pm
- Post datetime: 2011-08-02T14:06:55+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

What do I do with the .unk files?
## Post #10
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-03T11:37:46+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

I also UNK extract files, I think Mr. chrrox should also extracted, but he did not say the specific methods
## Post #11
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-25T10:27:59+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

How do you extract the textures? And is it supported by noesis?
## Post #12
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-26T02:47:27+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

> Reply from DOTAPRINCE
>
> How do you extract the textures? And is it supported by noesis?
I extracted all UNK file, do not you have to extract from other files UNK in it
## Post #13
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-26T03:08:14+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

I can't quite understand, How do I import the model in 3ds max?
## Post #14
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2011-08-26T03:28:53+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

> Reply from DOTAPRINCE
>
> I can't quite understand, How do I import the model in 3ds max?
I would also like to know how to import in 3dmax
## Post #15
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-17T03:12:17+00:00
- Post Title: [PS3]Bleach Soul Ignition demo SPk container for models

Shadowmoy any updates from this?
## Post #16
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-09-18T18:00:28+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

see first post ...
## Post #17
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2011-09-18T23:03:58+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

I read your post and I tried it out, you say just drag and drop. Is there anything special we are supposed to name the spk files?

As I do that I just says all these things missing variable name 'word' and 'filename' Then says Script Paused. I must be doing something wrong or just read your post wrong apparently.
## Post #18
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-09-19T10:38:24+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

> Reply from Milesgboy
>
> I read your post and I tried it out, you say just drag and drop. Is there anything special we are supposed to name the spk files?

As I do that I just says all these things missing variable name 'word' and 'filename' Then says Script Paused. I must be doing something wrong or just read your post wrong apparently.
sorry for that i forgot the dll with the exe, just download it from 1rst post and put in in the same folder as the exe .
## Post #19
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-19T10:46:55+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

I get an error :/

Anyway what to do with the unk files?

edit: nvm , found them at C:\Documents and Settings\user 
thanks
## Post #20
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-02-08T20:53:36+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

Any chance of this getting bones and weight data?
## Post #21
- Username: darkluap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2010 8:04 am
- Post datetime: 2012-05-04T04:49:16+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

Hello, I tried to find out about these models, but there is little that I have achieved, and the links that are left dead, could you upload again? Please
## Post #22
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-04T16:24:05+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

> Reply from darkluap
>
> Hello, I tried to find out about these models, but there is little that I have achieved, and the links that are left dead, could you upload again? Please

Here you have:

[http://www.mediafire.com/?008mria88bro87m](http://www.mediafire.com/?008mria88bro87m)
## Post #23
- Username: darkluap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2010 8:04 am
- Post datetime: 2012-05-04T17:28:53+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

thank you very much!!
## Post #24
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2012-06-08T21:46:09+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

any update this game
## Post #25
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2013-04-05T16:20:06+00:00
- Post Title: Re: [PS3]Bleach Soul Ignition demo SPk container for models

Curious if shadowmoy will continue to update this. Since I'd like to see these models with their full rig and proper meshes. If not if he could post the specs he has had of it.
