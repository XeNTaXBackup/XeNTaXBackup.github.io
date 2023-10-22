## Post #1
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-13T04:53:18+00:00
- Post Title: Project Diva F 2nd Noesis .osd

Here is a script to load these models with Textures and Bones.
To extract the encrypted farcs use the quickbms script here(Works on all Project diva farcs).
[http://aluigi.altervista.org/papers/bms ... hter_5.bms](http://aluigi.altervista.org/papers/bms/virtua_fighter_5.bms)
Then use the noesis script to open the model files.
I recommend using this command to extract the farcs.

```
quickbms.exe -d -F "*.farc"  c:\vf5.bms c:\farc_folder c:\farc_extracted
```

use the noesis merge script included from 
[https://code.google.com/p/noesis-plugin ... context.py](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/Rich/tool_batchload_context.py)
right click on the model files in noesis and load them in this order.
1 - Body
2 - Head
3 - Hands
4 - Hair
5 - anything else
and you should get this result

[project_diva.7z](https://xentaxbackup.github.io/file/7199_project_diva.7z)
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-13T07:58:06+00:00
- Post Title: Project Diva F 2nd Noesis .osd

PS3 or Vita??
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-13T08:03:21+00:00
- Post Title: Project Diva F 2nd Noesis .osd

PS3 version
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-13T08:11:48+00:00
- Post Title: Project Diva F 2nd Noesis .osd

Sweet!
## Post #5
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2014-04-13T15:51:51+00:00
- Post Title: Project Diva F 2nd Noesis .osd

rename 

```
quickbms.exe -d -F "*.farc'  c:\vf5.bms c:\farc_folder c:\farc_extracted
```


to

```
quickbms.exe -d -F *.farc  c:\vf5.bms c:\farc_folder c:\farc_extracted
```


And Work.

But Thax
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-13T16:06:58+00:00
- Post Title: Project Diva F 2nd Noesis .osd

I just had the wrong closing quote.
it was a miss type.
## Post #7
- Username: sakuraxangel31
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 12, 2012 1:22 pm
- Post datetime: 2014-04-13T19:59:29+00:00
- Post Title: Project Diva F 2nd Noesis .osd

Hey this might be a silly/nobish question buuuut how do i extract the farc files from EBOOT.bin i remember i did this with Dreamy Theater or am i doing this wrong ?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-13T20:21:27+00:00
- Post Title: Project Diva F 2nd Noesis .osd

eboot.bin? that is the main executable.
you need to extract the giant psarc archive to get to the farc files.
## Post #9
- Username: OkpOkpX2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 09, 2011 9:47 am
- Post datetime: 2014-04-13T23:50:02+00:00
- Post Title: Project Diva F 2nd Noesis .osd

I got kinda confused. Ive extracted the .psarc files but when i try to extract the .farc files  i keep getting .a3da files
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-14T00:00:09+00:00
- Post Title: Project Diva F 2nd Noesis .osd

run the command like i said then look for *.osd.
## Post #11
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-14T01:22:26+00:00
- Post Title: Project Diva F 2nd Noesis .osd

One thing, do not use the model merger if you don't want being pareting duplicated bones. Especially It's a pain in the ass if you're using motion builder or iClone.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-14T04:41:32+00:00
- Post Title: Project Diva F 2nd Noesis .osd

I don't understand what you mean.
If you merge them in the correct order that i mentioned you get one nice skeleton.
## Post #13
- Username: OkpOkpX2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 09, 2011 9:47 am
- Post datetime: 2014-04-15T00:48:36+00:00
- Post Title: Project Diva F 2nd Noesis .osd

I must be stupid, i'm still stuck...
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-15T01:38:47+00:00
- Post Title: Project Diva F 2nd Noesis .osd

The only way you are stuck is you did not follow directions.
Run the command like i said from command line.
Those other files you are getting are normal files you are extracting farc files with no meshes in them.
## Post #15
- Username: aobw
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 29, 2014 12:22 pm
- Post datetime: 2014-04-15T09:49:54+00:00
- Post Title: Project Diva F 2nd Noesis .osd

Big thanks to God
Thanks! Thanks! Thanks! Thanks! Thanks! Thanks!
Waited for three years!
## Post #16
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-15T16:02:26+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

> Reply from aobw
>
> Big thanks to God
Thanks! Thanks! Thanks! Thanks! Thanks! Thanks!
Waited for three years!

Lol Yeah:

[https://www.youtube.com/watch?v=JKpaSRprE1Q](https://www.youtube.com/watch?v=JKpaSRprE1Q)
## Post #17
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2014-04-17T16:19:20+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

Does this work on the first Project Diva F?
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-17T17:48:30+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

> Reply from Ayuvir
>
> Does this work on the first Project Diva F?
The archives can be extracted. There is an old blender script to import those models with as its a different format.
if i feel like torturing myself some more i might add support for the old format.
## Post #19
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-04-27T02:00:47+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

> Reply from chrrox
>
> Ayuvir wrote:Does this work on the first Project Diva F?
The archives can be extracted. There is an old blender script to import those models with as its a different format.
if i feel like torturing myself some more i might add support for the old format.

Can we torture you??
## Post #20
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2014-04-30T12:47:57+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

As far as I'm aware, all the modules available on the first Project Diva F are already included on 2nd, which I did not know at the time I posted my last message.

I managed to find one of the modules in 2nd which I thought was only available on the first one.

Thanks a lot for the scripts.
## Post #21
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-05-04T21:56:07+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

Hello.

I am having issues extracting the models for some reason. I have updated Noesis, already have osd and farc files ready, downloaded and put the Noesis script into the plugins folder... yet, when I try to open the characters, I get the 'File could not be previewed' error. Any specific reason? I'm probably doing something wrong here...
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-04T22:08:36+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

Did you extract the farc files with the bms script?
## Post #23
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-05-04T22:23:39+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

Yeah, they were extracted with that. I didn't do that myself because I got Kaito's files already available and ready to be loaded in Noesis. The same files seem to work for the person who passed them to me...
## Post #24
- Username: RunaWhite
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-04T22:42:49+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

I would download a fresh copy of noesis to a new folder and just put in the 2 plugins merge.py and the f 2nd py.
## Post #25
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-05-04T22:59:11+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

You said you have the scripts in The plugin folder. I dunno you most likely did but they have to be in the Phyton subfolder^^
## Post #26
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-05-04T23:02:08+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

Oh wow... I don't really know why I was having that issue, but I just did as you suggested and now it seems to work! Thank you very much chrrox! :3

@Crofty: lol yes, they actually were there ^^' *confused*
## Post #27
- Username: Gerte
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 04, 2014 2:04 am
- Post datetime: 2014-09-04T04:15:07+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

hi there i need a help with my noesis. this may a noobish question but im new here   
my noesis hasn't skeleton icon. does my noesis have a missing plugin that support bone? where plugin that i need??
sorry for bad english. thank u
## Post #28
- Username: bryciekai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 06, 2015 4:41 am
- Post datetime: 2015-07-05T20:43:22+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

How do i also rip the animations and rigs for individual characters. Also, when i try doing this with Dreamy Theatre, and Project Diva F, it just gives me bin files?
## Post #29
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-07-05T22:12:44+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

> Reply from bryciekai
>
> How do i also rip the animations and rigs for individual characters. Also, when i try doing this with Dreamy Theatre, and Project Diva F, it just gives me bin files?

Noesis plugins only supports models for PDF 2nd, not animations. Dreamy Theater and PD format is different.

I guess the only thing I could resquest here is if someone could fix chrrox maxscript, skinning is correct but the bone assignment is wrong.
## Post #30
- Username: Hamza
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 24, 2016 3:20 pm
- Post datetime: 2016-02-24T07:26:55+00:00
- Post Title: Re: Project Diva F 2nd Noesis .osd

Where do I run da command???
