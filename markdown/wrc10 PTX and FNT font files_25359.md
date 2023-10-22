## Post #1
- Username: waltran
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 17, 2022 4:59 am
- Post datetime: 2022-05-16T21:22:53+00:00
- Post Title: wrc10 PTX and FNT font files

hello 
i wanna add/change some letters to for a localisation mod but i am not even able to open these files that i assume are image files. 
There are also corresponding .FNT files probably adressing the letters in these PTX image files.
Both added, appreciate the help   

PTX files:
[https://www12.zippyshare.com/v/x93zo9ik/file.html](https://www12.zippyshare.com/v/x93zo9ik/file.html)

Attached file is .FNT file readable text (these are from WRC9 game but i assume WRC10 files are similar?)
[FONTS.zip](https://xentaxbackup.github.io/file/22235_FONTS.zip)
## Post #2
- Username: waltran
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-17T21:18:28+00:00
- Post Title: wrc10 PTX and FNT font files

Those PTX files are RIFF containers with BC4 compressed image data.

You can view them with rawtex after setting up correct parameters:
[https://imgur.com/a/mzm2j6H](https://imgur.com/a/mzm2j6H)
[https://imgur.com/a/iKq5UcJ](https://imgur.com/a/iKq5UcJ)
[https://imgur.com/a/XgETxox](https://imgur.com/a/XgETxox)

To automate export/import you can try to write Noesis script to support those PTX files.
It seems that there were some scripts made in the past for older games
[viewtopic.php?t=19102](https://forum.xentax.com/viewtopic.php?t=19102)
You can use them as a reference.

As for FNT files, they are really XML files with changed extension.
You can open them in Notepad++ without any issues. [https://imgur.com/a/OldlilM](https://imgur.com/a/OldlilM)
## Post #3
- Username: waltran
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 17, 2022 4:59 am
- Post datetime: 2022-05-18T19:08:16+00:00
- Post Title: wrc10 PTX and FNT font files

thank you very much for the info, 
i have opened the files in rawtext with the 82 offset, but the images are progressively getting slipped by the end so i guess there needs to be another offset for me to find.

i have never heard about noesis before, not really a modding guy but i assume this tutorial on the forum will be a good start [viewtopic.php?t=7760](https://forum.xentax.com/viewtopic.php?t=7760) if the old script doesn't work

edit:
I did a small edit to Acewell's script and was able to export all the images properly! thank you 

is there a way to import them back after i make my edits with the same script?
[tex_WorldRallyChampionship10_ptx.zip](https://xentaxbackup.github.io/file/22238_tex_WorldRallyChampionship10_ptx.zip)
## Post #4
- Username: waltran
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-18T21:20:23+00:00
- Post Title: wrc10 PTX and FNT font files

> is there a way to import them back after i make my edits with the same script?
Yes, there is a way to do it with Noesis.

First you need to declare new handle in registerNoesisTypes() function:

```
noesis.setHandlerWriteRGBA(handle, texWriteRGBA)
```


and then write export function:

```
   // your PTX export logic goes here
```


There are some example scripts shared with Noesis that uses this method.


Whole process of editing PTX after creating a proper function in Noesis would look like this:
1. Open PTX with Acewell's script.
2. Export PTX to DDS (or any other valid type) with Noesis
3. Make your changes in DDS using GIMP, Photoshop etc.
4. Load edited DDS in Noesis.
5. Save it as PTX with your new script with texWriteRGBA function.
6. Put PTX in game and test changes.
