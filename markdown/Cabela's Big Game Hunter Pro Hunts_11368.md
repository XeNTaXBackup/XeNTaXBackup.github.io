## Post #1
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-03-28T11:16:01+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

hello everyone, can someone help me to open this games files? there is CRS format, here is example too, if someone knows help me ? 
[http://www.4shared.com/file/Sq8eR9lvce/ ... er_ds.html](http://www.4shared.com/file/Sq8eR9lvce/trophy_tracker_ds.html) here is 1 file...
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-29T14:11:29+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

[http://ps23dformat.wikispaces.com/file/ ... 012CRS.bms](http://ps23dformat.wikispaces.com/file/view/BGH2012CRS.bms)
## Post #3
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-03-29T17:36:23+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

i tried this already, i used search function but it doesn't works that's because i opened this topic
## Post #4
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-29T20:50:58+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

Tabo8226
[http://ps23dformat.wikispaces.com/file/ ... 3andHE.bms](http://ps23dformat.wikispaces.com/file/view/CabelasDH2013andHE.bms)
It's worked

And
[http://ps23dformat.wikispaces.com/file/ ... 012CRS.bms](http://ps23dformat.wikispaces.com/file/view/BGH2012CRS.bms)
too
## Post #5
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-03-29T21:11:39+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

what i am doing wrong? 



Capture.PNG (17.94 KiB) Viewed 260 times
## Post #6
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-03-30T19:49:50+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

Tabo8226
Example:

```
quickbms.exe -w CabelasDH2013andHE.bms gui_textures.crs out
```
## Post #7
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-03-31T07:16:51+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from Tabo8226
>
> what i am doing wrong?

That's exactly the error I get as well, thought that perhaps the script was for the console version of the game or some such but I don't know what that "T" operator actually means.

Tried the above command line parameter as well but it gives the same error message.
(Also tried this BMS as well but it gives the same error - [http://www.extractor.ru/ipb/index.php?showtopic=8588](http://www.extractor.ru/ipb/index.php?showtopic=8588) )

EDIT: Tried against Dangerous Hunts 2013 (CRF) and the recent Big Game Pro Hunter (CRS)

EDIT: Version 0.5.30 of QuickBMS, seems to be the most recent one available.


EDIT: OK that solved it, you need version 0.5.24(b) of the program, seems something changed in the more recent versions and that error occurs.
(The old versions link on the QuickBMS program page - [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm) )
## Post #8
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-03-31T18:57:31+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

yeah that's worked, thanks jbeckman, i have 1 question. can you help me open lang file?  [https://www.dropbox.com/s/y0mteqzgpt5e5 ... ib.eng.tdb](https://www.dropbox.com/s/y0mteqzgpt5e5qx/textlib.eng.tdb)
## Post #9
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-04-02T08:20:03+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from Tabo8226
>
> yeah that's worked, thanks jbeckman, i have 1 question. can you help me open lang file?  https://www.dropbox.com/s/y0mteqzgpt5e5 ... ib.eng.tdb
noone knows?=[
## Post #10
- Username: SlappyT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 13, 2013 2:22 am
- Post datetime: 2014-04-02T13:54:02+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from Tabo8226
>
> Tabo8226 wrote:yeah that's worked, thanks jbeckman, i have 1 question. can you help me open lang file?  https://www.dropbox.com/s/y0mteqzgpt5e5 ... ib.eng.tdb
noone knows?=[

Here is tool for older version of CloakNT engine: [http://graphical-installer.com/temp/gt.zip](http://graphical-installer.com/temp/gt.zip)
This tool can open, import, export texts from the game like Chaser, Gene Troopers, Civil War and many others.

As your game is developed by Cauldron it uses the same engine.
But older games used lower version of engine (CloakNT 2) and this is CloakNT 3 or 3.5 so your file cannot be opened directly in this editor.

The older version can open file with magic word "TLIBv1.0d" and the newer version has "TLIB".
So there are small differences in the files but they are pretty close.

I hope this will help someone to develop updated editor.
## Post #11
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-04-03T17:47:56+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from SlappyT
>
> Tabo8226 wrote:Tabo8226 wrote:yeah that's worked, thanks jbeckman, i have 1 question. can you help me open lang file?  https://www.dropbox.com/s/y0mteqzgpt5e5 ... ib.eng.tdb
noone knows?=[

Here is tool for older version of CloakNT engine: http://graphical-installer.com/temp/gt.zip
This tool can open, import, export texts from the game like Chaser, Gene Troopers, Civil War and many others.

As your game is developed by Cauldron it uses the same engine.
But older games used lower version of engine (CloakNT 2) and this is CloakNT 3 or 3.5 so your file cannot be opened directly in this editor.

The older version can open file with magic word "TLIBv1.0d" and the newer version has "TLIB".
So there are small differences in the files but they are pretty close.

I hope this will help someone to develop updated editor.
i hope too, here are so many developers ^_^
## Post #12
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-04-04T12:10:21+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

I made a tool to extract the .crs bundles.
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-04T12:48:21+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from EcheloCross
>
> Here is a tool to extract the .crs bundles.

I'm posting this hoping someone will figure out the mesh and texture formats.  If someone does, I'll make it repack the .crs.

Enjoy.
Huh your unpacker without decompressing files. They using lzo1x
## Post #14
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-04-04T13:01:29+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from Ekey
>
> Huh your unpacker without decompressing files. They using lzo1x

Thanks, I didn't know that.
## Post #15
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-04-04T15:25:20+00:00
- Post Title: Cabela's Big Game Hunter Pro Hunts

> Reply from Tabo8226
>
> yeah that's worked, thanks jbeckman, i have 1 question. can you help me open lang file?  https://www.dropbox.com/s/y0mteqzgpt5e5 ... ib.eng.tdb
Try this: [http://www.sendspace.com/file/al2y7w](http://www.sendspace.com/file/al2y7w)
## Post #16
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2014-04-06T09:25:14+00:00
- Post Title: Re: Cabela's Big Game Hunter Pro Hunts

it works, thank you guys for help me
## Post #17
- Username: shrek
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 14, 2012 3:07 pm
- Post datetime: 2014-04-08T06:05:08+00:00
- Post Title: Re: Cabela's Big Game Hunter Pro Hunts

I'd like to replace some textures and I managed to extract them but it seems they need to be repacked into the packed archive to be recognized by the game. It didn't work by just putting them into the folder.
@EcheloCross: could you try to make a repacker for it?

What about the model format?
## Post #18
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-04-09T06:22:29+00:00
- Post Title: Re: Cabela's Big Game Hunter Pro Hunts

There's a file in the main game folder, I forgot what it was called but if you open it with notepad it will point towards all the other packed files, this is the same as in Dangerous Hunts 2013 and what you do is that you unpack all those files and then rename this little file so the game will be forced to use the unpacked data instead. 
(The unpacked data goes directly into the main folder, they should already have subfolders and such when extracted.)

I did this to test a few script changes when I tried to hide the games HUD (For screenshots primarily.) and that worked just fine so it should work the same for textures.
## Post #19
- Username: shrek
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 14, 2012 3:07 pm
- Post datetime: 2014-04-09T08:44:33+00:00
- Post Title: Re: Cabela's Big Game Hunter Pro Hunts

I found this file, too, and tried to change it but it didn't work for me.
I'll try again today. Thank you  

->doesn't work. I extracted all files into the main folder. The game doesn't use the extracted files, the info in the "resource_list.rmf" doesn't even match the content of the streams folder in the game. the game crashes without the resource_list.rmf or a missing .crs file in the streams folder. Sometimes it tries to load but doesn't start the level. At least I had time to read all the hints that appear while the game is loading...
There are four regions in the game (SE, NE, SW, NW) with a corresponding crs. file. these files don't appear in the resource_list.rmf but exist in the streams folder, if one of these files is renamed the game hangs.
I coudn't change any texture in the game so far (tried also with the HUD).

Have you tried it with Big Game Hunter Pro Hunts or only with Dangerous Hunts 2013?
## Post #20
- Username: Graagh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 16, 2015 2:58 pm
- Post datetime: 2016-04-22T19:51:54+00:00
- Post Title: Re: Cabela's Big Game Hunter Pro Hunts

> Reply from jbeckman
>
> Tabo8226 wrote:what i am doing wrong? 


That's exactly the error I get as well, thought that perhaps the script was for the console version of the game or some such but I don't know what that "T" operator actually means.

In case anyone is still interested in this, and since the 0.5.24 version of QuickBMS doesn't seem to be available anymore, I believe the "T" operator is the "Then" keyword on the If statement in the scripts, which is invalid syntax in the newer versions.  Just remove the "Then" from the end of the line, and the scripts should work in any version of QuickBMS. (Although, more properly, the != 0 comparison is redundant and should be removed as well.)
