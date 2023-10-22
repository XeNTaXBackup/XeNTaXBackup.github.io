## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-05T21:56:25+00:00
- Post Title: newer unreal engine games

Hi .. what about games like SW: Republik Commando / Brother in arms.
Any chance to get them supported ?

thx
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-05T23:15:06+00:00
- Post Title: newer unreal engine games

Hi,

Most of the games based on the Unreal engine will work with any program that opens the unreal archives, however I think there may be a new format emerging, because I encountered it when I was looking at the Splinter Cell: Chaos Theory game. If you attach an archive from the game, I may be able to take a look at it for you. However, at this point in time, I don't think MexCom will be able to support the Unreal engine, unless Mr Mouse writes a custom plugin for it - much like he did for the Painkiller game.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-06T17:00:33+00:00
- Post Title: newer unreal engine games

That's right. I'm looking for options to include support. We are working on a pluginmanager. When we get that to work, then we will start supporting it.
## Post #4
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-06T17:18:11+00:00
- Post Title: newer unreal engine games

hi 

this package uax from Brother in arms game (with new engine)

thanks
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-07T14:44:28+00:00
- Post Title: newer unreal engine games

I only just got the demo of this game, which is a good thing too because there are actually 3 different formats I found in this game.

It looks like the game developer wanted to use the Unreal game engine, but wanted it to load the files quickly. By this I mean that instead of using the space-saving indexing method that appears in all other Unreal-based packages, this game uses fixed 4-byte fields in place of them.


Here is the export directory structure of a typical unreal-based package...

```
// 1-5 - Parent Object
// 4 - Group ID
// 1-5 - Name ID
// 4 - Flags
// 1-5 - Raw File Length
// 1-5 - Data Offset

```


Where the 1-5 indicates the fields where you read the value using the special Unreal indexing technique. However, these formats (version numbers 156,157,159) use the following structure...

```
// 1-5 - Parent Object
// 4 - Group ID

if (version == 159){
  // 1 - Flag? (0/2/4)
  }

// 1-5 - Name ID
// 4 - Flags
// 4 - Raw File Length
// 4 - Data Offset

```


As you can see, the last 2 fields have become fixed length. Also, in one version, an additional 1-byte field is added, with unknown purpose (probably a flag).


If/When Mr Mouse gets the time to implement Unreal-based games, I would recommend that he contacts me for my unreal plugin source code because there have been 2 games thus far that use undocumented version values - this game and Splinter Cell Chaos Theory.

In the meantime, if you desperately need to open the files, you can use the Game Extractor plugin below - hopefully it will work. There are a few really small archives that do not work - these are archives that don't actually contain any files - all files over say 1kb in size should work. If not, please tell me the filenames that don't work and I will take a look at them, just in case there is another different version that I have missed ( such as version 158? )

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_U.zip](https://xentaxbackup.github.io/file/159_Plugin_U.zip)
## Post #6
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-07T17:09:04+00:00
- Post Title: newer unreal engine games

hi mr watto

iam test your plugin 

but not open file with error "no plugins..."

iam use on Brothers in arms

files "*.uax , *.utx

but open unreal files  (good)

thanks
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-08T00:00:38+00:00
- Post Title: newer unreal engine games

OK, I will take a look at the file you attached - see if I can work out what is wrong. Make sure you only test it on big archives, because small archives don't have any files in them.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-08T01:10:47+00:00
- Post Title: newer unreal engine games

OK, try this one...

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_U.zip](https://xentaxbackup.github.io/file/162_Plugin_U.zip)
## Post #9
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-08T06:26:58+00:00
- Post Title: newer unreal engine games

mr watto

Iam test uax with new your plugins 

open uax brothers in arm but

incorrect file name and file type and fie size
[fail.JPG](https://xentaxbackup.github.io/file/163_fail.JPG)
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-09T06:08:59+00:00
- Post Title: newer unreal engine games

OK, I will install the demo again and see whether I can find some files that do not work with my plugin.

If you can send me some of the archives too, it will help me out. I will need the full archives though, not a piece of them. You can email them to me if they are too large to put on these boards. [watto@watto.org](mailto:watto@watto.org) Zipped to <4MB

Thanks mate, hopefully this will be fixed up soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-09T08:53:32+00:00
- Post Title: newer unreal engine games

mr watto

iam sent to you one full package from brothers in arms game
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-10T03:22:40+00:00
- Post Title: newer unreal engine games

OK thanks, I will take a look at it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-10T04:54:47+00:00
- Post Title: newer unreal engine games

OK, the Brothers In Arms archive you sent me now works, so hopefully it will work for the other archives too.

The Brothers In Arms format (version 127) was different again. Firstly, these archives stored the directory at the end of the file instead of at the beginning - not a big deal but it is different. Also, all the fields are fixed length...

```
4 - Parent Object
4 - Group ID
4 - Name ID
4 - Flags
4 - Raw File Length
4 - Data Offset 
```


Attached is the updated plugin. Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_U.zip](https://xentaxbackup.github.io/file/167_Plugin_U.zip)
## Post #14
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-11T15:51:04+00:00
- Post Title: newer unreal engine games

hi

thanks for plugins

plugins good work, only extract without type fle name
## Post #15
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-12T17:19:02+00:00
- Post Title: newer unreal engine games

mr wattot
please fix plugin
extract incorrect file type
## Post #16
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-12T22:36:07+00:00
- Post Title: 

Hi mate,

The Unreal game engine does not have file types, does it? I will look in to it anyway, I would like to add more support for unreal formats soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #17
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-13T16:48:16+00:00
- Post Title: 

but in unrealed explorer packge with wav type file(swat 4 use uax pack and open with your plugins)
## Post #18
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-13T22:32:48+00:00
- Post Title: 

Yes, in some files they use WAV audio, which I can put the *.wav at the end of the filename, but I want to take a bit of a look into the format more anyway because surely there is a way to distinguish the type of files in the archive, even if it is just 1 format per archive.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #19
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-14T04:22:04+00:00
- Post Title: 

mr watto

but old your plugins open unreal game with correct file type (wav)

but now not open with correct file type 

and unrealed open unreal and swat 4 with file type wav
## Post #20
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-14T10:43:18+00:00
- Post Title: 

OK, I will have to look at that - it is probably an error that slipped in there accidentally.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
