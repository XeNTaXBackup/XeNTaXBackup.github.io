## Post #1
- Username: camjac251
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 27, 2016 3:07 pm
- Post datetime: 2019-03-01T08:09:00+00:00
- Post Title: Xbox Indie Game: ezmuze samples

I'm trying to obtain the samples used in these 3 games that are very nostalgic at this point. I don't have an xbox 360 anymore and Xenia doesn't work with .exe XNA indie titles, unlike .xex Arcade titles so there's no way for me to emulate this game anymore, and probably even download it official anymore with the indie store being shutdown years ago.

I was able to obtain the 3 games and successfully extract the file using wxPirs but am having trouble extracting the sound files for these 3 games. They all seem to have different archive types.

The one I tried first and the most was ezmuze2, their latest and final game out of the 3. It was structured like 

```
584E07D1\C\Packs\Bass 
584E07D1\C\Packs\Breaks 
584E07D1\C\Packs\Leads 
584E07D1\C\Packs\OneShot 
584E07D1\C\Packs\Vocals
```
 and has what looks like 2 files per each archive, the table of contents and raw .dat file. For example one is 
```
01_Ethnic_Atmospheres~Hamst3r.DAT 01_Ethnic_Atmospheres~Hamst3r.TOC
```


If the table of contents file is opened in plain text, it shows this

```
01.wv|2017|124146
03.wav.png|126163|3820
03.wv|129983|126344
04.wav.png|256327|1650
04.wv|257977|125010
05.wav.png|382987|1343
05.wv|384330|124064
06.wav.png|508394|2063
06.wv|510457|124992
07.wav.png|635449|2872
07.wv|638321|128558
08.wav.png|766879|1191
08.wv|768070|124404
09.wav.png|892474|1208
09.wv|893682|127536
10.wav.png|1021218|1927
10.wv|1023145|124594
11.wav.png|1147739|2903
11.wv|1150642|127350
12.wav.png|1277992|4616
12.wv|1282608|129614
13.wav.png|1412222|1419
13.wv|1413641|122944
14.wav.png|1536585|2834
14.wv|1539419|122612
15.wav.png|1662031|2875
15.wv|1664906|122682
18.wav.png|1787588|1901
18.wv|1789489|125474

```


But I haven't found any extractors that use a TOC file as the input. There was a forum post [https://forum.xentax.com/viewtopic.php?t=17272#p135294](https://forum.xentax.com/viewtopic.php?t=17272#p135294) that I saw about it but I couldn't find a tool to extract with.

The next one, ezmuze hamst3r has its folder structure like this 
```
584E07D1\C\Audio
```
 and XSB and XWB files for each archive. I found an extractor that should read them but it requires an offset found using a hex editor and looking for a specific string but I wasn't able to match what it was requiring so it didn't work.

EZMuze Break and House has a cleaner file structure 

```
584E07D1\Content\Audio\Bass 
584E07D1\Content\Audio\Breaks 
584E07D1\Content\Audio\Lead
```
 and the files appear to be normal XNB files but QuickBMS with the XNB PCM Wav script didn't work for me.

Does anyone know if possibly another game might have an extraction tool that would work for these games? I can supply a sample file if needed. Also I'm not sure if this might be in the wrong section since these are archives not sound files, but they contain them.
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-03-01T19:49:30+00:00
- Post Title: Xbox Indie Game: ezmuze samples

Upload some of the .toc and .dats, I can whip up a parser for them.
## Post #3
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-03-02T18:12:05+00:00
- Post Title: Xbox Indie Game: ezmuze samples

The attached will parse the TOC and DATs. Make sure the TOC and the each DAT that corresponds to its TOC is in the same folder, or extraction will not work. The ".wv" files can be parsed into RIFF WAVs by the provided BMS script. However, I have to figure out why they aren't playing properly, so stay tuned for that. 


Files:


 Toc and Dat.7z
(2.7 KiB) Downloaded 17 times
