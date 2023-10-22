## Post #1
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-06T19:10:34+00:00
- Post Title: WWE Raw 2 .FPK

Hi, if you could work out an extractor (and if possible repacker) for Raw 2's .fpks I would be very greatful. Heres an example file:

[http://lukereeve.co.uk/SoundSe.fpk](http://lukereeve.co.uk/SoundSe.fpk)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-06T22:16:08+00:00
- Post Title: WWE Raw 2 .FPK

Thanks, will examine it!
## Post #3
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-07T08:20:05+00:00
- Post Title: WWE Raw 2 .FPK

Also if its any help, I imagine its similar to the previous Raw game which was in .xpk format. An extractor already exists for this here:

[http://rawcaw.lukereeve.co.uk/xpkGUI030.zip](http://rawcaw.lukereeve.co.uk/xpkGUI030.zip)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-07T20:57:15+00:00
- Post Title: WWE Raw 2 .FPK

Nope, it's a different format (I browsed through the code of the extractor you mentioned). We'll need a new extractor...MultiEx
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-08T01:08:41+00:00
- Post Title: WWE Raw 2 .FPK

Alrighty, here is the format. There are a few things which I am not too sure about, but this would be clarified if we had another archive or 2 for comparison. Anyway, this works nice for the archive you supplied...

```
| WWE Raw 2 *.fpk |
+-----------------+

4 - Unknown
4 - Unknown
4 - Unknown
4 - Number Of Directories
4 - Number Of Files
4 - Length Of File Data
4 - Unknown
4 - Unknown

// for each directory {
  20 - Directory Name (null) (first directory name is "___RootDirectory___")
  2 - Number Of Sub-Directories in this directory
  2 - Number Of Files in this directory
  4 - Unknown (null if no subdirectories)
  4 - Unknown (null if no files)
  
  // for each sub-directory in this directory {
    repeat from "//for each directory"
    }

  // for each file in this directory {
    20 - Filename (null)
    4 - Offset (relative to the end of the directory)
    4 - Length
    }
    
  }
  
X - File Data
```


I don't think I could write a MultiEx script for this - I'm not sure how it can handle this type of archive. For one, I don't think MexCom can do string concatenation? Maybe Mr Mouse can whip up a script for you.

Otherwise, you can use Game Extractor to open the archive - use the attached plugin. The sound files are weird though - i can't get them to play anywhere  - they don't use the default sample rates or anything.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_FPK.zip](https://xentaxbackup.github.io/file/161_Plugin_FPK.zip)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-08T05:47:30+00:00
- Post Title: WWE Raw 2 .FPK

Yes, that's about the same format I had figured out. MultiEx can handle it, string manipulation is possible in the new version. 

Will create a script or maybe a plugin soon.
## Post #7
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-08T08:30:52+00:00
- Post Title: WWE Raw 2 .FPK

Wow thanks guys. You guy rule. Yeah the sound files are in Xbox Wave format. Unfortunately they can only be played via ingame. But thanks for all your help. If you get this into Multiex I will definitely donate into such a great project!
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-08T08:33:13+00:00
- Post Title: WWE Raw 2 .FPK

Okay, stay tuned
## Post #9
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-08T08:58:38+00:00
- Post Title: WWE Raw 2 .FPK

Just tried it and it works great but only for that one file. The others must be different. I'm uploading some more examples. Also I'm going to donate just for the help u guys have already given. Normally requests for this game get ignored.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-08T09:01:23+00:00
- Post Title: WWE Raw 2 .FPK

Ah I see, okay, yes please upload some more files, so we can compare.
## Post #11
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-08T09:10:51+00:00
- Post Title: WWE Raw 2 .FPK

[http://lukereeve.co.uk/FmoOther.fpk](http://lukereeve.co.uk/FmoOther.fpk) 5.00MB
[http://lukereeve.co.uk/Fool.fpk](http://lukereeve.co.uk/Fool.fpk) 2.47MB
[http://lukereeve.co.uk/TexOther.fpk](http://lukereeve.co.uk/TexOther.fpk) 50MB (still uploading)

These are some more examples if the 50mb one is too big dont worry bout it. Hope this helps you guys!
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-09T06:56:43+00:00
- Post Title: WWE Raw 2 .FPK

OK, the format specs were slightly wrong, here is the update...

```
| WWE Raw 2 *.fpk |
+-----------------+

4 - Unknown
4 - Unknown
4 - Unknown
4 - Number Of Directories
4 - Number Of Files
4 - Length Of File Data
4 - Unknown
4 - Unknown

// for each directory {
  20 - Directory Name (null) (first directory name is "___RootDirectory___")
  2 - Number Of Sub-Directories in this directory
  2 - Number Of Files in this directory
  4 - Unknown (null if no subdirectories)
  4 - Unknown (null if no files)
  
  // for each sub-directory in this directory {
    repeat from "//for each directory"
    }
  }

// for each file {
  20 - Filename (null)
  4 - Offset (relative to the end of the directory)
  4 - Length
  }
  
X - File Data
```


I have also fixed up the Game Extractor plugin for you and tested it on the 2 smaller archives you posted - works without a problem.

Finally, if you want to donate to Game Extractor --> [http://www.watto.org/extract/donate.html](http://www.watto.org/extract/donate.html)
If you want to donate to MultiEx Commander --> [http://multiex.xentax.com/donate/index.html](http://multiex.xentax.com/donate/index.html)

Thanks mate, have fun.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_FPK.zip](https://xentaxbackup.github.io/file/165_Plugin_FPK.zip)
## Post #13
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-09T08:58:00+00:00
- Post Title: WWE Raw 2 .FPK

Thanx so much! I donated yesterday!
## Post #14
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-09T15:36:22+00:00
- Post Title: WWE Raw 2 .FPK

Both have been donated to. Is there anyway to reimport the textures?
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-09T22:35:09+00:00
- Post Title: WWE Raw 2 .FPK

I am working on a plugin that will do that for you...
## Post #16
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-10T03:21:59+00:00
- Post Title: 

Thanks for your support!

I should be able to implement some kind of import for this game - I will take a look at it and get back to you soon. Mr Mouse is also working on a script for this game, so I believe, and it should allow importing too.

Thanks again, we will do whatever we can to help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #17
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-10T06:47:23+00:00
- Post Title: 

Thankyou to both guys. I look forward to the importing function.
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-10T11:11:30+00:00
- Post Title: 

Would you please upload one or two more (I noticed you have deleted them fpk files again, naturally). I still need them (and I haven't got them on my laptop yet
## Post #19
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-10T11:35:20+00:00
- Post Title: 

[http://lukereeve.co.uk/Abe.fpk](http://lukereeve.co.uk/Abe.fpk)
[http://lukereeve.co.uk/Fool.fpk](http://lukereeve.co.uk/Fool.fpk)
[http://lukereeve.co.uk/Hitomi.fpk](http://lukereeve.co.uk/Hitomi.fpk)
[http://lukereeve.co.uk/Kaji.fpk](http://lukereeve.co.uk/Kaji.fpk)
[http://lukereeve.co.uk/Marshall.fpk](http://lukereeve.co.uk/Marshall.fpk)
[http://lukereeve.co.uk/Moni.fpk](http://lukereeve.co.uk/Moni.fpk)
[http://lukereeve.co.uk/Scene.fpk](http://lukereeve.co.uk/Scene.fpk)
[http://lukereeve.co.uk/Shader.fpk](http://lukereeve.co.uk/Shader.fpk)
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-10T13:09:47+00:00
- Post Title: 

These links do not work?
## Post #21
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-10T13:42:29+00:00
- Post Title: 

Not sure why this happened - but it got posted twice. See the next message.

WATTO
## Post #22
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-10T13:42:55+00:00
- Post Title: 

Laptops - man I need one of them!

Alright - I have adjusted the Game Extractor plugin to allow the replacing of files in an archive. Download the updated plugin below.

This is the easiest way to replace files...
1. Open an archive and extract all the files you want to replace (to the extract/ directory)
2. Go to the extract directory and edit the files you want to change, or delete the files and replace them with different files of the same name
3. Go back in to Game Extractor and go to File --> Replace Multiple Files
4. Select the extract/ directory and press OK
5. Save the archive.

What this will do is go to every file on the computer (in the extract/ directory), and if a file on the computer has the same name as a file in your archive, the file will be replaced.

Alternatively, you can replace files 1 at a time by selecting the file in the archive that you want to replace, going to File --> Replace Single File, and choosing the new file on your computer.

Hope this helps - good luck. Let me know if you need any assistance.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_FPK.zip](https://xentaxbackup.github.io/file/169_Plugin_FPK.zip)
## Post #23
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-10T15:48:25+00:00
- Post Title: 

Im abouit to go out thanks for the updated plugin! And the fpks should now wokr mr mouse.
## Post #24
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-10T18:05:06+00:00
- Post Title: 

It says the files is reoplaced but it doesnt seem to replace it!
## Post #25
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-11T05:26:20+00:00
- Post Title: 

Hmm yeah, doesn't really work does it  - I will need to look into this because it is a bug somewhere in my program.

Sorry  - Hopefully it will be fixed soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #26
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-11T08:11:57+00:00
- Post Title: 

Ok thankyou so much still! You guys are trying hard!
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-11T09:16:43+00:00
- Post Title: 

There's a little more to the format than meets the eye. For one, in some instances the logic is "fuzzy". That prevends a uniform format to be applied to these files. However, replacement is not a problem, but extracting them with the right filename is, in some instances. 

nevertheless, I am working on it.
## Post #28
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-11T12:08:54+00:00
- Post Title: 

This was a duplicate post again - see the next message.

WATTO
## Post #29
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-11T12:10:33+00:00
- Post Title: 

OK, here is the fix for you. Sorry about that - it must have slipped in there when I made some changes in the last update 

If you are using the Full Version of Game Extractor, put the attached zip into your updates/ directory and run the UpdateInstaller. (don't unzip the file, just put the zip in the updates/ directory)

If you are using the Basic Version of Game Extractor, unzip the *.class file into the main program directory, overwriting the older one.

Good luck - both replace methods should now work in Game Extractor. Thanks for letting me know of the problem. I am also working on a better replace method, but it is taking longer to do than I had anticipated, so you will have to make do with the replace methods that are already in Game Extractor.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[ReplaceFilesBugFix.zip](https://xentaxbackup.github.io/file/171_ReplaceFilesBugFix.zip)
## Post #30
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-11T14:02:31+00:00
- Post Title: 

Hi just a note, now trying it. But the autoupdater doesnt work for me. It freezes on 78% and comes up at the bottom of the list with: "This should not happen."

Update: Also the replacement still doesnt seem to work. I extracted the updated class to the program directory and no luck. So I also extracted it to and replaced the one in the plugins directory to no luck!
## Post #31
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-12T03:00:21+00:00
- Post Title: 

OK, i will need to look into the autoupdater bug.

In the meantime, try this...

1. Put the attachment ZIP in the updates directory
2. Run the UpdateInstaller (not the update tool in Game Extractor!)

Or this, if the above did not work...

1. Unzip the attachment to your computer
2. Open the GameExtractor.jar file in WinZip or another ZIP program
3. Put the unzipped attachment into the GameExtractor.jar archive, overwriting the old file
4. Save the archive, making sure that it is called GameExtractor.jar NOT GameExtractor.zip

Good luck - sorry for all the issues.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #32
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-12T07:08:30+00:00
- Post Title: 

Thankyou, it works a treat now!
## Post #33
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-12T22:32:38+00:00
- Post Title: 

Thank you for letting me know that it worked. Good luck with it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #34
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-19T16:23:58+00:00
- Post Title: 

Finally had some time to work on the plugin I promised, for MultiEx Commander. 

1. Get the attached zip file and put it in the data\plugin directory of MultiEx Commander. 

2. Then, extract it there. You should now have a "fpk" directory. The fpk directory contains the plugin. 

3. Start MultiEx Commander normally and select to open a FPK file ! 

4. If you wish to import (replace) files in a FPK archive, go to the MultiEx Editor. 

Please note that my plugin will extract 100% and give you the correct filenames. Unfortunately, Watto's plugin for Game Extractor does not do the latter. I did try to warn him though  :

> Reply from I
>
> 
There's a little more to the format than meets the eye. For one, in some instances the logic is "fuzzy". That prevends a uniform format to be applied to these files. However, replacement is not a problem, but extracting them with the right filename is, in some instances. 

nevertheless, I am working on it.

Anyway, I sussed the format. Back up any of your FPK files that you wish to replace files from, to be sure. And if you find a bug (either in extraction/importation) let me know. Also, if it WORKS I also would like to know  .
[multiex_fpk_plugin.zip](https://xentaxbackup.github.io/file/182_multiex_fpk_plugin.zip)
## Post #35
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-20T06:00:02+00:00
- Post Title: 

I will have to take a look at the problem and see what I can do to fix it. When you posted that message, I didn't realise that you were implying errors in my plugin - i guess it was just too subtle . Thanks anyway mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #36
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-20T07:19:51+00:00
- Post Title: 

Works a treat thanx! But I get the same filenames through Game extractor.
## Post #37
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-20T07:22:58+00:00
- Post Title: 

Look more closely   When archives have just one or perhaps two directories it works ok. Compare multiple archives and there's a discrepancy.
## Post #38
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-20T07:39:13+00:00
- Post Title: 

Here are two examples in FfoOther.fpk and TexOther.fpk

Compare the encircled areas.
## Post #39
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-20T13:15:48+00:00
- Post Title: 

Hmm OK, thanks for finding some examples - I will take a look-see at my code and try to find out why it is working as it is. Thanks mate!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #40
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-04-20T15:48:21+00:00
- Post Title: 

Oh yeah I was looking at direct file names not directories.
## Post #41
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-05-11T21:27:48+00:00
- Post Title: 

This works great on MultiEx! 
Good Job man! 

I never knew this was made for RAW 2

Did anyone ever make Mods for RAW 2? Never heard of any.
## Post #42
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-06-29T11:08:21+00:00
- Post Title: 

Hmm, didnt use this for a while, but I wanted to use it again today, and it doesnt work anymore  

I get this two error messages

UPDATE:
Nevermind, I figured my HD was full, and there was no room for the program to create the temp file 

But I still get this error, when I am in the import menu, and click like 3-5 times into the right window I get this message and have to restart the program, thats really annoying if you want to replace 3 or more files at a time, only way to get around this, is to replace 2 files, restart the whole program, replace 2 files and repeat 

Is this fixable in some way?
## Post #43
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-29T14:31:04+00:00
- Post Title: 

Interesting. And weird at the same time. Can you send me the debug.log file? Should be in the MultiEx\Data directory. Please try to recreate the behaviour and specify exactly what you do.
## Post #44
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-06-29T15:21:32+00:00
- Post Title: 

Ok here it goes:

1.Open Multi Ex
2.Open TexCharacter0.fpk
3.Rightclick import
4.Click at 4 different files on the right side
5.Right after i clicked on the 4th th error as seen in pic above occurs


> MultiEx Commander - Debug Mode - Log File
>
> -----------------------------------------
>
> mc32, E:\Programme\MultiEx Commander
>
> 4.1.0
>
> -----------------------------------------
>
> 29.06.2005, 17:22:19
>
> 17:22:19 - ]-WebUpdate: user selected :3
>
> 17:22:19 - 17:22:19- Main : Opening MRF file
>
> 17:22:19 - -Main : Mex_FindPlugins
>
> 17:22:19 - -Main : Mex_FindPlugins->Searching
>
> 17:22:19 - -Main : Mex_FindPlugins->PGN at E:\Programme\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
>
> 17:22:19 - -Main : RunAnalysis->Registering attempt of E:\Programme\MultiEx Commander\data\plugins\wad\Sacrifice.dll
>
> 17:22:19 - -Main : RunAnalysis->Progid to connect to Sacrifice.archive
>
> 17:22:19 - Sacrifice WAD Files Extractor
>
> 17:22:19 - -Main : Mex_FindPlugins->PGN at E:\Programme\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
>
> 17:22:19 - -Main : RunAnalysis->Registering attempt of E:\Programme\MultiEx Commander\data\plugins\pak\Painkiller.dll
>
> 17:22:19 - -Main : RunAnalysis->Progid to connect to Painkiller.archive
>
> 17:22:19 - Painkiller PAK Files Extractor
>
> 17:22:19 - - Main : PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
>
> 17:22:19 - -Main : Mex_FindPlugins->PGN at E:\Programme\MultiEx Commander\data\plugins\fpk\WWE.dll for WWE
>
> 17:22:19 - -Main : RunAnalysis->Registering attempt of E:\Programme\MultiEx Commander\data\plugins\fpk\WWE.dll
>
> 17:22:19 - -Main : RunAnalysis->Progid to connect to WWE.archive
>
> 17:22:19 - WWE Raw 2 FPK Files Extractor
>
> 17:22:19 - - Main : PlugIn Called: WWE Raw 2 FPK Files Extractor version 1.0, type (2), importation(1), varsreturned(3), restypespec(0), cancreate(0)
>
> 17:22:19 - -Main : Mex_FindPlugins->PGN at E:\Programme\MultiEx Commander\data\plugins\idx\Survival.dll for Survival
>
> 17:22:19 - -Main : RunAnalysis->Registering attempt of E:\Programme\MultiEx Commander\data\plugins\idx\Survival.dll
>
> 17:22:19 - -Main : RunAnalysis->Progid to connect to Survival.archive
>
> 17:22:19 - Survival IDX/PAK format Extractor
>
> 17:22:19 - - Main : PlugIn Called: Survival IDX/PAK format Extractor version 1.0, type (2), importation(0), varsreturned(3), restypespec(0), cancreate(0)
>
> 17:22:19 - - Main : Loading 
>
> 17:22:19 - - Main : Creating Panels 
>
> 17:22:19 - - Main : Setting Variables 
>
> 17:22:19 - - Main : Preparing Datafile List Columns 
>
> 17:22:19 - - Main : Setting Additional Variables
>
> 17:22:19 - - Main : Loading SupportForm
>
> 17:22:19 - - Main : Setting FileFilter
>
> 17:22:19 - - Main : Enabling All
>
> 17:22:19 - - Main : Creating New Instance
>
> 17:22:19 - - Main : Showing Program
>
> 17:22:20 - - Main : BASS Init called.
>
> 17:22:20 - - Main : DevIL Init called.
>
> 17:22:21 - -Main : RunAnalysis Started
>
> 17:22:21 - - Main : RunAnalysisProcess: Format=PGN
>
> 17:22:21 - -Main : RunAnalysis->Attempting to connect to Plugin
>
> 17:22:21 - -Main : RunAnalysis->Registering attempt of E:\Programme\MultiEx Commander\data\plugins\fpk\WWE.dll
>
> 17:22:21 - -Main : RunAnalysis->Progid to connect to WWE.archive
>
> 17:22:21 - - Main : PlugIn Called: WWE Raw 2 FPK Files Extractor version 1.0, type (2), importation(1), varsreturned(3), restypespec(0), cancreate(0)
>
> 17:22:22 - Main : RunAnalysisProcess: Starting ProcessListFilePGN
>
> 17:22:22 - Main: ProcessListFile: Analyzing Content
## Post #45
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-29T18:10:13+00:00
- Post Title: 

Hmm, okay, the log doesn't help. Perhaps if I can reproduce the behaviour. I would need the .fpk file though, and know which files you click on. Is that possible to arrange?
## Post #46
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-29T18:33:32+00:00
- Post Title: 

Uploading now for you.

Having issues connecting to my server use this link for now:

[http://lukereeve.co.uk/WWE%20RAW%2.rar](http://lukereeve.co.uk/WWE%20RAW%252.rar)

Pass:rawpcheaven

I never encountered the problem as I didnt reimport the files, just extracted them. Also Gameextractor plugin is included as that was the first extracting plugin released.
## Post #47
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-06-29T21:29:07+00:00
- Post Title: 

Uploading the FPK File would be possible, but since the smallest with Textures is 50mb id prefer not to

I think i figured out the problem

I tried the non-texture FPKs and there was no problem, then I tried the .bmp files inside the Tex-FPKs and no problem
the DDS files seem to be the problem, and i think it is the preview of the dds file that causes the program to crash after you clicked 4 of them

Is it possible to just disable the preview?
## Post #48
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-30T04:52:29+00:00
- Post Title: 

> Reply from greendayduh
>
> Uploading now for you.

Having issues connecting to my server use this link for now:

http://lukereeve.co.uk/WWE%20RAW%2.rar

Pass:rawpcheaven

I never encountered the problem as I didnt reimport the files, just extracted them. Also Gameextractor plugin is included as that was the first extracting plugin released.

Hmm, the links fails.     Also, to my knowledge, that GE plugin will extract files with wrong filenames, so you don't know what you're extracting. It wouldn't help.
## Post #49
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-30T04:54:16+00:00
- Post Title: 

> Reply from TheKidRocker
>
> Uploading the FPK File would be possible, but since the smallest with Textures is 50mb id prefer not to

I think i figured out the problem

I tried the non-texture FPKs and there was no problem, then I tried the .bmp files inside the Tex-FPKs and no problem
the DDS files seem to be the problem, and i think it is the preview of the dds file that causes the program to crash after you clicked 4 of them

Is it possible to just disable the preview?

Perhaps, but I'd still want to take a look at what's actually going wrong. The preview can't be disabled at this time.
## Post #50
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-06-30T10:41:19+00:00
- Post Title: 

Ok there you go, here is one of the Tex Files:

EDIT:
Ill send you a PM with FTP Data 
hope it helps, thank u
## Post #51
- Username: greendayduh
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Apr 07, 2005 3:06 am
- Post datetime: 2005-06-30T16:16:22+00:00
- Post Title: 

Mr Mouse you misunderstood. I meant I uploaded that back before MultiEx Commander worked with the FPKs and it was only in there as it was the first one. I now use MultiEx for all tasks!

[http://lukereeve.co.uk/TexCharacter0.rar](http://lukereeve.co.uk/TexCharacter0.rar)

that should work at 17:45 GMT!
## Post #52
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-30T19:52:40+00:00
- Post Title: 

Thanks! Downloaded them... will take a look !
## Post #53
- Username: TheKidRocker
- Rank: VIP member
- Number of posts: 42
- Joined date: Thu May 05, 2005 4:04 am
- Post datetime: 2005-07-07T20:31:16+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Thanks! Downloaded them... will take a look !

Did you have the time to look into this yet?
Any luck?
## Post #54
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-07T20:43:03+00:00
- Post Title: 

Well, the file is ok. There's just something really fishy going on in the plugin I guess, and I haven't pinpointed it yet.  I did recreate the error though. happens right after you click any 5th file. WEIRD....................................
## Post #55
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-08-18T23:09:37+00:00
- Post Title: 

WATTO

How come your program won't allow me to replace files.(I have full version)
## Post #56
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-08-20T05:44:14+00:00
- Post Title: 

Hammer: it depends on whether I have written a replace plugin for this file or not. The way MexCom and Game Extractor work are both quite different - and replacing files in archives is definately where MexCom outshines Game Extractor.

For replacing or repacking to be enabled in Game Extractor, I *kinda* have to write a separate save script for each format. If you have a particular game you want supported for replacing, email me and tell me which one and I will try to write one for you.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #57
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-08-26T02:40:50+00:00
- Post Title: 

Actually I figured out with to do, I forgot to edit the post.


I needed to have the archive I was importing the file in the same folder the replacing file was in or vice versa.
## Post #58
- Username: whogivesaskit
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Apr 19, 2006 10:57 pm
- Post datetime: 2006-05-31T19:42:02+00:00
- Post Title: 

ok here's what i need for the fpk extractor

i opended the file texother.fpk in game extractor adn it gives me the directory 

texture\card\title0.dds

Then i open the same file texother.fpk in multiex and it gives me this directory

Texture\Overlay\Title0.dds

I extracted file with both and it extracts to those directorys

the problem is that when i edit the file and reupload it the xbox it dosen't change the file i think it's cause i'm not actually changing the file i'm changing where the program says the file is not where it actually is

any help would be apprecitave
## Post #59
- Username: Johhny Handsome
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 05, 2006 3:42 am
- Post datetime: 2006-08-04T19:56:28+00:00
- Post Title: 

i know this is an old topic, but by any chance is any willing to write an add and delete script for this plugin(multiex).
