## Post #1
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-09-08T13:28:34+00:00
- Post Title: mp3/vobis fsb?

hi the new fsb format support now vobis and mp3, well is here anyway to exact them/rebulid and replace? like i want to add own music in a game which use this format

sample fsb

[http://www.xup.in/dl,15182181/rrrr.fsb/](http://www.xup.in/dl,15182181/rrrr.fsb/)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-09-08T16:34:30+00:00
- Post Title: mp3/vobis fsb?

There is a way to extract using fsbext from lugi aureimass site. but not rebuolding and repacking the sounds.

But if its multichannel mp3 your screwed, that cannot be extracted.
## Post #3
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2009-09-09T09:15:46+00:00
- Post Title: mp3/vobis fsb?

Actually fsbext also allows rebuild the fsb files BUT that is only direct replacement so same amount files in as there already was and using same filenames as they had in it.

example fsb has two mp3s encoded by fmod's lame 3.98 encoder.

say wanna replace the mp3s in rrrr.fsb

fsbext -s files.dat rrrr.fsb
 doing this gets us the header and other original fsb archive data copied into files.dat and it will also extract the two files to the folder in this case as wav extension (they are mp3 actually) and yes you must know how to use command prompt in windows  

now, you get your own 2 mp3s (keep in mind fsbext does not encode your files, just insert them!) and it might be good idea to remove any ID3 tags just incase...

copy the names of extracted files precisely with the extension they had (in this case wav) and have them replace the extracted ones in same folder.

then rebuild the fsb bank by

fsbext -s files.dat -r output.fsb

and it copies the 2 files it extracted into output.fsb which you may rename as original rrrr.fsb etc

of course the rebuild feature is experimental so use at own risk (haven't done proper test myself), as for the 2 mp3s extracted..they don't normally seem to play unless use vlc media player but its speedy playback oddly.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-09-20T09:55:15+00:00
- Post Title: mp3/vobis fsb?

they are for sure multichannel mp3s.
if you want to substituite them with normal mono/stereo mp3s you can do it but you must manually modify files.dat for setting the correct number of channels.

don't worry it's not much difficult, practically the "numchannels" field in the FSB4 archives is located ever 0x2e bytes after the name.
it means that if you have a hex editor with the width set to 16 bytes it's enough that you go at the end of the filename (over the 00 byte), go down 3 times and at left of 2 bytes.
the numchannels field is just there.

take the following example:

```
63 68 61 6e 2e 77 61 76 00 00 00 00 00 00 00 00   chan.wav........
00 00 00 00 00 00 00 00 80 67 00 00 00 9e 01 00   .........g......
01 00 00 00 9f 64 00 00 00 02 00 04 80 3e 00 00   .....d.......>..
ff 00 80 00 80 00 ff 00 00 00 80 3f 00 40 1c 46   ...........?.@.F
```
the numchannels value is exactly that 0xff byte you see in the middle of the last line, I modified it to that value and when I rebuilt the fsb archive it showed 255 channels :)

in the latest versions of fsbext I have improved a lot the rebuilding function and corrected a lot of bugs so be sure to have the latest 0.2.7a version:
[http://aluigi.org/papers.htm#fsbext](http://aluigi.org/papers.htm#fsbext)

> from lugi aureimass siteoh my poor name... Luigi Auriemma :)
