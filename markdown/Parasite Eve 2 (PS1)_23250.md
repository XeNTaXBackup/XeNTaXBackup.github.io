## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-04T15:55:08+00:00
- Post Title: Parasite Eve 2 (PS1)

Parasite Eve 2 (PS1) tools.

Here's current solution. May not be perfect, but it allows to export all models.

1. Extract .CDF files with md_hyena's extractor. Most models are in stage0, and only very few (scenery stuff) in other stages.

2. Extracted files are missing information which is essential to auto-unpack models, so i made a workaround for this:
- drop .CDF onto Parasite2_cdf.exe
- run created .bat file in the folder with *.pe2pkg files - this will rename them

3. Drop renamed .PKG files onto Parasite2_pkg.exe or batch process them. This will extract all models as .MDL files.

4. You can convert .MDL files with my new tool (Parasite2_model.exe) or md_hyena's blender plugin. If you use md_hyena's plugin, some of them will be incomplete or have missing UVs. My tool will extract them all, and with all UVs.

5. Textures could be converted manually by combining images with palettes. There was some tool that could do that. In this game its easy, because images are 256-colored and each is using (hopefully) only one palette. You can find each model's textures inside the same set of packages. If you check "debug" file created by md_hyena's extractor you can notice all files are organized in sets, which is marked by "FF" byte of last package in each set. In other words, textures for a model package 1005 will be in image 1004 and clut 1003. Some extracted image packs are missing 1 or 2 bytes in the middle, which is probably a bug in extractor, but i'm not sure. Can be manually fixed with hex editor.

note: models have UVs in space of 256x256. Each texture is usually 128x256, so you have to fill it to the right up to 256x256. I don't recommend modifying UVs, because they are very precisely fit to pixels on a texture.




[Parasite_eve2.rar](https://xentaxbackup.github.io/file/19291_Parasite_eve2.rar)
## Post #2
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2021-01-07T22:41:53+00:00
- Post Title: Parasite Eve 2 (PS1)

I wonder if there are unused models in this game, can't wait to see.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-01-10T20:57:57+00:00
- Post Title: Parasite Eve 2 (PS1)

tools posted
## Post #4
- Username: VirusPunk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 12, 2012 7:32 am
- Post datetime: 2021-10-19T20:10:51+00:00
- Post Title: Parasite Eve 2 (PS1)

Edit: So how do we actually extract the textures? The tool only creates a folder for img/clut with nothing inside.
## Post #5
- Username: keroro23t
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 25, 2018 1:52 pm
- Post datetime: 2021-11-07T09:25:56+00:00
- Post Title: Parasite Eve 2 (PS1)

I got this error daemon1, any idea ?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-11-07T11:06:31+00:00
- Post Title: Parasite Eve 2 (PS1)

> Reply from keroro23t ↑Sun Nov 07, 2021 5:25 pm at Sun Nov 07, 2021 5:25 pm
>
> 
I got this error daemon1, any idea ?

Tool is not expecting PKG name with a path. This can be fixed, but i dont have time for it now.
Go to folder with PKG files and run again without path name.
## Post #7
- Username: keroro23t
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 25, 2018 1:52 pm
- Post datetime: 2021-11-08T17:45:59+00:00
- Post Title: Parasite Eve 2 (PS1)

> Reply from daemon1 ↑Sun Nov 07, 2021 7:06 pm at Sun Nov 07, 2021 7:06 pm
>
> 
keroro23t wrote: ↑Sun Nov 07, 2021 5:25 pm
I got this error daemon1, any idea ?


Tool is not expecting PKG name with a path. This can be fixed, but i dont have time for it now.
Go to folder with PKG files and run again without path name.

It worked thanks, now for the textures i could open raw files, contains images and lookup table but I don't really understand to make them like this 



again thank you for your tools and information
## Post #8
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2021-11-25T22:46:07+00:00
- Post Title: Parasite Eve 2 (PS1)

I have managed to get textures working with palettes, but so far only one half is showing right.

Edit: I managed to make the other half work by editing the offset of the palette.



Capture.PNG (237.46 KiB) Viewed 435 times
## Post #9
- Username: Outerreach
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 15, 2022 7:04 pm
- Post datetime: 2022-02-15T11:49:08+00:00
- Post Title: Parasite Eve 2 (PS1)

Hi,

thanks for the tools.
I have an issue.
I draged my STAGE0.cdf file to Parasite2_cdf.exe, the program run but nothing else is created or whatever.
Can someone help me please ?



Parasite2_cdf_q4lGLm1DvC.png (33.16 KiB) Viewed 357 times
## Post #10
- Username: Outerreach
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 15, 2022 7:04 pm
- Post datetime: 2022-02-20T20:44:47+00:00
- Post Title: Parasite Eve 2 (PS1)

Sorry for the up... 

I still have the same use, anyone can help ? 
I'm using the first attachment [viewtopic.php?f=35&t=13727&p=114438#p114438](https://forum.xentax.com/viewtopic.php?f=35&t=13727&p=114438#p114438) to extract the CDF file.
The other one looks like have a trojan.

Thanks.
## Post #11
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-20T22:12:57+00:00
- Post Title: Parasite Eve 2 (PS1)

That tool you linked appears to be the correct one. If not..

I used this tool here 
[https://drive.google.com/file/d/1M28Ar9 ... sp=sharing](https://drive.google.com/file/d/1M28Ar9IORNZlYxuu7W8VZ_Nv5cH-E_1R/view?usp=sharing)

Found on this post 
[https://gamefaqs.gamespot.com/boards/19 ... i/78796061](https://gamefaqs.gamespot.com/boards/198266-parasite-eve-ii/78796061)
## Post #12
- Username: Outerreach
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 15, 2022 7:04 pm
- Post datetime: 2022-02-20T22:34:00+00:00
- Post Title: Parasite Eve 2 (PS1)

Thanks for the help.
Here what i do : 

I tried this too : thats the same if i put the STAGE0.cdf and the Parasite2_cdf.exe on the STAGE0 folder.
## Post #13
- Username: Outerreach
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 15, 2022 7:04 pm
- Post datetime: 2022-02-21T13:42:34+00:00
- Post Title: Parasite Eve 2 (PS1)

Okay i guess I got it.



About the Parasite2_cdf.exe part, i just rename all the file to .pkg
After that, it work perfectly.
## Post #14
- Username: adolthered
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 27, 2020 6:14 pm
- Post datetime: 2022-07-05T03:53:35+00:00
- Post Title: Parasite Eve 2 (PS1)

Here's a list of all models (not including interface stencils). Notice I'm not using proper game jargon, feel free to take a better crack at it.

```
128 aya hands
131 aya
135 long handgun
139 rapid handgun
143 lasergun
147 long handgun
151 big handgun
154 small gun
164 big handgun
170 big gun
173 tommy gun
176 em rifle
179 cannon
182 shotgun
186 rifle
190 shotgun
197 night stick
201 rifle
205 rifle
209 launcher
212 gunblade
219 rifle
223 bayonette
226 rifle
230 rifle
234 rifle
238 smg
242 smg
246 smg
249 aya
255 body parts
1190 interface?
1196 interface?
1199 interface?
1205 interface?
1208 interface?
1211 interface?
1229 interface?
1232 interface?
1317 tall monster
1321 real big ?
1329 wolf
1336 fatty
1342 baby
1350 mosquito baby
1354 big bird
1358 stranger
1362 golem
1370 machine
1374 golem

1382 horn
1386 scorpion
1390 leech

1394 bat
1398 stingray

1402 baby
1409 stranger

1419 fuselage ?

1423 fatty
1427 tall monster

1431 trash boss
1435 trash boss

1439 golem

1451 golem

1459 fuselage ?

1484 mask man

1488 stranger

1495 mask man

1499 stranger

1502 injured black cop

1505 ponytail dude

1510 cowboy

1513 dude

1516 man

1519 eve

1526 baby

1536 cowboy

1539 man 

1544 cowboy/dog

1554 spear

1562 office man

1566 ponytail man

1570 tube

1573 eve

1576 soldier
1578 ponytail man

1580 man

1585_0 smg
1585_1 soldier

1589 tall monster

1593 monster

1597 wolf

1604 fatty

1608 baby
1616 mosquito baby

1620 big bird

1632 golem

1636 machine

1640 golem

1644 protruding fin

1648 scorpion

1652 leech

1655 office girl

1659 bat

1663 stingray

1667 baby

1678 fuselage ?

1682 ?

1684 eve

1688 leech

1692 golem
1696 golem

1700 station boss

1704 fuselage ? 

1708 greater stranger parts

1711 stranger

1714 black male officer

1717 male police captain

1720_0 office female
1720_1 clipboard


1723 ponytail male

1727 baby

1731_1 gun

1731_1 wounded black male

1735 office female

1747_0 flyer
1747_1 wolf

1754 fatty

1758 baby

1766 mosquito baby

1770 big monster

1778 stranger

1782 golem

1798 scorpion

1802 leech

1803 ?
1815 crawler

1851 cops

1860 man

1870 soldier

1873 stranger

1876 runner

1879 stranger girl/morph target

1882 runner

1887 cowboy/dog

1889 stranger parts

1893 stranger parts

1896 stranger parts

1899 eve (helmet)
1904 eve (helmet)

1907 horned stranger

1910_1 eve

1914 runner

1918 ?
1921 aquatic enemy

1927 greater stranger

1931 horned stranger

1935 tall stranger
1938 golem
1948 old runner

1960 misc/items
1961 final boss

1967 golem
1972 ?
1976 runner

1981 dude no top

1985 runner

1988 ponytail dude

1994_13 slug

2000 dude

2004 eve

2007 golem

2010 dude

2018 chamber

2023 golem

2028 hull

2033 golem

2038 eve
2047 eve

2116 dude
2122 dude
2128 dude
2134 dude
2139 dude


```


That I can tell there are no unused enemies in the game (except maybe the wolves? I don't remember. And what about that enemy with big feet?). Models are reused as often as enemies and characters are... each stage seems to have a distinct model set.

This Python script runs the necessary commands on the model files after they have been renamed to *.pkg. Make sure the script is run from the same folder as the files.

```

from pathlib import Path
import shutil
import os


count = 0

files = Path().glob('*.pkg')  # see: https://docs.python.org/3.10/library/glob.html
for file in files:
    count = count + 1
    print("extracting " + str(file))
    os.system("parasite2_pkg " + str(file))
    
print(str(count) + " files extracted")

count = 0

files = Path().glob('*.mdl')  # see: https://docs.python.org/3.10/library/glob.html
for file in files:
    count = count + 1
    print("converting " + str(file))
    os.system("parasite2_model " + str(file))

print(str(count) + " models converted")

```
## Post #15
- Username: adolthered
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 27, 2020 6:14 pm
- Post datetime: 2022-07-06T06:17:51+00:00
- Post Title: Parasite Eve 2 (PS1)

So some things are odd: the CLUT sizes for the 256 color textures are 1024 bytes or larger, rather than 512 as would be expected. On further inspection, the CLUT and image data don't have proper headers (like you'd see in TIM sections). All the CLUT and texture data used by a model group (character) seem to run into each other.

Which in practical terms, is a problem, because textures can be various sizes and bit depths.

Also recommend to use md_hyena's tool to extract (because you get more data) and daemon's tools to convert the data after extraction.
## Post #16
- Username: ayabreona11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 27, 2022 1:06 am
- Post datetime: 2022-09-26T17:22:13+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

Hi, sorry to bump this, but it's really impressive the fact that we can rip Parasite Eve 2 models and yet nobody shared them =(((
I would be interested to get at least the 2nd Aya outfit model... but even following the steps, I can't make anything to work at all.

1. What version is need to be use? (PAL, NTSC, JAP???)

2. When drop .CDF files (STAGE0, etc) onto Parasite2_cdf.exe, tutorial says this process
creates a new .bat file somewhere, but none of this actually happens...?

Without that step, all next can't be executed even if you rename manually the .pe2pkg to .pkg...

Can someone make a proper working tutorial? PLEASE i would drop everything for this lol
Or just share the models here!!
## Post #17
- Username: getwastedlol
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 27, 2022 11:26 am
- Post datetime: 2022-12-04T05:19:05+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

It is a strange process. The link to the GameFAQ discussion has another link to a Google Drive folder for an extraction .exe and an extracted model, but it has no extension name so it's useless. 

This is a very complicated procedure to extract these models, textures and other game files. I've followed the tutorial step by step but nothing works. The only thing that works is putting STAGE0.CDF into the PE2x04.exe to get the folder with all those files, but after that nothing works, not even changing the extension names to .pkg.

It would be nice if someone could post all the extracted models and images they managed to obtain or at least give a clearer and better explenation on how to rip them.
## Post #18
- Username: getwastedlol
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 27, 2022 11:26 am
- Post datetime: 2022-12-06T07:07:08+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

I rename .pe2pkg files to .pkg and put them in Parasite2_pkg.exe but nothing happens. wut do?

even using the python script a user posted doesn't help. i keep getting these errors

[https://imgur.com/ROr5ydR](https://imgur.com/ROr5ydR)
## Post #19
- Username: VirusPunk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 12, 2012 7:32 am
- Post datetime: 2023-03-21T06:36:08+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

A year later coming back to this and I too can't get it working. No .MDL files get generated when you drag the .pkg onto the .exe.
## Post #20
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2023-03-21T07:56:17+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

In fact those tools donesn't seem to be working properly, i created the .bat file using the tool in a CMD window and copying the result in a text note, then changing the extension to .bat
Here's the file:

[https://drive.google.com/file/d/1YjLtmn ... sp=sharing](https://drive.google.com/file/d/1YjLtmnEF1Xiqg_t61krO42zEmcuSpozm/view?usp=sharing)

To get the models, drag Parasite2_pkg.exe into CMD and only the name of the .pkg (not the full path) but this file and exe have to be directly in the user folder.

That was the method that worked for me.
[PE2 Extraction.PNG](https://xentaxbackup.github.io/file/23572_PE2 Extraction.PNG)
## Post #21
- Username: VirusPunk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Aug 12, 2012 7:32 am
- Post datetime: 2023-03-21T08:40:36+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

> Reply from Casedey ↑Tue Mar 21, 2023 3:56 pm at Tue Mar 21, 2023 3:56 pm
>
> 
In fact those tools donesn't seem to be working properly, i created the .bat file using the tool in a CMD window and copying the result in a text note, then changing the extension to .bat
Here's the file:

https://drive.google.com/file/d/1YjLtmn ... sp=sharing

To get the models, drag Parasite2_pkg.exe into CMD and only the name of the .pkg (not the full path) but this file and exe have to be directly in the user folder.

That was the method that worked for me.

Amazing! This actually worked, or at least now I got the .MDL file and converted.
[Desktop Screenshot 2023.03.21 - 02.47.53.86 copy.gif](https://xentaxbackup.github.io/file/23573_Desktop Screenshot 2023.03.21 - 02.47.53.86 copy.gif)
## Post #22
- Username: ayabreona11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 27, 2022 1:06 am
- Post datetime: 2023-05-16T21:14:36+00:00
- Post Title: Re: Parasite Eve 2 (PS1)

Oh this is good    

I managed to get the models following the new instructions, but it comes textureless =(

[](https://postimg.cc/mhrdBx4N)

I'm using the very last verison of Blender with .smd import.
Did I missed something? VirusPunk, how did you got the textures working?
