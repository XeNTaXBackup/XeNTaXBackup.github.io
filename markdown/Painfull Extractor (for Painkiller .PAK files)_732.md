## Post #1
- Username: saurav
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T19:37:44+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

Here's version 1.3.2 of Painfull

(Free registration required)

1.3.2 changes 23rd of May 2004

- Added option to delete resources in archives. 
  Use the DEL-key to remove a selected resource. 
  You will be prompted for confirmation. 
- New Painkiller.dll

1.3.1 changes 21st of May 2004

- Added option to make visible the PainEditor when the game is running
  This is crude and will not work if the devs change the window name in
  the future, but for now, it will work! Go to Game->View PainEditor

1.3 changes: 

- Really fixed the 0 sized file issue
- New PAK file support (from scratch) (go to file menu!)
- New PAK file creation (from directory, always compressed)
- Add function implemented (select a file to ADD to the open archive)
  To append, select the last resource in the archive prior Adding. 
  To insert select any other resource and the file with be inserted 
  after the selected resource. 
- New Painkiller.dll
- You can select "Overwrite Names" (Options) and then any changes in the
  resourcename (if you choose to edit the names in the right list) will be
  saved in the archive immediately!

> Reply from Read Me First!!!
>
> 
PainFull Extractor 
Done in 2004 by Mike Zuurman
AKA Mr.Mouse/XeNTaX

Latest Version 1.2.1
SEE BELOW FOR CHANGES

*Purpose

Small archiver to extract stuff (and import files one by one) 
into *.PAK files from the Painkiller game by DreamCatchers. 
Use this for domestic purposes only ! It's a tool for the standard
fan of the game that just wants to mess about with some of the
resources. 

>>>> Remember and respect the authors' copyrights on these files! <<<<

If you want to do something big, be sure to contact them first. 

*Installation
Install MultiEx Commander (http://multiex.xentax.com) first,
you may not need it, but it will ensure you have dlls that you're gonna need.

Then install the all the files in this zip file in one directory of your choice. 

Start with Painfull.exe

*Manual

Just browse to a PAK file of your choice at the left side 
of the tool, select it in the file-list, and hit "Open Painkiller PAK". 
You will notice the contents (entries) listed to the right. 

- Extraction 
  Just select all files at once, clicking on the top file first 
  followed by a click on the last while holding down shift. 
  Alternatively just select the files you want, by holding ctrl. 

  To extract, click the button below and in between the two lists, 
  with "<<" on it. Voila. It will extract the files into the current path. 

- Replacement
  Select a file in the file list that you want to use to replace a file 
  in the open archive. Second, select the file you wish to replace in the 
  contents list. Click the ">>" button, and wait until it's finished. 
  Done. 

  Important Note! PainFull will automatically import the new file, and will 
  NOT create a backup. If you want to mess around with any PAK file, 
  be sure to back it up first and store it somewhere save!

( http://www.xentax.com, 2004 )

 Thanks to Mambox for the initial hint! 

-=-=-=-=-=-=-==-==-=-=-=-=-=-=-=-=

1.2 changes 17th of May 2004

- fixed a few extraction/importation bugs
- removed references to sccrun.dll
- enabled "change filename" (go to options and check the Overwrite Filenames option)
  This is very crude however, it will write the full path of the file you insert, not
  relative to the pak file. 

-=-=-=-=-=-=-==-==-=-=-=-=-=-=-=-=

1.2.1 changes 18th of May 2004

- fixed an issue with files that were 0 in size, but compressed nevertheless by the Painkiller
  team. Gives rise to files of 8 in size (compressed, 0 uncompressed!)
[Painfull.zip](https://xentaxbackup.github.io/file/28_Painfull.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T08:16:52+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

New version 1.3.1 (view the PainEditor)
[painfulledit.jpg](https://xentaxbackup.github.io/file/30_painfulledit.jpg)
## Post #3
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2004-08-06T07:41:56+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

Always get an "archive Not Identified" when trying to extract Painkiller PAK files.

  (I have also installed Multiex Commander.)

  Any ideas??   

  Thanks.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-06T07:48:05+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

No, but you should just use MultiEx Commander to open them. 
Try it, and let me know what happens.
## Post #5
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-06T12:08:51+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

> Reply from Mr.Mouse
>
> No, but you should just use MultiEx Commander to open them. 
Try it, and let me know what happens.
I have tried using the latest MultiEx to open the Maps.pak file from the Painkiller multiplayer demo v1.3 and the Maps1.pak file from the full retail version v1.31,  and in both archives the files in the MOPPCode subdirectory inside the PAK file will not open.  Instead they cause MultiEx to crash.  And ideas why this is so?  The PAK files which come with the game don't have this problem.  PainFull will also extract these files without a problem.

Another bug I have found is that files can't be added to a PAK archive without adding the path to the filename.  Even adding a file from a root drive adds the initial backslash, i.e. \filename instead of just filename.  Files under subdirectories can be added without the preceding backslash so long as the subdirectory is included,  e.g. subdir\filename not just filename.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-06T12:38:46+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

Well, in all probability, they changed the format of the archives YET AGAIN. They've done this twice now. Because they don't want people to open their archives. Interesting...
## Post #7
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-06T19:37:42+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

> Reply from Mr.Mouse
>
> Well, in all probability, they changed the format of the archives YET AGAIN. They've done this twice now. Because they don't want people to open their archives. Interesting...
But that doesn't explain why the other PAK files from that demo and full version work.  It also doesn't explain why PainFull will open them.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-06T19:50:50+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

Okay, well, perhaps these are just a different type of PAK file, that I haven't laid eyes on yet. I don't actually have the game. Perhaps I can download the demo and see for myself. Which file refuses to be opened?
## Post #9
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-06T19:56:17+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

> Reply from Mr.Mouse
>
> Okay, well, perhaps these are just a different type of PAK file, that I haven't laid eyes on yet. I don't actually have the game. Perhaps I can download the demo and see for myself. Which file refuses to be opened?
Get the v1.3 multiplayer demo and try to extract all of maps.pak.  The files in the MOPPCode subdirectory will not preview or open and will cause Multiex to crash.

What is interesting is that these files appear to be created on the hard drive during game play of the correspondingly named map.
## Post #10
- Username: flaz
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Aug 06, 2004 3:38 pm
- Post datetime: 2004-08-07T01:39:41+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

When trying to open the textures.PAK from the Painkiller demo it says "Archive is not Valid." (Using MultiEx)

  I am specifically intersted in the textures. Is there any other known way of extracting them?

  Thanks!
## Post #11
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-07T06:53:51+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

> Reply from flaz
>
> When trying to open the textures.PAK from the Painkiller demo it says "Archive is not Valid." (Using MultiEx)

  I am specifically intersted in the textures. Is there any other known way of extracting them?

  Thanks!
The PainFull program linked in this thread will open all of the Painkiller PAK files for the latest version and the demo.  MultiEX opens them all including the textures.pak file from the demo which you are having a problem with except the files I mentioned above.

The real problem I have with MultiEX is that it can't create a working PAK file for the game.  It puts a backslash before each file listed in the root directory which is wrong.  In addition, it is using backslashes instead of forwardslashes in all paths inside the PAK file which apparently prevents the files from being used by the game.  MultiEX can delete and extract files from the PAK files, but the creation part needs some serious rework for it to function with the game.
## Post #12
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T06:57:22+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

This might be better worked as a plugin
## Post #13
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-07T07:01:34+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

> Reply from Rahly
>
> This might be better worked as a plugin
For MultiEX, the Painkiller file handling is a plug-in (DLL) already.  The problem is that it works less capably as an extractor than the standalone PainFull.exe.
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T07:19:03+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

> Reply from Riley Pizt
>
> Rahly wrote:This might be better worked as a plugin
For MultiEX, the Painkiller file handling is a plug-in (DLL) already.  The problem is that it works less capably as an extractor than the standalone PainFull.exe.

Really? I thought you had a problem creating a file, not extracting.  Creating and extracting are two different things.  Sorry I don't have the source for PainKiller or I could take a look at it.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T08:49:08+00:00
- Post Title: Painfull Extractor (for Painkiller *.PAK files)

You do now, see below. 

Look, I agree with the fact that Painkiller PAK files are not created in a proper manner. The thing is, I've been working on this MultiEx Commander project for a long time, and only recently have started to implement plug-ins this way. Besides that, I have a busy life, that prevends me from doing some hardcore work at a speedy pace. This issues will be addressed sooner or later, as they are all on my to-do list.

If I could find co-workers, who have more experience in this sort of thing, things would look better sooner.   Thus, any who are willing to participate (working on thier own subpart of MultiEx Commander, like plugin-interface, plugins, main interface etc) are more than welcome!
That's why I went "open source".
[painkillerdllsource.zip](https://xentaxbackup.github.io/file/50_painkillerdllsource.zip)
## Post #16
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-07T18:23:49+00:00
- Post Title: Thanks.

> Reply from Mr.Mouse
>
> Look, I agree with the fact that Painkiller PAK files are not created in a proper manner. The thing is, I've been working on this MultiEx Commander project for a long time, and only recently have started to implement plug-ins this way. Besides that, I have a busy life
Mouse, you do fantastic work.  Do not take my criticisms of MultiEX as a personal attack.  However, it is quite frustrating to be so close to a working solution and have it fail because the wrong type of slashes are being used and because slashes are being put in front of files in the root subdirectory in the PAK file.

> If I could find co-workers, who have more experience in this sort of thing, things would look better sooner.   Thus, any who are willing to participate (working on thier own subpart of MultiEx Commander, like plugin-interface, plugins, main interface etc) are more than welcome!
>
> That's why I went "open source".
Fair enough.
## Post #17
- Username: Riley Pizt
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 06, 2004 8:04 pm
- Post datetime: 2004-08-07T18:26:25+00:00
- Post Title: Thanks.

> Reply from Rahly
>
> Really? I thought you had a problem creating a file, not extracting.  Creating and extracting are two different things.
Read all of my previous posts in this thread.  I have two problems with MultiEX.  It won't extract all files from PAK files like PainFull, and it won't create proper PAK files that can be used by the game (which PainFull can't do at all).

Hopefully, you or I or someone can fix the creation problem since it is the most pressing.
## Post #18
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T18:56:44+00:00
- Post Title: Thanks.

Right now, I'm working on a new plugin system for the MultiEx Commander, look in the Misc Forum. I might end up being responsible for new plugins in the future.  Once this system is in place, i'll be converting the old plugins to the new system.  Unfortunately, I don't have a VB6 compiler, and can only make suggested changes.  Whats good about the plugin system, is that it can be in any language that can build a DLL.  Also, I don't have this game.  So I don't know how much help I can be.
## Post #19
- Username: CdeathJd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 23, 2004 9:56 pm
- Post datetime: 2004-08-08T21:52:07+00:00
- Post Title: Thanks.

i get a "runtime error:53: File not found zlib.dll"
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-08T21:53:36+00:00
- Post Title: Thanks.

This error has been discussed before on this forum.
