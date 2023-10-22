## Post #1
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-08-11T15:36:29+00:00
- Post Title: research on an obj to vkm converter

hello,

i need some help on researching an obj to vkm converter for a game called fung wan online. right now shahkotay2 has sucesfully created the vkm to obj standalone exporter at [viewtopic.php?f=16&t=10618](http://forum.xentax.com/viewtopic.php?f=16&t=10618). any help would be appreciated. Thanks .
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-11T16:33:13+00:00
- Post Title: research on an obj to vkm converter

As you all may know it's often not too hard to do a 'somewhat-3D-format' to (wavefront) obj conversion
(and create a converter or max script).

But most people expect the reverse way to be comparable simple.

Be told that it's not. Because you have to understand/rebuild the complete format of a 3D mesh file for example to get it loaded by the game engine without crashing.

While on analysing (vkm to obj for example) you can skip many bytes/data and your obj file will be fine, though.

With this said I'll try to build/show a concept for the "obj to vkm" conversion.

But it will take some time and: don't expect too much.

Feel free to contribute.
## Post #3
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-08-11T18:09:26+00:00
- Post Title: research on an obj to vkm converter

thanks. please take your time. i can wait for it
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-16T06:53:36+00:00
- Post Title: research on an obj to vkm converter

having a look at PC18Body.vkm reveals:

first submesh "PC18_Upper Body"
vertex start: 0x78, 307 vertices, vertex stride 44

0x353C, 410 faces, 
0x3540..0x4878, DWORD face indices

2nd submesh
0x6095 "PC18_Lower Body"

There's unknown data from 0x4890 to 0x607C.

You could overwrite these bytes with zeroes, put the vkm back to the game and see whether it crashes.
(If it doesn't we could dare the next step.)
## Post #5
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-08-16T08:52:43+00:00
- Post Title: research on an obj to vkm converter

hi .. i think to start with PC18Body.vkm maybe  a bit too hard because it contains animation. can we use something smaller and dont have any anim such as the CNY mask. if so .. i attach the file with this post.


[cnymask.zip](https://xentaxbackup.github.io/file/9538_cnymask.zip)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-16T10:09:02+00:00
- Post Title: research on an obj to vkm converter

would make sense
header

```
00000 56 4B 59 4D 69 00 00 00  01 00 00 00 00 00 00 00   VKYMi...........
00010 01 00 01 00 00 00 00 00  34 16 00 00 43 6C 6F 6E   ........4...Clon
00020 65 66 72 6F 6E 74 20 66  61 63 65 00 00 00 00 00   efront face.....
00030 00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
00040 00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
00050 00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
00060 F8 55 73 3F 90 72 50 C0  6C 2F 03 41 EE CD E1 40   øUs?rPÀl/.AîÍá@
00070 6F C2 0D 41                                        oÂ.A
```
five floats at 0x60 - so one float missing or it's not bounding box values?
at 0x74 DWORD vertex count: 89 vertices from 0x78 to 0xFC3
at 0xFC4 DWORD face count= 138

from 0xFC8 to 0x163F, 414 DW face indices

data after face indices (0x166C: "cnymask.dds"):

```
01640 00 00 00 00 00 00 00 00  01 00 00 00 24 02 00 00   ............$...
01650 00 00 00 00 95 95 95 01  95 95 95 01 E5 E5 E5 01   ....•••.•••.ååå.
01660 00 00 00 01 CD CC CC 3D  01 00 00 00 63 6E 79 6D   ....ÍÌÌ=....cnym
01670 61 73 6B 2E 64 64 73                               ask.dds
```

0x1677 to end of file: zero fill
## Post #7
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-08-16T10:57:43+00:00
- Post Title: research on an obj to vkm converter

> five floats at 0x60 - so one float missing or it's not bounding box values?
by this do u mean that the item have holes in it? if it is so then yes.



ss1.jpg (224.3 KiB) Viewed 195 times



is there any thing u want me to edit or to try at this vkm?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-16T14:08:48+00:00
- Post Title: research on an obj to vkm converter

> Reply from faridkamil
>
> by this do u mean that the item have holes in it? if it is so then yes.I don't know what it means. A bounding box is the smallest box the object just fits into.

> is there any thing u want me to edit or to try at this vkm?we need to understand the meaning of the header data
(DWORD at 0x18 might be an offset address for example) and the data before the dds filename.

"Clonefront face" should be the name of the mesh.
## Post #9
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2015-11-15T13:30:08+00:00
- Post Title: research on an obj to vkm converter

Hello shakotay2. We've met before    I was asking you about the converter too. I'm interested to know about the converter too. It will help this little game live.
I hope you can make this converter happen. I will appreciate it if you could help.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-15T14:36:44+00:00
- Post Title: research on an obj to vkm converter

Hello WazerHD,
I don't own/play the game.

so see my post as of Sun Aug 16, 2015 7:53 am -

Take PC18Body.vkm, for example,
overwrite the unknown data from 0x4890 to 0x607C with zeroes,
put the vkm back to the game and see whether it crashes.

If it does not we've done a step further.

edit: [viewtopic.php?f=16&t=13184&p=131049&hil ... ed#p131049](http://forum.xentax.com/viewtopic.php?f=16&t=13184&p=131049&hilit=+managed#p131049)
## Post #11
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-11-15T15:59:19+00:00
- Post Title: research on an obj to vkm converter

Hi .. thanks for the explaination. i have replaced  0x4890 to 0x607C for PC18Body.vkm. FYI PC18Body.vkm is for female type 3 character. It does not make the game crash. only make the upperbody of the character disappear.

Refer attachment



> Reply from shakotay2
>
> Hello WazerHD,
I don't owe/play the game.

so see my post as of Sun Aug 16, 2015 7:53 am -

Take PC18Body.vkm, for example,
overwrite the unknown data from 0x4890 to 0x607C with zeroes,
put the vkm back to the game and see whether it crashes.

If it does not we've done a step further.
[upperbody2.jpg](https://xentaxbackup.github.io/file/10020_upperbody2.jpg)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-15T17:40:40+00:00
- Post Title: research on an obj to vkm converter

> Reply from faridkamil
>
> It does not make the game crash. only make the upperbody of the character disappear.yeah, no crash, that's great.

But I still don't have a clue about the structure of this section. (Might be 307x20 bytes, for example.)
Dividing it up into six 1k blocks:

0x4C90-508F
0x5090-548F
0x5490-588F
0x5890-5C8F
0x5C90-608F
0x6090-647C (+19 zeroes)

Do you get a partial vanishing of the upper body if you zero out the last or the 2nd block?

btw, just to recall why we're doing this. faridkamil suggested using a simpler mesh without animations.

If you simply just want to mod the game I'd really recommend to start with inserting your own chest, for example.
Because with new chars/armours skinning will be required as soon as you add/change some vertices.
## Post #13
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2015-11-16T01:20:12+00:00
- Post Title: research on an obj to vkm converter

If the converter is out can i have it too?
I'd like to test it so i could help a little.
I believe the weapons and some other stuff only have 1 part instead of 2 parts in the body model.
## Post #14
- Username: ujang
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 26, 2015 10:08 am
- Post datetime: 2015-11-16T08:26:36+00:00
- Post Title: research on an obj to vkm converter

> Reply from WazerHD
>
> If the converter is out can i have it too?
I'd like to test it so i could help a little.
I believe the weapons and some other stuff only have 1 part instead of 2 parts in the body model.

i don't think so it can use into this game.
btw in this thread i seriously not understand .. hahaha  
it like i become from teletubies land.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-16T09:21:23+00:00
- Post Title: research on an obj to vkm converter

hahaha, yeah, long time no seen any trolls here in this forum.
Feel ignored from now on.

@WazerHD:

> Reply from WazerHD
>
> If the converter is out can i have it too?don't see a reason why not -
but we're far from having one atm.
## Post #16
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-11-16T09:46:43+00:00
- Post Title: Re: research on an obj to vkm converter

@shahkotay2

yea .. as i said armor is a bit tricky. can i proposed few vkm file that dont have any animations. i supply the vkm and u show me what address that i need to fill with 0

1 - Mask : iron_msk.vkm
2 - Armwear Right (iron_brr.vkm) | Armwear Left (iron_brl.vkm)
3 - Footwear Right (iron_grr.vkm) | Footwear Left (iron_grl.vkm)
4 - Saber (iron_sbr.vkm)
5 - Staff (iron_stf.vkm)
6 - Sword (iron_swd.vkm)
7 - Bow (iron_bow.vkm)
8 - Shoulderpad Right : iron_spr.vkm | Shoulderpad Left :  iron_spl.vkm

here is the link to the file : [https://www.fungwan-online.com/vkm.zip](https://www.fungwan-online.com/vkm.zip)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-16T11:13:25+00:00
- Post Title: Re: research on an obj to vkm converter

thanks - 
you can get the address after the face indices (0x29E4) from the
iron_sbr.vkm.obj the FungWang extractor exports:
...
f 202/202/202 203/203/203 200/200/200 
#   29e4: 
# face index min/max: 1 / 203

I'd suggest to zero out the vkm section from 0x2EA0 to 0x2F9F
and in a second step to 0x368F, for example.

btw: seems there's a small bug with the exporter concerning the sabre



iron_sabre.jpg (165.64 KiB) Viewed 158 times
## Post #18
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2015-11-16T17:54:03+00:00
- Post Title: Re: research on an obj to vkm converter

I have edited the iron_sbr.vkm as per instructed and i did not notice any changes with the model. i have attached the file that i edited with this post. in the zip file i also include the texture file for the mesh. (wsb0005l.dds). 
refer the file below
[https://www.fungwan-online.com/saber.zip](https://www.fungwan-online.com/saber.zip)

thanks
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-16T19:05:42+00:00
- Post Title: Re: research on an obj to vkm converter

what happens when you fill in zeroes from 0x2EA0 'til the end of the vkm?

(If the mesh appears to be unchanged pay attention to the texture shading.)
## Post #20
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2015-11-17T04:36:09+00:00
- Post Title: Re: research on an obj to vkm converter

> Reply from shakotay2
>
> what happens when you fill in zeroes from 0x2EA0 'til the end of the vkm?

(If the mesh appears to be unchanged pay attention to the texture shading.)

I've worked on the shading before. I Replace the hexes from shiny shader to non-shiny shader.
kinda replace it like this;


and replace it to this;



If i miss even 1 zeros, the game gonna crash. no idea why.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-17T18:58:32+00:00
- Post Title: Re: research on an obj to vkm converter

> Reply from WazerHD
>
> If i miss even 1 zeros, the game gonna crash. no idea why.that's the reason why we need a full format description

Meanwhile I've got the section start addresses
for Sabre:
0x29f4, 0x2c18

for PC18Body:
0x6095, 0xf314, 0x10834, 0x10b10, 0x155b2

which gives a good start for further analysing.

Headerbytes from offset 0x0C to 0x17 still unknown.
## Post #22
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2016-12-16T16:38:01+00:00
- Post Title: Re: research on an obj to vkm converter

Sorry.. its been awhile .. can we continue on this? anything that i can do to help.
## Post #23
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2017-04-03T16:36:15+00:00
- Post Title: Re: research on an obj to vkm converter

I have analyzed the vkm structure and this is my findings. i am using 1 Sword006.vkm and ZKSword.vkm (Edited based from Sword006.vkm). Here is the links for the diff file :-

[https://www.diffnow.com/?report=f2mn9](https://www.diffnow.com/?report=f2mn9)

what i have found is 

1) Headerbyte from 0x00 to 0x17 is all the same for all vkm file. below is the example

[](https://ibb.co/kKBRDv)

[](https://ibb.co/iOghmF)

[](https://ibb.co/g5LxLa)


2) On 0x18, when i tried to change the value, game load the mesh file but game would not load the dds file

- here is the original value on zksword.dds @ 0x18 value is 12688 , the dds load fine

[](https://ibb.co/hZ5Ttv)

[](https://ibb.co/dBVsmF)

- when i change the value to the original Sword006.vkm @0x18 which is 3496 - the sword did not load the dds but the game still load fine

Original Sword006.vkm
[](https://ibb.co/fERq6F)

After Edit
[](https://ibb.co/jTDgDv)

[](https://ibb.co/k7OZ0a)

3) from 0x5D to  0x73 is the same, but other type of weapon such as bow or saber is using different value

- Sword  0x5D to 0x73
[](https://ibb.co/eGsxmF)

- Mask 0x5d to 0x73
[](https://ibb.co/dLrq6F)

- Bow 0x5d to 0x73
[](https://ibb.co/gnDRfa)

4) from 0x74 is the mesh file i presume?

5) and on zksword.vkm called the dds at 000031C8, but the Sword006.vkm called the dds at 00000DE0.

6) On your post at [posting.php?mode=quote&f=16&p=112364](http://forum.xentax.com/posting.php?mode=quote&f=16&p=112364) , the extractor u have done is perfect, the mesh is indeed like that, when we put alpha dds, it will go invisible.

[](https://ibb.co/cYbXmF)

so far this is what i have manage to find out.
## Post #24
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2017-04-03T16:53:08+00:00
- Post Title: Re: research on an obj to vkm converter

> Reply from shakotay2
>
> 

btw: you could try to increase a known block (vertex or face indices) by adding zero bytes at its end,
then adjust all blockaddresses. 
Keep in mind to change the size of the increased block, too!
Then see whether the changed vkm is loaded successfully by the game.

i`m sorry, can u please point me to the address where i need to add zero bytes. really struggling to find the address of the known block (vertex or face indices)

> Reply from shakotay2
>
> 
what is the size? 0x927F for example
address size
0x6091 + 0x927F
0xF310 + 0x1520
0x10830 + 0x2DC
-----------------------------------------

Another thing is to compare the blockaddresses/sizes of the zksword to the sword and understand what was changed.
btw: a "byte to byte comparision" doesn't make sense! In most cases this works only when the file size doesn't change.

0x6091 + 0x927F -> 0xF310 right. so does this mean the blockaddress is 0xF310 ?
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-03T21:55:10+00:00
- Post Title: Re: research on an obj to vkm converter

> Reply from faridkamil
>
> i`m sorry, can u please point me to the address where i need to add zero bytes. really struggling to find the address of the known block (vertex or face indices)
You could use hex2obj to get an idea of the start/stop addresses: (PC18Body.vkm)



PC18body_vkm.JPG (58.41 KiB) Viewed 91 times


vertex start 0x78: 0x78 + 44 x 307 = 0x6D4 
(vertices of 2nd submesh?)
0x353B last byte of vertex block

FIs start address: 0x3540 +1230 (dec.) x4= 0x4878

0x4877 last byte of first FIs' block


> 0x6091 + 0x927F -> 0xF310 right. so does this mean the blockaddress is 0xF310 ?yep; add 4 bytes -> 0xF314 to get the start of sections which we got 16 months (!) ago, see some posts above.
## Post #26
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2017-04-12T10:42:46+00:00
- Post Title: Re: research on an obj to vkm converter

Hi,

> btw: you could try to increase a known block (vertex or face indices) by adding zero bytes at its end,
>
> then adjust all blockaddresses.

I have added 3 0 bytes at zksword.vkm ending of a known block as per picture below

[](https://ibb.co/bXz1gQ)

and i have change the headerbytes from 3190 to 3193

[](https://ibb.co/cYwQ85)

and the game loads fine, both mesh and texture. if i dont change the headerbytes the game load fine, mesh load fine but it did not load the texture
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-01T06:00:16+00:00
- Post Title: Re: research on an obj to vkm converter

3 weeks ago I managed to create some ugly obj2vkm converter.
It does handle static objects with a single mesh only and there's no plans to extend it on characters:


 FungWan-vkm.zip
(57.53 KiB) Downloaded 27 times



Bounding boxes are supposed to reside at offset 0x005C in the vkm file, but not sure.
So I decided not to update them when injecting the required test.obj into the base vkm (view obj2vkm_readme.txt).
## Post #28
- Username: faridkamil
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Aug 11, 2015 11:17 pm
- Post datetime: 2017-06-01T06:07:31+00:00
- Post Title: Re: research on an obj to vkm converter

> Reply from shakotay2
>
> 3 weeks ago I managed to create some ugly obj2vkm converter.
It does handle static objects with a single mesh only and there's no plans to extend it on characters:
FungWan-vkm.zip

Bounding boxes are supposed to reside at offset 0x005C in the vkm file, but not sure.
So I decided not to update them when injecting the required test.obj into the base vkm (view obj2vkm_readme.txt).

Thank you so much to shakotay2 for your effort in helping our fungwan community. if any of the fungwan player who have knowledge of 3d and want to use this converter and needs help on using this converter can message me via whatsapp or message me (GM)Goku ingame.
