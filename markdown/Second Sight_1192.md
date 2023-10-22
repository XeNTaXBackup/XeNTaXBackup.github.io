## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-20T17:49:30+00:00
- Post Title: Second Sight

hello

this is packge file second sight

thanks
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-22T04:57:22+00:00
- Post Title: Second Sight

Hmm, this is what I have so far...

```
| Second Sight *.pak |
+--------------------+

// NOTE: The files in the directory *may be* in a different order to the files in the archive
// eg. File1 in the directory may be File622 in the archive

4 - Header (P4CK)
4 - Unknown (Archive Size?)
4 - Unknown
4 - Size Of Filename Directory [-18]
16 - null
2 - Number Of Files?

// for each file
  1 - Filename Length
  X - Filename
  
// for each file
  1 - Description Length
  X - Description
  4 - Filename ID (starting at 0, incrementing by 1 for each file)
  2 - Unknown (127)
  2 - Unknown (127)
  2 - Unknown (15)
  2 - Unknown (13)
  4 - Unknown
  2 - Unknown
  4 - Unknown
  
X - File Data
```


Now I just need to fill in the blanks, but I can't seem to find the file offsets or lengths yet  - so can't get a script for this game yet.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-22T06:16:31+00:00
- Post Title: Second Sight

So many archives, so little time....
## Post #4
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-05-01T10:10:03+00:00
- Post Title: Second Sight

hello

please look new package from Second Sight game
## Post #5
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2005-05-01T15:33:36+00:00
- Post Title: Second Sight

its not the matter for this game but does the main exe of a game help to unpack his scheme or it's pure analysis of the packed data?
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-02T03:03:04+00:00
- Post Title: Second Sight

I am not too sure about Mr Mouse, but I think he is the same as me. I just look through the packages using my own custom hex editor, looking for common patterns and then seeing how they relate to the archive. It isn't usually too hard to do, but sometimes we just get one which is totally out of control.

I wouldn't really know where to start if I was given an EXE file - i guess I would need to know a bit of assembly language for that - but thats way too difficult for me.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2005-05-02T16:00:48+00:00
- Post Title: Second Sight

> Reply from friendsofwatto
>
> I wouldn't really know where to start if I was given an EXE file - i guess I would need to know a bit of assembly language for that - but thats way too difficult for me.

i dont believe you dont know about assembly as you do program i'm unable to do myself you're too modest! 

i had thought it was much easier to analyze the main exe to know where access what.
anyway thanks to both of you (Mr.Mouse and you) for the work done here.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-02T22:38:10+00:00
- Post Title: Second Sight

I know, its pretty embarassing - but when it comes to assembly I know absolutely nothing.


In regards to this game, yeah I still havn't found anything that gives me the offsets or lengths of the files - until we work that out I can't add support for this game.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-04T09:28:00+00:00
- Post Title: Second Sight

Hi, I was bored so I took a look at Scripts.

I read backwards starting from 0x00013FB0  I read backwards from that point. Seems each is split into 16bytes.

Starting at 0x00013FA0
4bytes unkown
4bytes Offset (Signed Long)
4bytes Size
4bytes blank?

Each Offset then begins 97134FF9 so I believe it is right for that.
## Post #10
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-05-04T10:10:56+00:00
- Post Title: Second Sight

Oops bored and tired   

Scripts.pak
4 bytes (Header)
4 bytes (offset to file size and location?) =79824

Then from that 4 bytes? 4 bytes (offset) 4 bytes (size?)

Sorry for the 2 posts couldn't edit guest.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-04T11:29:15+00:00
- Post Title: Second Sight

I've taken a look at the Scripts file:

```
IDstring	P4CK
uint32		Absolute offset of tail
uint32		Size of file info tail (divide by 16 and you have the number of files)
uint32		Size of Filename string tail

[FILEINFO TAIL] (file info entries are 16 bytes per file:)
uint32 		Relative offset of filename (from tail start)
uint32 		Offset of file
uint32		Size of file
uint32 		unknown 

[FILENAME STRING TAIL]
string		Null-terminated filename strings

```


That's it
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-05T13:27:13+00:00
- Post Title: Second Sight

Excellent - I guess I must have been asleep when I was looking at the format too 

Here is the MexCom Script for it...

```
Get DirOffset Long 0 ;
Get FNum Long 0 ;
Set NameOffset Long FNum ;
Math NameOffset += DirOffset ;
Set JP Long DirOffset ;
For n = 1 to FNum ;
GoTo JP 0 ;
Get FNO Long 0 ;
Math FNO += NameOffset ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get DN Long 0 ;
Math JP += 16 ;
GoTo FNO 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
Next n ;

```


Attached is a compiled script for the format - go to Tools-->Use Custom Script. I did try to test the script but it kept complaining about the line where it reads the String, saying something like "Invalid get type", but it did compile OK. I am hoping that this was just an error in the Mex3Scriptor  3.98 that was fixed in a later version of MexCom.

Game Extractor (Full Version) can also open these archives.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[pak.zip](https://xentaxbackup.github.io/file/209_pak.zip)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-05T14:44:17+00:00
- Post Title: Second Sight

Okay thanks. Just so you know, the first P4CK file is different from the Scripts.pak.
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-05T14:51:39+00:00
- Post Title: Second Sight

Hmm ok, i thought there must have been a reason why noone found anything in the first file 

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-05T18:36:17+00:00
- Post Title: Second Sight

> Reply from friendsofwatto
>
> I did try to test the script but it kept complaining about the line where it reads the String, saying something like "Invalid get type", but it did compile OK.

Actually, there was nothing wrong with either program, but the script itself was bugged   . 

Here's a working script: 

```
GoTo 4 0 ;
Get DirOffset Long 0 ;
Get FNum Long 0 ;
Math FNum /= 16 ;
Set JP Long DirOffset ;
For n = 1 To FNum ;
GoTo JP 0 ;
Get FNO Long 0 ;
Math FNO += DirOffset ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get DN Long 0 ;
SavePos JP 0 ;
GoTo FNO 0 ;
Get FN String 0 ;
Log FN FO FS FOO FSO ;
Next n ;

```


The problem was that you used the NameOffset variable to go to the filenames but you added the relative offset of the filenames AGAIN, before doing that. In essence you added 2016, and then before jumping to it , again 2016. So the script reached the end of the archive unexpectedly. 

Also, you forgot to divide the FNum variable by 16, before using it in the loop. That's a lot more resources to try to retrieve...  
[pak100percent.zip](https://xentaxbackup.github.io/file/211_pak100percent.zip)
## Post #16
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-06T03:34:18+00:00
- Post Title: 

Ah OK, i can see that now - it was hard for me to see what was going wrong because it said it was getting incorrect read errors on line, but it didn't tell me which line 

That makes sence though, so thanks for fixing it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-06T06:35:19+00:00
- Post Title: 

There is however a way of looking at what's going on. If you start MexCom anew and then use the Custom Script option, and it fails: go to Options and view the MultiEx 3 Progress Log. You can try to deduce where it fails, if offsets are correct and if gotten strings are okay etc.
## Post #18
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-06T06:58:32+00:00
- Post Title: 

OK cool, I will try that in the future too.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #19
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2007-01-20T15:08:42+00:00
- Post Title: 

I'm not find the all textures.
The storymem folder contain the textures, but (maybe because of Starforce3 ) not all.
Anybody know where is the missing textures?
[ss3.jpg](https://xentaxbackup.github.io/file/1040_ss3.jpg)
## Post #20
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-20T18:46:49+00:00
- Post Title: 

> Reply from mambox
>
> does the main exe of a game help to unpack his scheme?
The normal exe doesn't help cause the copy protection encrypts and compresses the file. Only a No-CD exe would be of interest.

> Reply from mambox
>
> i dont believe you dont know about assembly as you do program i'm unable to do myself you're too modest!
"Normal" programming doesn't really require knowledge of Assembler language.

> Reply from mambox
>
> i had thought it was much easier to analyze the main exe to know where access what.
It depends on the complexity of a format. A simple format can be figured out much faster by just looking at the file. But when things like checksums, custom compression, encryption etc. are used disassembling is essential.
But this is pretty hard.

> Reply from friendsofwatto
>
> I wouldn't really know where to start if I was given an EXE file - i guess I would need to know a bit of assembly language for that - but thats way too difficult for me.
You will need extensive knowledge of the Assembly language and the Win32 API.
