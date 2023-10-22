## Post #1
- Username: darkweb
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 13, 2007 12:11 am
- Post datetime: 2008-02-03T20:06:31+00:00
- Post Title: TMX file format help

Hi,
So I'm attempting to rip images from a game.  The file format is apparently a TMX format but I can't seem to find any info on it.  From what I can tell, the palette starts at 0x40 and consists of 256 colors at RGBA8888 possibly? The data of the image starts at 0x440 and appears to index the color palatte.  
Using this format I get the image found in atluspalette.jpg. This has some of the right colors but still doesn't look correct.  
For fun I used the index values as the RGB values and came up with atlusgreyscale.jpg which surprisingly looks good so I think it might be a combination of the palette and the index value?

A breakdown of the attached file:
atlus.jpg - this is how it should look
atluspalette.jpg - what I get with the indexed color palette
atlusgreyscale.jpg - what I get with the indices as the rgb values
atlus.tmx - the original file

Any help would be appreciated!
[atlus.rar](https://xentaxbackup.github.io/file/1440_atlus.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-02-04T02:32:40+00:00
- Post Title: TMX file format help

An Atlus format? Mind telling where this comes from?
## Post #3
- Username: darkweb
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 13, 2007 12:11 am
- Post datetime: 2008-02-04T19:28:57+00:00
- Post Title: TMX file format help

It's actually the art gallery picture format for princess crown but can also be extended to the sprites and animations.
## Post #4
- Username: darkweb
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 13, 2007 12:11 am
- Post datetime: 2008-02-20T18:50:16+00:00
- Post Title: TMX file format help

I still can't seem to get this working right... Does anyone have any ideas at all about what seems to be wrong?
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-08T19:26:07+00:00
- Post Title: TMX file format help

Instead of creating a new topic about the same thing I'll contribute to this one. Here is another TMX file, this one is from Persona 3 FES. Hopefully somebody will be able to crack it.
[PST_001.rar](https://xentaxbackup.github.io/file/1607_PST_001.rar)
## Post #6
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-09T19:09:01+00:00
- Post Title: TMX file format help

Can anybody upload more files ??? I need more files to test...
(I found (probably) clue how to convert it to bmp
## Post #7
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-08-09T21:42:27+00:00
- Post Title: TMX file format help

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-09T22:56:34+00:00
- Post Title: TMX file format help

Awesome, hope you luck on this! 

Also, I think 251 examples is enough for anyone. XD
## Post #9
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-10T18:48:39+00:00
- Post Title: TMX file format help

darkweb:
I think that "ATLUS.TMX" is corrupted... it has a wrong dimension + its BGRA + upside down  
There is converted image:
[http://img98.imageshack.us/img98/673/atlusby0.png](http://img98.imageshack.us/img98/673/atlusby0.png)

What I found to be really interesting is that indexes to palette has some color information of original image,in images posted by xrevenge there is no similar image using this technique:
[http://img98.imageshack.us/img98/577/at ... ttefk1.png](http://img98.imageshack.us/img98/577/atlusnopalettefk1.png)
So to get correct RGB value you should: add index value to every channel except A,or "xor" it,or "and" it,or "or" it... I'll look at that later but I need more similar files... like (ATLUS.TMX)


Darkfox: Your image seems to be converted correctly too...
[http://img398.imageshack.us/img398/9930/pst001fu0.png](http://img398.imageshack.us/img398/9930/pst001fu0.png)

xrevenge:
Your images seems to be fine when converted,no dimension error,colors seems to be in correct order,I dont know if there is any color loss... because I dont have any original image or screenshot from game...
[http://img218.imageshack.us/img218/6456/ibust0aavu2.png](http://img218.imageshack.us/img218/6456/ibust0aavu2.png)
[http://img398.imageshack.us/img398/3107/pst0c3tg4.png](http://img398.imageshack.us/img398/3107/pst0c3tg4.png)
[http://img218.imageshack.us/img218/9373/pst014yr8.png](http://img218.imageshack.us/img218/9373/pst014yr8.png)

Let me know if you think its converted correctly
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-10T19:49:45+00:00
- Post Title: TMX file format help

The images are correct but the colors are a bit off. Perhaps if I could find an example it'd help. But so far so good!
## Post #11
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-10T20:08:03+00:00
- Post Title: TMX file format help

> Reply from Darkfox
>
> The images are correct but the colors are a bit off. Perhaps if I could find an example it'd help. But so far so good!

Can you tell me how much is original image in game more colorful ? because if image is "palettized" then color depth is very limited...
## Post #12
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-08-10T21:51:57+00:00
- Post Title: TMX file format help

i don't know about corruption or not but tell me if you need anything else
## Post #13
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-10T22:34:42+00:00
- Post Title: TMX file format help

> Reply from xrevenge
>
> i don't know about corruption or not but tell me if you need anything else

I tried to convert next images again,but with swapped palette... now it should be correct:
[http://img230.imageshack.us/img230/5514/2pst0c3ta1.png](http://img230.imageshack.us/img230/5514/2pst0c3ta1.png)
[http://img230.imageshack.us/img230/6824/2pst014vt7.png](http://img230.imageshack.us/img230/6824/2pst014vt7.png)
Tell me if colors are not correct  but I think in this case its fine...
## Post #14
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-10T23:10:07+00:00
- Post Title: TMX file format help

> Reply from darkweb
>
> Hi,
So I'm attempting to rip images from a game.  The file format is apparently a TMX format but I can't seem to find any info on it.  From what I can tell, the palette starts at 0x40 and consists of 256 colors at RGBA8888 possibly? The data of the image starts at 0x440 and appears to index the color palatte.  
Using this format I get the image found in atluspalette.jpg. This has some of the right colors but still doesn't look correct.  
For fun I used the index values as the RGB values and came up with atlusgreyscale.jpg which surprisingly looks good so I think it might be a combination of the palette and the index value?

A breakdown of the attached file:
atlus.jpg - this is how it should look
atluspalette.jpg - what I get with the indexed color palette
atlusgreyscale.jpg - what I get with the indices as the rgb values
atlus.tmx - the original file

Any help would be appreciated!

I need more files to test than only one.... every time try to upload more files because of testing 

In your test file,I found out that 2 bit color information is saved in palette indexes (bit 4 & 5),probably 1 bit for R and 1 bit for B channel,A channel is correct and G channel seems to be untouched... It may be also some kind of "watermark" or lossy compression...
I tried to add these bits to RB channels,but not good results were given,I also tried to set that bits as 0 or 1,swap it but it was not worky....
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-11T07:59:23+00:00
- Post Title: TMX file format help

Ah yes! That looks far more accurate, possibly right on the nose there!
## Post #16
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-11T08:27:43+00:00
- Post Title: Re: TMX file format help

> Reply from Darkfox
>
> Ah yes! That looks far more accurate, possibly right on the nose there!

Thats good to know  But I'm still not sure if there is correct... I need one original image (non converted) or screenshot from game
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-12T03:00:19+00:00
- Post Title: Re: TMX file format help

You can find several on the Gamespot page here: [Persona 3 Screenshots](http://www.gamespot.com/ps2/rpg/persona3/images.html?om_act=convert&om_clk=tabs&tag=tabs;images)
## Post #18
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-13T10:03:24+00:00
- Post Title: Re: TMX file format help

> Reply from Darkfox
>
> You can find several on the Gamespot page here: Persona 3 Screenshots

From this screenshot...
[http://image.com.com/gamespot/images/20 ... een019.jpg](http://image.com.com/gamespot/images/2008/028/932312_20080129_screen019.jpg)

I guess that image posted in post above is decompressed correctly
## Post #19
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-13T19:14:41+00:00
- Post Title: Re: TMX file format help

Hm? I did see that one among the decompressed graphics and it did look right, albeit upside down but that's no biggie. The colors though of the Orpheus were a bit off. I could POSSIBLY get more screenshots by using PCSX2 by transferring over my savegames to it which has most of the Persona in the game. Including the unicorn.
## Post #20
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-13T19:22:20+00:00
- Post Title: Re: TMX file format help

> Reply from Darkfox
>
> Hm? I did see that one among the decompressed graphics and it did look right, albeit upside down but that's no biggie. The colors though of the Orpheus were a bit off. I could POSSIBLY get more screenshots by using PCSX2 by transferring over my savegames to it which has most of the Persona in the game. Including the unicorn.

I was thinking that its decompressed correctly previously,but if colors are not same as in game then something is really wrong... In header there is value 19,I think it means 19 bits per sample,or 19 bits per index,or its includes flags...

Any another screenshots will be really helpful...
## Post #21
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-13T20:14:48+00:00
- Post Title: Re: TMX file format help

Ok, emulation is a bit shaky in the 3D department but I did get Unicorn:

[Unicorn screenshot](http://img.photobucket.com/albums/v122/ShinDarkfox/Unicorn.png)

Koromaru (the dog)

[Koromaru!](http://img.photobucket.com/albums/v122/ShinDarkfox/Koromaru.png)
## Post #22
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-13T20:23:37+00:00
- Post Title: Re: TMX file format help

> Reply from Darkfox
>
> Ok, emulation is a bit shaky in the 3D department but I did get Unicorn:

Unicorn screenshot

Thank you:)

But I dont see any color difference between this picture:
[http://img230.imageshack.us/img230/6824/2pst014vt7.png](http://img230.imageshack.us/img230/6824/2pst014vt7.png)
and that yours posted above 

Maybe I'm blind
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-13T21:03:56+00:00
- Post Title: Re: TMX file format help

This may help:

[Comparison](http://img.photobucket.com/albums/v122/ShinDarkfox/UnicornComparison.png)

Your conversion is sooooo much like it, the colors look so accurate but if you look there is a smoother shading/lighting it seems on my screenshot. A thought did come to mind that Persona 3 smooths out the graphics but I'm not entirely sure.

Is that possible? That Persona 3 ingame smooths them out? This seems a bit odd to me... but... dunno.
## Post #24
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-13T21:37:09+00:00
- Post Title: Re: TMX file format help

> Reply from Darkfox
>
> This may help:

Comparison

Your conversion is sooooo much like it, the colors look so accurate but if you look there is a smoother shading/lighting it seems on my screenshot. A thought did come to mind that Persona 3 smooths out the graphics but I'm not entirely sure.

hmm really strange  I found out what you meant,there are some areas where color is darker or lighter,and on some areas are some noise pixels.

That dog image is completely out,there are many errors in my decompressed dog image,so decompressor needs to be fixed,I must find out whats "wrong" in tmx format
## Post #25
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-14T08:49:46+00:00
- Post Title: Re: TMX file format help

It is pretty close though, and in such a short time, a little more tweaking and it might be cracked yet.
## Post #26
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-08-24T20:09:38+00:00
- Post Title: Re: TMX file format help

Noticed it has been pretty quiet here, any updates or anything on the status of the TMX format?
## Post #27
- Username: Barubary
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2009 7:21 pm
- Post datetime: 2009-06-18T17:13:17+00:00
- Post Title: Re: TMX file format help

Although I am not keen on replying in a topic that is almost a year old, I figured I might be of service to some if I replied.

The reason the images above look odd, is because the order of colours in the palette is wrong. (obviously, actually)
The colours are stored in a way similar to tiled graphics; the first 8 colours are fine, but the second 8 colours are actually the third 8 colours. The third 8 colours are actually the second 8 colours, and the fourth set of 8 colours are fine again. The same behaviour would happen in tiled graphics when the tile size is 8x2. Example:

The palette on the left is the original, the one on the right is the same palette, but displayed using 8x2 tiles.

To make this post more helpful, a tool I made supports those type of palettes (albeit only recently); TiledGGD. (a tutorial can also be found behind this link)
It is a derivative of the obscure program GGD, which I think some of you will have worked with at least once or twice if you're into ripping graphics from files. One of its shortcomings was that it could not handle tiled graphics, so I decided to make my own version, which could handle tiled graphics, and more. I have recently added support for tiled palettes as well.
It also has a plug-in feature, so that when you want/need to rip from a lot of very similar files (eg: 251 TMX files ;]), you can make a Lua-plugin so that only the relevant data is displayed, and the proper settings are applied. That way, you only have to open each file, and do not need to scroll down to the desired offset to see the data you want to see.
## Post #28
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-18T18:59:45+00:00
- Post Title: Re: TMX file format help

Nice! Never mind the age of the thread. Nice work!
## Post #29
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-06-19T20:47:15+00:00
- Post Title: Re: TMX file format help

I like this GGD's interface much better. Thanks for the tool, I'll check if it displays a TMX correctly.
## Post #30
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2009-09-07T23:04:23+00:00
- Post Title: Re: TMX file format help

I played with TiledGGD this weekend, and it's awesome.

I did find a bug though: the 4bbp palette retrieved the bytes in a weird order so you never get a good picture (alpha is always replaced with blue or whatever).

Until I get off my butt and make a proper patch for Barubary I hope you don't mind my long post with some code.

If you download his code and recompile it with this region in PaletteData.cs changed (just replace the region with this one), it'll be correct:

```
                case PaletteFormat.FORMAT_4BPP:
                    for (palNo = 0; palNo < 256 && !atEnd; palNo++)
                    {
                        if (IsBigEndian)
                        {
                            fst = Next(out atEnd);
                            if (atEnd) break;
                            scn = Next(out atEnd);
                            thd = Next(out atEnd);
                            a = Next(out atEnd);
                        }
                        else
                        {
                            a = Next(out atEnd);
                            if (atEnd) break;
                            thd = Next(out atEnd);
                            scn = Next(out atEnd);
                            fst = Next(out atEnd);
                        }
                        switch (AlphaSettings.Location)
                        {
                            case AlphaLocation.START:
                                //a = Data[currIdx++]; fst = Data[currIdx++]; scn = Data[currIdx++]; thd = Data[currIdx++];
                                parsePalOrder(ref scn, ref thd, ref a, ref fst, out fullpal[palNo]);
                                break;
                            case AlphaLocation.END:
                                //fst = Data[currIdx++]; scn = Data[currIdx++]; thd = Data[currIdx++]; a = Data[currIdx++];
                                parsePalOrder(ref fst, ref scn, ref thd, ref a, out fullpal[palNo]);
                                break;
                            default: throw new Exception("Unkown exception: invalid AlphaLocation " + AlphaSettings.Location.ToString());
                        }
                        
                        //parsePalOrder(ref fst, ref scn, ref thd, ref a, out fullpal[palNo]);
                    }
                    break;
                #endregion
```


Also, here are the plugin files for easy drag/drop of the TMX files:

```
if readDWORD(0x8) == 811093332 then
	if readWORD(0x16) == 0x14 then
		format = 3; --graphics is 4 bit
		graphicsOffset = 0x80;
	else
		format = 4;
		graphicsOffset = 0x440;
	end
	
	width = readWORD(0x12);
	height = readWORD(0x14);
	bigendian = true;
	setData2(graphicsOffset,height*width/(5-format));
else
	warning = 'File is not TMX: '..readDWORD(0x8)
end

```


```
if readDWORD(0x8) == 811093332 then
	if readWORD(0x16) == 0x14 then
		format = 7; --graphics is 4 bit
		palSize = 16;
		tiled = false;
	else
		format = 7;
		palSize = 256;
		tiled = true;
	end
	
	paletteOffset = 0x40;   
	order = 'RGB';
	bigendian = true;
	alphaAtStart = false;
	ignoreAlpha = true;
	enableAlphaStrech = true;
	alphaStretch = {};
	alphaStretch[0] = 0;
	alphaStretch[1] = 128;
	tilesize = {};
	tilesize[0] = 8;
	tilesize[1] = 2;
	setData2(paletteOffset,palSize*4);
else
	warning = 'File is not TMX: '..readDWORD(0x8)
end

```


Finally, add these lines to the bindings.xml file:

```
    <Name>Atlus File (TMX)</Name>
    <FilterSet method="AND">
      <Filter type="FILENAME">TMX</Filter>
    </FilterSet>
    <Target type="LUA">Graphics_TMX.lua</Target>
  </Binding>
  <Binding type="PALETTE">
    <Name>Atlus File (TMX)</Name>
    <FilterSet method="AND">
      <Filter type="FILENAME">TMX</Filter>
    </FilterSet>
    <Target type="LUA">Palette_TMX.lua</Target>
  </Binding>

```


With all of that, you can get some nice pictures.  The files are RGBA, and without the code change it'll read it as RGAB, so you might be able to get by with just flipping the Blue channel with the Alpha in Gimp/Photoshop.

On an added note, the SPR files are very similar and have multiple TMX files inside with non-uniform sizes.  And on top of that, the BIN files have all sorts of files in them including TMX and SPR files.  And, both files are just files stacked on top of each other with a small header section--very easy to separate.

I'll end my first post with a converted TMX from Persona 3 which was looked at previously.
[temp.png](https://xentaxbackup.github.io/file/2345_temp.png)
## Post #31
- Username: Barubary
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2009 7:21 pm
- Post datetime: 2009-09-20T17:19:45+00:00
- Post Title: Re: TMX file format help

Although your version of that region looks a bit neater, it is not entirely correct. If the if-statement would read 'if(!BigEndian)', it would have been. (it seems I made the same mistake in another method though)
The color format of the TMX files is either 'ABGR' in BigEndian format, or 'RGBA' in LittleEndian format (since you read R->G->B->A if you read it per byte).

I've updated the code, but have not yet uploaded a new version of the executable.


EDIT: might as well put the adjusted plugin here as well:

```
if readDWORD(0x8) == 811093332 then
   if readWORD(0x16) == 0x14 then
      format = 7; --graphics is 4 bit
      palSize = 16;
      tiled = false;
   else
      format = 7;
      palSize = 256;
      tiled = true;
   end
   
   paletteOffset = 0x40;   
   order = 'BGR';
   bigendian = true;
   alphaAtStart = true;
   ignoreAlpha = false;
   enableAlphaStrech = true;
   alphaStretch = {};
   alphaStretch[0] = 0;
   alphaStretch[1] = 128;
   tilesize = {};
   tilesize[0] = 8;
   tilesize[1] = 2;
   setData2(paletteOffset,palSize*4);
else
   warning = 'File is not TMX: '..readDWORD(0x8)
end
```
## Post #32
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2009-09-20T18:23:18+00:00
- Post Title: Re: TMX file format help

Hah, thanks for that. I was wracking my brain wondering what was up cause I thought, no way he made an endian mistake, but I tried every option of palette order and such EXCEPT alpha at the start, because when I looked at the hex it was at the end... oh so silly of me.  I eventually just figured that instead of grabbing the bytes in chunks you'd just grab them in order since they were just single bytes, not shorts or words or whatever.

I do like your program a lot and it's code it pretty easy to understand so I've been teaching myself C# through emulating your design and making a RMD file inspector (not viewer yet since adding a 3D context seems a little more involved at the moment.).

RMD files from the Persona games have TMX file data embedded into them but they are swizzled.  I hacked in some ugly unswizzle code into TGGD, here it is if you are interested (this is for PS2, and I believe it is slightly different for other systems):

```
                    byte[] d1 = new byte[nNecessBytes];
                    byte[] d2 = new byte[nNecessBytes];
                    for (int i = 0; i < nNecessBytes && !atEnd; i++)
                    {
                        d1[i] = Next(out atEnd);
                        d2[i] = 0;
                    }

                    uint w = Width;
                    uint h = Height;

                    for (uint y = 0; y < h; y++)
                    {
                        for (uint x = 0; x < w; x++)
                        {
                            uint block_location = (uint)((y & (~0xf)) * w + (x & (~0xf)) * 2);
                            uint swap_selector = (uint)((((y + 2) >> 2) & 0x1) * 4);
                            uint posY = (uint)((((y & (~3)) >> 1) + (y & 1)) & 0x7);
                            uint column_location = (uint)(posY * w * 2 + ((x + swap_selector) & 0x7) * 4);

                            uint byte_num = ((y >> 1) & 1) + ((x >> 2) & 2);     // 0,1,2,3

                            d2[y * w + x] = d1[block_location + column_location + byte_num];
                        }
                    }

                    for (int i = 0; i < nNecessBytes; i++)
                    {
                        *(bmptr++) = palette[d2[i]];
                    }
                    #endregion
```


I put this into the linear 8BPP section because that's what I use--also added a bool for swizzling since you can't swizzle non-powers-of-two. (Source is [Sparky's code](http://playstation2-linux.com/download/p2lsd/sparkys_swizzle_code.html))
## Post #33
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-03T19:16:02+00:00
- Post Title: Re: TMX file format help

This topic was -extremely- helpful for getting the images out of Persona PS2 games. I am trying to take this one step further, but have hit a brick wall. I am hoping someone here can figure out what to do!

I have found on a Persona game disc, a series of .BIN files. I opened one in a text editor, and discovered the first bit of text says it contains a .TMX file. Using TiledGGD I could not initially make sense of the file. I then opened a .TMX file, and immediately opened a .BIN file in the same window, and got a character image in a somewhat muddled fashion. I didn't load the palette from the .BIN, for the result examples I am posting.

The file header in the .BIN is not exactly like the .TMX, especially given the .BIN specifies a .TMX file name before the TMX data. I have been looking for a way to either extract the file from the BIN, edit the bin to match the TMX format, or formulate a settings combination that will let TiledGGD use the .BIN directly.

Attached are some example files I have been using.
-The .TMX file, I load before the .BIN, so it carries over the image settings and lets me see what the image roughly is.
- Target1&2 are .BIN files containing .TMX data.
- Result1&2 are the muddled images I get out of TiledGGD from the respective .BINs

Here are 2 reference images for the Target .BINs:
[http://megamitensei.wikia.com/wiki/File ... nistP3.jpg](http://megamitensei.wikia.com/wiki/File:ProtagonistP3.jpg)
[http://megamitensei.wikia.com/wiki/File ... ssions.jpg](http://megamitensei.wikia.com/wiki/File:TheJourney-AegisExpressions.jpg)

I hope someone has some ideas, I'm stumped.
[Resources.zip](https://xentaxbackup.github.io/file/3005_Resources.zip)
## Post #34
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-05T02:11:00+00:00
- Post Title: Re: TMX file format help

I didn't look at the bin files yet, but I did look at the tmx you provided.  The first part is the main image of Aigis (512x512) and the seconded small image (512x64) is just her eye's shut for when she blinks.

The format is slightly different than the TMX file in that either your exporter or the file replaces nulls (0x00) with spaces (0x20) and so the GDD won't read it nicely... since it will try to make a huge image.  This screws up the actual image as well because the 0x00's used as indexes into the palette are now 0x20 instead of 0x00. I got some nice pictures from it though, only the alpha channel was confused (never got to full transparency).

Also, some of the TMX header got clipped off--there are 8 bytes before TMX that GDD looks for to know it's a proper TMX file.  Also, the end of the TMX file you gave might be missing too, I'm not sure.

**after looking at the bins

The bins do hold TMX files, in this format: Name of TMX file, padding, size of TMX file, TMX file, Name of next TMX file, ...

Looks like you copied the text side of the HEX viewer maybe to get your TMX file before, make sure to use the binary side (those spaces are what are hurting you).  The TMX file name probably uses the max length char string of 252 so you can use that to find your files better.  BINs can hold other file types as well, so maybe just searching for the TMX header will be enough.
## Post #35
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-06T04:49:48+00:00
- Post Title: Re: TMX file format help

Thank you for the fast reply!  

About the TMX file, I messed up and that wasn't the one I meant to post. I was going to give another clean TMX from the game, but uploaded an edited and renamed BIN instead. Thankfully that mistake lead to additional insight!

With your help I made significant progress. I've been able to pull the main character images from the BINs. I've found that the padding between file name and the start of the TMX proper ends at a hex value of 02 (being the first value of the tmx file.) However, when I apply this rule to the 2nd embedded file (The closed eye portion), it won't work.

What I've done so far:
- Used a hex editor to delete all the values prior to the 2nd file's file name.
-- Found 0x02 and removed the padding+filename from before it. Saved as a new .TMX
-- Loaded new tmx image and found a scattered mess.(A small block of black with red and green dots, most of the palette looks like an old tv test pattern instead of the browns and blacks the character palette should have)
----Opened the first image from the BIN, then opened the closed-eye TMX, which lets me see the image, but there is a couple rows of non-sense and the image is more pixelated than it should be. I -think- what is happening is the secondary TMX uses the same palette as the first, or my method is somehow corrupting the palette data.

You'd think a degree in programming would be sufficient, but we never really covered graphics.
## Post #36
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-06T18:19:58+00:00
- Post Title: Re: TMX file format help

Are you talking about the same bin files you linked last time?

I'm pretty sure they are separate files because the 1st palette doesn't work well with the 2nd picture.

Target2.bin :

First TMX starts @ 0x100 (0x100)
The 2nd int32 into the TMX is the size of the file (0x40440), so 0x100+that number is the 2nd file in the bin location. 
Second TMX starts @ 0x100 + the end of the First (0x40540) = (0x40640)

Something that might be useful would be to make a BIN extractor that would take a bin and pull out all the files in them for you to look at better.  Could have an option to put them in folders as well if ya want. There are a lot of BIN files in the archives and you might find something useful.
## Post #37
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-06T19:03:33+00:00
- Post Title: Re: TMX file format help

Yeah, it is the same files I am talking about.

One of the issues (the muddled mess with totally incorrect palette), was just a late night oversight. Apparently with the code supplied in this thread, GDD only applies the correct TMX settings if the file extension is in all caps. The files I was generating were lowercase, so I was getting the default settings. Simple enough to solve.

I'm not sure about the other issue, because the nearly correct results I got was from a manually hex-edited file. I was pretty careful about integrity. I probably found some new and impressive way to mess up the file though. I'll try again!

Since there are so many .BINs on the disc, I am writing a small C++ program to extract the files automatically.

How could you tell that the 2nd int was the file length? Does that come with knowing graphic file formats, or well educated guessing, etc?
## Post #38
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-06T19:19:36+00:00
- Post Title: Re: TMX file format help

I guess it's mostly from experience in looking at files. Most file formats have some sort of data size or file size number included as an integrity check.  I use XVI32 and it has a handy data inspector that tells you what the values at the cursor are in different formats--so I just start at the beginning of the file and move back and forth with the arrow keys to see numbers that make sense. 

Yeah, I found the case sensitivity of the bindings to be a little annoying as well.  You can edit the code to not send in the regex string in as case sensitive or just add a new binding with tmx as well as TMX.

Glad you are making progress, let us know what you get and do with all this stuff
## Post #39
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-07T06:50:53+00:00
- Post Title: Re: TMX file format help

Yeah, for now I am using the case sensitivity to my advantage, as any time I have a file I want to test, I do that 'Load a .TMX, then load a .tmx to see if I am roughly on the right track' test. For simplicity sake, I'll refer to .TMX as the files that are properly loaded with settings applied, and .tmx as ones that load, but use a previously loaded .TMX to properly display. Make sense?

With your significant help I've gotten quite close to cracking this thing. I now have a small program that can find and extract TMX files from the .BIN with a fair amount of accuracy. Once it is complete, I will post the source file here for others.

TMX observations:
File starts with 0x02000000, then the file size, as you stated, such as 0x40840000, the next 4 byte block spells out TMX0.
After that there are a few bytes I am not sure about. They seem to be a padding of 4 bytes (0x00 each), then two bytes that together equal 1 (possibly the 'Skip Size' as read by GGD?). The following 2 byte group appears to be the width of the image (usually 0x0002 -> 512), followed by another 2 bytes for the height.

Attached is progress I have made with the Target2.BIN of Aigis.
Inside is:
- i_bust_03_b2.TMX - Aigis's body shot as ripped by my application.
- i_me_03_b2.TMX - Aigis's closed eyes frame as ripped by my application.
- manualEdit.tmx - Aigis's closed eyes file, but I used a hex editor and did it myself. This file is byte for byte the same as the other version, but a bit longer at the end, as my application removes the padding.
- aigis_head.png - shows the current progress on the eyes closed image, which is nearly correct.

I found that on the full body TMX, the previously mentioned height and width values are both 512. When I looked at the closed eye TMX, they are 512 and 64. However, it does not appear that GGD is reading it right, or respecting the image size. If the closed-eye TMX is loaded first, it is loaded as a 64x64 image, and the palette looks incomplete.

If the eye TMX is loaded, then the body TMX, then the eye tmx, we get the .png I included, which is a 512x512 image with roughly the correct results. Ideally, there must be a way to get the image loaded at first try in the right 512x64 size, but I think I am done for tonight.

As for why I am working so hard to do this, it is for my users!
I have written a Persona fusion calculator / database / assistant program for Persona 3 and 4 called 'Igor's Index'
[The project page is here](http://tiredtracks.is-a-geek.com:8080/_Projects/Igor/). 
It lets you look at all the vital info on any persona, predicts fusions, and lets you search for persona based on your specific needs. If you are a player, as I think you are given your knowledge of Aigis, you may want to check it out. Totally free of charge, of course.

By popular demand, I (with the aid of this forum topic) managed to include images of each Persona on their profile. An update I am ever so slowly working on, involves the party members, so I wanted to get clean images of each of them, and found they were trapped in these .BIN files. With your additional help, I've now got the means to extract the profile shots of each party member and social link. Frankly, I could stop right there, but now I am personally curious about getting the closed eye frames, or possibly just doing it for completest sake. Curiosity may have killed the cat, but it just sucks away my spare time.  When I was younger I wanted to be in game design, so seeing how things are packaged on a professional disc like this is also kind of fun.
[progress_results.zip](https://xentaxbackup.github.io/file/3014_progress_results.zip)
## Post #40
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-07T17:28:25+00:00
- Post Title: Re: TMX file format help

That's a pretty sweet program you got there 

I'm able to get good pictures from all of your TMX's btw, so I'm not sure what's up with your weird sizes.  Are your plugin files exactly like the ones posted in this thread? Make sure you use the corrected palette lua file that Barubary gave.  The png file looks exactly what I get if I load the 64 pixel tall image in as generic data instead of specific data btw.  The garbage on the top is the palette.

As for the structure of the header, I don't remember all of my work on that but here is the gist:

```
	int32		startUnknown;	//0x02000000
	int32		tmxSize; 	 	//size of file including this header
	char[4] 	magicTag; 		// "TMX0"
	int32		unknown;  		//padding 0
	int16		unknown;  		//non zero, may be different version value
	int16		tmxWidth;
	int16		tmxHeight;
	int32		tmxFlags; 		//so far only discerned 2 formats
	int16		tmxEnd;   		//0x00FF 
	char[36]	reserved; 		//nulls
}; //0x40 bytes
```


Somewhere in there is a versioning value--I saw that it was different for P3, FES and P4, but I don't remember what was different anymore.
## Post #41
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-07T18:37:04+00:00
- Post Title: Re: TMX file format help

....... Wow.
Lessons:
- Don't work on something like this all night and expect no mistakes.
- Don't edit files when you have no clue what you are doing.

Thanks again bbarcher. The problem this time was NOT with my application. A few days ago I made a new set of .lua files for .tmx format, thinking I could experiment and tweak settings there if need be (without modifying the .TMX binding). Somehow, I brilliantly managed to edit the Graphics_TMX.lua file to 
width = readWORD(0x14);, where the value is supposed to be 0x12.  D'oh. No wonder it wasn't reading correctly.

Also, I somehow never thought of making a struct to deal with that data. I guess I've been approaching this problem far too linearly. *kneels* I have much to learn.

Everything is now reading correctly! I will provide the source code soon, once I've cleaned up my comments and such.
## Post #42
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-08T02:00:31+00:00
- Post Title: Re: TMX file format help

Alright, the code seems to be ready!
It is a simple batch application via the command line (or drag and drop?). I just compiled it, put it in the directory in question and used the command:
name_of_executable *.BIN
, and the program did the rest.
For ease of use, I made it convert the file extension to all caps, but that is easy enough to comment out if you want otherwise.

This has me wondering, does TiledGGD have a batch mode? Some command line arguments to make it translate a whole directory of .TMX to .png? That would save me a heck of a lot of time and effort. I already played around with it, and googled to no results.
[convertBin.zip](https://xentaxbackup.github.io/file/3018_convertBin.zip)
## Post #43
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-08T02:26:21+00:00
- Post Title: Re: TMX file format help

Pretty sure it doesn't, but the source is available, I say flex some more of those programming muscles and add it in.  I'm sure the owner (Barubary) would be fine with the addition 

As for the extractor, I've got a request/suggestion: Pull the first 252 bytes for the file name and then the 253-256 bytes for the file size and extract that file instead of going into the TMX header.  This way you can extract any file from a BIN.  There are a lot more files that are stored in BIN's than just TMX's, one of them being a SPR file that you can use to get more image info out of.  Also, I'm currently working on a model extractor and there are plenty of those hanging around in BIN's as well.  Be pretty cool to add to your program an animating persona eh?
## Post #44
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-08T04:23:45+00:00
- Post Title: Re: TMX file format help

Good points!

I was so focused in on the problem that it wasn't generic enough for other possible purposes. I've made the suggested change and tested it on a few tmx-bins. Few issues I found is if the filename is not stated, the extraction probably will fail for that BIN, and if the filename includes a directory path, if the directory doesn't exist the files won't be written. Just to be safe, have a 'data' subdirectory, as thats the only one I've seen. I'd rather not use non-standard libraries to fix the directory issue, and it doesn't appear possible in standard C++ from my quick glance on google.

I guess I will take a look at GGD, see what I can do. The problems just keep stacking up!  But it is this, or manually saving some 900 images.

As for the models, I'm not that interested in them....yet, at least. I personally prefer sprites over polygons, and the still images seem to have satisfied my users. It is certainly a possibility for the future though. I wish you luck on the modeling though, and would be interested in seeing the finished app.
[convertBin2.zip](https://xentaxbackup.github.io/file/3019_convertBin2.zip)
## Post #45
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-08T09:47:55+00:00
- Post Title: Re: TMX file format help

OK, you got me off my lazy butt.  I modified your code to just search for the TMX0 string and then pull out the TMX files from any file you give it.  As an added bonus/spammer, it'll convert it to a 32b BMP file as well.  Too bad windows ignores the alpha channel, I had to get a trialware app to view it to make sure it was coming out correctly.  I may change this to output a TGA later, I dunno.

I didn't try this with every file type, but I think it should do the trick.  For kicks I dropped the BTL.CVM (~300MB file) from Persona 4 onto it and got 1713 tmx/bmps.  I think only a few of them are swizzled so they look like junk.

*only supports 4/8bit TMX files atm, and I know there are 1/2/16/24/32bit versions out there somewhere, just have to find them and add a check*

**uses a locally global counter for unknown## filenaming, so after each drag/drop I'd move those files somewhere else or just drag all the files you want to search at the same time**

***related to that, if there are two files with the same name... they will be overwritten by any later extraction***
[extractTmx.zip](https://xentaxbackup.github.io/file/3020_extractTmx.zip)
## Post #46
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-08T16:30:16+00:00
- Post Title: Re: TMX file format help

Holy ****!  *Totally outclassed* Maybe I should rip up that previously mentioned degree in programming.

I wonder what social link I need to max to summon you at will!  

Edit: Now I wonder, is .bmp the best format to save as? These tmx files have a lot of transparency in them after all. I guess I'll have to actually run the prog and see first.
## Post #47
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-08T19:03:22+00:00
- Post Title: Re: TMX file format help

Nope, BMP is the worst 

But, it is the easiest.  TGA should be just as easy, but since I didn't have any examples around to test with and I was unsure if it was supported by default I just used BMP.  GIMP and other graphics programs should be able to batch convert the BMPs to something else as well--ImageMagick comes to mind as a command line option.

What format do you use in your tool?  Could probably set that up easily.
## Post #48
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-08T20:02:22+00:00
- Post Title: Re: TMX file format help

I've just been using the .png format.

I'm puttering on the code to do it, using a png made by GGD and a png reference manual. I'm finding it a bit of a headache,  but no effort, no reward!
## Post #49
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-09T00:07:53+00:00
- Post Title: Re: TMX file format help

Well, I think .png is a bit out of my grasp. I'll be putting it on the list of things I don't really need to know but would like to.

Turns out that the .BMP files created by bbrcher's version of the extractor does create bitmaps that do not have transparency. However, GIMP (horray for linux!) still reads those bytes as transparent. Since I will likely rename the files, I'll just use GIMP to do so, and save the .bmp as .png to let the transparency shine through! Furthermore, GIMP already has a batch mode, so with a little bit more research I think it will easily batch convert bmp to png. 

I am still interested in seeing other solutions, but I find myself fairly frustrated with all the hex editing and whatnot the last few days.
## Post #50
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-09T00:14:52+00:00
- Post Title: Re: TMX file format help

I did state that the transparency is there, just not supported by most programs--24b BMP's are the norm, not 32b.  GIMP will see it but windows will not for example.  If you figure out how to make it so it's more compatible, let me know though ;P
## Post #51
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-09T03:02:09+00:00
- Post Title: Re: TMX file format help

Yeah you totally did mention that..... I don't know how I managed to miss it. I think I assumed you meant GIMP could make it a png, but not necessarily maintain the transparency when the origin file was .bmp. Guess I'm just in a rush. I'm testing a small script for batching GIMP bmp->png, hopefully this thing will be 'solved' soon.
## Post #52
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-09T05:20:34+00:00
- Post Title: Re: TMX file format help

Don't burn yourself out.  This is suppose to be fun
## Post #53
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-09T06:12:19+00:00
- Post Title: Re: TMX file format help

It is fun! Well, parts of it. I like programming until I get to a problem that is overwhelming and I am unsure of where to start or how to break it down into manageable parts. I've always been a bit high-octane regardless.

I've now finished the GIMP script! It is based off a similar script I found as an example, but this actually does what I wanted. :-p Technically it will convert any GIMP compatible format into .png. Thankfully I learned LISP and Scheme in college. For once I got to use it without wanting to eviscerate something.   

```
;; any2pngbatch.scm
;; - By PersonaRipper, XaNTeX forums and http://tiredtracks.is-a-geek.com:8080/
;;
;;	Used to run GIMP in batch mode and convert all .BMP(or other 
;;		graphic formats) to .png format.
;;	To use:
;;		Place this file in gimp's script folder and run the following command
;;			in the desired folder.
;;	gimp -i -b '(any2pngbatch "*.BMP")' -b '(gimp-quit 0)'
;;
;; Old files not removed. New files are the old filename with .png appended.
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
(define (any2pngbatch pattern)
	(let* 
		((filelist (cadr (file-glob pattern 1)))) ;Get the file list.
		(while (not (null? filelist)) ;Iterate the file list
			(let* ( ; Set up variables for this iteration.
					(filename (car filelist))
					; Read the image data in.
					(image (car (gimp-file-load RUN-NONINTERACTIVE 
													filename filename)))
					; Handle to the editable image
					(drawable (car (gimp-image-get-active-layer image)))
					(outputfile (string-append filename ".png")))
				; Write out the new file.
				(file-png-save RUN-NONINTERACTIVE 
								image drawable 
								outputfile outputfile 0 9 0 0 0 0 0)
				(gimp-image-delete image))
			; Move to the next element in the list.
			(set! filelist (cdr filelist)))))
```


I think we may call that a wrap. >.> I've enjoyed the collaboration here. It WAS fun afterall.
## Post #54
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-09T07:37:36+00:00
- Post Title: Re: TMX file format help

Looks good, glad I could help
## Post #55
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-09T20:46:20+00:00
- Post Title: Re: TMX file format help

One last thing I forgot to mention. In bbrcher's extractTmx.cpp, I could not get it to compile unedited. I got the error:
extractTmx.cpp: In function ‘void convertTMXtoBMP(std::ifstream&, char*)’:
extractTmx.cpp:104: error: ‘memcpy’ was not declared in this scope
extractTmx.cpp:147: error: ‘memcpy’ was not declared in this scope

Which means I needed to add the line
#include <cstring>
near the top of the file.

I'm sure different compilers handle it differently, but g++ needed this extra line.
## Post #56
- Username: bbrcher
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 08, 2009 2:27 am
- Post datetime: 2010-05-10T20:10:59+00:00
- Post Title: Re: TMX file format help

Not sure how I got away with that
## Post #57
- Username: PersonaRipper
- Rank: n00b
- Number of posts: 14
- Joined date: Tue May 04, 2010 1:07 am
- Post datetime: 2010-05-13T20:52:49+00:00
- Post Title: Re: TMX file format help

No worries, like I said: different compilers handle these things differently. Some enforce as many rules as they can, others are more lax. Maybe your compiler considers cstrings as a required library and always imports it, or imports it if it finds it is required.

It just happens I use one of the stricter compilers it seems!
## Post #58
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-05-20T17:49:04+00:00
- Post Title: Re: TMX file format help

See below posts for later versions!
Update: Okay so it was admittedly stupid to leave a bug in that would take 5 minutes to fix, whether I'm interested in the project or not. So I fixed it and it will no longer hang if there are no input files. Also cleaned the code a tiny bit, removed some unused variable declarations and merged an if statement.

Hey everyone~ I've been monitoring this topic for a while, and it took forever to get my account activated but I have something to add. Thanks to help from PersonaRipper (who I contacted via email) I made a somewhat useful application called TMX Explorer which I will release in hopes it is useful to somebody. About it:

Features:
Written in FreeBASIC
Let's you "Explore" *.tmx and *.bin files visually, so you can see what you are getting before you extract it
Exports directly to PNG with transparency

Limitations:
Probably slower than it should be, but you really shouldn't notice it
Code is not terribly great, I am a novice after all
Operates only on the directory it is executed from.

License:
Do (almost) whatever you want license
Source is included, feel free to modify it and all that, please don't remove any contributors credit though
Don't sell it
Don't use it for evil purposes
Don't try to eat it

Credits:
PersonaRipper for his help with some programming problems and providing me the source to his and bbrchers extractors which I converted to FreeBASIC code for large parts of the program
Simon Nash for FreeBASIC PNG Library and Jean-loup Gailly and Mark Adler for zlib library

Obligatory screenshot:


See below posts for later versions!
## Post #59
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-06-04T00:02:20+00:00
- Post Title: Re: TMX file format help

New version available in next post!
I made a new version of the TMX explorer.

New Stuff:

You can change directories. The interface is certainly not standard, but it does the job.
File list is no longer generated via a command line "dir *.tmx > tempfile" type command, it is done with internal Freebasic commands
Application no longer closes if no files is in its directory, instead it redirects to the change directory interface.
Application no longer hangs on 0 length files or files with correct extension but no TMX within.

New Thanks:

Thanks to bcohio2001 @ Freebasic forums for directory/file reading code

Notes:

Directory and file code is not commented in the source, aside from the key reading and array writing, I've little idea how the FreeBasic DIR command works with the specified parameters. I just got the code from bcohio2001 hehe.

Hope you find it useful!

~Blyss
## Post #60
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-07-06T18:42:51+00:00
- Post Title: Re: TMX file format help

All new versions available at:
[viewtopic.php?f=32&t=4830](http://forum.xentax.com/viewtopic.php?f=32&t=4830)
Tinkered around with the TMX Explorer this morning and updated some stuff.

TMX Explorer 0.7 changes:

Edited directory reading code, file list was incorrect because listoffiles() array was not cleared properly.
Changed directory navigation control, you can no longer select "." and the cursor defaults to ".."
Changed the navigation through bin files, you can now only go through as many TMX as there actually are, not past.
The "deepness" navigation keys no longer work when viewing a straight TMX.
Changed the command "Imagedestroy(curimg)" to "if curimg then imagedestroy(curimg)" to avoid trying to clear memory that was not allocated. I don't think FreeBasic allows that to happen anyway but this is safer.



Update:

Just an update on TMX Explorer compatibility:

Confirmed working with:
Persona 3: FES (confirmed by me)
Persona 3 Portable (confirmed by taleds)
Persona 4 (confirmed by me)

Also a really quick tutorial for anyone who is wondering how you actually get to the TMX/BIN type files.

Note that this tutorial is valid for Persona 3, Persona 3: FES and Persona 4 for Playstation 2. Other games/platforms may or may not be laid out in this manner.

Pop your game disc in your optical drive. Get IsoBuster ---> [http://www.isobuster.com/](http://www.isobuster.com/) if you don't have it and fire it up. Go to File --> Open Image File. A dialog box will pop up. In the drop down menu on the right where you can choose a file type pick "All Files (*.*)" Now navigate to your optical drive. You'll see a few files, the ones you are interested in have the extension CVM. All of the game files are within these CVM, which are really just some kind of disc image file with a different extension.  For your reference, most of the graphics files are in "DATA.CVM" and "BTL.CVM" in Persona 3/4. If your just playing around and not looking for anything specific, go with "DATA.CVM" Whatever you pick, when you confirm and open it, a directory structure will appear in the right pane of IsoBuster. Now you can just drag and drop whatever directory you want from the window to your desktop or a folder or whatever and IsoBuster will extract it. Again for the record, you will find most of the character portraits in the "BUSTUP" subdirectory of the "DATA.CVM" Anyway, that's how you can get at the stuff.

Request:
So far the TMX Explorer has been tested with Persona 3: FES, Persona 3 Portable and Persona 4. If you own another game that uses the TMX format and try this, let me know if it works or not at my email address in the "about" section of the program, or through a PM please. 

~Blyss
## Post #61
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-08-01T01:31:02+00:00
- Post Title: Re: TMX file format help

For your reference, all further releases of the TMX explorer will be released in this thread:
[viewtopic.php?f=32&t=4830](http://forum.xentax.com/viewtopic.php?f=32&t=4830)
As of this post, I have released 0.8, so if you want the new version, then check out the new thread!

~Blyss
