## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-05-15T04:03:27+00:00
- Post Title: Is there a program that will let you replace DDS files?

I know that Game Extractor will scan an unknown archive and find and let you preview DDS files, but unless the archive is a known type, you can't replace the DDS files with different ones and save the archive.

What I was looking for, is a program that will scan an archive for DDS files, with preview if possible, and then let you replace each of them with the same sized and type DDS file.  A program with a GUI and preview window would be the best, but isn't a requirement.

Is there such a program already available, that someone has made?  The reason I am asking for this, is that I have been swapping DDS files in the game I've been hacking, using just a hex editor for way too long, and this would make it so much easier to do.  I have made my own archives that the game can read, but when I make updated archives, I always have to replace the DDS files manually with a hex editor.  

I can make a program myself, but it's been so long since I've made one, and I really don't have the time to invest in getting familiar with it again.  If anyone can help that is a really good programmer, and wants to make a program like that, or if anyone knows of an existing program like that, I'd really appreciate the help.  Thanks.
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-05-15T06:51:57+00:00
- Post Title: Is there a program that will let you replace DDS files?

At the top of this side is a "Tools" button. Use it, scroll down and search this: Jaeder Naub 2.1.4g
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-05-15T07:08:54+00:00
- Post Title: Is there a program that will let you replace DDS files?

> Reply from evin
>
> At the top of this side is a "Tools" button. Use it, scroll down and search this: Jaeder Naub 2.1.4g
I think I used that one time, but the interface was so ridiculous, I couldn't figure out how to do anything with it.
## Post #4
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-05-15T08:50:59+00:00
- Post Title: Is there a program that will let you replace DDS files?

Texmod should suit your needs.
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-05-15T17:45:41+00:00
- Post Title: Is there a program that will let you replace DDS files?

> Reply from AceAngel
>
> Texmod should suit your needs.
It would if I was changing textures in a DirectX9 PC application, but I am not.  I have simple archives that contain DDS files, and need to have an easy way to swap them with another DDS file.  The archive is not even used in a PC game, so TexMod simply won't work for me.  

It's starting to look like I may just have to program the thing myself, or figure out how to use Jaeder Naub, which I remember also had trojan alerts last time I went to use it too.  They of course could be false positives, but doesn't make me feel any safer, when other similar programs don't say they are a trojan, such as Game Extractor.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-16T07:07:23+00:00
- Post Title: Is there a program that will let you replace DDS files?

There never was a trojan or virus in Jaeder Naub (i am the author) , I did however use an EXE Packer for it, and since the antivirus companies are lame and cannot scan packed exes,
they assume that all packed exes (with that signature) is a virus, one of the reasons i dont use anti-virus software. I no longer pack it, since too many people thought it was a virus.
And yes, the injection part of jaedernaub wasnt really that thought through! but it works actually when you get hang of it =D
I might consider to rewrite it.

Edit: I would like someone to make a sketchy layout for how a decent and easy to use injector would look like, so that i have something to work on if/when im rewriting the Injector in Jaedernaub,
since the main problem with me is that i make interfaces that are easy for me to understand.
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-05-17T08:10:24+00:00
- Post Title: Is there a program that will let you replace DDS files?

> Reply from Strobe
>
> There never was a trojan or virus in Jaeder Naub (i am the author) , I did however use an EXE Packer for it, and since the antivirus companies are lame and cannot scan packed exes,
they assume that all packed exes (with that signature) is a virus, one of the reasons i dont use anti-virus software. I no longer pack it, since too many people thought it was a virus.
And yes, the injection part of jaedernaub wasnt really that thought through! but it works actually when you get hang of it =D
I might consider to rewrite it.

Edit: I would like someone to make a sketchy layout for how a decent and easy to use injector would look like, so that i have something to work on if/when im rewriting the Injector in Jaedernaub,
since the main problem with me is that i make interfaces that are easy for me to understand.
I didn't think it would have a virus, considering they had the program on the site here, but it's better to be safe than sorry, and your new version does not set off the anti-virus software now.  

The easiest interface, would be to either list the textures, giving them generic names, or to actually have them listed out with a preview of what they look like (not sure if you can implement an actual previewer like that).  Then make it a simple right-click selection menu to replace or even make it as easy as double-clicking it, then the open file interface would open up, you select the replacement texture, and click ok.  Hell, I don't even care if there is a "safety" feature, to make sure the textures are the right size, because I'm smart enough to know better than to replace them with a different size texture.  

I think your program looks like it is pretty powerful, and works really well, it's just hard for me to interface with it, and resorted back to the hex editor for now.
