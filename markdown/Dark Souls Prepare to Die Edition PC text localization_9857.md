## Post #1
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2012-11-11T17:21:39+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

Rick's tool for Dark Souls can extract the texts in .msg files, I just want to ask if there's any way to make them editable?
## Post #2
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2013-04-30T12:13:19+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

anyone?
## Post #3
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-02-04T09:24:46+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

It is a really old topic, but if someone still interested here some tools to try to edit texts. [http://www.sendspace.com/file/cbhe3v](http://www.sendspace.com/file/cbhe3v)
I use the scripts made by chrrox.
I test this on 1.02 game version.
Unpack tools to a folder and you need the latest Quickbms to put beside the tools.

Copy dvdbnd3.bdt and dvdbnd3.bnd5 to folder and drag & drop to bdt_unpack.bat.
Select the files from unpacked folder. English texts are 7.bnd and 15.bnd.
Drag a bnd to bnd_unpack.bat. Run text_export.exe and select the bnd_unpacked folder.
Edit text, run text_import.exe select the txt file and the bnd_unpacked folder.
Run bnd_import.exe select the bnd and the bnd_unpacked folder.
Make a folder named import and put the bnd file there.
Run bdt_import.exe, select dvdbnd3.bdt and the import folder. Quickbms use better zlib compression, so i think import will work even if the file is bigger than original.
## Post #4
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2014-02-04T21:10:47+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

Does anyone know where is stored fonts? Which archive or file? Thanks.
## Post #5
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2014-02-04T21:53:31+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

> Reply from swuforce
>
> It is a really old topic, but if someone still interested here some tools to try to edit texts. http://www.sendspace.com/file/jzsuxz
I use the scripts made by chrrox.
I test this on 1.02 game version.
Unpack tools to a folder and you need the latest Quickbms to put beside the tools.

Copy dvdbnd3.bdt and dvdbnd3.bnd5 to folder and drag & drop to bdt_unpack.bat.
Select the files from unpacked folder. English texts are 7.bnd and 15.bnd.
Drag a bnd to bnd_unpack.bat. Run text_export.exe and select the bnd_unpacked folder.
Edit text, run text_import.exe select the txt file and the bnd_unpacked folder.
Run bnd_import.exe select the bnd and the bnd_unpacked folder.
Make a folder named import and put the bnd file there.
Run bdt_import.exe, select dvdbnd3.bdt and the import folder. Quickbms use better zlib compression, so i think import will work even if the file is bigger than original.

I followed your manual to the letter, and the tools worked just fine until I tried to import the modified 7.bnd (put in a separate folder named 'import' created in the directory where the DS tools were extracted to) with bdt_import.exe. The program always returns with the message:

Error: wrong command-line argument (bdt_import.bms)

I used the dvdbnd3.bdt from Dark Souls patched to 1.02, and the latest (v0.5.29) version of QuickBMS. I could use some help.
## Post #6
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2014-02-04T23:33:53+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

GRiNDERKILLER > dvdbnd1 in font folder
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-02-05T08:31:45+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

> Reply from Rion
>
> 
Error: wrong command-line argument (bdt_import.bms)
Ok, i think should be work now, updated the link. If still not works, try to put all the files in somewhere else, eg c:\tools folder.
## Post #8
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2014-02-05T10:17:40+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

Thanks, swuforce, this time the bdt_import seemed to work, though the size of dvdbnd3.bdt didn't change after import (searched for another bdt, but this is the only one in the whole folder structure), and using it the game still shows the original English subtitles. Now I've tried it again, edited the text so it doesn't contain some non-English characters which might hinder the process, the text again seems to import just fine into the 7.bnd, its size has changed, but still, when I run bdt_import to merge the .bnd with a newly copied, untouched dvdbnd3.bdt taken from the game folder (the .bhd5 is also next to it), the size of the .bdt doesn't change at all, neither its date - meaning there's no modification, it doesn't import anything into it.

I start to think it's me doing something wrong.
## Post #9
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2014-02-05T16:37:33+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

Thanks hyndai for tip
## Post #10
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2014-03-11T17:55:29+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

I tried it all over again, with another release of the game, but the bdt_import process just doesn't work for me. Used again the original dvdbnd3.bdt with a (barely) modified 7.bnd put in a separate folder named import. The program says it's finished and the file date of the bdt is also updated, so it must be modified as well, yet the new texts just won't appear, only the original English. Can it be that the Eng language file doesn't recognize characters which are not normally English (like ú, á, and other CE characters)?
## Post #11
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-03-13T22:19:18+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

> Reply from swuforce
>
> It is a really old topic, but if someone still interested here some tools to try to edit texts. http://www.sendspace.com/file/cbhe3v
I use the scripts made by chrrox.
I test this on 1.02 game version.
Unpack tools to a folder and you need the latest Quickbms to put beside the tools.

Copy dvdbnd3.bdt and dvdbnd3.bnd5 to folder and drag & drop to bdt_unpack.bat.
Select the files from unpacked folder. English texts are 7.bnd and 15.bnd.
Drag a bnd to bnd_unpack.bat. Run text_export.exe and select the bnd_unpacked folder.
Edit text, run text_import.exe select the txt file and the bnd_unpacked folder.
Run bnd_import.exe select the bnd and the bnd_unpacked folder.
Make a folder named import and put the bnd file there.
Run bdt_import.exe, select dvdbnd3.bdt and the import folder. Quickbms use better zlib compression, so i think import will work even if the file is bigger than original.

does anyone have the script ?
## Post #12
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2016-09-20T21:20:30+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

Please reupload tnx or anybody tools for xbox/ps3 ?

> Reply from swuforce
>
> It is a really old topic, but if someone still interested here some tools to try to edit texts. http://www.sendspace.com/file/cbhe3v
I use the scripts made by chrrox.
I test this on 1.02 game version.
Unpack tools to a folder and you need the latest Quickbms to put beside the tools.

Copy dvdbnd3.bdt and dvdbnd3.bnd5 to folder and drag & drop to bdt_unpack.bat.
Select the files from unpacked folder. English texts are 7.bnd and 15.bnd.
Drag a bnd to bnd_unpack.bat. Run text_export.exe and select the bnd_unpacked folder.
Edit text, run text_import.exe select the txt file and the bnd_unpacked folder.
Run bnd_import.exe select the bnd and the bnd_unpacked folder.
Make a folder named import and put the bnd file there.
Run bdt_import.exe, select dvdbnd3.bdt and the import folder. Quickbms use better zlib compression, so i think import will work even if the file is bigger than original.
## Post #13
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2016-09-21T00:18:28+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

@dvoika
Try this: [https://yadi.sk/d/rHc3js00vTYbS](https://yadi.sk/d/rHc3js00vTYbS)
## Post #14
- Username: javurek91
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Feb 09, 2014 9:29 pm
- Post datetime: 2016-09-21T15:54:56+00:00
- Post Title: Dark Souls: Prepare to Die Edition PC text localization

> Reply from makcar
>
> @dvoika
Try this: https://yadi.sk/d/rHc3js00vTYbS

Hello, this tools isn't working with PS3 or X360. There is no possible to export text from .msgbnd files.
Please do you have a tool for export and import text for PS3 and X360? 
   Thank you so much with best regards javurek91
