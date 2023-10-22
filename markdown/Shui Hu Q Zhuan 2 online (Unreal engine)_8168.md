## Post #1
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-01T02:37:28+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2012-02-05T11:28:35+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

*.PAK format looked like very easy.

char header[8]; "FSH24001"
int32 size; //fize of PAK
int32 numfiles; //number of files in PAK
{char filename[32]; int offset; int sizeOfFile; char dummy[8];}[numfiles]
then data.
## Post #3
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-05T14:19:56+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

So is it possible to make a script to extracts files from paks?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T16:31:23+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

It does not seem that obvious.

There is still compression on the data.
I mean sure you can see strings in some of those csv's and all, but then there's a lot of other garble there.

If you look at the each file, it most likely starts with

```
dword size
dword compressed_size
....

```


But I don't know which compression algorithm is used.

This unpacks the archives, but is not complete based on the provided sample.

```

idstring "FSH24001"
get FSIZE long
get FILES long

set FOLDER_NAME = "/"
for i = 0 < FILES do
	getdstring NAME 32
	get OFFSET long
	get SIZE long
	get IS_FOLDER long
	get unk2 long
	
	if IS_FOLDER = 1
		set FOLDER_NAME = NAME
		string FOLDER_NAME += "/"
	else
		set TEMP = FOLDER_NAME
		string TEMP += NAME
		print %TEMP%
		log TEMP OFFSET SIZE	
	endif
next i

```


The IS_FOLDER value might be more than just one sub-level, so if there are multiple nested folders it'll have to be defined a little differently.
## Post #5
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-05T17:19:04+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

Thanks, the script is really works, it extracts a lot of ukx and utx files but them seems to not working with umodel for me, so all in Gildor's hands i think.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T17:29:26+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

The files should be compressed.
I just don't know the compression algorithm used.

But I guess you can upload some model/tex samples. It's probably the same compression used as the rest of the files.
## Post #7
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-05T17:34:10+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T17:45:05+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

You're right, it's not compressed.
Well, it is compressed. It just happens that it's the same as the original for whatever reason.

A proper unpacker that decompresses the file data would still produce the same result.

Try removing the first 12 bytes of the file and see if umodel can load it, since the first 12 bytes are not part of the model.
## Post #9
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-05T17:55:00+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

It's partially works.
Removing 12 bytes works with usx - static mesh packages and utx - textures.
But skeletal meshes - ukx still doesn't want to work.

P.S. But hand painted textures looks quite good. Simple cartonish style, but made by quite crafty artists.
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-05T19:45:30+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

well really great news, yes testing and trying crack UKX files but don't have lucky, I tested all files.

UKX= Pending
UTX=DONE
USX=DONE
UNR=DONE
UAX=DONE
## Post #11
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-06T09:11:32+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

Finale00 i'm not programmer but maybe it's not hard to modify bms script that it will extract packages without those extra 12 bytes? Because there are a lot of packages (129-utx, 248-usx, 679-ukx) and do it manually will be very looong process
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T12:45:37+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

Assuming you don't need those 12 bytes for any of the models/textures, we can just skip those 12 bytes by increasing the offset of each file.

```
#temp unpacker
#doesn't decompress files

idstring "FSH24001"
get FSIZE long
get FILES long

set FOLDER_NAME = "/"
for i = 0 < FILES do
   getdstring NAME 32
   get OFFSET long
   math OFFSET += 12
   get SIZE long
   get IS_FOLDER long
   get unk2 long
   
   if IS_FOLDER = 1
      set FOLDER_NAME = NAME
      string FOLDER_NAME += "/"
   else
      set TEMP = FOLDER_NAME
      string TEMP += NAME
      print %TEMP%
      log TEMP OFFSET SIZE   
   endif
next i

```
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-06T14:24:09+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

> Reply from finale00
>
> Assuming you don't need those 12 bytes for any of the models/textures, we can just skip those 12 bytes by increasing the offset of each file.
Code: Select all#Shui Hu Q Zhuan 2
#temp unpacker
#doesn't decompress files

idstring "FSH24001"
get FSIZE long
get FILES long

set FOLDER_NAME = "/"
for i = 0 < FILES do
   getdstring NAME 32
   get OFFSET long
   math OFFSET += 12
   get SIZE long
   get IS_FOLDER long
   get unk2 long
   
   if IS_FOLDER = 1
      set FOLDER_NAME = NAME
      string FOLDER_NAME += "/"
   else
      set TEMP = FOLDER_NAME
      string TEMP += NAME
      print %TEMP%
      log TEMP OFFSET SIZE   
   endif
next i
thanks a lot for it, after finish modify all you create a bms script for do it xX, I sick now anyway keep working, now the problem is UKX, Gildor is working in it, so hope see news very soon.
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-09T16:49:51+00:00
- Post Title: Shui Hu Q Zhuan 2 online (Unreal engine)

ummm well the compression say chrox is COMP_LZO1X, maybe can take a look and modify script? today I download new client, and script not work, they changed files, here I uplaod for take a look too, thanks.

[Shui Hu Q Zhuan 2 Online v80 [Samples+EXE]](http://www.mediafire.com/?fdrv8t45wht4dq4)
