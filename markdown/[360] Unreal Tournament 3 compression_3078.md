## Post #1
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-06-30T07:28:42+00:00
- Post Title: [360] Unreal Tournament 3 compression

It seems they made a small surprise by introducing new compression type in Unreal engine.
Not LZO, not even zlib this time.

Someone already digged that?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-04T13:34:37+00:00
- Post Title: [360] Unreal Tournament 3 compression

No, not yet, I had not taken a look yet. So any clue what IS used?
## Post #3
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-07-04T17:52:24+00:00
- Post Title: [360] Unreal Tournament 3 compression

The one thing I know exactly, the compressor is the same as in Devil May Cry 4 (it is discussed on xentax already).
Probably, the modification of MS LZX algorithm, but I am not sure..

The one, who will find, what the damn routine (in wild) can return the error code 81DE2001h, will find that compressor.
## Post #4
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2008-09-07T11:50:34+00:00
- Post Title: [360] Unreal Tournament 3 compression

> Reply from juskrey
>
> The one thing I know exactly, the compressor is the same as in Devil May Cry 4 (it is discussed on xentax already).
Probably, the modification of MS LZX algorithm, but I am not sure..

The one, who will find, what the damn routine (in wild) can return the error code 81DE2001h, will find that compressor.

Can you elaborate a bit more about the link between compression method used there and in DMC4?  And what gives it away that they are both the same, and a modification of MS LZX?

I am after uncompressing DMC4's archives and any insight might help.

Thanks.
## Post #5
- Username: juskrey
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 01, 2008 5:50 pm
- Post datetime: 2008-09-07T11:56:19+00:00
- Post Title: [360] Unreal Tournament 3 compression

> Reply from poly
>
> 

Can you elaborate a bit more about the link between compression method used there and in DMC4?  And what gives it away that they are both the same, and a modification of MS LZX?

I am after uncompressing DMC4's archives and any insight might help.

Thanks.

I have used dmc4 executable hack to uncompress some data from DMC4. After that, I tried to unpack a data block from UT3, and it worked.

I assume that this compression is included in latest XDK
## Post #6
- Username: ichigoogle
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2008 12:09 pm
- Post datetime: 2008-09-09T00:25:11+00:00
- Post Title: [360] Unreal Tournament 3 compression

Could you post the executable hack you used to uncompress DMC4?
## Post #7
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2008-09-22T20:40:57+00:00
- Post Title: [360] Unreal Tournament 3 compression

> Reply from juskrey
>
> poly wrote:

Can you elaborate a bit more about the link between compression method used there and in DMC4?  And what gives it away that they are both the same, and a modification of MS LZX?

I am after uncompressing DMC4's archives and any insight might help.

Thanks.

I have used dmc4 executable hack to uncompress some data from DMC4. After that, I tried to unpack a data block from UT3, and it worked.

I assume that this compression is included in latest XDK

Can you elaborate a bit on this "dmc4 executable hack"?
If I understand you correctly, you only partially found a method so far right?

Thanks for the info so far.
## Post #8
- Username: AnthonyFiveSixTwo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 24, 2008 11:52 am
- Post datetime: 2008-10-24T11:33:50+00:00
- Post Title: [360] Unreal Tournament 3 compression

> Reply from juskrey
>
> The one thing I know exactly, the compressor is the same as in Devil May Cry 4 (it is discussed on xentax already).
Probably, the modification of MS LZX algorithm, but I am not sure..

The one, who will find, what the damn routine (in wild) can return the error code 81DE2001h, will find that compressor.

You mean this??   

```

```


Unfortunately its part of the Xbox 360 XeXDK, and I found it in "xcompress.h" which is in fact LZX.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-24T12:15:45+00:00
- Post Title: [360] Unreal Tournament 3 compression

Nice find!
## Post #10
- Username: poly
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Aug 28, 2008 8:17 pm
- Post datetime: 2008-10-28T08:37:46+00:00
- Post Title: [360] Unreal Tournament 3 compression

> Reply from AnthonyFiveSixTwo
>
> juskrey wrote:The one thing I know exactly, the compressor is the same as in Devil May Cry 4 (it is discussed on xentax already).
Probably, the modification of MS LZX algorithm, but I am not sure..

The one, who will find, what the damn routine (in wild) can return the error code 81DE2001h, will find that compressor.

You mean this??   
Code: Select all#define XMCDERR_MOREDATA                    _HRESULT_TYPEDEF_(0x81DE2001)


Unfortunately its part of the Xbox 360 XeXDK, and I found it in "xcompress.h" which is in fact LZX.

Can you point us to any uncompression library that is compatible with the implementation used in the XeXDK?
## Post #11
- Username: SAS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 08, 2008 6:38 pm
- Post datetime: 2008-11-08T18:41:29+00:00
- Post Title: [360] Unreal Tournament 3 compression

Hi all! I`m interested in unpacking UE3 UPK files too. So I collect some information about it.

I found one little program with sourcecode. On this moment it can extract only sounds OGG:
EXE - [http://thehackisback.com/spartan018/UPK_Info_Win32.rar](http://thehackisback.com/spartan018/UPK_Info_Win32.rar)
Program Source - [http://thehackisback.com/spartan018/UPK_Info_Src.rar](http://thehackisback.com/spartan018/UPK_Info_Src.rar)

The sourse of information: [http://forums.epicgames.com/showthread.php?t=597581](http://forums.epicgames.com/showthread.php?t=597581)

author of this program says:

> I've managed to make a lot of progress on the UPK format. I can now partially extract data, although it doesn't always make sense. One of the types I've been more successful with are wav (actually ogg) files. Aside from some extra header data at the beginning of the file (which I haven't been able to decode, part of the reason why I'm posting all this now, but more on that later), OGG files are fully playable. Using a hex editor, you can just remove everything before the first occurance of "OggS" and you'll have a perfectly fine Ogg file.
>
> 
>
> Unfortunately, the extracted data from textures is unusable (for now). They aren't stored in the DDS format (as far as I can tell), so I need some help figuring it out. I'm posting a compiled version of the app for those who just want to extract sounds, while I'm posting the source for those who want to help. Its written in C# and uses .NET 2.0. Any and all help will be appreciated. If necessary, I will start up a Codeplex project just to keep everything organized.

how to work with  this program:

> To extract a file, just select an item in the right-most column ("Actual Exportable Items") and either use the Export > Selected menubar item, or just right-click on the item you want to export. Again, most of the stuff thats exported doesn't make any sense (at least to me), so don't complain if you can't get what you want.

I hope, that this information will be interesting for many people.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-08T23:24:48+00:00
- Post Title: [360] Unreal Tournament 3 compression

Thank you ! Excellent information!
