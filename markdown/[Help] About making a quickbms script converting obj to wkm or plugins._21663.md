## Post #1
- Username: Yukino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 20, 2020 11:49 pm
- Post datetime: 2020-01-25T15:55:20+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

Now I can convert wkm file of Romance of the Three Kingdoms 11 to obj file. But I cannot do it vice-versa. So, I want to request you make quickbms script converting obj to wkm or 3DS Max plugins. I upload involved files here and please refer to it. One script is made by Chinese, but I didn't understand why he attaches '.dec' extension. I spent days agonizing over whether to open it, but didn't get accomplishment. So I try to make a script directly, but also didn't do it. I would appreciate if you help me.
[Files.zip](https://xentaxbackup.github.io/file/17418_Files.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-25T17:44:03+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

> Reply from Yukino ↑Sat Jan 25, 2020 11:55 pm at Sat Jan 25, 2020 11:55 pm
>
> Now I can convert wkm file of Romance of the Three Kingdoms 11 to obj file.How exactly?

(I tried hex2obj, view link in my sig):



0000037b-wkm.png (34.18 KiB) Viewed 89 times



> But I cannot do it vice-versa.It's very hard - you need a complete format analysis for such.
(Search for threads where an obj to any_3D_format conversion is done - you won't find too many. There's reasons, why.)

> One script is made by Chinese, but I didn't understand why he attaches '.dec' extension. I spent days agonizing over whether to open it, but didn't get accomplishment.There's filexor in it - dec stands for "decoded" I guess.

> So I try to make a script directly, but also didn't do it. I would appreciate if you help me.wkm.txt? Uncomplete script - what is the input file?

btw: quickbms is very good for decompressing and vice versa. But there's better means to handle 3D data. Just my 2 cents.
## Post #3
- Username: Yukino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 20, 2020 11:49 pm
- Post datetime: 2020-01-26T03:17:27+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

> How exactly?
I use metasequoia plugins. But as I said, it cannot convert obj to wkm normally. 

> It's very hard - you need a complete format analysis for such.
>
> (Search for threads where an obj to any_3D_format conversion is done - you won't find too many. There's reasons, why.)
Does your mention means I need a search for thread? In fact, I don't know what the search word is.

> There's filexor in it - dec stands for "decoded" I guess.
It is right supposition I think. But I also don't know identity of decoded file.

> wkm.txt? Uncomplete script - what is the input file?
The input file is wkm, but the script purpose is to uses reimport.bat function.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-26T07:58:06+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

> Reply from Yukino ↑Sun Jan 26, 2020 11:17 am at Sun Jan 26, 2020 11:17 am
>
> Does your mention means I need a search for thread? In fact, I don't know what the search word is.No. The mention just should illustrate that chances are low for an obj_2_whateverformat converter.
As I wrote you need to analyse the wkm format. Completely. That is you need to understand the purpose of each byte in the .wkm file. 

```
get ENTIREOFFSET long
get HEADERLENGTH long
get null longlong
get UNK1 0x18
get UNK2 long
get HDTBLOFFSET long 
get UNK4 long
get ENDHDTBLOFFSET long
get UNK6 long
get UNK7 long
get FILENUM long
get UNK8 long
```
I'm not sure whether this is correct so far (see below). Where do you have it from?

> The input file is wkm, but the script purpose is to uses reimport.bat function.
This wkm.txt script doesn't make much sense to me (output with 0000037b.wkm):
headerlen, HDtablePffs, EndHDtableOffs -> 80, 1078057020, -784178799
file count, tablepos -> -1342177280, 61
And to be honest I've never heard of  someone using the quickbms reimport feature for a 3D format.

The -r parameter for quickbms is intended for
3) Reimporting the extracted files (see quickbms.txt)

It's working as a packer then. (I'd be surprised if you could use it as a 3D format converter.  )

----------

> But I also don't know identity of decoded file.That wkm.bms script needs an xor encoded input file. (If you don't have any you don't need it.)
## Post #5
- Username: Yukino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 20, 2020 11:49 pm
- Post datetime: 2020-01-26T12:56:12+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

> This wkm.txt script doesn't make much sense to me (output with 0000037b.wkm):
>
> headerlen, HDtablePffs, EndHDtableOffs -> 80, 1078057020, -784178799
>
> file count, tablepos -> -1342177280, 61
>
> And to be honest I've never heard of someone using the quickbms reimport feature for a 3D format.
>
> 
>
> The -r parameter for quickbms is intended for
>
> 3) Reimporting the extracted files (see quickbms.txt)
>
> 
>
> It's working as a packer then. (I'd be surprised if you could use it as a 3D format converter.  )
If so, should I use the wkm import/export 3D model software plugins? I even saw wkm as a kind of compressed file. That's why I wrote wkm.txt. But if you seem that is not right way to convert obj to wkm, I'll convert obj to wkm using 3DS MAX plugin. However, I have not known how to make 3DS MAX plugin. In fact, I couldn't analyse wkm format completely. So my script wkm.txt is also wrong about many parts. However, since you said the analysis is difficult, I don't think I can easily ask for an analysis. I'm really sorry, but could you help me?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-26T15:10:04+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

> Reply from Yukino ↑Sun Jan 26, 2020 8:56 pm at Sun Jan 26, 2020 8:56 pm
>
> If so, should I use the wkm import/export 3D model software plugins? [...], I'll convert obj to wkm using 3DS MAX plugin. However, I have not known how to make 3DS MAX plugin.You need to be a coder to write a dll plugin or a maxscript. 

> In fact, I couldn't analyse wkm format completely.Too sad... 

> I'm really sorry, but could you help me?I'm really sorry, too, because I don't have the time for such.

You need to realize that an obj_to_some3DFormat converter is very time consuming to create.
I'd suggest to search in "Romance of the Three Kingdoms 11" forums, if any.

btw: converting some3DFormat to obj usually takes 15 minutes (first submesh only) for simple formats.
That's probably the reason why some guys believe the vice versa way is similar. But it is not.

You may read here to understand better, why:
[viewtopic.php?f=16&t=13184&hilit=vkm](https://forum.xentax.com/viewtopic.php?f=16&t=13184&hilit=vkm)
## Post #7
- Username: Yukino
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 20, 2020 11:49 pm
- Post datetime: 2020-01-26T16:56:09+00:00
- Post Title: [Help] About making a quickbms script converting obj to wkm or plugins.

Could you answer a question for me? 

I wonder your opinion can apply the other 3D formats except obj.
