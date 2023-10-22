## Post #1
- Username: AD
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Sep 22, 2006 2:27 pm
- Post datetime: 2006-09-22T06:54:11+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

Hi there.  I've been doing some digging into the PSX version of Wing Commander 3.  It seems in this game all the files are stored in various *.LIB archives.    The games movies are stored in MOVIES1.LIB (the number being the disk number) and so on.  movies1.lib starts off by listing the files contained in the archive. It looks like this when viewed in a hex editor:    

```
00000010  6f 61 2e 77 76 65 00 00 00 00 d0 1e 47 07 00 50  oa.wve....Ã
```
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-22T08:10:34+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: AD
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Sep 22, 2006 2:27 pm
- Post datetime: 2006-09-22T14:52:10+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-22T19:51:08+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

Ok, that was an easy one, I think :

```
Get FN Int 0 ;
For T = 1 To FN ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
GetDString FName 16 0 ;
Log FName FO FS FOO FSO ;
Next T ;

```


Try this file (Use Custom BMS on..) on a LIB file.
[lib.zip](https://xentaxbackup.github.io/file/865_lib.zip)
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-23T09:34:41+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

You can reconvert the movies to xvid with ffmpeg
[http://www.ffmpeg.sf.net](http://www.ffmpeg.sf.net)
## Post #6
- Username: AD
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Sep 22, 2006 2:27 pm
- Post datetime: 2006-09-23T10:12:41+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

First, I'm still waiting for my Multiex serial code, so I haven't tinkered with this yet.  

> Reply from pulposo
>
> You can reconvert the movies to xvid with ffmpeg
http://www.ffmpeg.sf.net

Have you tried this out?  Do you have the PSX game?  Your link did not work for me.   

I've had a nagging suspicion that the game might use the typical PSX video format, yet no other program has been successful in extracting the videos.  Though if it is actually standard PSX video it would make sense that some of the plugins for ffmpeg might play them "out of the box" (so to speak).
## Post #7
- Username: AD
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Sep 22, 2006 2:27 pm
- Post datetime: 2006-09-24T22:16:00+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

Ok,  Tried it out and seems to work great for extracting all the Files from the library files.  Now to see if I can figure out how to read and convert wve, mve, and tai files   .

Thanks again.   Going to check, but this *should* also work on wc4 psx.

Also, regarding ffmpeg builds, Mplayer couldn't play the WVE files.  They are not the same as the wve/divx split format.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-26T09:51:53+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

Moved:
[http://ffmpeg.mplayerhq.hu/](http://ffmpeg.mplayerhq.hu/)
and have a look at this:
[http://www.mplayerhq.hu/DOCS/codecs-status.html#vc](http://www.mplayerhq.hu/DOCS/codecs-status.html#vc)
## Post #9
- Username: AD
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Sep 22, 2006 2:27 pm
- Post datetime: 2006-09-26T18:43:10+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

So I managed to convert all the games SEQ files into MIDIs playable in windows, but two of the files came up blank.   I had managed before (using a different utility)  to extract unnamed midis so I figured out which ones were missing to make a properly named set.  I don't know if this is a glitch in the BMS file?   Of course I still need to work on a solution to playing the WVEs and TAI files. 

On another note, has anybody made any MultiEx scripts for exploring the PC wing commander TRE files? Or does anyone know whether the format is the same from game to game?  If noone has done anything for MultiEX I provide samples from some of the games.  (you might want to look into the work done by Mario Brito (HCl) as well:  [http://www.wcrevival.de/hcl/](http://www.wcrevival.de/hcl/)

> Reply from pulposo
>
> Moved:
http://ffmpeg.mplayerhq.hu/
and have a look at this:
http://www.mplayerhq.hu/DOCS/codecs-status.html#vc
I'm really not sure what you are pointing out here.   I don't see anything there related to playing this specific file format.  Plus, beyond trying the mplayer builds (which I've done) I am not really the kind of person that is up for compiling my own build.  Other than some highschool pascal I have absolutely zero programming skills.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-26T19:10:06+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

> Reply from AD
>
> So I managed to convert all the games SEQ files into MIDIs playable in windows, but two of the files came up blank.   I had managed before (using a different utility)  to extract unnamed midis so I figured out which ones were missing to make a properly named set.  I don't know if this is a glitch in the BMS file?

I'm no sure what you mean. Are the names of the extracted files incorrect?
## Post #11
- Username: AD
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Sep 22, 2006 2:27 pm
- Post datetime: 2006-09-27T01:01:01+00:00
- Post Title: Wing Commander 3 PSX version (*.LIB files)

> Reply from Mr.Mouse
>
> I'm no sure what you mean. Are the names of the extracted files incorrect?

The files are all named correctly when extracted.   It's quite possible it's a glitch with the se2 to midi converter I used.   The resulting midis from only two of the conversions would not play.  And the same two files were broken when I repeated the extraction and then conversion.   I managed to extract unnamed midis ages ago with a different program but that program did not extract file names.   But I was able to tell which ones were the broken files so I do have copies of all the midis which all have names now.   I'd guess that its a problem with the conversion program.
