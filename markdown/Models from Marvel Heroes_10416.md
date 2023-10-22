## Post #1
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2013-05-13T23:24:51+00:00
- Post Title: Models from Marvel Heroes?

With this game being released as Free to Play, does anyone plan on making a tool to extract models from it? It has quite a huge collection of high quality super heroes and villains.

[https://marvelheroes.com/model-sheets](https://marvelheroes.com/model-sheets)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-14T00:41:21+00:00
- Post Title: Models from Marvel Heroes?

its an unreal 3 game already supported by umodel.
## Post #3
- Username: skyvenom
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Oct 18, 2011 8:32 pm
- Post datetime: 2013-05-14T17:15:29+00:00
- Post Title: Models from Marvel Heroes?

> Reply from chrrox
>
> its an unreal 3 game already supported by umodel.

*sigh* Always late to the party. Thanks for the heads up Chrrox =)
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2013-05-21T21:46:56+00:00
- Post Title: Models from Marvel Heroes?

> Reply from chrrox
>
> its an unreal 3 game already supported by umodel.

Yes but not fully supported for this game, ATM this system doesnt work with Textures, u only can extract 64x64 size, the other textures its imposible to extract. u know 64x64 textures its true crap.
## Post #5
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-09-25T23:43:38+00:00
- Post Title: Models from Marvel Heroes?

Is there any way to get a hold of these models now the game is offline? I can't find any copies of it.
## Post #6
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-09-28T10:26:43+00:00
- Post Title: Models from Marvel Heroes?

Check out [http://gamesrepository.000webhostapp.com/](http://gamesrepository.000webhostapp.com/) for Marvel Heroes Omega mate. Are after any character(s) in particular?
## Post #7
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-10-08T23:07:29+00:00
- Post Title: Models from Marvel Heroes?

thanks! i think i have all the ones i need.
## Post #8
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2019-10-11T21:17:45+00:00
- Post Title: Models from Marvel Heroes?

> Reply from Rimbros ↑Wed May 22, 2013 5:46 am at Wed May 22, 2013 5:46 am
>
> Yes but not fully supported for this game, ATM this system doesnt work with Textures, u only can extract 64x64 size, the other textures its imposible to extract. u know 64x64 textures its true crap. I also have this problem with DC Universe Online (Unreal Engine 3 MMO game). 
If Marvel Heroes has a TEXTUREFILECACHE directory, then the high resolution textures should be in there. 
There is a tool that can extract the textures from the .TFC files, it's called [Raw TFC Exporter](https://forum.xentax.com/viewtopic.php?f=18&t=16033). 

The tool comes with a few executables for different games, but you can try using any of them, just make sure to use the executable that extracts the most textures. There is a chance that an executable may extract a corrupt 512x512 image texture that is supposed to be 2048x2048, so you may want to try another executable. 

I shared my method with Gildor, the author of UModel, but it's not something that UModel can incorporate into its program. 
However, you can still try the method yourself: 
- [https://github.com/gildor2/UEViewer/issues/139](https://github.com/gildor2/UEViewer/issues/139) 


> Reply from Ecelon ↑Sat Sep 28, 2019 6:26 pm at Sat Sep 28, 2019 6:26 pm
>
> 
Check out http://gamesrepository.000webhostapp.com/ for Marvel Heroes Omega mate. Are after any character(s) in particular?
@Ecelon Thank you, did you use Raw TFC Exporter method too?
## Post #9
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-10-12T04:39:39+00:00
- Post Title: Models from Marvel Heroes?

> Reply from Curtain ↑Sat Oct 12, 2019 5:17 am at Sat Oct 12, 2019 5:17 am
>
> 
@Ecelon Thank you, did you use Raw TFC Exporter method too?

Yeah I did, there was one made specifically for Marvel Heroes that keeps file names mate.


 Marvel_heroes_tfc.rar
(66.07 KiB) Downloaded 24 times



Pity how the DC Universe Online textures don't keep their names, cause I'd rip the s**t outta them LOL

Also, I forget who created the tool, wasn't me, but credit to him!
## Post #10
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2019-10-12T06:10:17+00:00
- Post Title: Models from Marvel Heroes?

> Reply from Ecelon ↑Sat Oct 12, 2019 12:39 pm at Sat Oct 12, 2019 12:39 pm
>
> Pity how the DC Universe Online textures don't keep their names, cause I'd rip the s**t outta them LOL Lol yea, I was actually busy extracting the models and textures from the game this past month:
- [https://www.deviantart.com/xcurtainx/ga ... rse-online](https://www.deviantart.com/xcurtainx/gallery/65225525/dc-universe-online)
- It's a bit tedious.


> Reply from Ecelon ↑Sat Oct 12, 2019 12:39 pm at Sat Oct 12, 2019 12:39 pm
>
> Also, I forget who created the tool, wasn't me, but credit to him! It looks like that tool was also created by daemon1: 
- [viewtopic.php?f=18&t=14460&sid=ecd87d40 ... cacc74d15d](https://forum.xentax.com/viewtopic.php?f=18&t=14460&sid=ecd87d400b2d009a480f06cacc74d15d)
## Post #11
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-10-12T08:00:36+00:00
- Post Title: Models from Marvel Heroes?

> Reply from Curtain ↑Sat Oct 12, 2019 2:10 pm at Sat Oct 12, 2019 2:10 pm
>
> 
Lol yea, I was actually busy extracting the models and textures from the game this past month:
- https://www.deviantart.com/xcurtainx/ga ... rse-online
- It's a bit tedious.

They look pretty choice mate, good on you. It bloody is, but the "Bombshells" ladies are worth it . I've just uploaded the ones I did yonks ago to my website, along with some Pokemon GO models .

> Reply from Curtain ↑Sat Oct 12, 2019 2:10 pm at Sat Oct 12, 2019 2:10 pm
>
> 
 It looks like that tool was also created by daemon1: 
- viewtopic.php?f=18&t=14460&sid=ecd87d40 ... cacc74d15d

Thank god for him though. He's released a tonne of cool tools. Wish I were half as smart as him XD
