## Post #1
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-05-16T10:36:47+00:00
- Post Title: Metro Last Light vfs file

The code for 2033 does not work, this time it's .vfx not .vfi, I have provided a cut of the 1 gb .vfs0 and the .vfx files

[http://www.sendspace.com/file/jwc512](http://www.sendspace.com/file/jwc512)
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-16T17:46:32+00:00
- Post Title: Metro Last Light vfs file

Files are compressed and encrypted as well, not easy task!!
## Post #3
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2013-05-16T18:52:42+00:00
- Post Title: Metro Last Light vfs file

> Reply from michalss
>
> Files are compressed and encrypted as well, not easy task!!

Well I thought it'd be a simple change of code from the previous game extractor, but I guess it must be much more difficult than last time

[viewtopic.php?f=10&p=36125](http://forum.xentax.com/viewtopic.php?f=10&p=36125) <--- previous game "Metro 2033"
## Post #4
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-17T15:32:19+00:00
- Post Title: Metro Last Light vfs file

vfx structure:

```
int ver1; // 0x1
int ver2; // 0x1 - PC, 0x2 - PS3
char hash[16]; // crc or timestamp
long archives_count; // count of .vfs files
long records_count; // count of all file records in .vfx
long records_count2; // only in PS3 version

// archive list
for (i = 0, i < archives_count; i++) {
    string filename; // zero-ended (content.vfs0, motions.vfs0, ...)
    long size;
}

// records list
for (i = 0, i < records_count; i++) {
    short type;

    // if type > 0 then this is a directory
    short entries_num;
    long start_idx;
    string path; // zero-ended xored directory name, 1-st byte is lenght, 2-nd byte is xor base

    // if type == 0 then this is a fiile
    short vfs_idx;
    long offset; // absolute
    long unpacked_size;
    long packed_size;
    string filename; // xored filename, 1-st byte is lenght, 2-nd byte is xor base
}

// second records list (PS3)
for (i = 0, i < records_count2; i++) {
    short num1; // 0x00, ???
    short vfs_index;
    long offset; // absolute
    long unpacked_size;
    long packed_size;
    long num2; // ???
}

```
## Post #5
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-05-17T21:53:18+00:00
- Post Title: Metro Last Light vfs file

so far all I can do is extract the audio, effects and soundtrack, all audio .ogg.
The free tool is the Dragon Unpacker 5
[http://sourceforge.net/projects/dragonu ... t/download](http://sourceforge.net/projects/dragonunpacker/files/latest/download)
File> hyperripper> Formats> ogg> search sounds.vfs0

the question is: really are encrypted files .vfs???
## Post #6
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-17T21:58:09+00:00
- Post Title: Metro Last Light vfs file

> Reply from vitoci
>
> the question is: really are encrypted files .vfs???
no, it is LZ-like compression. see [viewtopic.php?f=21&t=4244](http://forum.xentax.com/viewtopic.php?f=21&t=4244)
## Post #7
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-18T13:11:49+00:00
- Post Title: Metro Last Light vfs file

How can extract patch.vfs0 & patch.vfx0 and content.vfs0 & content.vfx ? Which archive contains localization files?
## Post #8
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-05-18T15:42:36+00:00
- Post Title: Metro Last Light vfs file

> Reply from turkgamer
>
> Which archive contains localization files?
content.vsf0 contains localization files
## Post #9
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-18T16:27:07+00:00
- Post Title: Metro Last Light vfs file

```
content.vfs0
offset     packed  unpacked       name
1296960    814820    387309  stable_cz.lng
1684269   1147568    557990  stable_de.lng
2242259   1057097    517944  stable_es.lng
2760203   1114129    534492  stable_fr.lng
3294695   1088813    530555  stable_it.lng
3825250    853601    385543  stable_nl.lng
4210793    825441    384759  stable_pl.lng
4595552   1029047    533181  stable_ru.lng
5128733   1069656    519116  stable_us.lng

after patch:
patch.vfs0
offset     packed  unpacked       name
1405836    815414    387680  stable_cz.lng
1793516   1148185    558271  stable_de.lng
2351787   1057701    518420  stable_es.lng
2870207   1114728    535131  stable_fr.lng
3405338   1089406    530874  stable_it.lng
3936212    854179    385955  stable_nl.lng
4322167    826039    384916  stable_pl.lng
4707083   1029635    533417  stable_ru.lng
5240500   1070967    519779  stable_us.lng

```
## Post #10
- Username: killerpepo
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-05-18T16:34:14+00:00
- Post Title: Metro Last Light vfs file

Unpacker
[http://rusfolder.com/36430011](http://rusfolder.com/36430011)
## Post #11
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-18T17:20:23+00:00
- Post Title: Metro Last Light vfs file

> Reply from Haoose
>
> Unpacker
http://rusfolder.com/36430011

It doesn't works. When i drag & drop "content.vfs0" to the unpackerLL.exe, i see this screen :
## Post #12
- Username: SanGat
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 07, 2012 11:56 pm
- Post datetime: 2013-05-18T17:36:30+00:00
- Post Title: Metro Last Light vfs file

> Reply from turkgamer
>
> Haoose wrote:Unpacker
http://rusfolder.com/36430011

It doesn't works. When i drag & drop "content.vfs0" to the unpackerLL.exe, i see this screen :
copy unpackerLL.exe to the game folder and then run it (without drag & drop).
## Post #13
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-18T18:02:10+00:00
- Post Title: Metro Last Light vfs file

How can i repack content.vfs0 ? 

Thanks.
## Post #14
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2013-05-19T00:15:13+00:00
- Post Title: Metro Last Light vfs file

thank you very much for the unpacker.
i'm just curious if there's a way to get the
dynamic mesh files such as humans/monsters/animals etc. 
to load up in max/maya/blender/noesis or such.

the "old" tools only seem to work with static props only. and the map files.
[http://code.google.com/p/metro2033-tools/downloads/list](http://code.google.com/p/metro2033-tools/downloads/list)
dynamic mesh models let 3dsmax (2011/2012) crash.
## Post #15
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-19T01:04:05+00:00
- Post Title: Metro Last Light vfs file

I need content.vf0 packer for translation  Please someone help me!
## Post #16
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-19T01:39:18+00:00
- Post Title: Re: Metro Last Light vfs file

unpackerLL.exe does not process "patch.vfs0" :(
## Post #17
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-19T02:24:55+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from hhrhhr
>
> unpackerLL.exe does not process "patch.vfs0"

the unpacker only works in content.vf0.
copy unpackerLL.exe to the game folder and then run it (without drag & drop).
## Post #18
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2013-05-19T05:16:08+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from Haoose
>
> Unpacker
http://rusfolder.com/36430011

can someone post the unpacker on another file share site (not mediafire).  This page doesn't let me download.
thanks
Deposit, Gigapeta, Ul.to, are all good
## Post #19
- Username: fluupke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 24, 2010 7:36 pm
- Post datetime: 2013-05-19T08:35:08+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from rmezatang
>
> Haoose wrote:Unpacker
http://rusfolder.com/36430011

can someone post the unpacker on another file share site (not mediafire).  This page doesn't let me download.
thanks
Deposit, Gigapeta, Ul.to, are all good

[http://ul.to/3qf0v065](http://ul.to/3qf0v065)
## Post #20
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-05-19T10:18:49+00:00
- Post Title: Re: Metro Last Light vfs file

who did such a great job of creating the file unpacker for content.vsf, I just like to kiss that person  (no gay)
## Post #21
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-19T10:30:12+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from vitoci
>
> who did such a great job of creating the file unpacker for content.vsf, I just like to kiss that person
But needs an packer for the translation
## Post #22
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-05-19T18:38:04+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from turkgamer
>
> 
But needs an packer for the translation

I did not find the files with the text strings for the subtitles.
Where they will be??
## Post #23
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-19T18:50:35+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from vitoci
>
> turkgamer wrote:
But needs an packer for the translation 

I did not find the files with the text strings for the subtitles.
Where they will be??
First of all, extract content.vfs0 with this tool :  [http://ul.to/3qf0v065](http://ul.to/3qf0v065) (copy unpackerLL.exe to the game folder and then run it (without drag & drop).)

Then go to "content\localization". You can find localization files there.
## Post #24
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-19T18:53:56+00:00
- Post Title: Re: Metro Last Light vfs file

It seems patch.vf0 also contains localization files.

> Reply from hhrhhr
>
> Code: Select alloriginal:
content.vfs0
offset     packed  unpacked       name
1296960    814820    387309  stable_cz.lng
1684269   1147568    557990  stable_de.lng
2242259   1057097    517944  stable_es.lng
2760203   1114129    534492  stable_fr.lng
3294695   1088813    530555  stable_it.lng
3825250    853601    385543  stable_nl.lng
4210793    825441    384759  stable_pl.lng
4595552   1029047    533181  stable_ru.lng
5128733   1069656    519116  stable_us.lng

after patch:
patch.vfs0
offset     packed  unpacked       name
1405836    815414    387680  stable_cz.lng
1793516   1148185    558271  stable_de.lng
2351787   1057701    518420  stable_es.lng
2870207   1114728    535131  stable_fr.lng
3405338   1089406    530874  stable_it.lng
3936212    854179    385955  stable_nl.lng
4322167    826039    384916  stable_pl.lng
4707083   1029635    533417  stable_ru.lng
5240500   1070967    519779  stable_us.lng

 I wonder which files does the game read the texts from? We should know this first.
## Post #25
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-19T18:54:49+00:00
- Post Title: Re: Metro Last Light vfs file

> If you want to Converter for localization files, contact with me.
share it with us.
## Post #26
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2013-05-20T02:17:39+00:00
- Post Title: Re: Metro Last Light vfs file

If you add a - in exe properties in the desktop, starting the game seem a list of important commands that we can add to the file in the folder user.cfg.
[Captura.PNG](https://xentaxbackup.github.io/file/6414_Captura.PNG)
## Post #27
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-05-20T07:32:06+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from turkgamer
>
> It seems patch.vf0 also contains localization files.
hhrhhr wrote:Code: Select alloriginal:
content.vfs0
offset     packed  unpacked       name
1296960    814820    387309  stable_cz.lng
1684269   1147568    557990  stable_de.lng
2242259   1057097    517944  stable_es.lng
2760203   1114129    534492  stable_fr.lng
3294695   1088813    530555  stable_it.lng
3825250    853601    385543  stable_nl.lng
4210793    825441    384759  stable_pl.lng
4595552   1029047    533181  stable_ru.lng
5128733   1069656    519116  stable_us.lng

after patch:
patch.vfs0
offset     packed  unpacked       name
1405836    815414    387680  stable_cz.lng
1793516   1148185    558271  stable_de.lng
2351787   1057701    518420  stable_es.lng
2870207   1114728    535131  stable_fr.lng
3405338   1089406    530874  stable_it.lng
3936212    854179    385955  stable_nl.lng
4322167    826039    384916  stable_pl.lng
4707083   1029635    533417  stable_ru.lng
5240500   1070967    519779  stable_us.lng


 I wonder which files does the game read the texts from? We should know this first.
Well, almost everytime there is a patch file, the game reads from that. Nonetheless a repacker for the vfs0 file and a converter for the .lng file is needed, if somebody wants to do a translation.
## Post #28
- Username: turkgamer
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Oct 03, 2011 1:16 am
- Post datetime: 2013-05-20T19:16:18+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from lostprophet
>
> turkgamer wrote:It seems patch.vf0 also contains localization files.
hhrhhr wrote:Code: Select alloriginal:
content.vfs0
offset     packed  unpacked       name
1296960    814820    387309  stable_cz.lng
1684269   1147568    557990  stable_de.lng
2242259   1057097    517944  stable_es.lng
2760203   1114129    534492  stable_fr.lng
3294695   1088813    530555  stable_it.lng
3825250    853601    385543  stable_nl.lng
4210793    825441    384759  stable_pl.lng
4595552   1029047    533181  stable_ru.lng
5128733   1069656    519116  stable_us.lng

after patch:
patch.vfs0
offset     packed  unpacked       name
1405836    815414    387680  stable_cz.lng
1793516   1148185    558271  stable_de.lng
2351787   1057701    518420  stable_es.lng
2870207   1114728    535131  stable_fr.lng
3405338   1089406    530874  stable_it.lng
3936212    854179    385955  stable_nl.lng
4322167    826039    384916  stable_pl.lng
4707083   1029635    533417  stable_ru.lng
5240500   1070967    519779  stable_us.lng


 I wonder which files does the game read the texts from? We should know this first.
Well, almost everytime there is a patch file, the game reads from that. Nonetheless a repacker for the vfs0 file and a converter for the .lng file is needed, if somebody wants to do a translation.

It seems we need extract patch.vf0 & content.vs0.
## Post #29
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-05-20T19:53:59+00:00
- Post Title: Re: Metro Last Light vfs file

Here lng inserter only for the patch file. [http://www.sendspace.com/file/468quf](http://www.sendspace.com/file/468quf),Update: now it should work with the new patch too.
Actually it just put the lng at the end of the archive, and change the offset.
Maybe someone make a real packer later.

You can unpack the patch file if you copy both(vfx/s0) into a folder, rename patch.vfx0 to content.vfx and run the unpacker.

Looks like the lng is same format as the old metro, so you can try to edit with this tool: [http://www.sendspace.com/file/8ab0ej](http://www.sendspace.com/file/8ab0ej)
Each lng has its own character table, and you cant add any other character, if its not in the table.
Rename the new lng to orig name, before use the patch inserter.
## Post #30
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2013-05-21T02:22:40+00:00
- Post Title: Re: Metro Last Light vfs file

I have successfully extracted .ogg files from sounds.vfs0 and sounds.us.vfs0 using [Riveal](http://rshayter.net/Riveal/).
I also uploaded [unpackerLL.exe](http://hostr.co/N7AeN3BzSeEq) to another mirror in case if anyone has difficulties with Uploaded and other mirror.
## Post #31
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-05-21T21:55:49+00:00
- Post Title: Re: Metro Last Light vfs file

anyone found where to store font descriptors?
## Post #32
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2013-05-23T11:37:18+00:00
- Post Title: Re: Metro Last Light vfs file

looking forward to see the packer
## Post #33
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-12-31T17:58:46+00:00
- Post Title: Re: Metro Last Light vfs file

If I'd managed to modify the fonts, how could I use those ingame?
There is a program for reinserting the texts, but none for the fonts.
## Post #34
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-01-06T08:38:01+00:00
- Post Title: Re: Metro Last Light vfs file

I've read somewhere a while back, that config.bin should be edited to work with new characters in the font files. How can I edit config.bin?
## Post #35
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-08-29T04:04:25+00:00
- Post Title: Re: Metro Last Light vfs file

For Metro: Last Light Redux tools\script?
## Post #36
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-09-16T21:29:42+00:00
- Post Title: Re: Metro Last Light vfs file

I've found the unpacker for Metro 2033 Redux elsewhere (I think it works with Last Light Redux too). It works the same as Last Light's unpacker (copy it to the game directory and run it).
The texts are still in .LNG files, but they modified something, because swuforce's extractor can't extract them (hangs, waited for like 15 minutes).

Maybe we can figure out how to extract/repack the .lng files (maybe just needs some modification) and also how to inject them back to the vfs0 files (there was one for Last Light, but that one had patch.vfx).

Link to Redux unpacker: (credits go to abramcummer, I think) 
```
http://www54.zippyshare.com/v/82507976/file.html
```

Link to sample lng file: 
```
http://www16.zippyshare.com/v/43711715/file.html
```

Link to swuforce programs for Last Light: 
```
https://www.sendspace.com/file/8ab0e
```
 and 
```
https://www.sendspace.com/file/468quf
```
## Post #37
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-09-22T10:45:47+00:00
- Post Title: Re: Metro Last Light vfs file

Try these tools for the redux: [https://www.sendspace.com/file/m8i2n4](https://www.sendspace.com/file/m8i2n4)
Export, import on the lng. Each lng has its own character table, and you cant add any other character, if its not in the table.

Then copy insert and the lng (rename to orig name) to gamedir, backup content.vfx, run insert select the vfx then the lng.
## Post #38
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2016-01-28T18:02:04+00:00
- Post Title: Re: Metro Last Light vfs file

Most of the links are 404. Attaching the unpackerRedux here for future reference.
[unpackerRedux.zip](https://xentaxbackup.github.io/file/10381_unpackerRedux.zip)
## Post #39
- Username: Doutor Gori
- Rank: n00b
- Number of posts: 11
- Joined date: Tue May 02, 2017 3:15 pm
- Post datetime: 2017-09-10T07:49:31+00:00
- Post Title: Re: Metro Last Light vfs file

how to package the vfs0 file back?
## Post #40
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-12-17T11:23:09+00:00
- Post Title: Re: Metro Last Light vfs file

> Reply from swuforce
>
> Try these tools for the redux: https://www.sendspace.com/file/m8i2n4
Export, import on the lng. Each lng has its own character table, and you cant add any other character, if its not in the table.

Then copy insert and the lng (rename to orig name) to gamedir, backup content.vfx, run insert select the vfx then the lng.
link has been corrupted (
## Post #41
- Username: Tabo8226
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 10, 2012 6:42 pm
- Post datetime: 2018-02-08T10:05:12+00:00
- Post Title: Re: Metro Last Light vfs file

Hello Guys,  someone have LNG tools? extractor I have, but I need LNG tools to translate game, thank you! : )
