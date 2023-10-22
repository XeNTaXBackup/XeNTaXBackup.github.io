## Post #1
- Username: trumpdog
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 15, 2010 11:28 am
- Post datetime: 2012-06-23T02:54:16+00:00
- Post Title: what is texture2d

I recently came across a much needed gpk unpacker/repacker for tera online. The problem is the texture format that it uses.
If i use umodel, i can get the tga but what good is that when it needs to be texture2d to repack it and if i use the unpacker/repacker, i get texture2d which is as useless as the tga.

Is the texture2d some sort of archive contain the tga and is there a way to convert from tga>texture2d and back?
same issue with the models aswell. umodel exports .psk and the other exports .skeletalmesh.

Been searching everywhere and cannot find anything about working with these formats.
any help would be appreciated. ty in advanced.
## Post #2
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-06-23T14:12:48+00:00
- Post Title: what is texture2d

It's a bit more complicated... the .texture2d files of unreal engine based games contain headerless .DDS data in blocks...

first the "main" texture block, then all the mipmaps... you might want to check out the mortal kombat 9 texture modding topic where some guys explained how it works... however the format ofcours differs for each platform and game (some use dxt5, some dxt1 etc.)
