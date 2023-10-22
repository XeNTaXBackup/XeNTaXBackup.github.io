## Post #1
- Username: Omgheadshot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 05, 2011 4:19 am
- Post datetime: 2011-09-04T20:23:20+00:00
- Post Title: Cabal Ech File

hey guys can someone make a script unpacker to unpack this .ech file ? i Really need it 

thanks
## Post #2
- Username: Omgheadshot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 05, 2011 4:19 am
- Post datetime: 2011-09-07T00:58:39+00:00
- Post Title: Cabal Ech File

Anyone can help me whit this ?? :S
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-23T23:56:30+00:00
- Post Title: Cabal Ech File

> Originally Posted by Yamachi 
>
> /Data/Object/Character
>
> 
>
> woman.ech, woman2.ech, woman3.ech, woman4.ech, and woman5.ech for female
>
> man.ech, man2.ech, man3.ech, man4.ech, and man5.ech for male
>
> 
>
> If you want to modify a texture inside an EBM/ECH, just open the file in a hex editor. Then, find the name of the texture (*.dds), place you cursor before the following "DDS |", select until the end of the file, and then click on File -> Save selection as... (NOTE: This is how you do it in Hex Workshop, but shouldn't be much different from any other hex editor). Now that you've extracted the texture (along with some "fluff"), we need to find the compression rate of the image so we can save it correctly after editing it. Open up the DDS image in Hex Workshop. Near the top of the column on the right-hand side, you should see DXT1, DXT3 or DXT5. If none of those appear, you know that the texture is uncompressed. Now, edit the texture however you want, the resave it using the compression rate you found (DXT1, DXT3, DXT5, or nothing [argb32 if u use PS]). Then, what I do, is open the original EBM in Hex Workshop, and also open the texture in Hex Workshop. Write down the filesize for the texture (Hex Workshop displays EXACT filesize), then go into the EBM/ECH file, put ur cursor before the "DDS |" again, then click on Edit -> Select Block. Make sure "Dec" and "Size of Block" are checked, then type in the filesize of the texture, and click OK. Then, click on File -> Replace With File...", and choose the modified DDS file. Save, and you're done ^_^
>
> 
>
> Texture names for items contain:
>
> 
>
> Helmet = cap_XYY.dds
>
> Suit = body_XYY.dds
>
> Gloves = hand_XYY.dds (and sometimes arm_XYY.dds)
>
> Boots = foot_XYY.dds (and sometimes leg_XYY.dds)
>
> Cape = coat_XYY.dds
>
> 
>
> X can be either a, m, or z. a is armour. m is battle, and z is martial.
>
> YY starts at 00 for unclothed, and increases from there. The numbers are sometimes out of sequential order (ie. STit has a higher YY number than Mithril/Forcium)
>
> 
>
> 
>
> NOTE: Make sure you ALWAYS back up your EBM file BEFORE reinjecting the modified DDS file. I don't wanna see anyone whinging coz they fucked the file up...
>
> 
>
> NOTE 2: Once I release Mr. Paint, you'll be able to extract and inject textures without having to go thru all the crap with Hex Workshop. The only thing you'll need to do is modify the texture

from ragezone forum
