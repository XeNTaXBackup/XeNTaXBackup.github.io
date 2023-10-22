## Post #1
- Username: MarcosMC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 23, 2010 4:42 pm
- Post datetime: 2010-09-23T09:00:45+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

Hi!
  I have an. PKF unpacking very easy (in hexadecimal: after the file path, the first four bytes is the beginning of the file and the following 4 size). But there. Xml zlib compressed. How I can uncompress them?

Thanks
## Post #2
- Username: Hawkear
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 06, 2010 10:00 pm
- Post datetime: 2010-09-25T13:56:48+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

Use this script:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "PACKAGE "
endian big
comtype zlib_noerror
get UNKNOWN1 long
get UNKNOWN4 short
get HEADEREND long

do
    get UNKNOWN5 long
    get FILENAME string
    get OFFSET long
    get SIZE long
#    print "Filename %FILENAME% Offset %OFFSET% Length %SIZE%"
    savepos POS
    goto OFFSET
        get ZLIB long
        get UNKNOWN6 long
        get USIZE long
    goto POS
    if ZLIB == 1514948930    # ZLIB compressed
        math OFFSET += 12
        math SIZE -= 12
        clog FILENAME OFFSET SIZE USIZE
    else                    # uncompressed
        log FILENAME OFFSET SIZE
    endif
while POS < HEADEREND

```
## Post #3
- Username: k4roshi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 15, 2010 1:07 am
- Post datetime: 2010-09-26T12:46:57+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

the pkf script works wonders.. i think the pkd's is where the beef is, but they seem to be encrypted..
Anyway i noticed that /dev_hdd0/game/BCES00011SINGSTARFAMILY/USRDIR in the ps3 hard drive stores the dlc. Unfortunately I don't have any and obviously (as i'm on 3.41) i cannot download any now, if anyone has it he should have a look at how they're stored, so that we can add more songs, maybe from ps2 singstars or even custom ones.
## Post #4
- Username: MarcosMC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 23, 2010 4:42 pm
- Post datetime: 2010-09-27T06:22:14+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

Thanks Hawkear!!!!

   plugin for .PKD's?
## Post #5
- Username: wallflow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 29, 2010 5:37 pm
- Post datetime: 2010-09-29T09:47:16+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

> Reply from k4roshi
>
> the pkf script works wonders.. i think the pkd's is where the beef is, but they seem to be encrypted..
Anyway i noticed that /dev_hdd0/game/BCES00011SINGSTARFAMILY/USRDIR in the ps3 hard drive stores the dlc. Unfortunately I don't have any and obviously (as i'm on 3.41) i cannot download any now, if anyone has it he should have a look at how they're stored, so that we can add more songs, maybe from ps2 singstars or even custom ones.

Songs from singstore comes with some DRM protection/encryption (file extension are like this Pack0_XXXXX.pkg.drm).
If anyone know how to remove DRM from these files, we can easily unpack and pack again (it seem a standard PS3 PKG file with DRM protection/encryption).

I think like you, "PKD's seems to be where the beef is".
## Post #6
- Username: MarcosMC
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 23, 2010 4:42 pm
- Post datetime: 2010-10-04T14:25:17+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

[http://www.darklock.com/thps/pklayout.html](http://www.darklock.com/thps/pklayout.html)
## Post #7
- Username: bm1
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2011-03-20T11:30:10+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

hi guys.
Any news on this?
I'd love to put some more songs in.
## Post #8
- Username: Robberson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 08, 2011 3:03 pm
- Post datetime: 2011-10-08T07:07:05+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

Anyway i noticed that /dev_hdd0/game/BCES00011SINGSTARFAMILY/USRDIR in the ps3 hard drive stores the dlc. Unfortunately I don't have any and obviously (as i'm on 3.41) i cannot download any now, if anyone has it he should have a look at how they're stored, so that we can add more songs, maybe from ps2 singstars or even custom ones.


--------------------------------------------------------------
[wii remote controller](http://www.708buy.com/deal/nintendo-wii-remote)[xbox 360 controllers](http://www.708buy.com/deal/xbox-360-controllers)[ps3 accessories](http://www.708buy.com/deal/ps3-accessories-xbox360-accessories-wii-accessories)
## Post #9
- Username: blubber
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 16, 2013 4:58 am
- Post datetime: 2013-08-17T23:39:37+00:00
- Post Title: Singstar (PS3) .pkf file with zlib

> Reply from Robberson
>
> Anyway i noticed that /dev_hdd0/game/BCES00011SINGSTARFAMILY/USRDIR in the ps3 hard drive stores the dlc. Unfortunately I don't have any and obviously (as i'm on 3.41) i cannot download any now, if anyone has it he should have a look at how they're stored, so that we can add more songs, maybe from ps2 singstars or even custom ones.

I bought a Song (and 2 Demo Songs) and backed them up.

The Songs are safed as ".pkg.drm"

The names for Example are:
"Pack0_100SW6.pkg.drm"
"Pack0_100SXO.pkg.drm"

You can't extract them like normal pkg's.


BTW: There is another Folder "SongCache" in which the previews are stored and the preview files are NOT crypted!
Every Song/Video have his own Folder, for example:
"Prod_Sku_100SW6"

acts_1_0.xml
acts_2_0.xml
acts_3_0.xml
acts_4_0.xml
acts_5_0.xml
acts_6_0.xml
config.xml
covers.xml
melodies_1.chc
melodies_2.chc
melodies_3.chc
melodies_4.chc
melodies_5.chc
melodies_6.chc
songs_1_0.xml
songs_2_0.xml
songs_3_0.xml
songs_4_0.xml
songs_5_0.xml
songs_6_0.xml

and two Folder:
37446
melody_1.xml
melody_2.xml
melody_3.xml
melody_4.xml
melody_5.xml
melody_6.xml
preview.mp4

textures
page_0.jpg


I just wonder if it would be possible to copy all my Singstar Songs from the DVDs (Ps2)/Blu-rays(PS3) to my HDD so i don't have to change the Disc's all the time and search the songs on all the Backsides of the dvd's.

Like @wallflow already said:
The main Problem is the encrypted .pkg.drm
if we could extract them and repack them, we could import all our DVD/Blu-Ray Songs as "Downloaded Songs".

Edit: If anyone is interested in the files and want to do some research, write me a message.
