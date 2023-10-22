## Post #1
- Username: ItsmeJC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 30, 2009 7:40 am
- Post datetime: 2009-04-30T23:22:00+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-01T00:27:01+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

wasn't needed to upload 150 megabytes of files moreover because texture3d.xml (attached in case someone doesn't want to download the whole package) and texture3d.pak were more than enough.

with a bit of luck I have been able to parse the xml file and the following is the script for extracting the files:
```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get MYFILEEXT extension
if MYFILEEXT == "xml"
    open FDDE PAK 0
endif

open FDDE XML 1

for
    findloc NAME_OFF string "src='" 1
    if NAME_OFF == 0
        cleanexit 
    endif

    math NAME_OFF += 5
    goto NAME_OFF 1
    getdstring DUMMY 3 1    # skip the r:\ stuff
    getct NAME string 0x27 1

    findloc SIZE_OFF string "size='" 1
    math SIZE_OFF += 6
    goto SIZE_OFF 1
    getct SIZE string 0x27 1

    findloc OFFSET_OFF string "offset='" 1
    math OFFSET_OFF += 8
    goto OFFSET_OFF 1
    getct OFFSET string 0x27 1

    log NAME OFFSET SIZE
next
```

[texture3d.zip](https://xentaxbackup.github.io/file/2006_texture3d.zip)
## Post #3
- Username: ItsmeJC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 30, 2009 7:40 am
- Post datetime: 2009-05-01T16:19:19+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Thanks worked great.   

(my bad for including the big archive, wasn't sure how much was needed)

Anyone know what kind of compression the scripts have 
[scripts.rar](https://xentaxbackup.github.io/file/2007_scripts.rar)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-01T16:59:00+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

it's a classical zlib compression.

the following script can be used to decompress the chosed lua file:

```
if ZIP != 1
    cleanexit
endif

get NAME filename
string NAME += ".unzip"
get ZSIZE long
get SIZE long
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE
```
the output file will have a .unzip extension just to avoid to overwrite the original file
## Post #5
- Username: ItsmeJC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Apr 30, 2009 7:40 am
- Post datetime: 2009-05-01T17:42:00+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Thanks man, you rock
## Post #6
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-06-13T19:15:25+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

And how to pack it all back to .pak file?
## Post #7
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2010-04-30T17:52:51+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

I managed to extract the *.pak, but I can not edit the *.dlg and locale.ptxt4. I know that are text but I need help to edit them.

And, has some way to repack the files back to *.pak?

The file *.dlg and locale.ptxt4 are attached.
Thank you for your attention and help.

<link removed due forum rules violation>
## Post #8
- Username: JBieber
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2010 1:01 am
- Post datetime: 2010-10-03T01:54:36+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

> Reply from bhrun
>
> I managed to extract the *.pak, but I can not edit the *.dlg and locale.ptxt4. I know that are text but I need help to edit them.

And, has some way to repack the files back to *.pak?

The file *.dlg and locale.ptxt4 are attached.
Thank you for your attention and help.
+1 I need too. Please boys
## Post #9
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-03T09:03:03+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Here are my simple, work-in-progress tools.

pak_extr.exe     -> You can open and extract the .pak files, and you can replace a signle file in the .pak archive. The .pak maker function will be available soon!
Important: You don't need the .xml file-s for the .pak file handling!
ptxt4_viewer.exe -> This is just a viewer for the locale.ptxt files. (There are no editing, exporting, importing functions yet.)
## Post #10
- Username: JBieber
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 03, 2010 1:01 am
- Post datetime: 2010-10-03T09:19:09+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Thank you bacter     The tools work great but please update it for more options. I need to edit ptxt4 file. This tool working for sherlock holmes vs arsen lupin and The Awekened right?   That's wonderful.
## Post #11
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2010-10-06T13:46:13+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

I want to translate the game into my own language too. If you can include an option to make that possible it will be awesome!
## Post #12
- Username: deciasss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 31, 2010 3:25 am
- Post datetime: 2010-10-31T07:34:04+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Hi Xentax,

I would like to extract the music (it's on .ogg file format) of the game "Sherlock Holmes vs Jack the Ripper". I think it's on "sounds.pak" (with "sounds.xml") but I don't know how to extrack .pak archives. What do I have to do? Ideas? Thanks for all!   

Deciasss
Madrid, Spain
## Post #13
- Username: deciasss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 31, 2010 3:25 am
- Post datetime: 2010-10-31T07:39:17+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Thanks for all! With "pak_extr.exe" it's possible!!
## Post #14
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-01-08T09:05:50+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Here is my the new, .PAK maker utility! I hope that works.
A little tricky, so don't forget to read the instructions in the About... box.
## Post #15
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-01-22T12:36:13+00:00
- Post Title: Sherlock Holmes vs Jack the Ripper *.pak archive

Thank you guy's. You are incredible.
## Post #16
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-02-22T17:03:35+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

Here's the long waited "brother" of my previous .PAK maker utility:
The .PTXT4 file viewer / exporter / importer!
Now you can export the "locale.ptxt4" to editable, unicode text file, and then you can import back the modified texts.
## Post #17
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-10-26T16:09:31+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

> Reply from bacter
>
> Here's the long waited "brother" of my previous .PAK maker utility:
The .PTXT4 file viewer / exporter / importer!
Now you can export the "locale.ptxt4" to editable, unicode text file, and then you can import back the modified texts.

Sorry for the bump, but can you upload your tools again, please? they will be very useful for me. thank you
## Post #18
- Username: vitorrs100
- Rank: advanced
- Number of posts: 76
- Joined date: Sun Dec 12, 2010 1:39 am
- Post datetime: 2011-10-29T19:51:37+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

Please, someone can upload the tools?
## Post #19
- Username: shgim35
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 05, 2011 11:22 am
- Post datetime: 2011-12-05T03:29:31+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

> Reply from bacter
>
> Here are my simple, work-in-progress tools.

pak_extr.exe     -> You can open and extract the .pak files, and you can replace a signle file in the .pak archive. The .pak maker function will be available soon!
Important: You don't need the .xml file-s for the .pak file handling!
ptxt4_viewer.exe -> This is just a viewer for the locale.ptxt files. (There are no editing, exporting, importing functions yet.)

How can I download those tools?
There is no link in this post now. Please let me know.
## Post #20
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-04-18T23:27:28+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

Are the tools available anywhere? Please, help.
## Post #21
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-04-19T13:08:12+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

Here:[https://www.sendspace.com/file/1hdqy3](https://www.sendspace.com/file/1hdqy3)

Dont know why bacter remove all of his great tools.
## Post #22
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-04-19T18:15:58+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

Thank you, swuforce. You have my thanks. Fingers crossed that this works with Dracula: Love Kills as I hope it is...
## Post #23
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-04-21T01:11:34+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

It seems that the tools work fine with Dracula: Love Kills which is splendid news for me! I am currently translating the game, thank you very much, bacter for creating the tools that make it possible and swuforce for supplying them to me!
## Post #24
- Username: achiko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 03, 2012 3:35 am
- Post datetime: 2012-08-02T20:03:37+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

i did that... now i want to know how to make new font for sherlock... texture\font\en - in this file there is font texture, which i can edit, but what is it font1.font - i aviable to edit it too????
## Post #25
- Username: achiko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 03, 2012 3:35 am
- Post datetime: 2012-08-02T20:07:07+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

or i must to edit files on this folder? .texture\locales\en\normal\games\alphabet
## Post #26
- Username: achiko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 03, 2012 3:35 am
- Post datetime: 2012-08-03T06:24:58+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

i also want to edit sounds, i can edit ogg files, but am i aviable to edit .LIP files?!
## Post #27
- Username: hgdagon
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 07, 2014 10:39 am
- Post datetime: 2015-11-05T10:04:03+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

Could someone, please, reupload the tools or maybe PM?
## Post #28
- Username: dyermaker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 29, 2017 7:36 pm
- Post datetime: 2017-04-29T11:55:05+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

I know it's been a long time but, can someone upload the tools again, please?
## Post #29
- Username: erniethecat
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 04, 2017 2:19 am
- Post datetime: 2017-06-12T13:49:47+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

No one knows how to download bacter's tools yet? Script in the first page does not unpack my .pak files if that is what it's intention.
## Post #30
- Username: Doutor Gori
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 02, 2017 3:15 pm
- Post datetime: 2017-08-14T20:02:44+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

> Reply from erniethecat
>
> No one knows how to download bacter's tools yet? Script in the first page does not unpack my .pak files if that is what it's intention.

Tools

[viewtopic.php?f=10&t=16617](http://forum.xentax.com/viewtopic.php?f=10&t=16617)
## Post #31
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-03-26T00:54:09+00:00
- Post Title: Re: Sherlock Holmes vs Jack the Ripper *.pak archive

I'm interested in extracting assets from this game too, but in order for to have proper file names, I need the .xml files. Could someone send them to me so that I don't have to wait for long downloads of the game?
