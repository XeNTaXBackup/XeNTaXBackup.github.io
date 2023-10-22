## Post #1
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2019-02-14T12:35:30+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

I downloaded a PSVITA game made by Compile Heart. Most game files are in .pck format. I'm looking for help in extracting these files.
Here is a file called PatternFade.pck extracted from the game. I believed it is a package consists of serveral .tex files. Is it possible to extract these .pck files? 

File: [https://www.dropbox.com/s/t0exs3fll4whv ... e.pck?dl=0](https://www.dropbox.com/s/t0exs3fll4whvz4/PatternFade.pck?dl=0)
## Post #2
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2019-02-14T18:00:25+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

PCK is a game archive, in this case it's the same as Hyperdevotion Noire.
TEX are zlib'd and 8bit palletized, palette is right after the image data.
I didn't encounter 8bit palletized images in Hyperdevotion Noire PC back in 2016, so my script doesn't apply the palette.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-15T00:44:19+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

and because i like to dabble with anything graphics related i used 
TheUkrainianBard's findings to make a bms script to extract and
decompress the tex files from pck sample on the fly and
the Noesis python script opens the extracted tex samples.  


 CompileHeart.zip
(1.11 KiB) Downloaded 104 times


the scripts cater only to your sample and for this game.
## Post #4
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2019-02-15T07:45:30+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Using your help I was able to extract .pck files. Now I encounter a .tex file. I thought I can use the same BMS Script I used to decrypt a Date A Live game but I was wrong. This file contains ZLIB header. And I can get some .pck files from the extracted .pck file. They also have the ZLIB header. Can someone help me with extracting these .tex and ZLIB .pck files?

BG0001.tex file: [https://www.dropbox.com/s/5tj2kh48rg381 ... 1.tex?dl=0](https://www.dropbox.com/s/5tj2kh48rg381zg/BG0001.tex?dl=0)
MA010100.pck file: [https://www.dropbox.com/s/3kmlgy7qqbgw8 ... 0.pck?dl=0](https://www.dropbox.com/s/3kmlgy7qqbgw8f3/MA010100.pck?dl=0)
## Post #5
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2019-02-15T15:33:39+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

That's just zlib compression.
## Post #6
- Username: Maren
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 18, 2017 11:36 pm
- Post datetime: 2019-02-16T06:14:20+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

I was able to decompress ZLIB files, but can't get my hand on the .tex files. Unpacked .pck also include .tex files. BMS scripts, Noesis plugin and DSFO doesn't work. Look like they used different encryption/compression. Can these files still be extracted?

BG0001_unpacked.tex file: [https://www.dropbox.com/s/r2y4x5dgv3av8 ... d.tex?dl=0](https://www.dropbox.com/s/r2y4x5dgv3av8uj/BG0001_unpacked.tex?dl=0)
MA010100_unpacked.pck file: [https://www.dropbox.com/s/jwo21gzzl64h9 ... d.pck?dl=0](https://www.dropbox.com/s/jwo21gzzl64h977/MA010100_unpacked.pck?dl=0)
Zip archive of extracted MA010100_unpacked.pck file: [https://www.dropbox.com/s/s0ribase7wsfg ... d.zip?dl=0](https://www.dropbox.com/s/s0ribase7wsfg2v/MA010100_unpacked.zip?dl=0)
## Post #7
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2019-02-16T14:00:17+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Well, I caved in to rewrite my 2016 QuickBMS script into a Noesis one.
Automatic ZLIB handling - no need to decompress .tex files anymore.
You'll have to remove conflicting scripts (in this case Acewell's tex_CompileHeart_PSVita_tex.py).
I'll update with decompression of Sting/Aquaplus implementation of LZSS, so it would handle other games too.

UPD (Oct 20, 2019): a fix for [this](https://forum.xentax.com/viewtopic.php?f=18&t=21271).
UPD (Apr 13, 2020): added some game presets; check and edit the script itself.
[tex_Sting_Aquaplus_tex.zip](https://xentaxbackup.github.io/file/17924_tex_Sting_Aquaplus_tex.zip)
## Post #8
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-04-11T12:00:01+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Just saw this thread trying to decode LZ77 format .TEX from Dungeon Travelers 2-2 for PSVITA (Another Sting/Aquaplus game). Plugin doesn't seem to work with Noesis (get error), maybe format changed?

Example .TEX here.
[Shop.zip](https://xentaxbackup.github.io/file/17909_Shop.zip)
## Post #9
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2020-04-12T02:19:20+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

The compression is the same but I don't see width/height anywhere
## Post #10
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-04-12T04:19:40+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Sorry I'm an idiot I tried extracting manually forgot to leave other metadata.

Try another one, it just crash Noesis. See attached example TEX.
[Summon-Bustup-0012.zip](https://xentaxbackup.github.io/file/17917_Summon-Bustup-0012.zip)
## Post #11
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-04-12T04:22:36+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Another Example One thing to note is not all .TEX files are LZ77. Some are PNG which can be viewed in IrfanView anyway.
[NPC-0195.zip](https://xentaxbackup.github.io/file/17916_NPC-0195.zip)
## Post #12
- Username: TheUkrainianBard
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Jun 29, 2017 2:51 am
- Post datetime: 2020-04-12T10:31:10+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Remove tex_Sting_Aquaplus_tex.py from your noesis\plugins\python folder - I'll update the universal script sometime later.

UPD (Apr 13, 2020): universal script updated, please refer to [this](https://forum.xentax.com/viewtopic.php?p=148642#p148642) post.
## Post #13
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-04-12T14:40:32+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

Can confirm this works. Thanks very much for the quick response!
## Post #14
- Username: algcock
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 14, 2021 8:15 pm
- Post datetime: 2021-06-18T19:50:17+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

> Reply from TheUkrainianBard ↑Sat Feb 16, 2019 10:00 pm at Sat Feb 16, 2019 10:00 pm
>
> 
Well, I caved in to rewrite my 2016 QuickBMS script into a Noesis one.
Automatic ZLIB handling - no need to decompress .tex files anymore.
You'll have to remove conflicting scripts (in this case Acewell's tex_CompileHeart_PSVita_tex.py).
I'll update with decompression of Sting/Aquaplus implementation of LZSS, so it would handle other games too.

UPD (Oct 20, 2019): a fix for this.
UPD (Apr 13, 2020): added some game presets; check and edit the script itself.

weird, choosing preset #2 for Dungeon Travelers 2-2 just throws me an error when trying to view its .tex files [see pic](https://drive.google.com/file/d/1vYem5Klf8T_flPHyoDCIwlMvDAlQLvNo/view?usp=sharing)
Oddly enough, #3 (PC) Hyperdevotion Noire lets me view the .tex files for DT1 and 2 (the previous games) just fine.
## Post #15
- Username: narutolied
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 10, 2021 5:24 pm
- Post datetime: 2021-10-10T13:15:11+00:00
- Post Title: Extracting Compile Heart's .pck files from PSVITA game.

I am working on a Translation for  dt 2-2. For me the python plugin and noesis worked perfektly, thx a lot. I wasn´t able to unpack the .pck files so far. 

Question: If i export the images and change theme, how can i recode them for repatch to work on a vita system ? I can gues that the bits and bytes have to be at the exact same position to work but cant find a way to repack/rezip them like the original. 

I gues whit BMS i could reinject the edited ones but i cant get a bms script to work with DT 2-2 tex oder pck Files

Edit: I was able to extract the tex files form the pck with bms. Also i was able to extract an PNG from the TEX files and reimport it succsesfully after editing. RePatch with Vita worked and showed the right picture. As all of this is for DT2-2 i thing i dont follow up on this thread as this is for Compile Hearts. If anybody is intressted in my work with DT2-2 Mail me or search for my post in zenhax.
