## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-03-07T13:57:06+00:00
- Post Title: Help with .bik video subtitle display hook tools

Many game use .bik format to show the video .
Can anyone make a hook tools to show subtitle in a none subtitle .bik video?

for details, if the game play a special .bik video ,the hook tool will show a special  unicode subtitle on current window,the time_start,time_end,font_size,font_color,position_x,position_y can be set in source or in a ini file.

Please help me,very thanks. And my friend have made one,but not finished.If you want to take a look,i will post here. It used the way of proxy dll.
## Post #2
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-08T11:30:15+00:00
- Post Title: Help with .bik video subtitle display hook tools

Yep, its possible, and I think that I can do it  I have unofficial bink sdk, made by some guy, so I can make a app that will load and play bink videos with subtitles... but you probably want hook for bink dll, I know how to hook too, but I dont think that it will be legalish to release that hook package (injector + hook dll)...
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-03-08T13:54:54+00:00
- Post Title: Help with .bik video subtitle display hook tools

> Reply from Crypton
>
> Yep, its possible, and I think that I can do it  I have unofficial bink sdk, made by some guy, so I can make a app that will load and play bink videos with subtitles... but you probably want hook for bink dll, I know how to hook too, but I dont think that it will be legalish to release that hook package (injector + hook dll)...

so what help can you give me?
Can you give the unofficial bink sdk or the hook dll to me by mail instead of post here?
my mail [so750515@yahoo.co.jp](mailto:so750515@yahoo.co.jp)
Very thanks!
## Post #4
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-08T15:03:41+00:00
- Post Title: Help with .bik video subtitle display hook tools

Ehm  I always recommend to use google for searching "this kind" of stuff  
Anyway, if you want to hook bunk.dll, then sdk is useless for you, because you need to hook only one function -> BinkCopyToBuffer. This function has about 6 parameters, but you need only one for your purpose and its pointer to buffer where bink frame will be decompressed, and its second parameter: 

```
BinkCopyToBuffer(Bink:Pointer; OutBuffer:Pointer; ScanlineSize: DWORD; Height: DWORD; XOffset:DWORD; YOffset:DWORD; SurfaceFlag: DWORD);
```

To get size of output buffer, you need to multiply ScanlineSize and Height:
OutBufferSize:= ScanlineSize * Height;

-------------------------------------------------------------------

> And my friend have made one,but not finished.If you want to take a look,i will post here. It used the way of proxy dll.
Well, if its not finished, what about releasing source codes ? Maybe somebody (or I) will finish it 

Edit: I see you also asked on alugi forums
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-03-08T21:59:17+00:00
- Post Title: Help with .bik video subtitle display hook tools

very thanks for useful information!
## Post #6
- Username: clauddiu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Aug 26, 2010 1:45 am
- Post datetime: 2010-12-24T20:10:50+00:00
- Post Title: Help with .bik video subtitle display hook tools

The BinkCopyToBuffer params are:

C++

```
// The basic type U32 describes an unsigned 32-bit integer.

S32 BinkCopyToBuffer(
  HBINK bink,
  VOID_PTR dest_addr,
  S32 dest_pitch,
  U32 dest_height,
  U32 dest_x,
  U32 dest_y,
  BINK_COPY_FLAGS copy_flags
);

```


Delphi

```
  type
  U32 = UInt32; // Cardinal
  S32 = Int32; // Integer
*)
Function BinkCopyToBuffer(
  BINK: HBink;
  dest_addr: Pointer;
  dest_pitch: S32;
  dest_height : U32;
  dest_x : U32;
  dest_y : U32;
  copy_flags : U32
  ): U32;

```

In Parameters
bink 
Specifies the Bink handle. 
dest_addr 
Address of the destination memory buffer. 
dest_pitch 
Pitch of the destination buffer in bytes. 
dest_height 
Height of the destination buffer in pixels. 
dest_x 
X (left) pixel offset into the destination buffer. 
dest_y 
Y (top) pixel offset into the destination buffer. 
copy_flags 
Specifies the flags that describe the destination buffer type and other special copy options. 

Returns
Returns one if the frame was skipped, or zero otherwise.

I wonder if any of you have a working example of how to use bink, like to play a bink file? I have try but with no success.

Peace,
Claudiu
