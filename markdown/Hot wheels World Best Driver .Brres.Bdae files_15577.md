## Post #1
- Username: Pishu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 06, 2016 1:13 am
- Post datetime: 2016-12-05T17:36:10+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

I was wondering if there is any way to extract the .Brres and .Bdae files of Hot wheels World Best Driver.They are mainly the Texture and Model Files.Several programs are available like(.Brres Viewer) but it works with Wii games files (didnt worked with Hotwheels PC version files).
                      Is there any way to Extract these files from the PC version of the game ?
Here is the link of one of the car of that game..with both of the file formats:
[https://app.box.com/s/sqrcg942tacb87rgh1grifb6cgdmultb](https://app.box.com/s/sqrcg942tacb87rgh1grifb6cgdmultb)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-06T01:30:47+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

here is a bms script to extract the textures from the brres files  

```
get BYTEORDER short
get SKIPZERO short
get UNK long
get BASEOFFSET long
get FILES long
math STRINGOFFSET = FILES
math STRINGOFFSET * 0x18
math STRINGOFFSET + 0x1c
get UNK long
get TOTALDATASIZE long
for i = 0 < FILES
	get UNK long
	get OFFSET long
	math OFFSET + BASEOFFSET
	get SIZE long
	getdstring SKIP 0xc
	savepos TMP
	goto STRINGOFFSET
	get NAME string
	string NAME + ".dds"
	savepos STRINGOFFSET
	log NAME OFFSET SIZE
	goto TMP
next i
```
## Post #3
- Username: Pishu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 06, 2016 1:13 am
- Post datetime: 2016-12-06T02:44:49+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

How to do this..i am totally noob in this...but if you could give some idea about doing it...then i can do it...
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-06T04:48:24+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

download QuickBMS and extract the files
[http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)

create a new txt file and copy the script code into it and save it.
then launch the quickbms.exe
select the new script
then select the archive to extract
then select the output folder
then click the "Save" button
## Post #5
- Username: Pishu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 06, 2016 1:13 am
- Post datetime: 2016-12-07T15:41:45+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

> Reply from AceWell
>
> download QuickBMS and extract the files
http://aluigi.altervista.org/papers/quickbms.zip

create a new txt file and copy the script code into it and save it.
then launch the quickbms.exe
select the new script
then select the archive to extract
then select the output folder
then click the "Save" button
 Yes man it worked for me...    thank you for that...but one problem how to extract those .bdae files....or should there be some importer ?
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-08T00:01:11+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

i don't know about the models, the format looks too exotic/chaotic for me, there
might be a tool out there already that can open them or you could try Hex2obj.
## Post #7
- Username: Pishu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 06, 2016 1:13 am
- Post datetime: 2016-12-11T16:27:19+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

> Reply from AceWell
>
> i don't know about the models, the format looks too exotic/chaotic for me, there
might be a tool out there already that can open them or you could try Hex2obj.
Thanks for the information....there were some cool cars i  wanted to convert....i will try using Hex2obj....as i searched for the tools...but it dosen't seems there i any tool out there...
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-25T13:18:59+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

3 and a half years later and still no solution? As an associated member of RofDHorses club I feel oblieged to contribute...
.



lod0_livery-bdae.png (146.44 KiB) Viewed 153 times
## Post #9
- Username: chad420
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 02, 2020 1:54 pm
- Post datetime: 2021-03-31T23:20:33+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

> Reply from shakotay2 ↑Sat Apr 25, 2020 9:18 pm at Sat Apr 25, 2020 9:18 pm
>
> 
3 and a half years later and still no solution? As an associated member of RofDHorses club I feel oblieged to contribute...
.
lod0_livery-bdae.png

how did you do this?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-01T09:56:27+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

I don't remember (don't have that model sample any more).
## Post #11
- Username: chad420
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 02, 2020 1:54 pm
- Post datetime: 2021-04-12T06:42:43+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

no worries. I will update if i somehow manage to do something
## Post #12
- Username: Einar7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 10, 2021 12:18 pm
- Post datetime: 2022-10-27T23:23:46+00:00
- Post Title: Hot wheels World Best Driver .Brres/.Bdae files

for anyone who may find this of use. I was able to create an extractor for this game a while ago. Its not exactly complete and there are some issues with it(look at readme.txt), but its able to export all the sub-meshes as .obj files with UV coordinates.
[bdae exporter(WBD).zip](https://xentaxbackup.github.io/file/22976_bdae exporter(WBD).zip)
