## Post #1
- Username: hondamxer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 15, 2006 1:23 pm
- Post datetime: 2010-11-27T10:41:59+00:00
- Post Title: MX vs ATV Reflex - PC

This game was just released on steam.

The main archive files are .package files and there are also associated files that appear to be bxml files. 

Example file can be found here: [http://www.sendspace.com/file/nxbglk](http://www.sendspace.com/file/nxbglk)
## Post #2
- Username: stevoktm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 27, 2010 5:04 pm
- Post datetime: 2010-11-27T12:45:29+00:00
- Post Title: MX vs ATV Reflex - PC

I also play this game and it has just been released. What we really need is a way to extract files from each seperate package file and then possibly a way to re package them. If anybody with good expert knowledge of game archives could find a way to do this, hundreds of reflex players would be thankful and it would re-start the mx vs atv modding community. Thanks
## Post #3
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-11-29T22:05:18+00:00
- Post Title: MX vs ATV Reflex - PC

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Scawn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 11, 2010 1:47 pm
- Post datetime: 2010-12-18T04:41:46+00:00
- Post Title: MX vs ATV Reflex - PC

Any progress on this one yet? I can upload some more files if they would help with figuring out how to open them.
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-18T16:31:10+00:00
- Post Title: MX vs ATV Reflex - PC

there is an already thread in the compression sectoin: [viewtopic.php?f=21&t=5479](http://forum.xentax.com/viewtopic.php?f=21&t=5479)

i've written a tool to convert bxml to xml: [download/file.php?id=3676](http://forum.xentax.com/download/file.php?id=3676)

i also posted the rough format spec in plaintext earlier inthe thread if anyones interested. i started writing a bms version, but i started having problems with it. the sourcecode is written in pascal.
## Post #6
- Username: Scawn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 11, 2010 1:47 pm
- Post datetime: 2010-12-18T20:00:26+00:00
- Post Title: MX vs ATV Reflex - PC

> Reply from WRS
>
> i've written a tool to convert bxml to xml: download/file.php?id=3676

There are 2 main groups of files for this game. It appears that the xml/bxml files have to do with things such as physics, controls, etc which I would classify as the "engine" of the game. I am more interested in converting the database/package files which contain the graphics (bike and rider skins) as well as the tracks. I am not interested in changing the way the game plays, I am interested in adding content to the game. 

Maybe the editing of the database/package files somehow starts with the xml/bxml files, and if so, then I apologize for my oversight, but I do not see the link between the two.
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-18T22:07:59+00:00
- Post Title: MX vs ATV Reflex - PC

> Reply from Scawn
>
> WRS wrote:i've written a tool to convert bxml to xml: download/file.php?id=3676

There are 2 main groups of files for this game. It appears that the xml/bxml files have to do with things such as physics, controls, etc which I would classify as the "engine" of the game. I am more interested in converting the database/package files which contain the graphics (bike and rider skins) as well as the tracks. I am not interested in changing the way the game plays, I am interested in adding content to the game. 

Maybe the editing of the database/package files somehow starts with the xml/bxml files, and if so, then I apologize for my oversight, but I do not see the link between the two.

i just spent time on the bxml format in another thread, so i decided to link it with this request too.
your in the wrong forum if you want to demand things
## Post #8
- Username: Scawn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 11, 2010 1:47 pm
- Post datetime: 2010-12-18T23:36:21+00:00
- Post Title: MX vs ATV Reflex - PC

> Reply from WRS
>
> i just spent time on the bxml format in another thread, so i decided to link it with this request too.
your in the wrong forum if you want to demand things

Sorry about that. I thought this thread was asking for assistance in opening the .package files within Reflex. Are you suggesting that I post in the Graphic File Formats section? I thought that was more appropriate when I first came here but found this thread already asking about opening the .packages files and did not want to duplicate a request.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-19T01:24:59+00:00
- Post Title: MX vs ATV Reflex - PC

the bxml format that you are pushing away is quite important.
the DATABASE, SCENE and LEVEL files all use the BXML format. my tool does break when you run it, but only because unsigned integers were not inthe samples i had before.

once they're implemented, the SX_Kingston.dx9.database xml is basically the filelist of the PACKAGE file, with pointers and sizes needed to extract the PACKAGE file, hence solving the problem.

so add the unsigned integer (valuetype 4) to the code i released so it can read uints from the pool and then you can read stuff like this:

```
<Block offset="0" size="0"/>
<Compress enabled="_bool:true" codec="LZX"/>
</Asset>
<Asset type="anim" name="FlagPerson_Anim">
<Heap offset="9034" size="72042"/>
<Block offset="0" size="0"/>
<Compress enabled="_bool:true" codec="LZX"/>
</Asset>
<Asset type="anim" name="ScoreTowerPerson_Idle01">
<Heap offset="81076" size="16406"/>
<Block offset="0" size="0"/>
<Compress enabled="_bool:true" codec="LZX"/>
</Asset>

```


there are also bxmls INSIDE the PACKAGE, so you'll need it there too!

edit removed stuff. also, although i can identify files, i can't seem to decompress them with the LZX algo which it mentions.

edit2

that scene file had a container to it:

```
# quickbms script for mva .dx9.scene files

get SIG long
get FILES long

for f = 1 to FILES

  getdstring NAME 256
  get ZERO long
  get PNTR long

  savepos POS
  goto PNTR

    get BXMLS long
    get UNKNOWN long

    for b = 1 to BXMLS
      savepos BXMLPOS
      getdstring BXMLHEADER 32
      get BXMLSIZE long
      math BXMLSIZE += 36 # 32 + 4

      string FNAME = NAME
      string FNAME += "/"
      string FNAME += b
      string FNAME += ".bxml"

      log FNAME BXMLPOS BXMLSIZE

      math BXMLPOS += BXMLSIZE
      goto BXMLPOS
    next b

  goto POS

next f

```


this has shown how incomplete by bxml converter is!
at least now i have.. 157.. more.. bxml.. examples  ....
## Post #10
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2011-05-25T15:01:22+00:00
- Post Title: MX vs ATV Reflex - PC

I have a question that I'm not sure has been answered here yet.

I want to change the physics of the bikes in Reflex for the PC. I was the guy that created the Caffeine mods for Unleashed, and all the other guys ripped me off by changing two or three values in my work and renaming it as if they created something new and wonderful (Turbine, Speed, Tea2Sugars, etc.), but I digress...

In Unleashed there were only .pak files to open and modify the contents and re-pak them.

Reflex looks to be a bit more complicated. Do I need to open files other than the .package files? I'm not sure how to approach this and I'm sorry if this is a silly question that's already been resolved.

Thanks for any help you can provide.
## Post #11
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2011-11-23T15:55:10+00:00
- Post Title: MX vs ATV Reflex - PC

Has any further progress been made so that the MvA Reflex files can be edited and repacked to work in the game via MultiEX? 

I would really like to make another physics mod for the MvA series (I made Caffeine I, II, & III for Unleashed), but I am clueless when it comes to cracking the file formats.
## Post #12
- Username: MikeyMikey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 12, 2012 3:28 pm
- Post datetime: 2012-01-12T07:58:23+00:00
- Post Title: MX vs ATV Reflex - PC

"I would really like to make another physics mod for the MvA series (I made Caffeine I, II, & III for Unleashed), but I am clueless when it comes to cracking the file formats. "

 Hi Bill..check [www.twisteddirt.com](http://www.twisteddirt.com) website for latest Reflex info..
## Post #13
- Username: Bogey
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Oct 04, 2006 5:21 am
- Post datetime: 2012-01-12T16:07:09+00:00
- Post Title: MX vs ATV Reflex - PC

> Reply from MikeyMikey
>
> "I would really like to make another physics mod for the MvA series (I made Caffeine I, II, & III for Unleashed), but I am clueless when it comes to cracking the file formats. "

 Hi Bill..check http://www.twisteddirt.com website for latest Reflex info..

I poked around on your Forums and didn't find anything helpful that pertains to my question.

I need the info required to open the Reflex game files, modify them and repack them for use in the game. I have used BXML to look around but haven't seen the method posted to repack the files that are modified so they work in the game.
