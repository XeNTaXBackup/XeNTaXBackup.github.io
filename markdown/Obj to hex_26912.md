## Post #1
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-28T17:44:39+00:00
- Post Title: Obj to hex

¿Is Posible convert obj to hex?
## Post #2
- Username: lorak
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 26, 2023 4:27 am
- Post datetime: 2023-06-29T01:08:28+00:00
- Post Title: Obj to hex

I think so. In theory, you just need to express real numbers -float- from the vertices attributes as hex numbers with the proper file structure, either little endian or big endian. Express data for v, vn and vu in sections or blocks as an hex number. Similar for faces indices.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-29T06:13:42+00:00
- Post Title: Obj to hex

> Reply from lorak ↑Thu Jun 29, 2023 9:08 am at Thu Jun 29, 2023 9:08 am
>
> 
I think so. In theory, you just need to .."In theory", yes, but... (quoting myself:) "Generally the "reverse way" requires a FULL format analysing."

That means you'll need to know the meaning of nearly EVERY byte in said 3D format to be transformed to.

bin/hex to obj is rather simple in most cases while obj to hex means a shitload of work, usually..

To find this being true just
"Search this forum and you'll see that there's very rare solutions for 'obj to someBinaryGameFormat' conversions."

There's a simple approach, however. You could just inject vertices and face indices into an existing file of your preferred 3D format.
This requires the destination file to contain more or equal vertices than the source obj.

If not equal you'll need to adjust the counts in the destination file.

(From my experience this works for static meshes.)
## Post #4
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-29T07:29:31+00:00
- Post Title: Obj to hex

Yes, but is a tool available or script ?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-29T08:24:23+00:00
- Post Title: Obj to hex

> Reply from Dani ↑Thu Jun 29, 2023 3:29 pm at Thu Jun 29, 2023 3:29 pm
>
> 
Yes, but is a tool available or script ?Since you didn't mention WHICH hex format you're talking of I'm not sure whether you understood correctly. There's a myriad "hex" 3D formats. Each of them would require a specific tool/script for an "obj to this specific hex format" conversion.

So usually it has to be written/created.
## Post #6
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-29T10:16:47+00:00
- Post Title: Obj to hex

Ooo sorry i forget to tell ok.
I used hex2obj and the faces in on short short and the uvs half_uv and vertices float
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-06-29T10:55:49+00:00
- Post Title: Obj to hex

> Reply from Dani ↑Sat Jun 17, 2023 12:08 am at Sat Jun 17, 2023 12:08 am
>
> 
I have a idea i need a small script that convert only faces vértices uvs and animation data to hex similar to hex2obj but in this case obj to hex
What the heck do you need that for? Ambiguous discussion like this will lead you nowhere.
## Post #8
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-29T11:50:08+00:00
- Post Title: Obj to hex

I need to overwrite a binary File mesh data
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-06-29T15:40:47+00:00
- Post Title: Obj to hex

Thought you were trying to understand the binary data from an opposite aspect. Well then, good luck with that.
## Post #10
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-29T18:37:25+00:00
- Post Title: Obj to hex

Just for Giggles.
I took the Terrain Data for Silent Hunter 5 and converted it to an obj file format with 010 so Modders could adjust the heights in a 3D program.
Then wrote a script for 010 that converts it BACK to a binary format. So knowing the whole format? It can be done.
Here's a quick snip of converting from a obj file to a data file SH5 understands.

int i, s[30603], b, a;

char String[20], W[40];

TFindStringsResults r = FindStrings( 8, FINDSTRING_ASCII,
FINDSTRING_NUMBERS | FINDSTRING_SYMBOLS );

for( i = 0; i < 30603; i++ )
  {
     i=(i+1);//Jump past the x 
      s=r.start;
      String=ReadString( s, 10);
      SScanf( String, "%f", a);
      b = SwapBytes(a);
      Printf( "%.8X\n", b);
     i=(i+1);//Jump past the z

  }

W = InputString("Save File", "Name your save file", "c:\\temp\\");// You can change the path when saving.
OutputPaneSave( W );

That Script jumps past the X and Z of an obj file to output what I needed. 
Should I show you the Script to convert FROM the SH5 Data to a useable obj file format?
No one taught me how to do this. I spent time to figure it all out. 
It's called learning! Seems to be an extinct thing now days.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-29T21:51:15+00:00
- Post Title: Obj to hex

> Reply from Dani ↑Thu Jun 29, 2023 7:50 pm at Thu Jun 29, 2023 7:50 pm
>
> 
I need to overwrite a binary File mesh dataThen the question is: "do you know where the count of vertices and the count of face indices are located in said binary file?"
## Post #12
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-29T22:24:12+00:00
- Post Title: Obj to hex

> Reply from shakotay2 ↑Fri Jun 30, 2023 5:51 am at Fri Jun 30, 2023 5:51 am
>
> 
Dani wrote: ↑Thu Jun 29, 2023 7:50 pm
I need to overwrite a binary File mesh data
Then the question is: "do you know where the count of vertices and the count of face indices are located in said binary file?"
Not only that but can you adjust others areas involved with the file?
Such as file size count and so on. 
It's never as easy as one thinks!

Now you want to talk files I understand? I can edit those as I wish. But I spent YEARS working with them.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-29T23:13:46+00:00
- Post Title: Obj to hex

> Reply from 05SpeedMaster ↑Fri Jun 30, 2023 6:24 am at Fri Jun 30, 2023 6:24 am
>
> 
Not only that but can you adjust others areas involved with the file?I'll implement a poor obj2hex converter into hex2obj (that was the reason why I was asking). It will be very simple with no need to resize regions or something. (In case the source new.obj contains the same amount of vertices/face indices as the destination the counts can be left untouched.)
## Post #14
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-29T23:24:59+00:00
- Post Title: Obj to hex

> Reply from shakotay2 ↑Fri Jun 30, 2023 7:13 am at Fri Jun 30, 2023 7:13 am
>
> 
05SpeedMaster wrote: ↑Fri Jun 30, 2023 6:24 am
Not only that but can you adjust others areas involved with the file?I'll implement a poor obj2hex converter into hex2obj (that was the reason why I was asking). It will be very simple with no need to resize regions or something. (In case the source new.obj contains the same amount of vertices/face indices as the destination the counts can be left untouched.)

That's really cool. I'll be honest with you. I have never tried hex2obj.
I have always just worked with 010. Kind of a hard core Guy myself. But I only work with a certain files type.
Mostly the Silent Hunter Games from 3 to 5. 5 being the GR2 file format. The GR2 file format? I'm pretty danged good with that!

On the conversion from obj to a hex file? Would you like to see the files I did for SH5?
It takes a file and converts it to a 3D obj file for editing. Then converts back to a data file SH5 reads as a terrain file.
To me? It's not outstanding but a very good example of working the information.

I'll upload a simple terrain file. See what you think.

Convert this to a 3D mesh.....
[https://www.mediafire.com/file/tpjrxte0 ... t.RAW/file](https://www.mediafire.com/file/tpjrxte067e486p/Test.RAW/file)
## Post #15
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-29T23:57:17+00:00
- Post Title: Obj to hex

1st thing I expect is you will fail. You don't understand how that file works. You may grab some info but you will probably be lost as to how to use it.
Let me know when you want the answer as to how and why.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-06-30T03:07:52+00:00
- Post Title: Re: Obj to hex

> Reply from 05SpeedMaster ↑Fri Jun 30, 2023 7:24 am at Fri Jun 30, 2023 7:24 am
>
> 
(quoting shakotay2)
...
Would you like to see the files I did for SH5?
...
See what you think.
Which "you" are you referring to? I'm confused, coz it doesn't seem to make much sense to tease the OP.  

> Reply from 05SpeedMaster ↑Fri Jun 30, 2023 7:57 am at Fri Jun 30, 2023 7:57 am
>
> 
1st thing I expect is you will fail...



test.png (44.36 KiB) Viewed 146 times


Something like that?
## Post #17
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2023-06-30T04:37:48+00:00
- Post Title: Re: Obj to hex

> Reply from 05SpeedMaster ↑Fri Jun 30, 2023 7:24 am at Fri Jun 30, 2023 7:24 am
>
> 
...
It takes a file and converts it to a 3D obj file for editing. Then converts back to a data file SH5 reads as a terrain file.
...

Why not just write an editor and edit the file without converting it back and forward?
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-30T06:53:58+00:00
- Post Title: Re: Obj to hex

> Reply from 05SpeedMaster ↑Fri Jun 30, 2023 7:57 am at Fri Jun 30, 2023 7:57 am
>
> 
1st thing I expect is you will fail. You don't understand how that file works. You may grab some info but you will probably be lost as to how to use it.
Let me know when you want the answer as to how and why.Sorry man, I have no idea what you're talking about. This is NOT a competition. I'm sorry if you feel pissed 'cause I didn't have a look into your 010 solution (never used that template thingie). So let's end this discussion since it leads to nowhere.
## Post #19
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-06-30T11:15:54+00:00
- Post Title: Re: Obj to hex

in fact, he continues to "produce" topics:
[Obj to hex](https://forum.xentax.com/viewtopic.php?t=26912)
[¿Looney Tunes Dash! Animations?](https://forum.xentax.com/viewtopic.php?t=26856)
[help fmlb files](https://forum.xentax.com/viewtopic.php?t=26551)
[Buffer problem](https://forum.xentax.com/viewtopic.php?t=26536)
[Looney Editor!](https://forum.xentax.com/viewtopic.php?t=25925)
[Looney Tunes Dash! xml and fmlb files](https://forum.xentax.com/viewtopic.php?t=26519)
[Please help my with fmlb files 3d looney tunes dash](https://forum.xentax.com/viewtopic.php?t=25058)

plugin:
[fmt_fmlb.zip](https://forum.xentax.com/viewtopic.php?p=182216#p182216)

*the last thing I'll say is if you're using python, look towards "struct"
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-30T14:40:57+00:00
- Post Title: Re: Obj to hex

> Reply from Durik256 ↑Fri Jun 30, 2023 7:15 pm at Fri Jun 30, 2023 7:15 pm
>
> 
in fact, he continues to "produce" topics:Haha, yes, I noticed that, too.  

For the "Buffer problem" thread: I didn't find it as worse as you may do. It gave me the chance to decrease the entropy of the universe. Or encrease?  Dunno... 

edit: while checking my obj2hex solution I found a problem which I didn't foresee: two different meshes having the same vertex count don't have inevitably the same face index count. Weird. So you'll need to find a destination file where both counts are bigger than or equal to the ones of the source file.
## Post #21
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-07-01T06:28:46+00:00
- Post Title: Re: Obj to hex

You are making obj2hex tool?
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-01T12:59:35+00:00
- Post Title: Re: Obj to hex

> Reply from Dani ↑Sat Jul 01, 2023 2:28 pm at Sat Jul 01, 2023 2:28 pm
>
> 
You are making obj2hex tool?Done (see Tutorials forum). But don't expect too much.
