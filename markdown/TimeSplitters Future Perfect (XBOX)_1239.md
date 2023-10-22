## Post #1
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-05-14T08:14:13+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Hey guys,  I've seen a few requests for this game. So I thought I would suggest it. Pretty much the entire game are pak files. It looks like there are two kinds, Audio and everything else I've looked at are the same.

Seems similar to Second Sight Pak file.

Begins:
4 Byte - Header (P5CK)
4 Byte - Direct Offset to archive information
4 Byte - Size / 16

From the Direct Offset:
4 Bytes: ID (Useful for Audio?)
4 Bytes: Offset
4 Bytes: Size

The Difference between the Audio and other pak files is that the Audio uses offset number 1 for naming convention. (you might notice second file is blank but that is what it was named  )   The rest of the pak files begin as it seems with straight information and no names.

I'm not sure if you want to take it a step further and try to build headers on export. If it is no problem, I'll gladly help as best as I can. Example in chr.pak last file contains only image dimensions repeated.

Should be Audio.pak and chr.pak. I cut tails based on offset as said above. I'd try out making a script myself, but I'm cursed with laziness.

Anyways, if you already have a script that will do this stuff feel free to kill attachment and smack me   
[tsp3.zip](https://xentaxbackup.github.io/file/224_tsp3.zip)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-15T15:02:27+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Excellent - good work on the format analysis. I havn't got the game to test it on or anything, but I trust your script works fine 

Thanks mate, it is appreciated.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-05-16T00:58:42+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Thanks, I included in the zip just 2 files split to show what I was talking about. Didn't include a script  though.

I do have a question about the audio, what would be the easiest way to name these files?
## Post #4
- Username: neotheone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 19, 2005 8:49 am
- Post datetime: 2005-05-19T00:51:10+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

How about a format analysis for MUSICTS.PAK?
## Post #5
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2005-05-19T03:32:00+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

> Reply from neotheone
>
> How about a format analysis for MUSICTS.PAK?

It follows same format as above. So a standard script could export pretty much all of the game. Files do not have headers, I gave a quick try on listening to the audio, I didn't confirm but it is or could be xb-adpcm codec.
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-19T15:00:20+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

I did a Game Extractor plugin for this game - available to full version users. Thanks for your help with the specs mate! 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: dyce
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 17, 2005 11:36 am
- Post datetime: 2005-05-22T20:26:00+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

i too would like to see this for multiex commander
## Post #8
- Username: dyce
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 17, 2005 11:36 am
- Post datetime: 2005-06-05T05:22:40+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Mr. Mouse, can you whip up a script for this? shortly i will be writing the ut2k4 mesh thing.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-05T12:26:45+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

```
SavePos TailOffOff 0 ;
Get TailOff Long 0 ;
Get TailSize Long 0 ;
Set J Long 2048 ;
GoTo J 0 ;
Get FileNum Int 0 ;
SavePos D 0 ;
Get B Byte 0 ;
GoTo D 0 ;
Set FNT String file ;
Set TJ Long TailOff ;
For T = 1 To FileNum ;
If B > 0 ;
GoTo D 0 ;
Get FNS Byte 0 ;
GetDString FN FNS 0 ;
SavePos D 0 ;
Else ;
Set FN String FNT ;
String FN += T ;
EndIf ;
GoTo TJ 0 ;
Get DUM Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get DUM Long 0 ;
SavePos TJ 0 ;
Log FN FO FS FOO FSO ;
Next T ;

```


Here's a script that might do the trick. However, I do not have full archives, so it's a bit tricky. If I could have full archives it might help.
[pak.zip](https://xentaxbackup.github.io/file/276_pak.zip)
## Post #10
- Username: dyce
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 17, 2005 11:36 am
- Post datetime: 2005-06-06T05:11:49+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

here ya go, hope its big enough

[http://sendmefile.com/00004744](http://sendmefile.com/00004744)
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-06T07:36:39+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Ok thanks. I can see that the specs at the WIKI ( [http://wiki.xentax.com](http://wiki.xentax.com) ) are not complete. This pak format is again different from that description, not much, but enough to not work with any program.  

I will see if I can come up with a universal method that WILL support them.
## Post #12
- Username: dyce
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 17, 2005 11:36 am
- Post datetime: 2005-06-08T22:36:24+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

do you need another pak file to look at?
## Post #13
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-05-12T20:38:27+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Sorry for the bump 

I went back and looked at this game a bit more. The Unknown Int32 (Hash/ID?) are CRC's of strings.

It gets a little strange for this, it is based on 12 or more Asset Paths in the xbe (executable)  The names are seperated from these paths (some inside the xbe). The sounds/music names contained inside the files are actually for the PS2. (Extension .vag etc) These are part of the filenames as well except without .vag and in place .xbs combined with the asset path. All these variables are to hard to read on the fly. So instead I'm more or less just running collisions on the names with the 12 or so asset paths against the Table CRC listings. Still at around 60% of the names, when I feel they are 100% I am just going to build a file to read from.

I also did Timespltters 2 pak files (2 different variations) I'll toss the format up here if anyone holds any interest in the game anymore.
## Post #14
- Username: kholdfuzion
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 19, 2006 2:51 pm
- Post datetime: 2006-09-27T16:50:43+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

im interested in it still, fairly new to the site so this is a new thread to me, sorry bout the old bump
## Post #15
- Username: FileMan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 06, 2015 8:03 am
- Post datetime: 2015-12-06T00:42:46+00:00
- Post Title: TimeSplitters Future Perfect (XBOX)

Sorry for the bump but i wanted to know how you viewed the pak files?
