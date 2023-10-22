## Post #1
- Username: OperateSystemP
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 04, 2015 9:26 am
- Post datetime: 2016-10-02T23:13:30+00:00
- Post Title: Klonoa 2 Textures

I'm looking for a way to rip textures from Klonoa 2. The only way I know so far is by using GGD tools, but that method is a pain to use and inificient as hell.
Everything is inside KLDATA.bin, i've included HEADPACK.bin becasue it contians some header information that could help extracting textures as well.
[https://www.dropbox.com/s/m11lbxd2udn0t ... A.zip?dl=0](https://www.dropbox.com/s/m11lbxd2udn0t01/KLDATA.zip?dl=0)
[https://www.dropbox.com/s/ktvtg77cqfk6w ... K.BIN?dl=0](https://www.dropbox.com/s/ktvtg77cqfk6wbb/HEADPACK.BIN?dl=0)
EDIT: Found something at hex 8AF7D. Looks like sprites?
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-20T01:43:33+00:00
- Post Title: Klonoa 2 Textures

i guess you want to extract files from the archive, a bms script would make this easier
and aluigi could probably write one in a day   

> Reply from OperateSystemP
>
> EDIT: Found something at hex 8AF7D. Looks like sprites?
if you mean the data under the "GIM." headings, i remember seeing gim conversion tools
floating around the web that might work for you. 

edit
they must not be valid gim files because GitMO cannot find them in KLDATA.BIN   
[http://www.richwhitehouse.com/index.php ... itmo11.zip](http://www.richwhitehouse.com/index.php?content=inc_projects.php&filemirror=gitmo11.zip)
## Post #3
- Username: OperateSystemP
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 04, 2015 9:26 am
- Post datetime: 2016-10-23T00:40:01+00:00
- Post Title: Klonoa 2 Textures

> Reply from AceWell
>
> i guess you want to extract files from the archive, a bms script would make this easier
and aluigi could probably write one in a day
Funyn thing is aluigi wrote a script for ripping content from KLDATA and in turn, the other .BIN fiels in the game. But the extraction of KLDATA seems to be really weird, if not broken.
[http://aluigi.altervista.org/bms/klonoa2.bms](http://aluigi.altervista.org/bms/klonoa2.bms)
