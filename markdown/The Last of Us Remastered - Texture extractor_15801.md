## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-29T08:02:47+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

Hello!

finally I have a decrypted backup of TLOU Remastered and right now I want to extract some textures.

the problem is the current tools available for extract textures from ps3 versions doesn't work in the ps4 version and is very difficult to locate a certain texture using texturefinder because everything is swizzled.

the swizzled method is not a problem, I solved the problem thanks to m0xf but I want to extract all textures classified and with respective names like the ps3 versions.

there are some big files that contains all textures of a respective stage in game. This files only contain textures with the same structure that the following samples.

so, here are some samples with models if anyone want to take a look, maybe someone can create a tool or can explain me the logic about how to find a start address of a specific texture.

[http://www.mediafire.com/file/53w3n68di ... ctor50.rar](http://www.mediafire.com/file/53w3n68dis74zs9/commonactor50.rar)

same files from ps3 for compare.

[http://www.mediafire.com/file/64hck7cgj ... el-ps3.rar](http://www.mediafire.com/file/64hck7cgjhmzuk6/Joel-ps3.rar)

here is a big file

[http://www.mediafire.com/file/c5jbys1ak ... -tstrm.rar](http://www.mediafire.com/file/c5jbys1aku4dgk1/common-tstrm.rar)

NOTE: YES, ALL MODELS ARE DECOMPRESSED !
## Post #2
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-01-30T04:27:08+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

You mad genius, Luxox! Hopefully someone can help you out with these!
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-30T06:52:40+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> Reply from trexjones
>
> You mad genius, Luxox! Hopefully someone can help you out with these!

thanks, I hope too because I can't understand the logic in files for locate a texture.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-31T08:59:47+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> the problem is the current tools available for extract textures from ps3 versions doesn't work in the ps4 version
what tools you use for the PS3 version? is there source available for it?

in the joel-head-destroyed-tstrm.pak sample it look like texture or pallete data might start at 0xbcde0
near "RAW_DATA" and this is also true in the PS3 sample of almost the same name at 0x4dac0.
these files are a mess in my eyes, you can see the pattern changes which might indicate a new
texture but i don't see an obvious way to split it to files   
maybe aluigi could have better luck
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-01-31T14:52:33+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

Hi,

after being contacted by luxox, I updated my last of us ps3 texture editor to support ps4 files. It is incomplete but I still wanted to share it.

Preview is only supported for DXT1 compressed textures but you can still export other textures to view them with gimp/photoshop etc.

There are 4 export options : 

1) DDS Export :
Probably the best option for easy exporting. It tries to find the compression type of the texture data, uses the unswizzle algortihm (by m0xf) on the data and exports it with a proper header. After that you have to open the exported images with photoshop/gimp. The problem is that the program sometimes finds the compression type wrong and the resulting image might be garbage. I am trying to improve this. Still it is the easiest method.

2) Raw Data :
Just exports the raw texture data from the file. You need to add the header yourself and unswizzle the data.

3) Raw Data + Header
Raw data with a header automatically added by the program. Still the header might be wrong and you need to unswizzle the data yourself.

4) PNG
Only works for DXT1 compressed textures. It is basically the full scale version of the preview image.

Also I added a no preview version of the tool to load bigger files faster. It unswizzles the data during export and only for dds export. It should be better if you are interested in exporting raw data.

Program Screenshot : 


Some textures from the common file : 


Download : 

Huge thanks to luxox18 and m0xf.

Edit : I removed the preview version, it makes loading times longer and not really useful. Just select the dds export and open exported files with gimp.
[TextureEditor.rar](https://xentaxbackup.github.io/file/12585_TextureEditor.rar)
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2017-01-31T15:36:17+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

is there any way to export models as well ?
## Post #7
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-01-31T23:52:54+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> Reply from michalss
>
> is there any way to export models as well ?

for the moment only with hex2obj

[http://www.mediafire.com/file/z5zl54f5y ... ctor50.rar](http://www.mediafire.com/file/z5zl54f5yi9mmet/world-tommys-damactor50.rar)
## Post #8
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-19T01:25:15+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

Can you explain how you decrypted the PS4 game? Because so far what I see is nobody has figured out how to do that for the PFS blocks, only the RSA blocks.
## Post #9
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-02-20T22:03:40+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> Reply from volfin
>
> Can you explain how you decrypted the PS4 game? Because so far what I see is nobody has figured out how to do that for the PFS blocks, only the RSA blocks.

check your pm
## Post #10
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-27T07:39:55+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

I'm having trouble opening up the normals exporting as DDS files, and tried both gimp and photoshop. Is there something I'm missing or a specific version or plug in I should have? The other textures work great, just these ones are tripping me up a bit. Anyone able to take a look at these?

[https://mega.nz/#!DYZgTLKK!X-dsOXlM9oXs ... lf4hLtJ-8Y](https://mega.nz/#!DYZgTLKK!X-dsOXlM9oXsxWoIPSQIRAdtJGQFvg5Qslf4hLtJ-8Y)
[https://mega.nz/#!iUBmDRBI!_6GFcOhndtLl ... eEpn66nBRs](https://mega.nz/#!iUBmDRBI!_6GFcOhndtLloeNMDFAtq08bsTgPD-sGieEpn66nBRs)
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-03-27T10:26:18+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> Reply from trexjones
>
> I'm having trouble opening up the normals exporting as DDS files, and tried both gimp and photoshop

Are you using the latest version? I updated the program on 9th of March. 

If yes, from what file did you extract the textures?
## Post #12
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2017-03-28T05:43:05+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> Reply from trexjones
>
> I'm having trouble opening up the normals exporting as DDS files

in this case use the latest version of the tool, but in the future if you have problems with BC7 or BC5 textures use noesis
## Post #13
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-03-28T10:47:48+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

Just sat down with it then and it works perfectly! Stupidly I did not remember to put the new texture tool in until you guys mentioned it!  Sorry for the hassle!
## Post #14
- Username: Xeeynamo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jan 07, 2011 6:25 pm
- Post datetime: 2017-03-31T19:49:19+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

> Reply from luxox18
>
> volfin wrote:Can you explain how you decrypted the PS4 game? Because so far what I see is nobody has figured out how to do that for the PFS blocks, only the RSA blocks.

check your pm

I would like to know how to do that too.
## Post #15
- Username: smasher248
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 14, 2015 9:52 am
- Post datetime: 2018-02-10T14:20:52+00:00
- Post Title: The Last of Us Remastered - Texture extractor?

Is there no way to repack them so I can have modified textures like the ps3 version?
