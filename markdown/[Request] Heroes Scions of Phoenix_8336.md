## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T20:51:23+00:00
- Post Title: [Request] Heroes Scions of Phoenix

Ok guys the game have .pak format so well chrrox make a script for unpack it but all files I get have 0 bytes, so maybe somebody can take a look files.

Here is the bms script of chrrox

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype deflate
for
    findloc start string "UZ\x03\x04"
    goto start
    idstring "UZ\x03\x04"

    get ver         short
    get flag        short
    get method      short
    get timedate    long
    get crc         long
    get comp_size   long
    get uncomp_size long
    get name_len    short
    get extra_len   short
    filexor 0xb2
    getdstring name     name_len
    filexor ""
    getdstring extra    extra_len
    savepos offset

    if method == 0
        Log name offset uncomp_size
    elif method == 8
        CLog name offset comp_size uncomp_size
    else
        print "unsupported compression method %method%"
        cleanexit
    endif

    math offset += comp_size
    goto offset
next
```

[Heroes Scions of Phoenix Archive Research](http://www.mediafire.com/download.php?k6d48un8r6os4xp)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T22:31:20+00:00
- Post Title: [Request] Heroes Scions of Phoenix

I think I can see why the script skips to all of the "UZ\x03\x04", but that is not the right way to do it.

For the cases where the "Flag" has value 9, these are when you are reading the primitives and models.

It looks like images have "method" value of 8.

Check out the attached file.
I've cut out two file entries based on idstring, and if you jump to the 2nd idstring, you'll see two integers right before it.

Now highlight all of the ""UZ\x03\x04" and then go to the second one.
Look at the previous 16 bytes, and you'll see this

```
dword ?
dword compressed size
dword size

```


It should not be coincidental that the size of the data is exactly the size that's shown.
However it doesn't seem like the compression method used is deflate.

Try this out:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
# updated Feb 18, 2012 by Tsukihime

for
    findloc start string "UZ\x03\x04"
    goto start
    idstring "UZ\x03\x04"

    get ver         short
    get flag        short
    get method      short
    get timedate    long
    get crc         long
    get comp_size   long
    get uncomp_size long
    get name_len    short
    get extra_len   short
    filexor 0xb2
    getdstring name     name_len
    filexor ""
    getdstring extra    extra_len
    savepos offset
	if flag == 9
		#comtype ???
		FindLoc NEXT STRING "UZ\x07\x08"
		goto NEXT
		idstring "UZ\x07\x08"
		get unk LONG
		get ZSIZE long
		get SIZE long
		savepos curr
		#clog NAME offset ZSIZE SIZE --- I don't know compression format
		print "%NAME% %ZSIZE% %SIZE%"
		goto curr
	else
		comtype deflate
		if method == 0
			Log name offset uncomp_size
		elif method == 8
			print %name%
			CLog name offset comp_size uncomp_size
		else
			print "unsupported compression method %method%"
			cleanexit
		endif
		
		math offset += comp_size
		goto offset
	endif
next
```


All you need is to specify the compression format used for those particular files when the flag == 9.
Maybe. Lol
[cutout.7z](https://xentaxbackup.github.io/file/5083_cutout.7z)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-18T23:59:03+00:00
- Post Title: [Request] Heroes Scions of Phoenix

they changed the archive format then the script did work perfectly on the archive when it was posted.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-19T04:46:33+00:00
- Post Title: [Request] Heroes Scions of Phoenix

yeah now it working, some dds files, just I unistall client fopr get space in my HD, later maybe I install it for put samples of models, thanks for support guys.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T04:48:54+00:00
- Post Title: [Request] Heroes Scions of Phoenix

The DDS files were always extracted correctly.
Just the models aren't getting extracted because we don't know compression format.
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-19T16:47:25+00:00
- Post Title: [Request] Heroes Scions of Phoenix

60mb pack file Heroes Scions of Phoenix in the repository.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-07-19T19:17:35+00:00
- Post Title: [Request] Heroes Scions of Phoenix

> Reply from Rimbros
>
> 60mb pack file Heroes Scions of Phoenix in the repository.well thanks a lot, I have a question, why all folder names inverted? I can't read it fine lol, I don't know is my problem.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-19T20:11:43+00:00
- Post Title: [Request] Heroes Scions of Phoenix

That's the point.
