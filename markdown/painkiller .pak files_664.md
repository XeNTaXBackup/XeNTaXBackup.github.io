## Post #1
- Username: burzum
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 16, 2004 5:29 pm
- Post datetime: 2004-04-16T09:35:14+00:00
- Post Title: painkiller .pak files

Is there support planned for painkiller?

The 1st single player demo use a different pak format than the 2nd one (which is the same as the final game).

cheers.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-20T10:35:11+00:00
- Post Title: painkiller .pak files

Soon I will start to take a look at it.
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-04-22T09:16:10+00:00
- Post Title: painkiller .pak files

I have the game and also interested to unpack those files.
not for the contents but to learn.

maybe can you (Mr.Mouse) post a small tutorial on how you reverse the pack process?

i'm sure others people here would be interested to learn instead to use like common users..

Hope nothing unpleasant in my post   

thanks!
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-04-26T21:12:55+00:00
- Post Title: painkiller .pak files

I would like a tutorial also.

thanks
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-27T13:52:57+00:00
- Post Title: painkiller .pak files

> Reply from mambox
>
> I have the game and also interested to unpack those files.
not for the contents but to learn.

maybe can you (Mr.Mouse) post a small tutorial on how you reverse the pack process?

i'm sure others people here would be interested to learn instead to use like common users..

Hope nothing unpleasant in my post   

thanks!

Yeah, I have been thinking about doing something along those lines. Mind you, at the beginning of 2003 I wrote a two-page How-To on this very subject for the Dutch hardcopy magazine PCZone, but hey, that's in Dutch, so unless you understand the language, that won't help you out.   Anyway, an English version is on my to-do list.
## Post #6
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-04-27T14:39:00+00:00
- Post Title: painkiller .pak files

maybe a translator can help a bit 

are those pages avail online?

about painkiller i'm almost sure its a xor encryption but enough skill to manage rip the routine to convert the files 

not only time to use but time to learn also.

greets!
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-27T19:09:04+00:00
- Post Title: painkiller .pak files

Actually no, the resources in there are packed using unzip32.dll or some other standard PKZip tool, but the file uses it's own format to store the variables PKZip would need. .

I'm working on a way to either convert/reconvert the *.PAK <> PKZip (so you can open them using WinZip) or a MultiEx Commander implementation.  

EDIT
More specifically, it turns out the *.PAK files are actually complete *.ZIP files, but some of the "PK" identification tags have been altered. I will write a converter that will be able to flip between the two states. I just keep being surprised at the trouble these game programmers go through to find yet another package format. In this case, they betrayed the PKZip-format-with-a-twitch all too easily.  I don't really understand why they do this. The MOD community would probably love to use their base as a way forward, and they could have just used a real standard zip format to be used. Like the Quake3 engine does, a simple rename of the Quake3.PAK files to .ZIP will do the trick. Oh well.
## Post #8
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-04-28T13:11:25+00:00
- Post Title: painkiller .pak files

In the first demo,.pak was altered pkzip file,another curious guy brought the way to get it back but all has changed,at least in the retail version,the pak version seem xored.

I was looking during a debug session the way it changed some xored ascii back to a more readable text.

but a bit too complicated to reverse the whole scheme for me 

anyway thanks for the time spent!
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-29T05:45:16+00:00
- Post Title: painkiller .pak files

> Reply from mambox
>
> In the first demo,.pak was altered pkzip file,another curious guy brought the way to get it back but all has changed,at least in the retail version,the pak version seem xored.

OMG Why did you not say this before? If you already knew that the demo version was an altered zip file, I needn't have looked into that.    

I do not have access to any retail *.PAK files, so I won't be able to check em out.
## Post #10
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-04-29T07:20:15+00:00
- Post Title: painkiller .pak files

Sorry,i tought that you'll see retail package.

anyway 2 demos are out,the first from feb.04.

data\levels.pak was:
50 61 69 6E-50 61 63 6B-00 00 33 98-50 30 00 00  PainPack  3Ã¿P0
00 00 00 00-00 00 00 00-00 00 0A 00-00 00 43 32            â—™   C2
4C 35 5F 54-6F 77 6E 2F-05 06 03 04-14 00 04 00  L5_Town/â™£â™ â™¥â™¦Â¶ â™¦
08 00 A7 9E-50 30 9F 91-1C 4D C7 02-00 00 59 07  â—˜ Âºâ‚§P0Æ’Ã¦âˆŸMâ•Ÿâ˜»  Yâ€¢
00 00 1A 00-00 00 43 32-4C 35 5F 54-6F 77 6E 2F    â†’   C2L5_Town/
43 32 4C 35-5F 54 6F 77-6E 2E 43 4C-65 76 65 6C  C2L5_Town.CLevel

this one is an altered zip but PK authors didnt liked that someone can reverse to a zip so they improved the second demo version:
same file:

01 FC F8 01-00 78 01 -54 DB 6E DA-40 10 7D AF  â˜ºâ
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-29T07:51:09+00:00
- Post Title: painkiller .pak files

How big is that file in bytes you are talking about?
## Post #12
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-04-29T08:47:06+00:00
- Post Title: painkiller .pak files

there is 2 demos! 
this is the single player demo 2 it have have the same pak format than retail  version. 
[http://www.gamershell.com/download_5522.shtml](http://www.gamershell.com/download_5522.shtml)
## Post #13
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-04-29T09:07:29+00:00
- Post Title: painkiller .pak files

3,981,827 Levels.pak
1,060,767 LScripts.pak
1,202,744 Maps.pak
3,132,070 Models.pak
 388,396 Scripts.pak
 447,678 Shaders.pak

or as said in the second version files are same as retail (i mean encryption)
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-29T09:17:23+00:00
- Post Title: painkiller .pak files

Right, well, I figured it out almost completely. The PAK format now uses ZLib instead of PKZip compression. I have only to figure out how it encrypts the names of the resources and we're done.
## Post #15
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-04-29T15:29:54+00:00
- Post Title: painkiller .pak files

> Reply from Mr.Mouse
>
>  I have only to figure out how it encrypts the names of the resources and we're done.

that's what i can't find!

found some occurence of xoring in lscripts.pak

search:Pyvjhxl
xor P with 19=C
xor y        21=l
      v        23=a

and so on xor 19+2 and you'll find Classes

but i'm lost further...that's why i required some help on teaching from you as you know the reverse much better than me 

and why not to learn instead using as dead-user?
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-29T15:41:39+00:00
- Post Title: 

That I knew already. 

The problem is finding the start "XOR" number for each filename string. 
And that's what I am trying to figure out.
## Post #17
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-04-30T06:52:59+00:00
- Post Title: 

Keep up the good work here.
## Post #18
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-04-30T06:53:49+00:00
- Post Title: 

explain your avatar.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-01T18:48:45+00:00
- Post Title: 

Good news for those interested : 
I cracked the Painkiller *.PAK filename encryption code. 

I wrote a little PAKAnalyzer to test my theory and it worked. 

It shows the contents of a given *.PAK file. 

Here's an example of a text file that it creates:

> Reply from PAKAnalyzor
>
> 
XeNTaX' PAYNKILLAR *.PAK Analyz0r - 2004 - Mike Zuurman
C:\Program Files\DreamCatcher\Painkiller SP Demo 2\Data\Shaders.pak
<---------------------------------------------~
88 files: 
-------------------~
0 - blur.pso
1 - blur.vso
2 - bw.pso
3 - colortest.pso
4 - compose2.pso
5 - compose4.pso
6 - embm.pso
7 - embm_mblur.pso
8 - emissive.pso
9 - fog.pso
10 - fog.vso
11 - fog_color.vso
12 - fog_palskin.vso
13 - layer3_blend.pso
14 - menu_ref.vso
15 - neg_gray.pso
16 - ntu.vso
17 - ntu_detail.vso
18 - nvasm.exe
19 - palskin.bones1.lights0.vso
20 - palskin.bones1.lights1.vso
21 - palskin.bones1.lights2.vso
22 - palskin.bones1.lights3.vso
23 - palskin.bones1.lights4.vso
24 - palskin.bones2.lights0.vso
25 - palskin.bones2.lights1.vso
26 - palskin.bones2.lights2.vso
27 - palskin.bones2.lights3.vso
28 - palskin.bones2.lights4.vso
29 - palskin.bones3.lights0.vso
30 - palskin.bones3.lights1.vso
31 - palskin.bones3.lights2.vso
32 - palskin.bones3.lights3.vso
33 - palskin.bones3.lights4.vso
34 - palskin.bones4.lights0.vso
35 - palskin.bones4.lights1.vso
36 - palskin.bones4.lights2.vso
37 - palskin.bones4.lights3.vso
38 - palskin.bones4.lights4.vso
39 - palskin.vso
40 - palskin_2_layers.vso
41 - palskin_embm.vso
42 - palskin_freeze.vso
43 - palskin_fresnel.vso
44 - palskin_nmap.vso
45 - palskin_shadow.vso
46 - palskin_water.vso
47 - palskin_water_simple.vso
48 - proj.pso
49 - psa.exe
50 - ps_atten_dst2.pso
51 - Scripts/
52 - Scripts/blend.shader
53 - Scripts/custom.shader
54 - Scripts/default.shader
55 - Scripts/light.shader
56 - Scripts/lm.shader
57 - Scripts/lmx2.shader
58 - Scripts/skin.shader
59 - Scripts/sky.shader
60 - Scripts/volumetric.shader
61 - Scripts/vssver.scc
62 - Scripts/water.shader
63 - simple.vso
64 - simple_proj.vso
65 - skin_dirtywater.pso
66 - skin_PixelSpecTable.pso
67 - skin_water.pso
68 - teleport_embm.pso
69 - teleport_embm_14.pso
70 - teleport_ref.vso
71 - teleport_ref_14.vso
72 - tu2.vso
73 - tu2_blend.vso
74 - tu2_color.vso
75 - tu2_detail.vso
76 - tu2_fog.vso
77 - tu2_lmap.vso
78 - tu2_point_pass.vso
79 - tu2_proj_1.vso
80 - tu2_sproj.vso
81 - vsa.exe
82 - vssver.scc
83 - water_embm.pso
84 - water_embm_14.pso
85 - water_lm.vso
86 - water_ref.vso
87 - water_ref_14.vso
 I am able to do whatever I wish with these archives now as I have mapped the purpose of every single bit that is in there.
## Post #20
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-05-02T12:54:12+00:00
- Post Title: 

Interested for sure!!

may i hope a small explanation of your reverse work?

i've lost track into the gpak engine.dll
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-02T13:10:38+00:00
- Post Title: 

I haven't used any of the dll's or exe of the program. Just a hex editor, a piece of paper and thinking binary.
## Post #22
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-05-02T13:21:11+00:00
- Post Title: 

damn!!

High logic mind...

i'm blowed 

Hope you'll doing soon an unpacker?
(it will for sure doing revolution into the modding of PK)

and a small notice about the analysis?

Hope really not to bother you with my question,only a way to progress.

greets!
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-02T14:18:15+00:00
- Post Title: 

I'm working on it, to implement it in MultiEx Commander. Making progress! See the screenshot! 
[pain.jpg](https://xentaxbackup.github.io/file/14_pain.jpg)
## Post #24
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-05-02T14:19:46+00:00
- Post Title: 

great!!

thanks for the work!!
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-02T14:21:27+00:00
- Post Title: 

No problem. I will get round to explaining the way it works in the future. I hope you can tell those Painkiller fans that this support is upcoming!
## Post #26
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-05-02T14:43:14+00:00
- Post Title: 

this news will fall like thunder on PK modders as authors seem not to want sharing locked files.

thats why they encrypted the second demo and the retail.

until today..
## Post #27
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-02T19:54:41+00:00
- Post Title: 

neato

any ETA when a multiex version able to open them will be available? 

great work
## Post #28
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-05-02T21:14:39+00:00
- Post Title: 

dont hurry,let him finish the work...

still pleasant he took time to work on this.

For sure more work to do than requesting.
## Post #29
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-02T21:17:38+00:00
- Post Title: 

UNOFFICIAL TEST VERSION FOR PK FANS!

Does not work on all games anymore! But will work for those *.PAK files. 

You can try this version to see if extraction works on your files. It's an unofficial version. Use at your own risk. 

Also, get the dll plugin, and store that in the data\plugins\pak directory. 

You will have to make the pak directory yourselves in the plugins directory. 

 I will release a 100% working final version later, along with the new version of MultiEx Commander. I hope I will have replacement support as well by then. Also, I will post the whole encryption method.
[mc32UNOF.zip](https://xentaxbackup.github.io/file/16_mc32UNOF.zip)

[Painkiller.zip](https://xentaxbackup.github.io/file/15_Painkiller.zip)
## Post #30
- Username: burzum
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 16, 2004 5:29 pm
- Post datetime: 2004-05-03T00:21:17+00:00
- Post Title: 

worked like a charm, thanx a bunch =)
## Post #31
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-03T11:54:07+00:00
- Post Title: 

where did you post the files?
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-03T11:57:28+00:00
- Post Title: 

Huh? Look up in this thread. You can see them! Three posts ago!   
You must register on the forum to see them I guess.
## Post #33
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-03T12:04:07+00:00
- Post Title: 

dumbass me!

I should leave now..later for sure.
## Post #34
- Username: Comrade
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 04, 2004 1:08 am
- Post datetime: 2004-05-03T17:13:31+00:00
- Post Title: 

...Brilliant! Gone moddin`...
## Post #35
- Username: Cluster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 04, 2004 2:41 am
- Post datetime: 2004-05-03T18:44:53+00:00
- Post Title: 

Thank YOU!!
time to get my hands dirty =)
## Post #36
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-03T23:41:06+00:00
- Post Title: 

The encryption method:

Oh, a Xor method preceded by a inclusive (the new bit will be set) shift-left of the size (in bytes) of the filename (a size which is saved neatly in the PAK file, right before the encrypted resource name), and subsequently is incremented by either -2, -1, 0, 1, 2 depending on the two different hexadecimal parts of the size of the filename (in bytes) and then by the relative filenumber in the archive (the first file is 1, the second is 2 etc.).

Ok, so if I would write a filename of exactly 255 bytes in length in hexadecimal I would get FF. Hexadecimal is 0, 1...9, a, b, c, d, e, f. F = 15 in decimals. F F = 15 * 16 + 15 = 255. The byte is 255. But the two hexadecimal parts of the byte are F F or 15 15. 
So, create a two-dimensional table in which [0, 0] = -2, [0, 1] = -1, [0, 2] = 0, [0, 3] = 1, [0, 4] = 2, [0, 5] = -2, [0, 6] = -1 etc until [15, 15]. (Thus, [1, 0] = -1). 

So, to decode, read the size variable (a long, 4 bytes) of the filename first. Multiply it with 2. Add 1. Add the number from the above created table. Add the relative filenumber (the first resource in the archive gets a 1) and you have a variable which you will XOR with the first byte of the filename, the resulting byte is the first byte of the actual filename. Now keep adding two to the XOR-byte before you XOR it with a subsequent byte of the filename (giving you actual bytes of the filename) and repeat it in total until you reach the end of the filename. Voila , you have the decrypted filename string. 

If there are any questions, don't hesitate.
## Post #37
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-04T12:23:31+00:00
- Post Title: 

where are the files ?
## Post #38
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-04T12:24:35+00:00
- Post Title: 

They are only visible to registered users. Registration is free.
## Post #39
- Username: slider
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 05, 2004 8:02 am
- Post datetime: 2004-05-05T00:22:01+00:00
- Post Title: 

Where's that dutch article you wrote? Is it up somewhere to download?

Thx
-Slider
## Post #40
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-05T15:20:47+00:00
- Post Title: 

About the article, no, it's in the magazine. It's not online. 

About the Painkiller *.PAK progression, I have updated painkiller.dll to be able to replace resources in the GRA. It's not implemented in MultiEx Commander yet, although my personal DLL plugin Tester has shown that it works (I replaced sounds of some creature with those from C&C Generals, and the game used them perfectly).   It makes all the difference if this creature says "We will take what is ours" before it bashes your skull in.
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-05T23:05:35+00:00
- Post Title: 

Okay, I just finished a stripped-down version of my plugin-tester and called it "PainFull". Here's the details , a screenshot, and the file. To see the screenshot and file, you must register. 

[EDIT] FIXED BUG, SEE NEXT POST FOR FILE!

> Reply from readme
>
> PainFull Extractor 
Done in 2004 by Mike Zuurman
AKA Mr.Mouse/XeNTaX

*Purpose

Small archiver to extract stuff (and import files one by one) 
into *.PAK files from the Painkiller game by DreamCatchers. 
Use this for domestic purposes only ! It's a tool for the standard
fan of the game that just wants to mess about with some of the
resources. 

>>>> Remember and respect the authors' copyrights on these files! <<<<

If you want to do something big, be sure to contact them first. 

*Installation
Install MultiEx Commander (http://multiex.xentax.com) first,
you may not need it, but it will ensure you have dlls that you're gonna need.

Then install the all the files in this zip file in one directory of your choice. 

Start with Painfull.exe

*Manual

Just browse to a PAK file of your choice at the left side 
of the tool, select it in the file-list, and hit "Open Painkiller PAK". 
You will notice the contents (entries) listed to the right. 

- Extraction 
  Just select all files at once, clicking on the top file first 
  followed by a click on the last while holding down shift. 
  Alternatively just select the files you want, by holding ctrl. 

  To extract, click the button below and in between the two lists, 
  with "<<" on it. Voila. It will extract the files into the current path. 

- Replacement
  Select a file in the file list that you want to use to replace a file 
  in the open archive. Second, select the file you wish to replace in the 
  contents list. Click the ">>" button, and wait until it's finished. 
  Done. 

  Important Note! PainFull will automatically import the new file, and will 
  NOT create a backup. If you want to mess around with any PAK file, 
  be sure to back it up first and store it somewhere save!

( http://www.xentax.com, 2004 )

 Thanks to Mambox for the initial hint!
[pfscreen.jpg](https://xentaxbackup.github.io/file/20_pfscreen.jpg)
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-06T16:29:41+00:00
- Post Title: 

Here's the updated file! 

[EDIT] 

Version 1.1 available!

Fixes the bug mentioned 2 posts down. (Could not extract from MAPS.PAK). Have fun!
[Painfull.zip](https://xentaxbackup.github.io/file/22_Painfull.zip)
## Post #43
- Username: Cluster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 04, 2004 2:41 am
- Post datetime: 2004-05-07T14:46:10+00:00
- Post Title: 

And again
Thanks Mr.Mouse, great tool!
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-07T14:51:05+00:00
- Post Title: 

Thanks. I'll have to fix another bug though, in the MAPS.PAK file of the demo are directories that have extentions in their names like "mmoops\level.mpk\sounds\blah.txt"; the extractor fails to extract those, because of my quick and dirty coding. I will get to that small bug as soon as possible.
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-07T18:44:01+00:00
- Post Title: 

Okido, fixed the bug. Scroll up for the new version (1.1).
## Post #46
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-08T07:54:32+00:00
- Post Title: New pak files?

How much trouble would it be to add the functionality to create a new pak file from a directory structure?  Or at least insert new files?  

If that is asking to much, would it be possible to easily change the filenames?

Thanks
## Post #47
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-05-08T11:27:07+00:00
- Post Title: New pak files?

Great!!

i didn't even expected to have a replace features!

thanks again!
## Post #48
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-08T13:45:08+00:00
- Post Title: New pak files?

> Reply from fleabay
>
> How much trouble would it be to add the functionality to create a new pak file from a directory structure?  Or at least insert new files?  

If that is asking to much, would it be possible to easily change the filenames?

Thanks

I'll see that I can do. I had already planned a "Create From Directory" option in the painkiller.dll file, for MultiEx Commander purposes, so it won't be a problem to implement it in Painfull. Changing filenames is also not a problem, but I wonder what the game will say if you do that. If some script expect some file with some name, you better make sure you change that script accordingly.  

Meanwhile, I show some minor modding in MexModCentral  
[viewtopic.php?p=3686#3686](http://forum.xentax.com/viewtopic.php?p=3686#3686)
## Post #49
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-08T17:25:22+00:00
- Post Title: New pak files?

Right now I can exchange the .scc file with one of my choice.  Its not needed for the scripts.  I can't change the name of it though.

If you have ways to put in new files or create a new pak from scratch, its not needed.

Thanks for the program, looking good so far.

I also liked the screenshot of the XeNTaX name in the sky in the other thread.
## Post #50
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-10T10:30:39+00:00
- Post Title: New pak files?

Ok, I'm working on these features you asked for. 

I can't tell you when I will be done with them, as my daily job takes a lot of time, and in the evening I'm working on a new article as freelancer for the Dutch hard-copy game magazine PCZone. 

It will be completed however.
## Post #51
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-11T12:54:08+00:00
- Post Title: New pak files?

Update : I have quickly implemented a function that will change the name of the resource in that which is used to replace a file. This will however be the full path (e.g. "c:\models\mymodel.mdl" ) to the file that you use to replace. It depends on what you would like. I could change it so it would be "models\mymodels.mdl" and ommit the "c:\".
## Post #52
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-11T16:17:16+00:00
- Post Title: New pak files?

All the paths are derived from the scripts.  No path is needed or desired   

for instance, if i wanted to change the filename in the pak file - Loader.lua to myloader.lua

It should be all relative to the root of the pak file.

I'm not really sure what your doing here.  Has the program file been updated with these changes?  If so, I'll check it out.

The path to the pak files are ../Data/
thats the absolute path from the painkiller.exe to the pak files and is used alot in the scripts.  But again, your program shouldn't need to know this.

What is needed is to update the filename as well as the contents when a file is dropped from the left window.

Sorry if this was long.  I thought it better to be to much info than not enough.  Don't put to much into this quick fix on my behalf.  I can issue my next update the same way i've been doing.
## Post #53
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-11T16:18:43+00:00
- Post Title: New pak files?

Opps, sorry.  That was my post.
## Post #54
- Username: mcloud355
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 12, 2004 11:10 pm
- Post datetime: 2004-05-12T17:03:44+00:00
- Post Title: New pak files?

having problems with painfull v1.1

it extracts ok but when i try to replace a file into the .pak it says 'import failed'

i am selecting the new file in the left side box (game.lau) and selecting the file to be overwritten (main/game.lau) within the pak contents list on the right, then click on the >> icon and i get 'import failed!'

any ideas what im doing wrong?
## Post #55
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-12T17:59:14+00:00
- Post Title: New pak files?

Did you install MultiEx Commander first?

It may be a problem with zlib.dll, it will be installed with MultiEx Commander.
## Post #56
- Username: mcloud355
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 12, 2004 11:10 pm
- Post datetime: 2004-05-13T02:22:22+00:00
- Post Title: New pak files?

multiex commander v3.9.701 is installed, zlib.dll is in the windows/system32 directory

i tried running the painfull.exe within the multiex directory but same problem, 'import failed'

wondering if its my directory structure, i have the new game.lua file from Dreamcatcher\LScripts\Main directory highlighted in the left side box and the 'main\game.lua' highlighted in the right side box
## Post #57
- Username: sh1ny
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 13, 2004 10:10 am
- Post datetime: 2004-05-13T02:25:25+00:00
- Post Title: New pak files?

hmm i got an error while trying to extract files from a pak.

Run Time Error '9'
Subscript out of range.
I am using retail PK patched to 1.15
## Post #58
- Username: mcloud355
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 12, 2004 11:10 pm
- Post datetime: 2004-05-13T02:35:30+00:00
- Post Title: New pak files?

im running painkiller v1.0, no problems with unpaking
## Post #59
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-13T05:25:58+00:00
- Post Title: New pak files?

Ah problems arise now. I wonder how much of you have problems extracting, importing. A lot don't have problems, I know.

I will see what I can do to help fix it on theose computers that won't run it.
## Post #60
- Username: BarfHappy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2004 5:51 am
- Post datetime: 2004-05-13T22:43:35+00:00
- Post Title: New pak files?

No problem for me, thanks for the fantastic help you gave me with that, spared me some programming 

i couldn t have done that  without you:
[primehud.jpg](https://xentaxbackup.github.io/file/26_primehud.jpg)
## Post #61
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-14T05:41:47+00:00
- Post Title: 

Wow! Nice work, man!

Hey, would you repost that pic (or any other interesting results in MexModCentral? Perhaps even with a short how-to?

[viewforum.php?f=12](http://forum.xentax.com/viewforum.php?f=12)

Good stuff! Beats my face on a hellbiker anyday!
## Post #62
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-14T21:26:55+00:00
- Post Title: 

OKay, to those that have problems running version 1.1 : I'm still going to release a new version, my day job is still bugging me. It would help if you would post a little information such as : what you installed first and what OS you use (Win98/XP and so on). I am trying to recreate the bug.  
And meanwhile I hope it works on the new 1.5 version of the game.
## Post #63
- Username: OmegaThree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2004 5:06 am
- Post datetime: 2004-05-16T21:36:05+00:00
- Post Title: 

Well done!  I was just thinking, "Damn this game has some wicked textures, I wish I could rip them and get a closer look."  So I sneak around a while, dig up some dirt on possible extraction tools, discover Painfull (thanks to a link BarfHappy provided over at Painkillerhell) and holy crap, I got 1.2 gigs of textures to pour over.

Interface needs a little cleaning up, but otherwise great job!  I hear it's got import features as well.  Nothing I'd use, but it sounds like some other people are pretty happy about that.

Haven't seen any bugs yet.
## Post #64
- Username: dek001
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2004 1:52 am
- Post datetime: 2004-05-16T21:45:11+00:00
- Post Title: 

hey thanks for the pak extractor and i found the errors (runtime errors)it gets is when extracting all the files from a pak and also is there anyway to create a pak yet because like most games it looks like it loads pak's in alphabetical order or am i wrong(im wrong see below), could do with the ability to make our own pak files for easier mod distribution.

*Just done some testing and found out it wont load paks by different names does anyone know why it wont do this whats deciding what paks are used i.e why it loads a pak called Textures1 but not a pak called Textures2.
## Post #65
- Username: sh1ny
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 13, 2004 10:10 am
- Post datetime: 2004-05-17T01:06:29+00:00
- Post Title: 

PC : Celeron@1.7, 512 ram, FX5200
OS : Windows XP/Pro
Latest drivers and stuff. I've managed to extract files with some other tool ( dragonsomething ), but it does not support importing of files. When i try to do that i get "Import Failed" error. 
Still Running v1.15 of the game...
## Post #66
- Username: DemonS_HorizoN
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2004 2:21 am
- Post datetime: 2004-05-17T05:58:36+00:00
- Post Title: 

PC : Athlon 2100+, 512 ram, FX5200 
OS : Windows 2K/Pro 
Latest drivers and stuff. 
I've the same problem but I use version 1.1(eng).
## Post #67
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T07:00:43+00:00
- Post Title: 

Okay, I will need to figure out why some people have problems and some don't. 

-I hope all of you have installed MultiEx Commander first
-Can you point me to some pak files that don't work? 
-Perhaps you can upload such a pak file (if it is not to big) somewhere?

Thanks. 

I'm rather busy with MultiEx Commander and I've just bought a house, that takes time, not to mention my marriage in september, and my daily job, so naturally I cannot put all energy in Painfull at the moment. I hope you have patience.
## Post #68
- Username: OmegaThree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2004 5:06 am
- Post datetime: 2004-05-17T14:09:29+00:00
- Post Title: 

Congratulations x2
## Post #69
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-17T18:24:42+00:00
- Post Title: 

First : I must say "Hi" cause I'm new to this forum and "What an amazing job!"
Your soft is very good but I'm experiencing little problems... I identified one file that doesn't want to extract :

```

./Templates/Health/Heart.CItem

Size : 8 

Error :
Run-time error'9':

Subscript out of range
```


Note : I'm using the french version of the game (1.0) ... maybe this helps.
I can upload the file somewhere if you want (1MB).

And finally I'm patient   Just take your time and continue the great work when you can...
## Post #70
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T18:29:10+00:00
- Post Title: 

Yes, that would certainly help, if you could upload that file somewhere!
## Post #71
- Username: dek001
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2004 1:52 am
- Post datetime: 2004-05-17T19:09:54+00:00
- Post Title: 

Yep i get same error on that file too and i must thank him aswell cause i didnt know i had loads of files not extracted until i went to check it out. im using the patched english version of the game. And what file you want uploading the Lscripts one i got some space i can use if u want it.
## Post #72
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T19:39:26+00:00
- Post Title: 

Painfull 1.2

Uploaded a new version that should hopefully fix some of the errors you got, plus I added a crude "Overwrite filenames" option. 

You can get it here:

[viewtopic.php?p=3838#3838](http://forum.xentax.com/viewtopic.php?p=3838#3838)
## Post #73
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-17T20:21:32+00:00
- Post Title: 

Thanks, your update (v.1.2) fixed the extraction problem for the file mentionned above but now I cannot extract Loader.lua   

Anyway you're the man Mr. mouse you updated SO fast...Thanks again
## Post #74
- Username: DemonS_HorizoN
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2004 2:21 am
- Post datetime: 2004-05-17T20:24:01+00:00
- Post Title: 

LScripts.pak v 1.1 (eng):
[http://mitglied.lycos.de/religionz/LScripts.pak](http://mitglied.lycos.de/religionz/LScripts.pak)

export of Tweak.lua works
but the reimport of the extracted file don't work
## Post #75
- Username: dek001
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2004 1:52 am
- Post datetime: 2004-05-17T20:37:08+00:00
- Post Title: 

the heart file mentioned it says it's extracted it but it doesnt extract it just extract's the folders and i got a runtime 5 error when extracting from the maps.pak, them are the only problems ive found but least most of it is extracted
## Post #76
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-17T20:50:37+00:00
- Post Title: 

Ooops didn't checked that... You're right dek001, the file is not extracted...
I'm wondering what's happening with this file...

I upped my LScripts.pak (v1.0 FR) :
[http://www.membres.lycos.fr/tts/XeNTaX/LScript.pak](http://www.membres.lycos.fr/tts/XeNTaX/LScript.pak)

Hope this helps
## Post #77
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-17T20:57:06+00:00
- Post Title: 

Sorry I forgot to log in and made a mistake in my path.    
Here's the good one :
[http://www.membres.lycos.fr/tts/XeNTaX/LScripts.pak](http://www.membres.lycos.fr/tts/XeNTaX/LScripts.pak)
## Post #78
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T20:57:18+00:00
- Post Title: 

> Reply from DemonS_HorizoN
>
> LScripts.pak v 1.1 (eng):
http://mitglied.lycos.de/religionz/LScripts.pak

export of Tweak.lua works
but the reimport of the extracted file don't work

I tried it, and I can extract AND import the Tweak.lua file succesfully. 
I changed it first and then imported it back, and re-extracted it to confirm succesful importation. So I don't know yet why it doesn't work with you.
## Post #79
- Username: DemonS_HorizoN
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2004 2:21 am
- Post datetime: 2004-05-17T22:28:37+00:00
- Post Title: 

lol
I don't know why but now it works
## Post #80
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-18T07:21:27+00:00
- Post Title: 

I posted a new version 1.2.1 that fixes the issue with the Heart.Citem file. Turns out it is actually a file that was 0 in length prior compression by the Painkiller devs, but they compressed it nevertheless, leaving a file now 8 in size. A remarkable choice of events. Anyway, the decompressor routine in Painfull simply decompresses the 8-sized compressed file back to 0. Something Painfull did not expect, naturally. Now when this happens, Painfull will simply open the said file and close it, without writing anything to it, recreating the 0-sized original.   

[viewtopic.php?t=732](http://forum.xentax.com/viewtopic.php?t=732)
## Post #81
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-18T10:35:51+00:00
- Post Title: 

Wow that's weird...
Thanks A LOT Mr. Mouse 

Edit: : The files Loader.lua and vssver.scc don't want to extract, I've got the message "Error extracting".  Is there a chance to get it working? I think this file is used to initialize the engine at startup. It seems interresting 

Re-Edit : Sorry, after some indeep testing, I managed to get it! In fact these files were extracted as folder by a previous version. This confuses the new extractor    Everything seems to be working now for me! Thanks again
## Post #82
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-18T11:12:47+00:00
- Post Title: 

Excellent!   So, this might help others as well. Once you get a new version of Painfull, make sure you remove such directories that might get in the way of Painfull normal function. Just as a tip. I know it should not make a difference, but the previous version was not 100% and I hope Painfull becomes more and more 100% as new version arise!
## Post #83
- Username: dek001
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2004 1:52 am
- Post datetime: 2004-05-18T13:49:05+00:00
- Post Title: 

hey that chearts what is it is it just an empty file cause still on extraction it doesnt show up havent found any other probs with latest version.Keep up the good work.
## Post #84
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-18T13:53:40+00:00
- Post Title: 

Yes, it is just an empty file. I don't know why it does not create this empty file, at my work it also doesn't, but at home it worked. Hmmmmmmmmmm.
## Post #85
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-18T23:37:04+00:00
- Post Title: 

New errors here 

```
Maps.pak

File :
MOPPCode/1x01_Chaos.mpk/cathedral_fix

Size :
8

Error :
Run-time error '5':
Invalid procedure call or argument
```


Hope these informations helps
## Post #86
- Username: dek001
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 16, 2004 1:52 am
- Post datetime: 2004-05-19T13:59:43+00:00
- Post Title: 

yeah i got runtime error 5 on extracting maps didnt know which 1 though
## Post #87
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-20T15:39:02+00:00
- Post Title: 

New version 1.3 at the NEWS forum!
## Post #88
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T08:18:45+00:00
- Post Title: 

And again a new version :
[viewtopic.php?t=732](http://forum.xentax.com/viewtopic.php?t=732)

View the PainEditor while running the game. 
Start the game, go to windows with with CTRL-ESC, or any other means, and click Game->View PainEditor in Painfull.
## Post #89
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-21T16:44:13+00:00
- Post Title: 

WOOW you're amazing man! I really appreciate your job but I still have the error mentionned above  

My pak file is still on my account et lycos if you want
## Post #90
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T17:17:44+00:00
- Post Title: 

Yeah, but you said you got the error in a maps.pak file, right? That one is not at the lycos address is it? Or do you have an error in that LScripts.pak as well?
## Post #91
- Username: TTS
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 18, 2004 1:53 am
- Post datetime: 2004-05-22T11:12:28+00:00
- Post Title: 

Oh I'm sorry.You're right : the Maps.pak file is not on my account due to the file size (235MB). I'll check if I can put it somewhere else... 
The LScript.pak file extracts like a charm 

Sorry again : I've posted too fast
## Post #92
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-23T10:53:32+00:00
- Post Title: 

New (and more or less final version) 1.3.2

- you can now delete resources as well, this makes it complete in my opinion. 

[viewtopic.php?t=732](http://forum.xentax.com/viewtopic.php?t=732)
## Post #93
- Username: A_Llama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 25, 2004 10:45 pm
- Post datetime: 2004-05-25T15:18:06+00:00
- Post Title: 

Argh, I get a "run time error '53': file not found" when I try to browse to anywhere other than the directory painfull is in   

I have multiex installed and my os is win98...
## Post #94
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-25T15:21:25+00:00
- Post Title: 

Argh, indeed. This is really weird. Just when you double-click on any other directory this happens???!
## Post #95
- Username: A_Llama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 25, 2004 10:45 pm
- Post datetime: 2004-05-25T15:22:15+00:00
- Post Title: 

Yep, that is exactly what happens....
## Post #96
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-25T15:24:08+00:00
- Post Title: 

Huh? And if you change drives?
## Post #97
- Username: A_Llama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 25, 2004 10:45 pm
- Post datetime: 2004-05-25T15:34:43+00:00
- Post Title: 

The same thing happens....

I just tried it on another comp and it worked fine...
## Post #98
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-25T18:53:21+00:00
- Post Title: 

Weird stuff. The other computer also runs win98?
## Post #99
- Username: A_Llama
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 25, 2004 10:45 pm
- Post datetime: 2004-05-25T19:55:54+00:00
- Post Title: 

Yeah, it does
## Post #100
- Username: *NoReMoRsE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 04, 2004 10:43 am
- Post datetime: 2004-06-02T07:37:06+00:00
- Post Title: 

Hello, Hey MR.Mouse, im a noobee that loves youre program but something happend to it to where i get a error.. it sais this   m (MODMAIN: Initializing MC
INITMC: Loading Splash
INITMC: Creating FS-Object
ERROR: 429-ActiveX component can't create object

what the heak have i done?   it used to work,, well if you have the time to help thanks,,peace  lataz noremorse
## Post #101
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-02T07:40:28+00:00
- Post Title: 

That's MultiEx Commander you're talking about. 

You should check the Troubleshooting forum first. 

You might have found this:

[viewtopic.php?p=3316#3316](http://forum.xentax.com/viewtopic.php?p=3316#3316)
## Post #102
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-06-02T18:30:45+00:00
- Post Title: 

awsome thanks,, and great job on the pain paks

 thanks agian  noremorse
## Post #103
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-03T08:22:25+00:00
- Post Title: 

No problem.   

Actually, this error will not occur again in the upcoming new version.

Read all about the progress of the new version in my .plan thread. 

[viewtopic.php?t=631](http://forum.xentax.com/viewtopic.php?t=631)

The new version will be a major step forward.
## Post #104
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-06-13T01:46:00+00:00
- Post Title: 

Can you unpack the pak files with painfull?  I see how to remove/insert  files and create new paks but I can not 'unzip' the pak files with this utility.

Thanks

Nevermind, I selected all on the right and unpacked.  Kinda unintuitve, but as long as it works.
## Post #105
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-29T09:27:26+00:00
- Post Title: 

XeNTaX Press Release 29th of June 2004
------------------------------------------------------------

MultiEx Commander 4.0

A new version of the no.1 tool that can handle more than 155 
different game resource archive formats (GRAFs) has been released. 

There's a huge number of changes, making it a solid 4.0. 

For review of the changes, read Mike Zuurman's plan thread:
[viewtopic.php?t=631](http://forum.xentax.com/viewtopic.php?t=631)

New GRAFs supported include:

Painkiller 
Sacrifice 
Port Royale
Far Cry 
City of Heroes
Mechwarrior 4

The new build-in MultiEx Editor makes creation of new GRAFs also possible. 

Find the - open source - program at :
[http://multiex.xentax.com](http://multiex.xentax.com) 

MultiEx Commander is under GNU Public License
(c) 2004 XeNTaX, [http://www.xentax.com](http://www.xentax.com)
------------------------------------------
## Post #106
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-06-30T05:27:12+00:00
- Post Title: n00b needs help

Hey this is a great tool!

I'm trying to import an edited LUA file back into a Painkiller saved game pak to get around a game bug.

I get an import error.

I edited the LUA file with notepad.

I also tried importing the file with PainFull and got the same error.

Any help would be much appreciated!
## Post #107
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-30T07:16:23+00:00
- Post Title: n00b needs help

Hmm, what file is that (PAK) and what LUA file? Can you give some details on the error?
## Post #108
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-06-30T16:28:48+00:00
- Post Title: n00b needs help

There's a bug in painkiller I'm trying to workaround.

The file I was unpacking was a save game file.
It's found in a save game folder and has the name "Save.dat"
It unpacked fine, and has lots of LUA files.
The particular LUA file I edited and tried to import back into the .dat archive was called "Kont_Big_009.CItem"

I also got a MultiEx start up error saying it couldn't find the bass.dll.
I have the latest MultiEx (4.0).
I have painkiller with patch 1.2 installed.
I am using win2k OS with SP4.

The inport error message was "cm32: error - reason ..." The rest of the message doesn't display since I have large fonts enable for my desktop and the text doesn't fit in the pop up window.

But here's a copy of the error log below -
MODMAIN: Initializing MC
INITMC: Loading Splash
INITMC: Getting mc32.exe path info
INITMC: Checking existence of MultiExDC
INITMC: MC_MRF = C:\Program Files\MultiEx Commander/data\config\mc.mrf
INITMC: Loading Connect Form
INITMC: Loading Options Form
INITMC: Getting Options 
INITMC: Checking Debug Mode
INITMC: Checking Online Start
.]-WebUpdate: user selected :3
.9:19:53 AM- Main : Opening MRF file
INITMC: OpenMRF
INITMC: Mex_FindPlugins Starting
.-Main : Mex_FindPlugins
.-Main : Mex_FindPlugins->Searching
.-Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll for Painkiller
.-Main : Mex_FindPlugins->PGN at C:\Program Files\MultiEx Commander\data\plugins\wad\Sacrifice.dll for Sacrifice
MAINMOD: Checking registry entry
MAINMOD: Loading Main Form
.- Main : Loading 
.- Main : Creating Panels 
.- Main : Setting Variables 
.- Main : Preparing Datafile List Columns 
.- Main : Setting Additional Variables
.- Main : Loading SupportForm
.- Main : Setting FileFilter
.- Main : Enabling All
.- Main : Creating New Instance
.- Main : Showing Program
.53.File not found: bass.dll
MAINMOD: Processing any command line pars
MAINMOD: Possible pars found: C:\DOCUME~1\mbennett\Desktop\Save.pak
MAINMOD: Possible Archive Filename found: C:\DOCUME~1\mbennett\Desktop\Save.pak
MAINMOD: Loading StartUp Form
MAINMOD: Opening Archive C:\DOCUME~1\mbennett\Desktop\Save.pak as 9/16
.-Main : RunAnalysis Started
.- Main : RunAnalysisProcess: Format=PGN
.-Main : RunAnalysis->Attempting to connect to Plugin
.-Main : RunAnalysis->Registering attempt of C:\Program Files\MultiEx Commander\data\plugins\pak\Painkiller.dll
.-Main : RunAnalysis->Progid to connect to Painkiller.archive
.- Main : PlugIn Called: Painkiller PAK Files Extractor version 1.4, type (2), importation(1), varsreturned(5), restypespec(0), cancreate(1)
.Main : RunAnalysisProcess: Starting ProcessListFilePGN
.Main: ProcessListFile: Analyzing Content
MAINMOD: Unloading Splash
.!!!!Import>>ERROR : 

Thanks for the quick reply!
## Post #109
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-30T17:31:28+00:00
- Post Title: n00b needs help

Please attach that save.dat here, if you will, so i can open it. 

I tried another save.dat, and everything worked fine, replacing and stuff. 

Also, I sneakily uploaded a new setup, to include bass.dll and another version of the Painkiller dll. Please install that too.
## Post #110
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-06-30T18:12:06+00:00
- Post Title: n00b needs help

The save.dat is attached below
## Post #111
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-06-30T18:17:49+00:00
- Post Title: n00b needs help

Attach didn't work, trying again with fake extension (it's original name is "save.dat")
[Save.zip](https://xentaxbackup.github.io/file/38_Save.zip)
## Post #112
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-06-30T18:21:23+00:00
- Post Title: n00b needs help

Here's another tidbit of info that may help explain the error.

I had to exchange the save.dat extension to .pak to open it.
## Post #113
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-06-30T19:07:51+00:00
- Post Title: n00b needs help

No longer get the bass.dll error at init   

Still get the same error when trying to replace the file in the archive
## Post #114
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-01T06:04:50+00:00
- Post Title: n00b needs help

I tried and it worked here. 

I could replace it.

So, extraction works for you, it's only the replacing that doesn't?
## Post #115
- Username: Thrasher91604
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2004 10:19 am
- Post datetime: 2004-07-01T06:59:12+00:00
- Post Title: n00b needs help

The editor let me replace it, but then when I try to create a new archive with the replaced file I get the aforementioned error. The file I tried to replace was "Kont_Big_009.CItem"

Is there a way to save the archive with the replaced file without having to create a new archive?
## Post #116
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-01T07:11:52+00:00
- Post Title: n00b needs help

Well, what I do is this. 

- Open the save.dat
- Switch to the Editor
- Either browse to the file in question (Kont_Big etc) and click the arrow to the right (whilst having selected Kont_Big etc in the save.dat) or double-click on the <not replaced> of Kont_Big etc to search for it. 
- Now it is targeted for replacement, you can then click the large "Replace targets" button (second from the left) and then it should replace it. 

It replaces immediately, you don't have to go to "Create new archive" or something. Your save.dat will contain the replacement when you have clicked the "Replace Targets" button. 

Did you use the "Create Archive" option?
## Post #117
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-01T18:54:19+00:00
- Post Title: n00b needs help

I get the same error both ways (by replacing or creating a new archive)
## Post #118
- Username: Linear
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 24, 2005 5:55 pm
- Post datetime: 2005-12-24T10:06:53+00:00
- Post Title: n00b needs help

First of all , i would like to thank Mr.Mouse for this0 great tool !

Ok, now to the point - i'm pretty new to hacking file formats and i tried your tool. It all worked just fine, except with the first PainKiller demo ( the one with the burning city with zombies, the oriental palace etc.). I heard it it's just a pk zip archive and it uses modified identity header.
So my question is , how i would go about opening the first demo pak's , what i need to modify and how ? Is there a tool that does that, or i would have to modify the zip32 source and recompile , in order to make it recognize and extract that "new" archive format ?

Thanks in advance.
