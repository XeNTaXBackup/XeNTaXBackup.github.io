## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2012-04-29T22:28:19+00:00
- Post Title: Trials Evolution *.pak

Has anyone looked into this? There's a bms script which can unpack the *.pak files for Trials 2 and Trials HD, but it doesn't work with this game. Looking at the files, it looks like the basic format is the same but maybe the compression scheme used is different.

Edit: Fiddling more with this, it seems many files in the archives don't actually have any compression.

If you use this bms script: [http://aluigi.altervista.org/papers/bms/trials2.bms](http://aluigi.altervista.org/papers/bms/trials2.bms) - and add "comtype copy" it'll successfully extract the archives and many files will be as intended. I dunno what compression is used for the compressed files though.
## Post #2
- Username: Kaisonic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 06, 2012 6:14 am
- Post datetime: 2012-05-07T16:26:39+00:00
- Post Title: Trials Evolution *.pak

Awesome find!

And for those music fanatics out there (like me), the music from Trials Evolution can be extracted from music.fsb using [good-ole towav](http://www.ctpax-x.ru/index.php?goto=files&show=24) - just drag and drop music.fsb onto the towav executable and it'll spit out wav's of all the songs.

So to recap (sanity check):

1. Extract the *.pak files from the Trials Evolution Xbox 360 file using something like [wxPirs](http://gael360.free.fr/wxPirs.php)
2. Open Luigi's [Trials2 BMS script](http://aluigi.altervista.org/papers/bms/trials2.bms) in Notepad and add a line with the text "comtype copy" (without quotes)
3. Use [QuickBMS](http://aluigi.altervista.org/quickbms.htm) on the script you just edited and data.pak from Trials Evolution
4. Now to get the music, find music.fsb in the files extracted from data.pak (I think it's soundsystem/xbox/music.fsb)
5. Download towav (above), drag-and-drop music.fsb onto towav, and viola! Trials Evolution soundtrack.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-07T16:45:27+00:00
- Post Title: Trials Evolution *.pak

if you can send me via PM the link to where I can download one of the pak I will try to update the script
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-09T09:04:05+00:00
- Post Title: Trials Evolution *.pak

script updated:
[http://aluigi.org/papers/bms/trials2.bms](http://aluigi.org/papers/bms/trials2.bms)
## Post #5
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-03-04T16:54:33+00:00
- Post Title: Trials Evolution *.pak

Looks like the file format was updated again in Trials Evolution: Gold Edition. Three of the four files extract fine, but the main data.pak file fails. Here's the error, which may not be all that helpful to script writers. I should also note that if I manually rename that first file " pCΣ♀dC╪ÉWC╤─PC╔áHC┼xEC═êLC" I can get a valid Trials XML file, but the process stops after that. The table of contents is still in cleartext at the bottom of the file, and the header still shows xV4, which is the same version? that the other Trials Evolution .paks use.

```
------------------------------
  000149b0 2529       pCΣ♀dC╪ÉWC╤─PC╔áHC┼xEC═êLC▐

- it's not possible to create that file due to its filename or related
  incompatibilities (for example already exists a folder with that name), so
  now you must choose a new filename for saving it.
  if you press RETURN a new name will be generated automatically.
  - old: pCΣ♀dC╪ÉWC╤─PC╔áHC┼xEC═êLC▐
  - new: a

Error: incomplete input file number -1, can't read 25148 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted


Press RETURN to quit
```


I should point out that RedLynx said a while back there *will* be a demo in the future. Dunno when, but if this isn't figured out before then I'll reply later on with a link to the demo. Thanks as always!
## Post #6
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-04T17:51:16+00:00
- Post Title: Trials Evolution *.pak

Teancum, Use Offzip
## Post #7
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-03-05T00:26:46+00:00
- Post Title: Trials Evolution *.pak

It works -- that being said I lose all the filenames and directories. Here's Aluigi's script. I'm going to do my best to dive into the MexScript docs and try to see if I just need to fix an offset or something.

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "\x78\x56\x34\x12"
get OFFSET long
get FILES long
savepos INFO_OFF

math TMP = FILES
math TMP -= 1
math TMP *= 17
math TMP += INFO_OFF
goto TMP
    get DUMMY long
    get ZSIZE long
    get SIZE long
    get ZIP byte
    get OFFSET long
if ZIP == 0
    log MEMORY_FILE OFFSET SIZE
else
    clog MEMORY_FILE OFFSET ZSIZE SIZE
endif

get FILES long MEMORY_FILE
goto INFO_OFF
for i = 0 < FILES
    get DUMMY long
    get ZSIZE long
    get SIZE long
    get ZIP byte
    get OFFSET long
    get NAMESZ short MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE

    if ZIP == 0
        log NAME OFFSET SIZE
    elif ZIP == 4
        comtype xmemdecompress
        savepos TMP
        goto OFFSET
        get SIZE long
        get ZSIZE long
        savepos OFFSET
        clog NAME OFFSET ZSIZE SIZE
        goto TMP
    else
        comtype zlib
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

```
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-06T12:50:29+00:00
- Post Title: Trials Evolution *.pak

I have seen the pak but the names table is obfuscated in some way so I have updated the script to work on these archives but the files will be extracted without name.
## Post #9
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-03-06T23:48:40+00:00
- Post Title: Trials Evolution *.pak

Obfuscated how? I don't know much, but I know the names are in cleartext in the pak. Again, I don't know much, I just wasn't sure if you saw it.

**EDIT**

Do the files extract in order? If so I can peacemeal the directories back together. The game can run content outside of the archives, so I plan to use some modified files but need to get the structure and names correct.
## Post #10
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-03-07T06:28:10+00:00
- Post Title: Trials Evolution *.pak

Teancum
[http://yadi.sk/d/j34Q5u2W3-eXZ](http://yadi.sk/d/j34Q5u2W3-eXZ)
Import 4 files in data.pak =)
[](http://savepic.ru/4254823.png)


 Trials Evolution Gold Edition Beta - Tools by Haoose.rar
(187.32 KiB) Downloaded 43 times
## Post #11
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2013-03-07T15:57:08+00:00
- Post Title: Trials Evolution *.pak

Did I need to understand that there's a way to unpack all the files from the .pak archives with properly names or nope?

And Hoose, what are your tools for?

I haven't downloaded them, because I'm browsing from my phone now.
## Post #12
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-03-07T19:42:43+00:00
- Post Title: Trials Evolution *.pak

> Reply from Haoose
>
> Teancum
http://yadi.sk/d/j34Q5u2W3-eXZ
Import 4 files in data.pak =)

Trials Evolution Gold Edition Beta - Tools by Haoose.rar

I was hoping to do cross-functionality between the PC and 360 versions, thus why I want to extract the files. But this is great, too.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-09T09:32:08+00:00
- Post Title: Trials Evolution *.pak

I have updated the script trying to auto guess the file entry where is located the namestable.
In fact, as Teancum noticed, it's not longer the last file to contain the names but I have found no other references regarding what of them does this job now so I simply try to compare the number of FILES+1 in it and the number of FILES in the archive... seems to work :)

[http://aluigi.org/papers/bms/trials2.bms](http://aluigi.org/papers/bms/trials2.bms)
## Post #14
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2013-03-09T15:52:52+00:00
- Post Title: Trials Evolution *.pak

Seems to work perfectly! Thanks Aluigi!
