## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-16T23:55:26+00:00
- Post Title: Star Ocean Anamnesis Tools

I have managed to make a working tool for loading the character/monster models. So I have decided to release it with some other tools I have been using.

Decompress ASF (possibly other files too)

Most of the character files use compression type 7 (zstd). You can use this to decompress them : [https://www.mediafire.com/file/2spl5lxx ... Dec_U2.rar](https://www.mediafire.com/file/2spl5lxxjcqk558/SOADec_U2.rar)  Drag and drop a folder on to the exe file and it will try to decompress all the files inside.

If your file has a different compression type, you can use this script : [http://aluigi.org/bms/slz.bms](http://aluigi.org/bms/slz.bms) . Note that both of these methods guess the decryption key, so you might need to decrypt it manually if the program/script fails.

3D Models

Use this tool for loading the models (.asf) and animations (.apk). You need to decompress them before, as described above.



How to use
- Select the model file (.asf) you want to load.
Note :  Weapon/prop placement might be wrong. I don't know if I will ever fix it.

- Select the animation file (.apk) you want to load.
- If file contains multiple animations, you will see arrows to go to the next/previous animation.
- Animate Position :  Will be unchecked by default. It is easier to preview the animations this way. You can check this before exporting if you need to have position keys in the animation.

- Export GLB:  Exports the model in the binary format of GLTF called GLB. There are a bunch of importers for this format. I mainly use Noesis.
- Export NUX:  Exports the model to a custom binary format (.nux), intended to be loaded by Noesis. Noesis script for this format : [NUX Script](https://www.mediafire.com/file/89bozjxaq13edua/fmt_Nux.py/file)

- Export Textures:  Exports all the textures inside the asf file in PNG format. 

Download :  [https://www.mediafire.com/file/wu2jhgwr ... 1.rar/file](https://www.mediafire.com/file/wu2jhgwrad87xja/SOAExporter_V3_U1.rar/file)

An animation preview



Textures

This tool will extract textures as ktx, from the asf/aif files (as always decompress before) : [http://www.mediafire.com/file/6126nmb4w ... SOATex.rar](http://www.mediafire.com/file/6126nmb4wmc5y6h/SOATex.rar) Drag and drop the asf/aif file on to the exe. You can open the extracted ktx with Mali Texture Compression Tool or PVRTextool.

Guides

- [Star Ocean Anamnesis Nox Data Extraction](https://github.com/seiyria/soanamnesis-extract/blob/master/README.md) by seiyria

Bonus - Bullet Girls Phantasia (PS Vita) 

I dropped the support for Bullet Girls. You can try using the old tool for getting some models. Not tested a lot. [Download old exporter](https://www.mediafire.com/file/jhk563hm64eja6d/SOAExporter_U5.rar/file)



Credits
- dian333 - Help with animation research
## Post #2
- Username: warpawn
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 18, 2018 4:12 am
- Post datetime: 2018-08-17T20:16:14+00:00
- Post Title: Star Ocean Anamnesis Tools

SOADec.exe not working for me. I drag cp0101_b01a.asf but nothing happen. Help please.
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2018-08-18T01:21:46+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from warpawn
>
> SOADec.exe not working for me. I drag cp0101_b01a.asf but nothing happen. Help please.
not work single file. you need drag folder.

> Reply from akderebur
>
> I have managed to make a somewhat working tool for loading the character models. So I have decided to release it with some other tools I have been using.

Decompress ASF (possibly other files too)

Most of the character files use compression type 7 (zstd). You can use this to decompress them : http://www.mediafire.com/file/x5jw5wydd ... SOADec.rar  Drag and drop a folder on to the exe file and it will try to decompress all the files inside.

If your file has a different compression type, you can use this script : http://aluigi.org/bms/slz.bms . Note that both of these methods guess the decryption key, so you might need to decrypt it manually if the program/script fails.

3D Models

Use this tool for loading the models from ".asf" files. You need to decompress them before, as described above.

Overview


How to use
- Select the file you want  to use with Browse.
- Load :  Loads the model 
- Load Offset :  If the meshes are misaligned with the skeleton try this option instead. For some models the offset is required, for others it is fine with just Load. I will try to figure this out automatically in a future update.
- Export IQE :  Exports the model in IQE format. How to open/convert IQE: viewtopic.php?p=138153#p138153

Download :   http://www.mediafire.com/file/oay3u5rkq ... porter.rar

Textures

This tool will extract textures as ktx, from the asf/aif files (as always decompress before) : http://www.mediafire.com/file/6126nmb4w ... SOATex.rar Drag and drop the asf/aif file on to the exe. You can open the extracted ktx with Mali Texture Compression Tool or PVRTextool.

Bonus - Bullet Girls Phantasia (PS Vita) 

This game seems to use the same format as SOA. I have made some slight changes to support those files too, but I haven't tried it on lot of files yet. I will try to improve it in the future.



There is room for improvement, and I am planning to work further on this as I have time. Still I wanted to release this version, as it seems to load good amount of character models without a problem.
really great work akderebur.
Some models have UV damage(ex, cc0001_b02a lenath shield and hands), Nevertheless you job really really excellent.
I have one request, you can support manually xor key input?
There are many files that can not be decrypted, cause the keys are different.
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-18T02:44:52+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from einherjar007
>
> 
Some models have UV damage(ex, cc0001_b02a lenath shield and hands),
There seems to be bunch of different vertex block types, so the uv offset/type was wrong for some meshes. You can download the updated tool from the link in the first post. It should fix the uv of that char.

Also I have improved the handling of vertex blocks and how skinned/non-skinned meshes are loaded. So more model support overall. Tried it on some monsters and seems fine.



> Reply from einherjar007
>
> I have one request, you can support manually xor key input?
Yes, I can do that. I will do it some time tomorrow.

> Reply from warpawn
>
> I drag cp0101_b01a.asf but nothing happen.
Like einherjar said, drag and drop the folder that has the asf files, on to the exe.
## Post #5
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2018-08-18T08:29:35+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> Yes, I can do that. I will do it some time tomorrow.

great! can't wait your update.

> Reply from akderebur
>
> There seems to be bunch of different vertex block types, so the uv offset/type was wrong for some meshes. You can download the updated tool from the link in the first post. It should fix the uv of that char.

I could confirm that Lenath shields are repaired, excellent work!
but, I tried [cc0001_b02a.asf, cc0002_b01a.asf] export, they're corrupted UV and Weight of the eye.
cc0001_b02a.asf does incorrect the weight of eyes.
cc0002_b01a.asf had incorrect UV coordinates of the eyes.
I've not tried other files yet, but I think they're have probably the same problems.
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-18T09:58:20+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from einherjar007
>
> 
cc0001_b02a.asf does incorrect the weight of eyes.
Incorrect or no weight? Both eye meshes seem to have no weight data, so they are exported as non-skinned.

> Reply from einherjar007
>
> cc0002_b01a.asf had incorrect UV coordinates of the eyes.
Eyes seem fine to me. Is it not like this with you?


If you encounter another problem send me a pm with a sample file. I didn't get all the files from the game, so I might be missing some.
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2018-08-18T12:17:22+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> 
Incorrect or no weight? Both eye meshes seem to have no weight data, so they are exported as non-skinned.
very sorry, akderebur.
You're right, I'm wrong I used converter is old, wrong output result.

> Reply from akderebur
>
> If you encounter another problem send me a pm with a sample file. I didn't get all the files from the game, so I might be missing some.
You're definitely a hard worker. If find other problems, will send you a file, Thanks!
## Post #8
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-08-18T22:44:26+00:00
- Post Title: Star Ocean Anamnesis Tools

thx man ur tools work perfectly , just didnt realize that the model textures of this game is so small and bad compare to the in-game appearance
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-18T23:55:25+00:00
- Post Title: Star Ocean Anamnesis Tools

I have updated the model tool again, make sure to download the latest version. It should be able to load great deal of monsters or any other skinned mesh now. Also has mesh names too. There might be slight problems with some models still, I will attempt a fix later. I will be busy for a couple of days. Non-skinned stuff like maps/weapons won't load at all probably, but support for those are not high priority.



> Reply from einherjar007
>
> 
great! can't wait your update.
I have updated the decompression tool too. Pass the custom xor key as the second parameter and as hex string. Example usage : "SOADec foldername 6361313266633931".

> Reply from wansf
>
> just didnt realize that the model textures of this game is so small and bad compare to the in-game appearance
Yes, there isn't much going on in terms of textures. There aren't even hair textures for characters. It seems like most of the magic is done via shaders in-game.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-19T02:21:50+00:00
- Post Title: Star Ocean Anamnesis Tools

Can you add an option to output the decompressed buffers to load models not supported b the tool.
## Post #11
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2018-08-19T05:12:20+00:00
- Post Title: Star Ocean Anamnesis Tools

[http://www.mediafire.com/file/dtgmbl6h2 ... e.rar/file](http://www.mediafire.com/file/dtgmbl6h2nlztz1/unpack_move.rar/file)

I created a program to move only the decompressed files to "decrypt" folder.
It may be a slow, but I think a it will work until akderebur tool updates.
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-19T08:20:12+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from chrrox
>
> Can you add an option to output the decompressed buffers to load models not supported b the tool.
I can do that, but I think it will be better/easier if I post the decompression code. I believe you can already get the index buffers using "addr" tags. After you get the buffer the first integer (2 bytes) is not part of the index list. It is the max step that you should use to decode the high watermark. So you read the first integer as max step, and use the methods below on rest of the buffer.

```
{
    List<int> out_inds = new List<int>();

    int hi = max_step - 1;
    foreach (int v in in_inds)
    {
        int decV = hi - v;
        out_inds.Add(decV);
        hi = Mathf.Max(hi, decV + max_step);
    }

    return out_inds;
}

```


```
{
    List<int> out_inds = new List<int>();

    for (int i = 0; i < inds.Count;)
    {
        int a = inds[i++];
        int b = inds[i++];
        int c = inds[i++];
        out_inds.Add(a); out_inds.Add(b); out_inds.Add(c);

        if (a < b)
        {
            int d = inds[i++];
            out_inds.Add(a); out_inds.Add(d); out_inds.Add(b);
        }
    }

    return out_inds;
}

```


You pass the max step and the indices to the "inverse_watermark_transform" and get the decoded indices. Then you pass that result to "unpack_inds" and get the decompressed index list.

Source : [https://fgiesen.wordpress.com/2013/12/1 ... mpression/](https://fgiesen.wordpress.com/2013/12/14/simple-lossless-index-buffer-compression/)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-19T12:55:51+00:00
- Post Title: Star Ocean Anamnesis Tools

can you print the result of the inverse_watermark_transform decompression on this example
03 00 01 00 02 00 05 00 02 00 01 00 02 00 05 00 02 00 
I just want to make sure I am reading it correctly.
3 should be the max_step?
## Post #14
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-19T13:15:06+00:00
- Post Title: Star Ocean Anamnesis Tools

> Reply from chrrox
>
> can you print the result of the inverse_watermark_transform decompression on this example
I won't have access to my computer whole day. I can do it tomorrow.

> Reply from chrrox
>
> 
3 should be the max_step?
If it is the first integer in the buffer then yes, it should be the max step.
## Post #15
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-19T16:27:18+00:00
- Post Title: Star Ocean Anamnesis Tools

Never mind lol I feel stupid I got it now.

1st decomppression
[1, 2, 0, 3, 5, 6, 4, 7]
then back to triangles
1 2 0
1 3 2
5 6 4
5 7 6
## Post #16
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2018-08-22T11:22:07+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

Hi akderebur, can you take a look at the .SPK audio files?
After depressing them by your tool.
Most .SPK files which contains many aideos cannot be played while few others can, as these 
just contains one audio.
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-22T11:39:16+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

A user commented on audio files over at zenhax : [https://zenhax.com/viewtopic.php?p=37609#p37609](https://zenhax.com/viewtopic.php?p=37609#p37609) it might be useful.

If the files aren't decrypted properly because of the wrong key, I can't do much about it sadly. If the program can't guess the correct key, you have to manually find it.
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-23T23:07:21+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

UPDATE
- Can load weapons
- Fixed wrong bone positions (monster weapons mostly) with few of the models. Everything should be fine now
- New uv type
- Attempt at better camera positioning, but still not that great
- Separate checkbox for loading Bullet Girls

At this point it seems to load most of the stuff I throw at it, so I will stop doing tests for the time being. Couple of characters were enough for me anyway  If you encounter a problem with a specific file, pm me and I might take a look.

UPDATE 2

There are some meshes that use multiple uv channels. I have updated the tool to export the secondary uv channel too, for the meshes that have it. So if a mesh appears to have wrong uvs, try the second uv set.

I have attached a modified IQE script to load the secondary uv set. The updated tool is in the first post.
[iqe_import.rar](https://xentaxbackup.github.io/file/14793_iqe_import.rar)
## Post #19
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-07T13:06:39+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

> Reply from akderebur
>
> einherjar007 wrote:
cc0001_b02a.asf does incorrect the weight of eyes.
Incorrect or no weight? Both eye meshes seem to have no weight data, so they are exported as non-skinned.
einherjar007 wrote:cc0002_b01a.asf had incorrect UV coordinates of the eyes.
Eyes seem fine to me. Is it not like this with you?


If you encounter another problem send me a pm with a sample file. I didn't get all the files from the game, so I might be missing some.
i think i did  something wrong here,  both of you can decrypt  cc0001_b02a.asf and cc0002_bo1a.asf and load them in IQE exporter. 
 on my computer,soadec was not able to decrypt them . I managed to unpack them using the slz.bms, but  I got model error when l loaded them in  iqe exporter .

Another thing, i was able to get unpack and get the model of cp0518_b01a.asf, but when I used the texture tool, I only got  .raw files
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-07T15:08:54+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

> Reply from tone
>
> 
i think i did  something wrong here,  both of you can decrypt  cc0001_b02a.asf and cc0002_bo1a.asf and load them in IQE exporter. 
 on my computer,soadec was not able to decrypt them.
You are dragging the folder containing the asf files, right? If you are dragging the asf files it won"t work.
## Post #21
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-08T06:37:54+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

> Reply from akderebur
>
> 
You are dragging the folder containing the asf files, right? If you are dragging the asf files it won"t work.
i did, i dragged  the hi folder  on to  the decrypter, but  cc0001_b02a and cc0002_b02b  weren't unpacked
## Post #22
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-08T08:42:29+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

Can you pm me the those 2 asf files then? I only tried the files of the JP version, and they were fine for the most part. Are you getting the files from JP or Global?
## Post #23
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2018-09-08T19:17:23+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

when try to read .apk action but find some trouble...
is it a Bone_Matrix bug happen ?or build action in wrong way
main code

```
                        Q_y = ba.readFloat()
                        Q_z = ba.readFloat()
                        Q_w = ba.readFloat()
                        Q_read = mathutils.Quaternion((Q_w,Q_x,Q_y,Q_z))
                        bpy.data.objects[BONE_hierarchy_name].pose.bones[bonename].rotation_quaternion = Q_read.inverted()
```

some simple pose works，like :
charater   "ネル ダガー"(cp0305_b01a) Motion: viewer_Daggercp0305_b01a
home_t_stance (T-Pose)
but a lot of action is just look like the gameplay，inaccurate
here is a spin action

====
edit:fix the W-xyz，Thank akderebur.
edit2:fix read location_XYZ move,:the  reading way mark by "03 05 04",now it's active.and fix the Blender .iqe plugin(2012-12-2),sorry to author "Tor Andersson".directly,ban "has_v0" (about curmesh) in line633

```
has_v0 = False#len(iqmodel.meshes[0].v0) > 0
```

now some .iqe model don't make bug when import into Blender,like cp0005_b01a(ベルダ,gunner),cp0108_b01a(フィア) ...etc
sadly,find more problems:1.Bone_Matrix bug,all Bead user character,like cp0110_b01a, the bone "R:at_W08Be" use 2 bone_matrix
reading Bone way marking "FF 07 02 02" ?(not sure) have some
A.location[0,-90.86,0] scale[1,1,1] 
B.
```
[0,0.93457,0,     -2.3]
[0,0,0.93457,        0]
```

when use animation,the bone use location[0,-90.86/0.93457,0] as origin_point,in another word=copy parent_bone "R:POS_Pad2" bone_matrix.check in action"viewer_Beadscp0110_b01a_unpack" (character:マーヴェル)and "viewer_BeadsFemale_unpack"
pic up later ==
cp005,bone of lash or bone of eye may lack of some animation

cp0110,マーヴェル
NOT SSR female character who use bead(magic_ball) as weapon have a default action"viewer_BeadsFemale_unpack" .
if.not fix bone"R:at_W08Be"

change it's bone_matrix = it's parent_bone's bone_matrix
 
cp0110's action  in view_room
 
(have fix reading  euler_rotation way marking"02 07 08", one of the skirt bone,"R:XD_SLska_01" use it )
=====
edit3:fix location_move marking"03 00 01", "03 00 02","03 00 03"
 (mainly be used in bone[R:POS_ROOT] to control charater's X,Z.   in bone[R:Hips] to control Y  ,example:FemaleKnuckle_unpack   xxx.aaf)
 fix  euler_rotation way marking"03 05 08"
and,In default,  euler_rotation data  translate to quternion "WXYZ". it's convenient for Blender NLA_editor .
now,majority RUSH action('s location_moving) should be worked,except for some action use 6 byte/Frame rotation data.
[StarOceam_motion_apk_date10_31.zip](https://xentaxbackup.github.io/file/15102_StarOceam_motion_apk_date10_31.zip)
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-08T22:51:40+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

Instead of inverting the whole Quaternion just invert the y and z components. Should be like this :

```
Q_y = -ba.readFloat()
Q_z = -ba.readFloat()
Q_w = ba.readFloat()
Q_read = mathutils.Quaternion((Q_w,Q_x,Q_y,Q_z))
                    
bpy.data.objects[BONE_hierarchy_name].pose.bones[bonename].rotation_quaternion = Q_read

```
## Post #25
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-09T05:28:26+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

can anyone confirm whether  star ocean jp still run on emulator?  I manage to run it on nox, but then  it closes itself.  I sometimes managed pass main menu and  get the game to download  a little file before it closes. thanks
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-09T11:05:16+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

you need to set the emulator's mode to phone.
## Post #27
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-10T09:59:44+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

> Reply from chrrox
>
> you need to set the emulator's mode to phone.
thanks,  it still closes,  but  at least it stays open long enough to download a few mb
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-10T10:22:36+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

use Android5.1.1 mode

file links (NA)
[http://production-cache.na.so-ana.com/d ... ll.version](http://production-cache.na.so-ana.com/download/28424/Android/manifest/etc2/hi/version_latest_all.version)
[http://production-cache.na.so-ana.com/d ... ll.version](http://production-cache.na.so-ana.com/download/28424/IOS/manifest/etc2/hi/version_latest_all.version)
[http://production-cache.na.so-ana.com/d ... st_all.bin](http://production-cache.na.so-ana.com/download/28424/Android/manifest/etc2/hi/version_latest_all.bin)
[http://production-cache.na.so-ana.com/d ... st_all.bin](http://production-cache.na.so-ana.com/download/28424/IOS/manifest/etc2/hi/version_latest_all.bin)
## Post #29
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-11T11:23:05+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

> Reply from chrrox
>
> use Android5.1.1 mode

file links (NA)
http://production-cache.na.so-ana.com/d ... ll.version
http://production-cache.na.so-ana.com/d ... ll.version
http://production-cache.na.so-ana.com/d ... st_all.bin
http://production-cache.na.so-ana.com/d ... st_all.bin

thank you chrrox
## Post #30
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-09-12T07:48:47+00:00
- Post Title: Re: [WIP] Star Ocean Anamnesis Tools

is it possible to download assets only with NOX?
## Post #31
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-12T15:39:14+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Tosyk
>
> is it possible to download assets only with NOX?
yes, use multi instance 5.11 , emulator mode (phone).  you have to be patient because the game  closes  itself
## Post #32
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-13T00:46:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

@dian333 Nice work on the animation script.

> Reply from dian333
>
> 
now some .iqe model don't make bug when import into Blender,like cp0005_b01a(ベルダ,gunner),cp0108_b01a(フィア) ...etc
Are you using the new iqe script : [viewtopic.php?p=143565#p143565](http://forum.xentax.com/viewtopic.php?p=143565#p143565) ? I have added v0 for secondary UV Channel. The new script should be able to load it fine, but you might have problems if you are using the old one.

> Reply from dian333
>
> check in action"viewer_Beadscp0110_b01a_unpack" (character:マーヴェル)and "viewer_BeadsFemale_unpack"
I have tried "viewer_Beadscp0110_b01a" and it looks more or less fine to me. Am I missing something?
## Post #33
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2018-09-13T13:16:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

the old one...there before
and the new uv layer have no UV message or the same as another old UV layer..still have to spilt some mesh by hand ,which should use different material.
## Post #34
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-13T13:24:28+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from dian333
>
> still have to spilt some mesh by hand ,which should use different material.
I have never encountered that before. From what I have seen no split is necessary. I haven't tested loads of characters though, so I can't say that is the case 100%.
## Post #35
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2018-09-15T16:29:23+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I am working with bullet girls. Tried to extract textures from iqe but get error.
[2018-09-15 16_01_55-Greenshot.jpg](https://xentaxbackup.github.io/file/14848_2018-09-15 16_01_55-Greenshot.jpg)
## Post #36
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-15T17:00:48+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from andthen619
>
> Tried to extract textures from iqe but get error.
You should be getting the textures from asf/aif files. Still I don't think the image extractor works with the Bullet Girls atm, I haven't checked the textures yet. I will do it and update the program when I have the time.
## Post #37
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2018-09-23T00:11:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from dian333
>
> ...
How use animation script? In blender not working. =\
[https://imgur.com/m1Ff1Bt](https://imgur.com/m1Ff1Bt)
## Post #38
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2018-09-26T16:22:13+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mrtest
>
> 
How use animation script? In blender not working. =\
https://imgur.com/m1Ff1Bt
change the object.name "cp0513_b01a_unpack.amt" to "cp0002_b01a_unpack.amt" match the code 
pose_reset("cp0002_b01a_unpack.amt") ,and  loadAqm_NIFL(...,"cp0002_b01a_unpack.amt")
or change the code default_Object_name
str_apk="...." also will be rewrite to match your PC data filepath ,
loadAqm_NIFL(str_apk+...)  input the name of animation file.
battle animation file usually have 20 action,like "win_LOOP.aaf" and RUSH action ,you can change "i_aaf = .." to read Specific one.Or just add a # before "trackback()" then find it in blender action_editor .
different character's  have a lot of same action,maybe it is a little boring.i only check the character who feed up in my box...
## Post #39
- Username: BiteMeUniverse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 19, 2018 8:59 am
- Post datetime: 2018-10-19T01:59:31+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I dug the thread for a while, couldn't find how to manually find the decryption code so that the SOAExporter would convert a file (in a folder). I didn't wanna PM akderebur because I've asked enough from him. 

As well, the ability to grab animations, that entire section, I understood none of it. Saw a lot of lines of code and was able to read the structured arguments but I have no idea how to get that off of the APKs. Unless I drag and drop the zip file in that section to blender, that's about all I'm missing....blender....

C4D Imports the files just fine after exporting the rigged character from Noesis.
## Post #40
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-20T10:18:27+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from BiteMeUniverse
>
> couldn't find how to manually find the decryption code
I have a better version of SOADec that finds most of the keys automatically. I will update my post with the new version when I get back home on Monday. If I don't forget
## Post #41
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-10-22T10:19:15+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> BiteMeUniverse wrote:couldn't find how to manually find the decryption code 
I have a better version of SOADec that finds most of the keys automatically. I will update my post with the new version when I get back home on Monday. If I don't forget

up
## Post #42
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-10-22T15:05:54+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Updated the SOADec link in first post. As before the tool will work with type 7 asf files only.
## Post #43
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-10-22T15:21:11+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> Updated the SOADec link in first post. As before the tool will work with type 7 asf files only.
thxxxx
## Post #44
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2018-11-27T01:32:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from dian333
>
> ...
Not bad. Thx!


There are problems with textures and sometimes the animation does not work correctly. But overall it looks great.   

[](https://imgur.com/pcacnMt)
[](https://imgur.com/kKpZJKQ)
## Post #45
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-08T05:32:34+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

well done~~;
thx
## Post #46
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-01-17T18:19:31+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from dian333
>
> when try to read .apk action but find some trouble...
is it a Bone_Matrix bug happen ?or build action in wrong way
main code
Code: Select all                        Q_x = ba.readFloat()
                        Q_y = ba.readFloat()
                        Q_z = ba.readFloat()
                        Q_w = ba.readFloat()
                        Q_read = mathutils.Quaternion((Q_w,Q_x,Q_y,Q_z))
                        bpy.data.objects[BONE_hierarchy_name].pose.bones[bonename].rotation_quaternion = Q_read.inverted()
some simple pose works，like :
charater   "ネル ダガー"(cp0305_b01a) Motion: viewer_Daggercp0305_b01a
home_t_stance (T-Pose)
but a lot of action is just look like the gameplay，inaccurate
here is a spin action

====
edit:fix the W-xyz，Thank akderebur.
edit2:fix read location_XYZ move,:the  reading way mark by "03 05 04",now it's active.and fix the Blender .iqe plugin(2012-12-2),sorry to author "Tor Andersson".directly,ban "has_v0" (about curmesh) in line633
Code: Select allhas_v0 = False#len(iqmodel.meshes[0].v0) > 0
now some .iqe model don't make bug when import into Blender,like cp0005_b01a(ベルダ,gunner),cp0108_b01a(フィア) ...etc
sadly,find more problems:1.Bone_Matrix bug,all Bead user character,like cp0110_b01a, the bone "R:at_W08Be" use 2 bone_matrix
reading Bone way marking "FF 07 02 02" ?(not sure) have some
A.location[0,-90.86,0] scale[1,1,1] 
B.Code: Select all[0.93457,0,0,    0]
[0,0.93457,0,     -2.3]
[0,0,0.93457,        0]
when use animation,the bone use location[0,-90.86/0.93457,0] as origin_point,in another word=copy parent_bone "R:POS_Pad2" bone_matrix.check in action"viewer_Beadscp0110_b01a_unpack" (character:マーヴェル)and "viewer_BeadsFemale_unpack"
pic up later ==
cp005,bone of lash or bone of eye may lack of some animation

cp0110,マーヴェル
NOT SSR female character who use bead(magic_ball) as weapon have a default action"viewer_BeadsFemale_unpack" .
if.not fix bone"R:at_W08Be"

change it's bone_matrix = it's parent_bone's bone_matrix
 
cp0110's action  in view_room
 
(have fix reading  euler_rotation way marking"02 07 08", one of the skirt bone,"R:XD_SLska_01" use it )
=====
edit3:fix location_move marking"03 00 01", "03 00 02","03 00 03"
 (mainly be used in bone[R:POS_ROOT] to control charater's X,Z.   in bone[R:Hips] to control Y  ,example:FemaleKnuckle_unpack   xxx.aaf)
 fix  euler_rotation way marking"03 05 08"
and,In default,  euler_rotation data  translate to quternion "WXYZ". it's convenient for Blender NLA_editor .
now,majority RUSH action('s location_moving) should be worked,except for some action use 6 byte/Frame rotation data.
How did you import the animation apks? Whrn I try to import them, It comes out looking messy.
## Post #47
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-17T23:49:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Probably, your procedure is not wrong. If it is wrong, it can not be imported. 
Not all animations are processed correctly, only partly.
## Post #48
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-01-18T14:48:57+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007
>
> Probably, your procedure is not wrong. If it is wrong, it can not be imported. 
Not all animations are processed correctly, only partly.
Well the thing is I tried this tutorial

> Reply from dian333
>
> 
change the object.name "cp0513_b01a_unpack.amt" to "cp0002_b01a_unpack.amt" match the code 
pose_reset("cp0002_b01a_unpack.amt") ,and  loadAqm_NIFL(...,"cp0002_b01a_unpack.amt")
or change the code default_Object_name
str_apk="...." also will be rewrite to match your PC data filepath ,
loadAqm_NIFL(str_apk+...)  input the name of animation file.
battle animation file usually have 20 action,like "win_LOOP.aaf" and RUSH action ,you can change "i_aaf = .." to read Specific one.Or just add a # before "trackback()" then find it in blender action_editor .
different character's  have a lot of same action,maybe it is a little boring.i only check the character who feed up in my box...
But I am a bit confused with this procedure. It would be best to create a Noesis plugin.
## Post #49
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-18T15:27:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from MarioSonicU
>
> It would be best to create a Noesis plugin.
Using dian333's research, I am planning to add animation support to the tool. There is one data type that got figured out recently, and I haven't implemented it in code yet. I will release an update after I implement that too.
## Post #50
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-18T15:41:38+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from MarioSonicU
>
> It would be best to create a Noesis plugin.
I agree that the replacement procedure is troublesome.
I do not have any knowledge of the script. However, they can be relaxed somewhat by using string variable.
Let's try it later.

> Reply from akderebur
>
> Using dian333's research, I am planning to add animation support to the tool. There is one data type that got figured out recently, and I haven't implemented it in code yet. I will release an update after I implement that too.
That's great news. I'm looking forward to the next report.
## Post #51
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2019-01-19T17:54:08+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

can anyone tell me where is the file asset?s
## Post #52
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-01-21T23:02:49+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from kurokozeref
>
> can anyone tell me where is the file asset?s
I think you have to root your device. the file assets are under "data\data\com.square_enix.android_googleplay.StarOceanj\files\download"

Note: this is if you have the Japanese version of the game.
## Post #53
- Username: DrXadium
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 24, 2019 11:57 am
- Post datetime: 2019-01-24T04:04:12+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I am trying to get to the assets via Nox emulation (I want to try and rip the Gemini Sunrise Sakura Taisen event model before that ends) but even with root mode set up and using either the Nox browser or ES File Explorer with root on, when I navigate to that folder, there is no "download:" folder present (And I know it downloaded several gigs of data / hidden folder viewing is on). 

Is there anywhere else this data could be located in the filesystem?
## Post #54
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-25T23:25:23+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

UPDATE
- Vertex normals support
- Experimental animation support (research credits to dian333) : Will not work with some animation files
- New export format (.nexs) 

Updated download link in the first post.

Note :  You need to download this Noesis script for loading exported animations : [Nexs Script](https://www.mediafire.com/file/exu7446rh5qzr64/fmt_Nexs.py/file)
## Post #55
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-01-26T18:57:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> UPDATE
- Vertex normals support
- Experimental animation support (research credits to dian333) : Will not work with some animation files
- New export format (.nexs) 

Updated download link in the first post.

Note :  You need to download this Noesis script for loading exported animations : Nexs Script
Thanks for updating the tool. By the way would you mind taking a look at these animation files? It's for two of the Sakura Taisen collab characters. I take it that their animations are a bit broken. Will you be updating your program to improve motion support.
[viewer_Swordcc0022_b01a_unpack.zip](https://xentaxbackup.github.io/file/15589_viewer_Swordcc0022_b01a_unpack.zip)
## Post #56
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-01-26T19:11:54+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from MarioSonicU
>
> I take it that their animations are a bit broken.
Yep, that is why I said some animations won't work, mostly the newer ones.

> Reply from MarioSonicU
>
> 
Will you be updating your program to improve motion support.
I just released an update. If I was able to improve it I would have released the improved version 

If someone figures out more about the animation format, I would gladly implement it in my program. I am not planning to work actively on the animations though.
## Post #57
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-01-26T19:35:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> MarioSonicU wrote:I take it that their animations are a bit broken.
Yep, that is why I said some animations won't work, mostly the newer ones.
MarioSonicU wrote:
Will you be updating your program to improve motion support.
I just released an update. If I was able to improve it I would have released the improved version 

If someone figures out more about the animation format, I would gladly implement it in my program. I am not planning to work actively on the animations though.
I guess that makes sense.
## Post #58
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-01-31T17:08:37+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

How does the textures work in this game?
## Post #59
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-02-02T11:04:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

The diffuse map will probably look dark. 
There are two diffuse map textures, and good results can be obtained by synthesizing them with an appropriate effect.

not sure about hair. Everything is the odd primary color. 
I pull out the transparent alpha map from the channel and adjust the color tone by myself.

Also, this game only has much smaller texture than you can see on the game.
Probably because advanced shader magic is being used, the same result can not be obtained with models and textures alone.

Tri-Ace's game features a lot of special specifications 
Despite much hope, the PS2 Valkyrie Profile 2 model has not yet been extracted.
two contributors akderebur (model), and dian333 (animation).
the achievement that made it possible to extract data like this time. That's a miracle job.
## Post #60
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-02T12:41:17+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007
>
> 
Despite much hope, the PS2 Valkyrie Profile 2 model has not yet been extracted.
I am pretty sure there is a maxscript for SO3 on the forums, which also works with Valkyrie Profile 2 and Radiata Stories. I guess there was no skeleton support though.

I was planning to make a tool for VP2 but I didn't get a chance to start, because of other games. Maybe I can do it sometime.
## Post #61
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-02-02T15:05:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> einherjar007 wrote:
Despite much hope, the PS2 Valkyrie Profile 2 model has not yet been extracted.

I am pretty sure there is a maxscript for SO3 on the forums, which also works with Valkyrie Profile 2 and Radiata Stories. I guess there was no skeleton support though.

I was planning to make a tool for VP2 but I didn't get a chance to start, because of other games. Maybe I can do it sometime.
Unfortunately, the SO3 script supports some VP2 models, but most of them can not be read.
It is a part of the field and NPC, and most of the main characters can not be read...

But if you were able to create tools for VP2 it would be really wonderful.
I'm not want to break the rules of the forum, but I don't hesitate to pay for consideration.
Because VP2 is the game I loved the most and models and textures are very beautiful.

by the way, I know that the model in battle scenes has been diverted to Valkyrie Anatomia.
## Post #62
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-02T19:28:20+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007
>
> 
by the way, I know that the model in battle scenes has been diverted to Valkyrie Anatomia.
I didn't get this. Does that mean VA uses the same models as VP2?

This reminded me that I should release the Valkyrie Anatomia tool. It has been quite some time since I finished it, but too lazy to clean up and upload
## Post #63
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-02-02T23:20:46+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur
>
> einherjar007 wrote:
by the way, I know that the model in battle scenes has been diverted to Valkyrie Anatomia.
I didn't get this. Does that mean VA uses the same models as VP2?

This reminded me that I should release the Valkyrie Anatomia tool. It has been quite some time since I finished it, but too lazy to clean up and upload

Yes, but only for models of low polygons in battle.
Of course the file format is different. I talk about geometory. Although there are some differences somewhat accurately, I think it is almost the same.
Alicia, Lufas, Lezard(Boss).

The VP2 tool is also desirable, but Anatomia's tools would be great, too. We will wait for the next report!
## Post #64
- Username: DrXadium
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 24, 2019 11:57 am
- Post datetime: 2019-02-14T00:31:52+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Perhaps a silly question, but I have managed to extract the models given the tools above, but I'm not sure how thetextures are supposed to be applied. I extracted them separately, but am not sure how to reapply them to the model. Does this have to be done in another tool?
## Post #65
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-14T02:09:47+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from DrXadium
>
> I extracted them separately, but am not sure how to reapply them to the model.
You can do that in a 3D Software of your choice : Blender, Maya, 3ds Max etc.
## Post #66
- Username: DrXadium
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jan 24, 2019 11:57 am
- Post datetime: 2019-02-15T22:42:19+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I managed to get a model out, and it looks like Noesis sees bones, but when I export to Blender (trying as .OBJ and .DAE) it doesn't seem to bring the bones over. Is there any kind of special setting or parameter I need to set? I tried the UV flipping based on some other threads I had seen on the forum, but with no luck. 

Alternatively, is there another program I could / should be pulling it into if I want the skeleton, so I can try posing the model?

EDIT: : I *think* I solved it in case anyone else has the issue. Export as .FBX with the parameter -fbxnewexport .
## Post #67
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-15T22:48:53+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Obj format doesn't have skeleton/skinning support, so you shouldn't be using that. Dae should work fine actually, but I use fbx export myself. I don't know if Blender can import fbx though.

Alternatively you can export the model as IQE and use the IQE import script for Blender. Maybe that might work better for you. There are links in the first post for how to load IQE.
## Post #68
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2019-02-18T08:35:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Dose this tool fit for pc version?
## Post #69
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-18T08:48:06+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from phay008 ↑Mon Feb 18, 2019 4:35 pm at Mon Feb 18, 2019 4:35 pm
>
> 
Dose this tool fit for pc version?
There is no PC version.
## Post #70
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2019-02-18T08:55:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Mon Feb 18, 2019 4:48 pm at Mon Feb 18, 2019 4:48 pm
>
> 
phay008 wrote: ↑Mon Feb 18, 2019 4:35 pm
Dose this tool fit for pc version?

There is no PC version.

Sorry iT'S my fault,Star Ocean Anamnes，Star Ocean 4:The Last Hope are not the same games.
## Post #71
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2019-02-18T09:55:03+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from dian333 ↑Thu Sep 27, 2018 12:22 am at Thu Sep 27, 2018 12:22 am
>
> 
battle animation file usually have 20 action,like "win_LOOP.aaf" and RUSH action ,you can change "i_aaf = .." to read Specific one.Or just add a # before "trackback()" then find it in blender action_editor .

Hi akderebur, what about this. I use your noesis plugin, but when i load the file which should contains mutipule actions. 
I just get the first action.
## Post #72
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-18T10:39:24+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from z22901206 ↑Mon Feb 18, 2019 5:55 pm at Mon Feb 18, 2019 5:55 pm
>
>  
I just get the first action.
Yea, it is like that atm. I can add support for multiple animations some time.
## Post #73
- Username: pepitomama
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 23, 2019 7:06 pm
- Post datetime: 2019-02-24T20:01:23+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hi! I followed all steps but I can't decompress/unpack models and textures...   

For Models I take the Characters folder of in-game files and for Textures the Images folder.... I used Nox to take the files with root and  ES file manager Pro...

I drag and drop the folder that contains the .asf files to the SOADec.exe, cmd black screen appeared, it closes, and no decompress/unpack files over there... so I can't open them with SOAExporter and so on...  Same for textures (even with textures I tried it manually with node.js command prompt and master files but no extracted files...)

I don't know what I'm doing bad, I tried, tried and tried but no results come, please some help with it    thanks!
## Post #74
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-24T20:53:54+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from pepitomama ↑Mon Feb 25, 2019 4:01 am at Mon Feb 25, 2019 4:01 am
>
> 
I can't decompress/unpack
I am assuming you are using the files from the global/english version of the game. Only the JP version of the game works atm. Global version files are using a new encryption method.
## Post #75
- Username: pepitomama
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 23, 2019 7:06 pm
- Post datetime: 2019-02-24T21:16:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hmmm I see... D:  I'll try it with the jp files then xd Thanks for the quick response!  



Current Status: Downloading jp files...
## Post #76
- Username: pepitomama
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 23, 2019 7:06 pm
- Post datetime: 2019-02-25T17:38:18+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Mon Feb 25, 2019 4:53 am at Mon Feb 25, 2019 4:53 am
>
> 
pepitomama wrote: ↑Mon Feb 25, 2019 4:01 am
I can't decompress/unpack

I am assuming you are using the files from the global/english version of the game. Only the JP version of the game works atm. Global version files are using a new encryption method.

It Works  Thank you again! Not for all files but almost, I just wanted it in order to make a study of 3d models and setup in mobile games
## Post #77
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-02-27T00:19:02+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I have not noticed SOA recently, but akderebur's wonderful tool does not yet support multi animation.
we need to manually import it with the script created by dian333 until akderebur updates the tool.
I mentioned earlier that we will use variable strings to save time of replacement.

Since the import mechanism does not change at all, there is no improvement. 
I do not have any knowledge of the script. It just makes it easier to use.

----

I have found a problem about weights. 
In the silmeria of cc0002_b01a.asf there seems to be no face weight. There is no problem with the body.
[StarOceam_motion_apk_date10_31_replace.zip](https://xentaxbackup.github.io/file/15811_StarOceam_motion_apk_date10_31_replace.zip)
## Post #78
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-02-27T02:37:09+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007 ↑Wed Feb 27, 2019 8:19 am at Wed Feb 27, 2019 8:19 am
>
> 
I have not noticed SOA recently, but akderebur's wonderful tool does not yet support multi animation.
we need to manually import it with the script created by dian333 until akderebur updates the tool.
I mentioned earlier that we will use variable strings to save time of replacement.

Since the import mechanism does not change at all, there is no improvement. 
I do not have any knowledge of the script. It just makes it easier to use.

----

I have found a problem about weights. 
In the silmeria of cc0002_b01a.asf there seems to be no face weight. There is no problem with the body.

I think any questions relating to animation might be answed by dian333. Though he hasn't been seen since valentine's day.
## Post #79
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-27T07:25:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Multi animation wouldn't take too much time to implement, but I am lazy to change the GUI for it and add an option to select which animation to export. I will do an update some time.

> Reply from einherjar007 ↑Wed Feb 27, 2019 8:19 am at Wed Feb 27, 2019 8:19 am
>
> 
cc0002_b01a.asf there seems to be no face weight
Rarely some of the meshes don't have weights. I have seen this with eyes, but don't remember if I have seen face meshes too. Still send me that file and I will take a quick look to be sure it isn't a bug.
## Post #80
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2019-03-03T14:52:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

@akderebur is it possible to make texture extractor and injector tool for bullet girls?
## Post #81
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-03T15:29:43+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from andthen619 ↑Sun Mar 03, 2019 10:52 pm at Sun Mar 03, 2019 10:52 pm
>
> 
is it possible to make texture extractor and injector tool for bullet girls?
Maybe extractor, but I can't bother with a repacker. I don't think I have the files of that game anymore. If you can post 2-3 aif/asf files, I can take a look.
## Post #82
- Username: fdtggf
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 07, 2016 3:12 am
- Post datetime: 2019-03-03T17:08:48+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Sun Mar 03, 2019 11:29 pm at Sun Mar 03, 2019 11:29 pm
>
> 
andthen619 wrote: ↑Sun Mar 03, 2019 10:52 pm
is it possible to make texture extractor and injector tool for bullet girls?

Maybe extractor, but I can't bother with a repacker. I don't think I have the files of that game anymore. If you can post 2-3 aif/asf files, I can take a look.
I have some sample ,akderebur can you try this?
[
https://mega.nz/#!RZgl0CxQ!RswbVDyF-rP ... utqSyLZ57Q](https://mega.nz/#!RZgl0CxQ!RswbVDyF-rPUoBUxCmj6coAUPoeI06tbNutqSyLZ57Q)
## Post #83
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-03T19:01:54+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from fdtggf ↑Mon Mar 04, 2019 1:08 am at Mon Mar 04, 2019 1:08 am
>
> 
I have some sample ,akderebur can you try this?
I can get the image data out, but I don't know the pixel format used. They seem to be 4/8bpp images. Might be one of the pixel formats supported by GXT.

I will attach the raw pixel data (compressed) of a texture, in case someone wants to take a look. It should be a 512x512 jeans texture when loaded properly.
[jeans - 512x512 - NA.rar](https://xentaxbackup.github.io/file/15824_jeans - 512x512 - NA.rar)
## Post #84
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-04T03:24:23+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Mon Mar 04, 2019 3:01 am at Mon Mar 04, 2019 3:01 am
>
> I will attach the raw pixel data (compressed) of a texture, in case someone wants to take a look.
that sample is morton swizzled dxt3   

> Reply from fdtggf ↑Mon Mar 04, 2019 1:08 am at Mon Mar 04, 2019 1:08 am
>
> 
I have some sample ,akderebur can you try this?
https://mega.nz/#!RZgl0CxQ!RswbVDyF-rPU ... utqSyLZ57Q
what game and platform are these samples from?
## Post #85
- Username: fdtggf
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 07, 2016 3:12 am
- Post datetime: 2019-03-04T03:55:09+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Acewell ↑Mon Mar 04, 2019 11:24 am at Mon Mar 04, 2019 11:24 am
>
> 
akderebur wrote: ↑Mon Mar 04, 2019 3:01 amI will attach the raw pixel data (compressed) of a texture, in case someone wants to take a look.
that sample is morton swizzled dxt3   
fdtggf wrote: ↑Mon Mar 04, 2019 1:08 am
I have some sample ,akderebur can you try this?
https://mega.nz/#!RZgl0CxQ!RswbVDyF-rPU ... utqSyLZ57Q
what game and platform are these samples from?

Bullet Girls Phantasia ps vita version
## Post #86
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-04T04:28:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from fdtggf ↑Mon Mar 04, 2019 11:55 am at Mon Mar 04, 2019 11:55 am
>
> Bullet Girls Phantasia ps vita version
thanks, here is Noesis python script to open your aif samples.  


 tex_BulletGirlsPhantasia_PSVita_aif.zip
(873 Bytes) Downloaded 94 times


supports morton swizzled dxt1, dxt3, dxt5
## Post #87
- Username: fdtggf
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 07, 2016 3:12 am
- Post datetime: 2019-03-04T05:31:12+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Acewell ↑Mon Mar 04, 2019 12:28 pm at Mon Mar 04, 2019 12:28 pm
>
> 
fdtggf wrote: ↑Mon Mar 04, 2019 11:55 amBullet Girls Phantasia ps vita version
thanks, here is Noesis python script to open your aif samples.   
tex_BulletGirlsPhantasia_PSVita_aif.zip
supports morton swizzled dxt1, dxt3, dxt5

thank's your help Acewell
## Post #88
- Username: slideblue
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 31, 2016 9:05 am
- Post datetime: 2019-03-27T07:39:57+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hi,akderebur.
Im working on ripping SO2 Rena blue sphere models.(updated on JP ver. this March)
I tried to export "cp0202_b06a.asf", but the models have UV damage.
Also i tried to export with updated tools, but still does not work.
Does "cp0202_b06a.asf" work correctly? or do i still miss something?
## Post #89
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-03-27T09:50:52+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from slideblue ↑Wed Mar 27, 2019 3:39 pm at Wed Mar 27, 2019 3:39 pm
>
> 
I tried to export "cp0202_b06a.asf", but the models have UV damage.
PM me the file. I will take a look when I have the time.

Edit : Checked the model and everything is fine. You have to use the secondary uv sets for some meshes.
## Post #90
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2019-03-27T17:30:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Acewell ↑Mon Mar 04, 2019 12:28 pm at Mon Mar 04, 2019 12:28 pm
>
> 
fdtggf wrote: ↑Mon Mar 04, 2019 11:55 amBullet Girls Phantasia ps vita version
thanks, here is Noesis python script to open your aif samples.   
tex_BulletGirlsPhantasia_PSVita_aif.zip
supports morton swizzled dxt1, dxt3, dxt5

Thank you! I was able to extract the textures from bullet girls with this script. Is there a way to inject my modified textures back in?
## Post #91
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-30T01:47:27+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from andthen619 ↑Thu Mar 28, 2019 1:30 am at Thu Mar 28, 2019 1:30 am
>
> Is there a way to inject my modified textures back in?
not that i'm aware of, modding is not my area though.
## Post #92
- Username: vainotechnik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 29, 2019 9:30 pm
- Post datetime: 2019-03-31T10:45:21+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Acewell ↑Mon Mar 04, 2019 12:28 pm at Mon Mar 04, 2019 12:28 pm
>
> 
fdtggf wrote: ↑Mon Mar 04, 2019 11:55 amBullet Girls Phantasia ps vita version
thanks, here is Noesis python script to open your aif samples.   
tex_BulletGirlsPhantasia_PSVita_aif.zip
supports morton swizzled dxt1, dxt3, dxt5

Thanks for releasing the script! Very useful in exploring those lingerie images in the cpk data. 

However my concern is that of the converted IQE / NEXS from asf files. It loads no texture at all? 
I want to explore character / weapon textures in the game.
## Post #93
- Username: okitasan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 18, 2018 8:46 am
- Post datetime: 2019-04-02T12:42:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

After the latest JP update SOADec nor the slz script are working anymore. [Error screenshot](https://i.imgur.com/oqX382L.png). [Sample files if needed](https://www.mediafire.com/file/mlq25s723y7cn4j/SOA.rar/file), has some aif images and an old version of a model (working) and the new one (not working). Thank you for your wonderful tool.
## Post #94
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-04-02T14:51:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from okitasan ↑Tue Apr 02, 2019 8:42 pm at Tue Apr 02, 2019 8:42 pm
>
> 
After the latest JP update SOADec nor the slz script are working anymore.
New encryption. Since this is an online game,  keys are probably sent over the network and can be changed over time. So it would require constant finding of the keys. I also think that different files use different keys. Overall not worth the effort.

Technically model and texture tools still work. You are on your own for getting the decrypted files though.
## Post #95
- Username: otherself
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 04, 2012 12:26 am
- Post datetime: 2019-04-11T21:44:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

The models from Bullet Girls Phantasia are not coming with UV. Am I the only one with this problem? Or...

Anyway, thanks for the program.
## Post #96
- Username: esterTion
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 26, 2019 9:05 am
- Post datetime: 2019-04-26T01:21:59+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

So someone requested me to take a look at this game's asset encryption. 
Basically, there are two asset versions, marked by integer after the ADLD header. Decryption of two versions already exists on the first release of the game, so it’s not that the game updated the encryption, but changed from an older algorithm. 

I also looked at your tool, and that XOR key guessing is pretty charming. 
To properly obtain the key, first calculate the crc32 of the asset path, like “Character/cc0001_b01a.apk”. Note that here is not the standard crc32, the standard crc32 initialize the crc with value 0xFFFFFFFF, this initialize it with string length. 
Then here’s the different, in v1 asset, convert crc to hex, and this is the xor key. 
In v2 asset, pad this crc with 0 to 32 length, then convert this as hex to binary string, the result is the key for AES128, IV is hex2bin(“09375711857134629684891855841614”)

So if use this proper way to get the key, accurate asset path is needed.

Reference:
Standard crc32: [https://opensource.apple.com/source/xnu ... rn/crc32.c](https://opensource.apple.com/source/xnu/xnu-792.13.8/bsd/libkern/crc32.c)
## Post #97
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-27T01:11:19+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

What version are you looking at of the apk could you say what offset the function is at in that version.
## Post #98
- Username: esterTion
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 26, 2019 9:05 am
- Post datetime: 2019-04-27T02:48:24+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

jp v2.7.0, 0xC99940

How to find this function in other version: 
Find "Framework::CFileLoader::SetDecryptFunction" usage in "CGame::OnInitialize", F5, click on the off_xxx above the function call, function reference is at + 0x14 (6 int below)
There should be a obvious "MOV R2, #0x444C4441" at fourth instruction, this function exists at the first version of the game
## Post #99
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-28T03:58:21+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Can you show an example of a string and the correct crc and key.
are these the options you used? "32 -1 -1 0 0 1"
## Post #100
- Username: esterTion
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 26, 2019 9:05 am
- Post datetime: 2019-04-29T02:26:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from chrrox ↑Sun Apr 28, 2019 11:58 am at Sun Apr 28, 2019 11:58 am
>
> 
Can you show an example of a string and the correct crc and key.
Character/cc0001_b01a.apk       00000000000000000000003566186470

> Reply from chrrox ↑Sun Apr 28, 2019 11:58 am at Sun Apr 28, 2019 11:58 am
>
> 
are these the options you used? "32 -1 -1 0 0 1"
What's this
## Post #101
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-30T21:12:13+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

what values do you put in this site to get it to work?
[http://www.sunshine2k.de/coding/javascr ... rc_js.html](http://www.sunshine2k.de/coding/javascript/crc/crc_js.html)
## Post #102
- Username: esterTion
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 26, 2019 9:05 am
- Post datetime: 2019-05-01T10:03:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from chrrox ↑Wed May 01, 2019 5:12 am at Wed May 01, 2019 5:12 am
>
> 
what values do you put in this site to get it to work?
http://www.sunshine2k.de/coding/javascr ... rc_js.html

Weird, can't figure out the parameter

This is my code, CRCTABLE is from the above apple open source file

```
  $remaining = strlen($str);
  $crc = 0;
  if ($remaining) {
    $crc = $remaining;
    /*
    crc32 standard：
    $crc = 0xFFFFFFFF;
    */
    $i = 0;
    do {
      $current_char = ord($str[$i]);
      $remaining--;$i++;
      $crc = CRCTABLE[($current_char ^ $crc) & 0xff] ^ ($crc >> 8);
    } while ($remaining);
  }
  return $crc;
}

```


Also, I've written an article about this
[https://estertion.win/2019/04/%e6%98%9f ... %e6%b3%95/](https://estertion.win/2019/04/%E6%98%9F%E4%B9%8B%E6%B5%B7%E6%B4%8B-%E8%AE%B0%E5%BF%86-%E8%B5%84%E6%BA%90%E7%AE%97%E6%B3%95/)
(In Chinese, might auto play background music)
## Post #103
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-02T13:52:16+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I have released a new version of SOADec for decrypting/decompressing the latest files. You can find it in the first post. Usage is the same. Credits to esterTion for figuring out the decryption method.
## Post #104
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-05-02T15:26:31+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

esterTion, akderebur, fantastic job.

The new collaboration character (GGX Sol) has been confirmed, but it has been loaded successfully.
Of course, past models are also loaded properly.
## Post #105
- Username: alduin2000
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 30, 2019 8:34 pm
- Post datetime: 2019-05-02T16:31:36+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Thanks akderebur and esterTion for your works!
I have a personal request, since no one have interest to extract files from Star Ocean 5, I really want to do. This game use the same file extention of Anamnesis, (.AIF) for textures and (.ASF) for 3D models. They are compressed in somekind of SLZ type but I really don't know.  

In the attachments there are a couple a sample files, extracted from the PS4 version of the game.


 samples.zip
(88.47 KiB) Downloaded 29 times



Is this possible to use the SOADec tool for decompress these files?
## Post #106
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-02T17:04:16+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from alduin2000 ↑Fri May 03, 2019 12:31 am at Fri May 03, 2019 12:31 am
>
> 
Is this possible to use the SOADec tool for decompress these files?
No, but I have posted the decompression code for SLZ type 3 on zenhax : [https://zenhax.com/viewtopic.php?p=45696#p45696](https://zenhax.com/viewtopic.php?p=45696#p45696)

I have also modified my model and texture tools a bit to work with SO5 but there isn't anything interesting really. Models are almost identical to SOA. It seems like they used the assets from SO5 directly in SOA. So you are not missing too much in terms of character models since SOA has almost all of them I guess. I am not really interested in other stuff, so didn't check anything else.
## Post #107
- Username: esterTion
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Apr 26, 2019 9:05 am
- Post datetime: 2019-05-07T01:34:37+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Thu May 02, 2019 9:52 pm at Thu May 02, 2019 9:52 pm
>
> 
I have released a new version of SOADec for decrypting/decompressing the latest files. You can find it in the first post. Usage is the same. Credits to esterTion for figuring out the decryption method.

After a week off I finally have some time to look at your update. 
So here are two suggestion:
1. Why not support both asset version? It is there at 0x4.
2. Guessing original path from extension might not be enough, have a list of all possible path and try every one will definitly improve the tool. (I'm not sure about AES decrypt speed, maybe only try first 16 bytes and look for "DCNE")
## Post #108
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-07T06:38:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I am not really concerned about the quality of SOADec. My main tools are model/texture ones. So as long as it can decrypt the models folder it is fine  I just added image and motions folder too for other people's convinience.

Feel free to make a tool yourself if you feel mine is not enough for your needs. I don't enjoy encryption stuff and busy working on other games atm, so I probably won't update SOADec anytime soon.
## Post #109
- Username: DumbFish
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 04, 2019 2:28 am
- Post datetime: 2019-06-03T18:33:08+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Can someone explain to me how the decompress tool works, I'm pretty new to this.  I've been able to move my character files from nox to my pc (which show up as assorted .apk and .acf files) but then I get stuck.  Perhaps its a stupid question, but how do I unpack these .apk files?

Edit:
Ok, so I see I'm supposed to be dragging the folder with the files in them, not just the individual files.  Would this be the character folder that I copied from nox?  When I drag the folder to the decompress tool nothing happens.  I'm also a little curious why my files are .acf and not .asf.

Edit Edit:
Welp I'm a dummy.  The .asf files where in the hi folder.
## Post #110
- Username: lord014
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 29, 2018 6:28 am
- Post datetime: 2019-06-06T00:11:52+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Fri May 03, 2019 1:04 am at Fri May 03, 2019 1:04 am
>
> 
alduin2000 wrote: ↑Fri May 03, 2019 12:31 am
Is this possible to use the SOADec tool for decompress these files?

No, but I have posted the decompression code for SLZ type 3 on zenhax : https://zenhax.com/viewtopic.php?p=45696#p45696

I have also modified my model and texture tools a bit to work with SO5 but there isn't anything interesting really. Models are almost identical to SOA. It seems like they used the assets from SO5 directly in SOA. So you are not missing too much in terms of character models since SOA has almost all of them I guess. I am not really interested in other stuff, so didn't check anything else.

Does SO5 have higher res textures?
## Post #111
- Username: alduin2000
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 30, 2019 8:34 pm
- Post datetime: 2019-06-15T17:08:12+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

SO5 is a bit different from SOA.  
SO5 have high poly 3D models with high res textures. Probably 2048x2048 for the characters. 
But I'm totally sure that are better 3D models, because smartphone doesn't have enough gpu power to move to many polygons, SOA is low poly. SOA is SO5 Lite Edition   

sorry for my english
## Post #112
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-15T17:55:23+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from alduin2000 ↑Sun Jun 16, 2019 1:08 am at Sun Jun 16, 2019 1:08 am
>
> 
But I'm totally sure that are better 3D models
Like I said main characters are almost identical. I modified my SOA tool and extracted some chars. Geometry and skeleton are almost same. Even some SOA animations work with SO5 chars.

Textures are higher quality for sure. Maybe some environment/monster models too but I don't care for those. I don't see the need for SO5 tool now, also busy with other games. Maybe if there is more interest I might finish it and release it.
## Post #113
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2019-06-16T02:08:17+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from alduin2000 ↑Sun Jun 16, 2019 1:08 am at Sun Jun 16, 2019 1:08 am
>
> 
SO5 is a bit different from SOA.  
SO5 have high poly 3D models with high res textures. Probably 2048x2048 for the characters. 
But I'm totally sure that are better 3D models, because smartphone doesn't have enough gpu power to move to many polygons, SOA is low poly. SOA is SO5 Lite Edition   

sorry for my english

nah most of the game wtever PC or smartphone do not have high poly models because its unnecessary , they use shader and lighting to make them looks good , SOA SO5 are one of them , so do FF15 ,MHW, SEKIRO
## Post #114
- Username: DeathChaos
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 01, 2017 2:27 pm
- Post datetime: 2019-10-11T00:05:58+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I don't know if the tool creator still checks here, but worth a try!

We're attempting to dump the models and animations from SOA for the new collaboration with P5R.

The models successfully dump with load offset.

Animations are completely broken, when we load an apk file, the model just, well, I guess "explodes" would be the correct word.

And while models load correctly with load offset, Makoto Yuki's evoker (gun model) loads on origin position (and rigged 100% to Root bone), while loading it with the misaligned skeleton sort of loads it in the intended position albeit offset a bit (edit: just tested Joker, his gun model has the same problem).
## Post #115
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-10-12T15:10:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from DeathChaos ↑Fri Oct 11, 2019 8:05 am at Fri Oct 11, 2019 8:05 am
>
> 
I don't know if the tool creator still checks here
I still check the forums time to time, but I don't have the time to work on model ripping projects atm.

I am aware of both the prop misposition and animation problems. No plans to fix them on my part.
## Post #116
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2019-10-13T23:45:05+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from DeathChaos ↑Fri Oct 11, 2019 8:05 am at Fri Oct 11, 2019 8:05 am
>
> 
I don't know if the tool creator still checks here, but worth a try!

We're attempting to dump the models and animations from SOA for the new collaboration with P5R.

The models successfully dump with load offset.

Animations are completely broken, when we load an apk file, the model just, well, I guess "explodes" would be the correct word.

And while models load correctly with load offset, Makoto Yuki's evoker (gun model) loads on origin position (and rigged 100% to Root bone), while loading it with the misaligned skeleton sort of loads it in the intended position albeit offset a bit (edit: just tested Joker, his gun model has the same problem).

You could ask dian333, but he has'nt been on the forums since valentine's day.
## Post #117
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2019-10-14T08:19:44+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

is it still possible to run the game on nox?
## Post #118
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2019-10-14T19:29:28+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from tone ↑Mon Oct 14, 2019 4:19 pm at Mon Oct 14, 2019 4:19 pm
>
> 
is it still possible to run the game on nox?

Looks like the latest update will prevent the game from even downloading it, if you use 3rd party download tools to get the apk file it wont let you install it, I'm not aware if there are ways to circumvent that
## Post #119
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2019-10-16T10:34:15+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from GDL ↑Tue Oct 15, 2019 3:29 am at Tue Oct 15, 2019 3:29 am
>
> 
tone wrote: ↑Mon Oct 14, 2019 4:19 pm
is it still possible to run the game on nox?


Looks like the latest update will prevent the game from even downloading it, if you use 3rd party download tools to get the apk file it wont let you install it, I'm not aware if there are ways to circumvent that
ah crap.  thanks for answering
## Post #120
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2019-10-16T10:34:38+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

By the way, if we use vpn to  download a game from japanese google play,  do  we still need an active vpn to download the game data?
## Post #121
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2019-10-20T22:48:20+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from tone ↑Wed Oct 16, 2019 6:34 pm at Wed Oct 16, 2019 6:34 pm
>
> 
By the way, if we use vpn to  download a game from japanese google play,  do  we still need an active vpn to download the game data?

Just found out that the game was updated to ONLY work with 64bit android phones, so you might need to wait for the emulators to release an update before trying to download the game.
## Post #122
- Username: ilove3dmodels
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 19, 2019 4:47 pm
- Post datetime: 2019-11-17T16:37:10+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I would like to get Bullet Girls 3D models (player character(s))
How can I get them?
Im confused
## Post #123
- Username: ilove3dmodels
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 19, 2019 4:47 pm
- Post datetime: 2019-11-19T14:32:43+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from vainotechnik ↑Sun Mar 31, 2019 6:45 pm at Sun Mar 31, 2019 6:45 pm
>
> 
Acewell wrote: ↑Mon Mar 04, 2019 12:28 pm
fdtggf wrote: ↑Mon Mar 04, 2019 11:55 amBullet Girls Phantasia ps vita version
thanks, here is Noesis python script to open your aif samples.   
tex_BulletGirlsPhantasia_PSVita_aif.zip
supports morton swizzled dxt1, dxt3, dxt5


Thanks for releasing the script! Very useful in exploring those lingerie images in the cpk data. 

However my concern is that of the converted IQE / NEXS from asf files. It loads no texture at all? 
I want to explore character / weapon textures in the game.

You have playable character models for Bullet Girls phantasia?
## Post #124
- Username: vertalion336
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 22, 2018 2:53 pm
- Post datetime: 2019-11-30T17:29:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Thank you for the tool !
I want to ask, is it possible to rip the model from star ocean japanese version with this tool ?, since the global version of this game have been shutdown, anyone here still have the latest datas from global apk ?
## Post #125
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-11-30T18:10:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from vertalion336 ↑Sun Dec 01, 2019 1:29 am at Sun Dec 01, 2019 1:29 am
>
> 
is it possible to rip the model from star ocean japanese version with this tool ?

Why not try and see for yourself  It should be possible. The tool always targeted the jp version anyway.

You will need the old SOADec though. It seems like they reverted to old encryption recently, with an update.
## Post #126
- Username: ilove3dmodels
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Mar 19, 2019 4:47 pm
- Post datetime: 2019-12-01T23:05:46+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Sun Dec 01, 2019 2:10 am at Sun Dec 01, 2019 2:10 am
>
> 
vertalion336 wrote: ↑Sun Dec 01, 2019 1:29 am
is it possible to rip the model from star ocean japanese version with this tool ?


Why not try and see for yourself  It should be possible. The tool always targeted the jp version anyway.

You will need the old SOADec though. It seems like they reverted to old encryption recently, with an update.

hello
sorry you dont think you can help me please?
I am trying to get models for bullet girls 2 or phantasia
i try to open the software but nothing happens
i dont even really know what to do
## Post #127
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2020-02-01T21:40:58+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Can i confirm that this tool should be able to extract models from the psp vita game Bullet Girls Phantasia WITH uvs intact
So far i can get the models into blender eaither by exporting to iqe and using the blender importer or by exporting as nexs and going the noesis route
Both methods gives me the model in blender but the uvs are all squashed to the right and stretches into infinity along the y axis

I can get the model i can get the textures but i cant get anything with working uvs
Am i missing something or??
## Post #128
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-02T07:57:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from speaker60 ↑Sun Feb 02, 2020 5:40 am at Sun Feb 02, 2020 5:40 am
>
> 
I can get the model i can get the textures but i cant get anything with working uvs
I haven't  checked many bullet girls files. Some of them might be using different uv data types like star ocean. If you send me a sample I can take a look.
## Post #129
- Username: Cyn1kal
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 20, 2017 8:32 am
- Post datetime: 2020-02-04T00:30:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Does anyone have the Makoto Yuki and Orpheus models from the P5R event?
## Post #130
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-21T12:32:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

NEW UPDATE : SOAExporter V2

- Support for new animation types (most animations should load now)
- Support for files with multiple motion clips
- UI overhaul
- Dropped bullet girls support
## Post #131
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-21T19:08:24+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Thanks for the great update!
Check and test it tomorrow.

It looks like ADLD encryption has returned from AES to XOR.
In the case of AES, getting CRC32 allowed me to manually decompress some of the files that SOADec could not decompress.
Now that back to XOR, I'll try to see if I can manually decompress files that SOADec cannot.

*EDIT
Thank you very much. It works very well.
Many animations that couldn't be played until now can be played normally.
Also, it is very convenient because we can select the animation to output on the Viewer.
it's funtastic job. Thanks!
## Post #132
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-22T11:10:05+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007 ↑Sat Feb 22, 2020 3:08 am at Sat Feb 22, 2020 3:08 am
>
> 
It looks like ADLD encryption has returned from AES to XOR.
Yes, they reverted to the old one. I should probably update SOADec to use proper decryption using CRC names. For now it should work fine with most files.

> Reply from einherjar007 ↑Sat Feb 22, 2020 3:08 am at Sat Feb 22, 2020 3:08 am
>
> 
Thank you very much. It works very well.
Nice to hear that it works fine for you
## Post #133
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-22T11:59:11+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

This time, I focused on some files that cannot be decrypted by SOADec. Some of them could be deployed when AES.

I compared the files to see why they couldn't be decrypted with XOR.
Many of them seem to require different XOR comparisons with other files.

53 4C 5A 05 00 01 25 00 E0 04 08 00 30 3A 0C 00

XORing this binary data allowsto manually decrypt some files that cannot currently be decrypted by SOADec.
(ex. cm102_b01b.asf , cn0005_b01a.asf)
## Post #134
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-22T12:42:59+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007 ↑Sat Feb 22, 2020 7:59 pm at Sat Feb 22, 2020 7:59 pm
>
> 
53 4C 5A 05 00 01 25 00 E0 04 08 00 30 3A 0C 00
That is normal than. 53 4C 5A 05 is SLZ5 which is not supported by SOADec. It will only work for SLZ7.
## Post #135
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-22T12:59:25+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Sat Feb 22, 2020 8:42 pm at Sat Feb 22, 2020 8:42 pm
>
> 
einherjar007 wrote: ↑Sat Feb 22, 2020 7:59 pm
53 4C 5A 05 00 01 25 00 E0 04 08 00 30 3A 0C 00

That is normal than. 53 4C 5A 05 is SLZ5 which is not supported by SOADec. It will only work for SLZ7.

thanks reply! I didn't know because there was no knowledge about the file format.
thanks for the tips!
## Post #136
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-02-24T14:56:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Is there any way to download assets only via Bluestacks? Apparently the only Android emulator besides BStacks to support 64-bit versions of MEMu, but SOA crashes when you try to install it on them.

I don't know if this is a good idea, but could anyone PM me the game files? I would love do root my phone to get the files myself, but I don't want to run the risk of losing warranty, or getting my phone hacked.
## Post #137
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-02-24T16:20:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

i also need the game files of the latest version.
## Post #138
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-25T01:56:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

hmm, Actually, I don't even have a Root device.
I ran SOA on a non-root device and got the URL of the asset by packet capture.
## Post #139
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-02-25T04:04:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007 ↑Tue Feb 25, 2020 9:56 am at Tue Feb 25, 2020 9:56 am
>
> 
hmm, Actually, I don't even have a Root device.
I ran SOA on a non-root device and got the URL of the asset by packet capture.

How'd you do that?
## Post #140
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-02-25T18:33:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from MarioSonicU ↑Mon Feb 24, 2020 10:56 pm at Mon Feb 24, 2020 10:56 pm
>
> 
Is there any way to download assets only via Bluestacks? Apparently the only Android emulator besides BStacks to support 64-bit versions of MEMu, but SOA crashes when you try to install it on them.

I don't know if this is a good idea, but could anyone PM me the game files? I would love do root my phone to get the files myself, but I don't want to run the risk of losing warranty, or getting my phone hacked.

do you have the game files
## Post #141
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-02-25T18:41:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from ChaoticFusion40 ↑Wed Feb 26, 2020 2:33 am at Wed Feb 26, 2020 2:33 am
>
> 
MarioSonicU wrote: ↑Mon Feb 24, 2020 10:56 pm
Is there any way to download assets only via Bluestacks? Apparently the only Android emulator besides BStacks to support 64-bit versions of MEMu, but SOA crashes when you try to install it on them.

I don't know if this is a good idea, but could anyone PM me the game files? I would love do root my phone to get the files myself, but I don't want to run the risk of losing warranty, or getting my phone hacked.


do you have the game files

I can't access them w/o rooting my phone, and that's a risk I'm not willing to take.
## Post #142
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-02-27T22:40:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Attached a program that downloads the game assets automatically. Use SOADec as usual after getting the assets. Thanks to einherjar007 for getting the urls.

Download everything
- You can just run the program and it will download all the assets.

Filtering
- If you just want to download specific folders you can use filtering. In cmd just write the letter codes of the folders, without any spaces. For example the below usage will only download Character and Motion folders.

```
> SOADown cm
```

Filters
- b = BG
- c = Character
- d = Deco
- e = Effect
- i = Image
- m = Motion
- s = Sound
- w = Weapon

REMOVED
## Post #143
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2020-04-02T12:50:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hi there, i was interested in ripping bullet girls phantasia models
but i can't seem to get the textures ?

i can rip the models just fine, they export and all, but how do you get the textures ?
i tried the asf and aif files it creates a "texture" folder but its empty

Thanks...
## Post #144
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-02T13:11:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Tsunani ↑Thu Apr 02, 2020 8:50 pm at Thu Apr 02, 2020 8:50 pm
>
> 
but how do you get the textures ?

Vita : [viewtopic.php?p=149112#p149112](https://forum.xentax.com/viewtopic.php?p=149112#p149112)

PC : [viewtopic.php?p=161229#p161229](https://forum.xentax.com/viewtopic.php?p=161229#p161229)
## Post #145
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2020-04-02T13:20:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Thu Apr 02, 2020 9:11 pm at Thu Apr 02, 2020 9:11 pm
>
> 
Tsunani wrote: ↑Thu Apr 02, 2020 8:50 pm
but how do you get the textures ?


Vita : viewtopic.php?p=149112#p149112

PC : viewtopic.php?p=161229#p161229

Ah thank you very much, i might have missed it, sorry for the trouble
## Post #146
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-04-08T09:19:53+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

So with soadown and soadec_u2 the sound files can be unpacked too, it seems is some sort of generic container file with an ISF header then a bunch of file names and a bunch of CAA (aac/laac) files after that:





Is there any script to extract the aac files without having to do it manually one by one via hex editor?
## Post #147
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-04-22T17:24:43+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Did they update the game or disable the extractor? because every time I ran it says "Error getting the version file."

And talking of it, but were are the textures of the models? because they're not on the Image file.
## Post #148
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-22T18:32:31+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Darkhowlings ↑Thu Apr 23, 2020 1:24 am at Thu Apr 23, 2020 1:24 am
>
> 
Did they update the game or disable the extractor? because every time I ran it says "Error getting the version file."

Updated the tool. Download here : [viewtopic.php?p=160398#p160398](https://forum.xentax.com/viewtopic.php?p=160398#p160398)

> Reply from Darkhowlings ↑Thu Apr 23, 2020 1:24 am at Thu Apr 23, 2020 1:24 am
>
> 
were are the textures of the models? because they're not on the Image file.
They are inside the asf file. Drag and drop on SOAImgEx.
## Post #149
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-04-22T19:46:25+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Thu Apr 23, 2020 2:32 am at Thu Apr 23, 2020 2:32 am
>
> 
They are inside the asf file. Drag and drop on SOAImgEx.

The .as that are in the Character folder? Because they are way too small for being a texture, but, I will give a try.

And thank you for take your time for update the tool.

EDIT:
No, still getting same message.
## Post #150
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-22T21:06:15+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Darkhowlings ↑Thu Apr 23, 2020 3:46 am at Thu Apr 23, 2020 3:46 am
>
> 
The .as that are in the Character folder?

The same file you get the 3d model from  It contains the textures too. Load it with "SOAExporter" to get the model, with "SOAImgEx" to get the textures.

> Reply from Darkhowlings ↑Thu Apr 23, 2020 3:46 am at Thu Apr 23, 2020 3:46 am
>
> 
No, still getting same message.

They must have updated the url recently for the new update. Try again now.
## Post #151
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-04-23T01:21:03+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Thu Apr 23, 2020 5:06 am at Thu Apr 23, 2020 5:06 am
>
> 
Darkhowlings wrote: ↑Thu Apr 23, 2020 3:46 am
The .as that are in the Character folder? 


The same file you get the 3d model from  It contains the textures too. Load it with "SOAExporter" to get the model, with "SOAImgEx" to get the textures.
Darkhowlings wrote: ↑Thu Apr 23, 2020 3:46 am
No, still getting same message.


They must have updated the url recently for the new update. Try again now.
Yes, it could had being the server, because now it works like a charm!

And I didn't notice of that, now it did extract all the textures.
Thanks you a lot for help me!
## Post #152
- Username: Mojang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 05, 2019 12:49 am
- Post datetime: 2020-04-27T19:04:50+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hi akderebur,

Thank you so much for the detailed walkthrough, quick question on the download tool.
Is it working for Win 10 1909? Tried running it in admin and compatibility and it pops up quickly saying 'Getting the version file' and closes.
Sorry for the noobish question.  I'm an artist student just venturing into 3D modeling and have been a fan of the series.

Best Regards!
## Post #153
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-27T19:26:08+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mojang ↑Tue Apr 28, 2020 3:04 am at Tue Apr 28, 2020 3:04 am
>
> 
Tried running it in admin and compatibility and it pops up quickly saying 'Getting the version file' and closes.
Try again now. The url got updated. That is why it wasn't working. Should work now.
## Post #154
- Username: Mojang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 05, 2019 12:49 am
- Post datetime: 2020-04-27T20:09:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Thank you so much! Works awesome
## Post #155
- Username: chrnodroid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 17, 2019 5:41 pm
- Post datetime: 2020-05-02T09:14:12+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from GDL ↑Wed Apr 08, 2020 5:19 pm at Wed Apr 08, 2020 5:19 pm
>
> 
Is there any script to extract the aac files without having to do it manually one by one via hex editor?

I've found a tool that can extract ogg files, it's called "Nova Software Extractor", 
but I still don't know how to extract aac files. 
Extracting them manually from hex editor one by one is impossibile because there are thousands of these aac files.
It would be nice if someone can do a bms script for that
## Post #156
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-02T10:00:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from chrnodroid ↑Sat May 02, 2020 5:14 pm at Sat May 02, 2020 5:14 pm
>
> 
It would be nice if someone can do a bms script for that
If you mean extracting aac files from spk, you can use the attached bms script. Use after decompressing with SOADec.
[soa_isf_unp.rar](https://xentaxbackup.github.io/file/18073_soa_isf_unp.rar)
## Post #157
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-05-03T00:31:16+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

akderebur, Thanks for the script.

need to change the aac extension to .laac.
Previously it could not be played without rewriting(0x148), but it seems that there is no need to rewrite if it is the latest vgmstream.
(Tested on foobar2000 with vgmstream plugin r1050-2946-g1e583645)

Also, some files are ogg instead of aac. can distinguish it in the header.
## Post #158
- Username: chrnodroid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 17, 2019 5:41 pm
- Post datetime: 2020-05-03T08:46:59+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Thanks for the script akderebur! It's work like a charm.
Tested the extracted laac with foobar2000 and latest vgmstream, everything works like a charm.
I think now almost everything has been extracted in this games.
Thanks!
## Post #159
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2020-05-08T12:57:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Please. Add support Tales Of Crestoria. APK: [https://apkpure.com/de/store/apps/detai ... storia_obt](https://apkpure.com/de/store/apps/details?id=com.bandainamcoent.crestoria_obt)
## Post #160
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-08T13:48:30+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mrtest ↑Fri May 08, 2020 8:57 pm at Fri May 08, 2020 8:57 pm
>
> 
Please. Add support Tales Of Crestoria.
I will take a look. Interesting that they use ASKA engine.

Edit : 

Everything is almost same as SOA, with small changes. I got the models and images working. Just need to take a look at animations. I will release the new tools when I have the time.

Here is a random character model and image from the game.
## Post #161
- Username: tatsumaki04
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 16, 2020 8:38 am
- Post datetime: 2020-05-18T02:03:20+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Have anyone found Ky kiske or Dizzys voice files? i think their missing on the sound folder or the game assets aren't latest? 
I managed to find Sol badguy and Elphelt files though.
i went and listen every "gacha" voice lines to find the characters, so far cc0028_2021_Gacha_010.laac is sol and elpheit - cc0029_2021_Gacha_010.laac.
I thought ky kiske was - cc0030_2021_Gacha_010.laac, but i dont think thats him.
And do you guys rename every extensions manual? is there easier way to just rename their extensions?
## Post #162
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-05-28T02:28:55+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Do anyone  have the star ocean anamnesis characters file I been looking  around  but can not find them.
## Post #163
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-06-14T11:16:50+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I get the error "error getting version file" when i try to downlaod files with the > SOADown cm command with cmd. Did they update urls again? please help
## Post #164
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-14T16:57:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Makoto ↑Sun Jun 14, 2020 7:16 pm at Sun Jun 14, 2020 7:16 pm
>
> 
I get the error "error getting version file" when i try to downlaod files

It should work now.
## Post #165
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-06-15T06:42:58+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Mon Jun 15, 2020 12:57 am at Mon Jun 15, 2020 12:57 am
>
> 
Makoto wrote: ↑Sun Jun 14, 2020 7:16 pm
I get the error "error getting version file" when i try to downlaod files


It should work now.

It is downloading files now, thank you so much!
## Post #166
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-06-15T09:25:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from tatsumaki04 ↑Mon May 18, 2020 10:03 am at Mon May 18, 2020 10:03 am
>
> 
Have anyone found Ky kiske or Dizzys voice files? i think their missing on the sound folder or the game assets aren't latest? 
I managed to find Sol badguy and Elphelt files though.
i went and listen every "gacha" voice lines to find the characters, so far cc0028_2021_Gacha_010.laac is sol and elpheit - cc0029_2021_Gacha_010.laac.
I thought ky kiske was - cc0030_2021_Gacha_010.laac, but i dont think thats him.
And do you guys rename every extensions manual? is there easier way to just rename their extensions?

I'm looking at models and the only number skipped seems to be 25, I can't find dizzy's model either, and 28, 29 and 30 are other chars just like the audio
edit: char 43
## Post #167
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-07-16T23:19:09+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

is SOA Down not working for anyone else?
## Post #168
- Username: Aiye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 28, 2018 7:13 pm
- Post datetime: 2020-07-17T03:23:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

It's definitely not working at the moment. Maybe they changed something with the new update?
## Post #169
- Username: bymutou
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Nov 08, 2018 9:57 am
- Post datetime: 2020-07-30T11:06:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

error getting the version file
## Post #170
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-01T12:45:40+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

UPDATE

- New vertex/normal type support

> Reply from GDL ↑Fri Jul 17, 2020 7:19 am at Fri Jul 17, 2020 7:19 am
>
> 
is SOA Down not working for anyone else?
I won't be maintaing SOADown anymore.
## Post #171
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-08-07T07:22:23+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I,m looking for star ocean Anamnesis games or the character file but it nowhere to be fond.
## Post #172
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-08-09T19:27:27+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

[https://mega.nz/file/DpwQUSQZ#rp-Dx8IcO ... Yio6yedBw4](https://mega.nz/file/DpwQUSQZ#rp-Dx8IcOx_OcbFz5VgEGx-lC6Ckv72VNYio6yedBw4)
[ss.jpg](https://xentaxbackup.github.io/file/18579_ss.jpg)
## Post #173
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-08-16T05:35:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

can,t open file  is this the model  [https://sta.sh/01bak27qyzue](https://sta.sh/01bak27qyzue)
## Post #174
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-16T13:13:53+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from blacknight411 ↑Sun Aug 16, 2020 1:35 pm at Sun Aug 16, 2020 1:35 pm
>
> 
is this the model
No. Models are ".asf" files, as stated in the first post.
## Post #175
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-08-19T22:41:47+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Textures problem  color  wrong.


eye_mipmap0_combined.png (148.19 KiB) Viewed 229 times
## Post #176
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-08-19T23:12:58+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from blacknight411 ↑Thu Aug 20, 2020 6:41 am at Thu Aug 20, 2020 6:41 am
>
> 
Textures problem  color  wrong.eye_mipmap0_combined.png

that some kind of shader processing is applied in the game.
texture not be the same as the game as it is. need to process it yourself.
## Post #177
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2020-09-04T04:31:40+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

A another thing  cp0005 texture for skin  is wrong to


1.png (31.51 KiB) Viewed 170 times
## Post #178
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-09-04T04:50:49+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from einherjar007 ↑Thu Aug 20, 2020 7:12 am at Thu Aug 20, 2020 7:12 am
>
> 
blacknight411 wrote: ↑Thu Aug 20, 2020 6:41 am
Textures problem  color  wrong.eye_mipmap0_combined.png


that some kind of shader processing is applied in the game.
texture not be the same as the game as it is. need to process it yourself.

Out of context question:
How do you apply those textures on 3D Max?
## Post #179
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-15T07:16:06+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

SOAExporter.exe can't lord the Unpack .asf files,error lording model。
[搜狗截图20201015151145.png](https://xentaxbackup.github.io/file/18832_搜狗截图20201015151145.png)
## Post #180
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-10-15T08:49:16+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from kaimuangel ↑Thu Oct 15, 2020 3:16 pm at Thu Oct 15, 2020 3:16 pm
>
> 
SOAExporter.exe can't lord the Unpack .asf files
Upload a sample.
## Post #181
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-15T14:22:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

asf files:[https://drive.google.com/file/d/1JBM0TK ... sp=sharing](https://drive.google.com/file/d/1JBM0TKVKyVozfRm962DcWxsl3OFTFHNy/view?usp=sharing)
## Post #182
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-10-15T18:28:29+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from kaimuangel ↑Thu Oct 15, 2020 10:22 pm at Thu Oct 15, 2020 10:22 pm
>
> 
asf files

You should make the file public. It requires access to download.
## Post #183
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-15T23:57:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Fri Oct 16, 2020 2:28 am at Fri Oct 16, 2020 2:28 am
>
> 
kaimuangel wrote: ↑Thu Oct 15, 2020 10:22 pm
asf files


You should make the file public. It requires access to download.
sorry,
[https://drive.google.com/file/d/1XmVGQw ... sp=sharing](https://drive.google.com/file/d/1XmVGQwPmYahUVNEwsk1_wQPol5M0OH7K/view?usp=sharing)
## Post #184
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-10-16T08:01:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from kaimuangel ↑Fri Oct 16, 2020 7:57 am at Fri Oct 16, 2020 7:57 am
>
> 
https://drive.google.com/file/d/1XmVGQw ... sp=sharing

You seem to have unpacked the file wrongly somehow. Use the files from the latest JP version and use SOADec tool to unpack them.

Here is the correctly unpacked file: [http://www.mediafire.com/file/jnbs6qic6 ... k.asf/file](http://www.mediafire.com/file/jnbs6qic6ffe9xl/cc0001_b02a_unpack.asf/file) . It loads fine with SOAExporter.
## Post #185
- Username: miroki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 21, 2020 8:17 pm
- Post datetime: 2020-10-21T12:22:18+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Is anyone here able to upload the files for all weapons in SOA? I do not have an Android phone. I was able to download and play SOA on BlueStacks but was unable to extract the game files out from the emulator. If I'm correct while taking a look at the game folder in Bluestacks, the files for all weapons in the game are about 160mb in total.
Thank you in advance

Edited: I've figured out how to extract weapon files, but it looks like SOAExporter can not read them.
Edited 2: I forgot to unpack the weapons files before so SOAExporter didn't work. I unpacked the files so everything now works.
The way the textures work on the weapons are really odd (at least for the 2 guns I extracted). It looks like there are 2 meshes for each model I exported, the 2 meshes are identical but actually use a different texture so texture clipping is gonna be a big problem.
## Post #186
- Username: Planet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 08, 2020 9:49 pm
- Post datetime: 2020-11-13T12:08:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from A EON ↑Mon Aug 10, 2020 3:27 am at Mon Aug 10, 2020 3:27 am
>
> 
https://mega.nz/file/DpwQUSQZ#rp-Dx8IcO ... Yio6yedBw4
thank you very much.  Can you please  update it?  no need to upload the whole  folder again.  just add new files
cc0049_b02a
cp0022_b02a
cp0113_b03a
cp0202_b09a
cp0303_b08a
cp0308_b02a
cp0402_b07a
## Post #187
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-11-14T14:51:50+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Planet ↑Fri Nov 13, 2020 8:08 pm at Fri Nov 13, 2020 8:08 pm
>
> 
A EON wrote: ↑Mon Aug 10, 2020 3:27 am
https://mega.nz/file/DpwQUSQZ#rp-Dx8IcO ... Yio6yedBw4

thank you very much.  Can you please  update it?  no need to upload the whole  folder again.  just add new files
cc0049_b02a
cp0022_b02a
cp0113_b03a
cp0202_b09a
cp0303_b08a
cp0308_b02a
cp0402_b07a

Yes, I also intend to, because there are cool new characters, but I'm busy with other activities, so maybe I'll try tomorrow or the day after.

Via google translate
## Post #188
- Username: Planet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 08, 2020 9:49 pm
- Post datetime: 2020-11-16T00:23:58+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from A EON ↑Sat Nov 14, 2020 10:51 pm at Sat Nov 14, 2020 10:51 pm
>
> 


Yes, I also intend to, because there are cool new characters, but I'm busy with other activities, so maybe I'll try tomorrow or the day after.

Via google translate
Thank you.
## Post #189
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-11-17T14:25:05+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Planet ↑Fri Nov 13, 2020 8:08 pm at Fri Nov 13, 2020 8:08 pm
>
> 
A EON wrote: ↑Mon Aug 10, 2020 3:27 am
https://mega.nz/file/DpwQUSQZ#rp-Dx8IcO ... Yio6yedBw4

thank you very much.  Can you please  update it?  no need to upload the whole  folder again.  just add new files
cc0049_b02a
cp0022_b02a
cp0113_b03a
cp0202_b09a
cp0303_b08a
cp0308_b02a
cp0402_b07a

I already have the data, I will sort it first because I have updated it 2x since I uploaded & shared in this forum, or do I just upload that 1 folder like before?


via google translate
## Post #190
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-11-17T17:02:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

```
https://mega.nz/folder/vkh1EAII#gnklpqvJPEPAC4SjN4jMwQ
```

I uploaded it in a folder, if you want please find what you want in that folder

__ / Charcter (old) (.apk) = 868 items
__ / Charcter (new) (.apk) = 898 items
__ / hi (old) (.asf) = 531 items
__ / hi (new) (.asf) = 548 items
[soa1.png](https://xentaxbackup.github.io/file/19044_soa1.png)
## Post #191
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-11-17T18:01:11+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

HI guys, I see the tool works with various game related or not to Star Ocean.
 Could anyone write a list of the games supported?

Thanks in advance,
Drawing
## Post #192
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-11-17T18:32:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Drawing ↑Wed Nov 18, 2020 2:01 am at Wed Nov 18, 2020 2:01 am
>
> 
 Could anyone write a list of the games supported?
Current version should only support SOA. Tales of Crestoria and Bullet Girls use the same engine with slight changes. I have released separate tools for those though.
## Post #193
- Username: Planet
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 08, 2020 9:49 pm
- Post datetime: 2020-11-17T22:14:05+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from A EON ↑Wed Nov 18, 2020 1:02 am at Wed Nov 18, 2020 1:02 am
>
> 
Code: Select allhttps://mega.nz/folder/vkh1EAII#gnklpqvJPEPAC4SjN4jMwQ
I uploaded it in a folder, if you want please find what you want in that folder

__ / Charcter (old) (.apk) = 868 items
__ / Charcter (new) (.apk) = 898 items
__ / hi (old) (.asf) = 531 items
__ / hi (new) (.asf) = 548 items
thank you very much.  the files have been arranged in a very good way. Thank you
## Post #194
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-11-17T22:27:11+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Planet ↑Wed Nov 18, 2020 6:14 am at Wed Nov 18, 2020 6:14 am
>
> 
A EON wrote: ↑Wed Nov 18, 2020 1:02 am
Code: Select allhttps://mega.nz/folder/vkh1EAII#gnklpqvJPEPAC4SjN4jMwQ
I uploaded it in a folder, if you want please find what you want in that folder

__ / Charcter (old) (.apk) = 868 items
__ / Charcter (new) (.apk) = 898 items
__ / hi (old) (.asf) = 531 items
__ / hi (new) (.asf) = 548 items

thank you very much.  the files have been arranged in a very good way. Thank you

OK~
## Post #195
- Username: slideblue
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 31, 2016 9:05 am
- Post datetime: 2020-12-08T17:28:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Does anyone plz upload cp0202_b10a (or different name)?
Maybe the file would be the new unit 'singing star Rena'
## Post #196
- Username: nathannia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 13, 2021 12:55 am
- Post datetime: 2021-01-12T17:03:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

anything new in the characters datamine ?
I was trying to datamine via bluestacks but it won't show 
files\download no matter what I do =,=
## Post #197
- Username: chrnodroid
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 17, 2019 5:41 pm
- Post datetime: 2021-01-25T18:26:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from nathannia ↑Wed Jan 13, 2021 1:03 am at Wed Jan 13, 2021 1:03 am
>
> 
anything new in the characters datamine ?
I was trying to datamine via bluestacks but it won't show 
files\download no matter what I do =,=

You need BlueStacks Tweaker, then open the built-in file manager and extract what you want
## Post #198
- Username: nathannia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 13, 2021 12:55 am
- Post datetime: 2021-01-27T01:53:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

did it worked well, thanks mate now I will try to see if gg collab will have a new part or its just a sad rerun
## Post #199
- Username: Solace
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 29, 2021 8:59 am
- Post datetime: 2021-01-29T01:03:48+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Can someone PLEASE share the models for the persona characters, more specifically, the “Makoto Yuki” one that was with the collaboration event on Nov 2019. I tried opening every single .asf file listed and I got nothing. I also tried using the extract tool but it doesn’t run properly.
## Post #200
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-02-11T18:32:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

NEW UPDATE : SOAExporter V3

- Material Support (WIP)
- GLB  and NUX  export
- Export textures directly as PNG
- Removed the "offset" option for the skeleton. Most skeletons should be positioned correctly.
- Moveable camera

Updated link in the first post.

Previews
## Post #201
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2021-02-14T18:41:08+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Uh akderebur  there  some error like cp0005_b03a.Texture  work find  but  error exporting.
## Post #202
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-02-16T00:02:41+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from blacknight411 ↑Mon Feb 15, 2021 2:41 am at Mon Feb 15, 2021 2:41 am
>
> 
Texture  work find  but  error exporting.

I will take a lookand see what the problem is. Thanks for reporting.
## Post #203
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2021-04-22T16:00:40+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Game is shutting down in June, although there will be an offline version. Just thought I should mention.
## Post #204
- Username: Longya
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2020 8:16 pm
- Post datetime: 2021-04-22T17:18:59+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Andelx ↑Fri Apr 23, 2021 12:00 am at Fri Apr 23, 2021 12:00 am
>
> 
Game is shutting down in June, although there will be an offline version. Just thought I should mention.
Yeah, but just the story and the character viewer will be saved for now, I don't think if there will be playable levels, but we're not sure yet. They said the collab characters will not be viewable, but they said all of that might be subject to change.
## Post #205
- Username: Longya
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2020 8:16 pm
- Post datetime: 2021-04-22T17:30:20+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

A friend of mine had issues with the Persona 5 models (cc0037) and they told me these things:
"there’s no cc0025, It’s missing, it goes cc0024, cc0026 and it skips a couple numbers when it gets to cc0040,
Numbers cc0040, 41 are both missing,
Cc0050 is also kinda messed up
There’s no cp1, 4, 6, 7, or 8 and it jumps from 22 to 101,
cp003(Coro) doesn't load correctly into the model viewer, you can see the dots where the skeleton is supposed to be, but no 3D model"
## Post #206
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-22T18:24:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Longya ↑Fri Apr 23, 2021 1:30 am at Fri Apr 23, 2021 1:30 am
>
> 
had issues with the Persona 5 models (cc0037)

cp003(Coro) doesn't load correctly into the model viewer

Coro and persona models load fine for me. Some models have problems with export which is already reported by blacknight411. I have fixed it but not released yet. I will release it sometime soon.

> Reply from Longya ↑Fri Apr 23, 2021 1:30 am at Fri Apr 23, 2021 1:30 am
>
> 
it jumps from 22 to 101,
Your friend should understand the naming convention then  It is not 101, it is 01 / 01. Start ocean 1 / character 1. Cp02 would be for star ocean 2 characters. Cp00 is anamnesis characters in this case. So there will be skips like that. Anything else is related to how developers named the files.
## Post #207
- Username: Longya
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2020 8:16 pm
- Post datetime: 2021-04-23T12:46:11+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Fri Apr 23, 2021 2:24 am at Fri Apr 23, 2021 2:24 am
>
> 
Longya wrote: ↑Fri Apr 23, 2021 1:30 am
had issues with the Persona 5 models (cc0037)

cp003(Coro) doesn't load correctly into the model viewer


Coro and persona models load fine for me. Some models have problems with export which is already reported by blacknight411. I have fixed it but not released yet. I will release it sometime soon.
Longya wrote: ↑Fri Apr 23, 2021 1:30 am
it jumps from 22 to 101,

Your friend should understand the naming convention then  It is not 101, it is 01 / 01. Start ocean 1 / character 1. Cp02 would be for star ocean 2 characters. Cp00 is anamnesis characters in this case. So there will be skips like that. Anything else is related to how developers named the files.

Yeah we both figured that out sometime later, I probably copied the messages wrong 

Will you be extracting the units and saving them somewhere like a Google Drive or something so we can take them to have on our own computers?
## Post #208
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-23T14:44:57+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Longya ↑Fri Apr 23, 2021 8:46 pm at Fri Apr 23, 2021 8:46 pm
>
> 
Will you be extracting the units and saving them somewhere like a Google Drive or something so we can take them to have on our own computers?
Nope. I will just update my downloader tool with the last update, incase anyone wants to grab the latest assets. It probably won't work after the game shuts down though.

You can then use the tools on this thread to extract any model you want. I won't be hosting/sharing any models myself.
## Post #209
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2021-05-04T18:47:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hope the next tool update is soon, but no rush of course. I presume the next update will fix the issue with some models not working? Just curious.

Also I am making sure to keep all the character files saved and might share them later for those interested. But not until the game shuts down properly, as right now its quite simple to get the files.
## Post #210
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-05-05T10:15:02+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Andelx ↑Wed May 05, 2021 2:47 am at Wed May 05, 2021 2:47 am
>
> 
Hope the next tool update is soon, but no rush of course. I presume the next update will fix the issue with some models not working? Just curious.
I will probably release it in a couple of weeks. It will fix the exporting issue for some models if that is what you mean by "not working". If you refer to models that don't load it probably won't fix that.

If someone can PM me a list of non-working stuff I would be happy to take a look in my free time. Just don't  report the export and material issues. Any other problem is fine including weapons and monsters. I haven't checked them really, but I might as well support them properly since the game is finalized. Also, when you are reporting an issue tell me the file name too
## Post #211
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2021-06-10T20:41:10+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

cn0006_b01a,cn0002_b01a,cn0003_b01a,cn0004_b01a,cn0005_b01a,cn0007_b01a,cn0008_b01a,cn0009_b01a,cn0012_b01a,cn0013_and cn0015_b01a
none of them open the SOADec.
## Post #212
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-11T14:39:52+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hi guys,

I've a question for everyone that ripped from this game. Is there a datamining table or something that matches Character/monster names with models name? It will make a lot easier to find the specific characters I need. 

Thanks in advance.
## Post #213
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2021-06-11T16:29:10+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

The file names are referred to the game they appear in.

Like cp0201_b01a_unpack is Star Ocean 2.
cp0301_b01a_unpack is Star Ocean 3 and so on.

So that should help a bit.
## Post #214
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-06-11T17:06:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Andelx ↑Sat Jun 12, 2021 12:29 am at Sat Jun 12, 2021 12:29 am
>
> 
The file names are referred to the game they appear in.

Like cp0201_b01a_unpack is Star Ocean 2.
cp0301_b01a_unpack is Star Ocean 3 and so on.

So that should help a bit.

Thanks for answering but I'm not interested in knowing in which Star Ocean they appeared/came from. But matching real name with models name.  For examples : Luther (boss) -> model **** , Michales ( boss) model **** . Is there a table ? This will make easier to find the characters I need.
## Post #215
- Username: Erk In Danger
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 14, 2021 9:47 am
- Post datetime: 2021-06-14T05:16:47+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Big thanks to everybody involved with these tools! I had been hoping to tinker with some of the collab models/animations (eg. the Phantasia chars) before shutdown, but I just cannot get SOA to work with either Nox or MEMu, regardless of settings or tweaks. Everything seems up-to-date, so I don't know what's wrong. Consistent crashes upon startup.
## Post #216
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-06-16T04:53:25+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I don't need to brag but, we need to check on this forum [viewtopic.php?f=16&t=22122&start=45](https://forum.xentax.com/viewtopic.php?f=16&t=22122&start=45) about these unsuccessfully decompressed files [https://mega.nz/file/E0kzkaaD#WE_QpL8RV ... BoxEE1knMk](https://mega.nz/file/E0kzkaaD#WE_QpL8RVA5ff6YHdDca-1nikh5Jszj3yBoxEE1knMk) cause the TOCDec didn't decompress all of them.

Also can somebody update the tools for Tales Of Crestoria cause the dev is planning to upgrade the compression of the SLZ header.
## Post #217
- Username: GDL
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-06-18T03:03:31+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Script to download the star ocean files before it shuts down at the end of the month.
Un comment the file you want to download at the start o the script.


 StarOcean.7z
(1.19 KiB) Downloaded 108 times
## Post #218
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2021-06-21T01:43:29+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from chrrox ↑Fri Jun 18, 2021 11:03 am at Fri Jun 18, 2021 11:03 am
>
> 
Script to download the star ocean files before it shuts down at the end of the month.
Un comment the file you want to download at the start o the script.
StarOcean.7z

I tried it, and it worked! But unfortunately, SOADec Does not work on them.
## Post #219
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-06-21T03:46:55+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from MarioSonicU ↑Mon Jun 21, 2021 9:43 am at Mon Jun 21, 2021 9:43 am
>
> 
chrrox wrote: ↑Fri Jun 18, 2021 11:03 am
Script to download the star ocean files before it shuts down at the end of the month.
Un comment the file you want to download at the start o the script.
StarOcean.7z


I tried it, and it worked! But unfortunately, SOADec Does not work on them.

Can you send out a sample file?
## Post #220
- Username: OokamiYashiro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 22, 2021 7:37 am
- Post datetime: 2021-06-21T23:46:02+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Is there a way to extract the battle voice of a character from the game? I want to extract Elphelt and Dizzy voices before the game shutdown.
## Post #221
- Username: BiteMeUniverse
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 19, 2018 8:59 am
- Post datetime: 2021-06-24T09:10:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Drawing ↑Sat Jun 12, 2021 1:06 am at Sat Jun 12, 2021 1:06 am
>
> 
Thanks for answering but I'm not interested in knowing in which Star Ocean they appeared/came from. But matching real name with models name.  For examples : Luther (boss) -> model **** , Michales ( boss) model **** . Is there a table ? This will make easier to find the characters I need.

No. I've not found a single pattern to that.

Additionally, the files for rushes with all the extra data and small versions of Fayt, Cliff, and Albel are just random as well. I've been digging through those but there's about 3k files and I've gotten slightly lucky a few times.

___________________________________

update: Idea was worthless lol
## Post #222
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2021-06-25T04:10:03+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Uh I looking  for Jeanne Mathwest in the  game files  does anyone  know  what  number  she in or can,t open files.
## Post #223
- Username: daniel87
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 10, 2020 1:20 am
- Post datetime: 2021-07-04T20:51:46+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

i need valkyrie hrist weapons please 
por cierto hablo español
## Post #224
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-06T23:05:47+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I grabbed the most recent model data from this post:

[viewtopic.php?f=16&t=24108&p=175793&hil ... is#p175793](https://forum.xentax.com/viewtopic.php?f=16&t=24108&p=175793&hilit=anamnesis#p175793)

...but none of them seem to load in SOAExporter. I select the models and nothing happens.
## Post #225
- Username: sDynamo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 07, 2021 6:52 am
- Post datetime: 2021-07-06T23:39:54+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Wed Jul 07, 2021 7:05 am at Wed Jul 07, 2021 7:05 am
>
> 
I grabbed the most recent model data from this post:

viewtopic.php?f=16&t=24108&p=175793&hil ... is#p175793

...but none of them seem to load in SOAExporter. I select the models and nothing happens.

Need to unpack the .asf files first. Read the first post about Decompress ASF.
## Post #226
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-06T23:42:59+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from sDynamo ↑Wed Jul 07, 2021 7:39 am at Wed Jul 07, 2021 7:39 am
>
> 
Mihna wrote: ↑Wed Jul 07, 2021 7:05 am
I grabbed the most recent model data from this post:

viewtopic.php?f=16&t=24108&p=175793&hil ... is#p175793

...but none of them seem to load in SOAExporter. I select the models and nothing happens.


Need to unpack the .asf files first. Read the first post about Decompress ASF.

Oh, sorry, I misunderstood--I thought the files I downloaded were already unpacked. My mistake. Thanks for the quick response!
## Post #227
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-09T12:23:56+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Some of the models are loading in the program, but give me an error when I try to export them as GLB or NUX (the textures export fine, but not the models). Specifically, the error is happening with cp0212_b02a, cp0202_b08a, cp0210_b01a, cp0202_b07a, cm427_b01a, and cp0205_b04a. Any idea what's wrong? Is it a problem with the program or the files?
## Post #228
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-09T12:38:42+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Fri Jul 09, 2021 8:23 pm at Fri Jul 09, 2021 8:23 pm
>
> 
Any idea what's wrong? Is it a problem with the program or the files?
I have updated the tool recently. If you don't have the "V3_U1" version, download the tool again using the link in the first post. It should fix the export errors mostly.
## Post #229
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-09T21:18:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from akderebur ↑Fri Jul 09, 2021 8:38 pm at Fri Jul 09, 2021 8:38 pm
>
> 
Mihna wrote: ↑Fri Jul 09, 2021 8:23 pm
Any idea what's wrong? Is it a problem with the program or the files?

I have updated the tool recently. If you don't have the "V3_U1" version, download the tool again using the link in the first post. It should fix the export errors mostly.

Thank you, the updated version works with them!
## Post #230
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-12T01:14:05+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Has anyone been able to install SOA on an emulator since the offline version was released? I've had no luck with it through the Google Play store or with apk files using either BlueStacks or Nox. I'd just like to extract the weapons and the handful of new characters they'd released in the last months before it shut down (mainly Gabriel, Filia, Ashlay, and Dorne).

The furthest I've been able to get is installing it in BlueStacks 5 through APKPure, but the game throws an unknown error after I enter my username and I can't get past the title screen.

[edit] Actually, never mind. You don't need to emulate the game to extract the files... just download the apk, rename the extension to zip, and unzip it. Voila, there are your files.
## Post #231
- Username: CuchiPol
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 29, 2020 11:29 pm
- Post datetime: 2021-07-16T17:44:24+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Mon Jul 12, 2021 9:14 am at Mon Jul 12, 2021 9:14 am
>
> 
Has anyone been able to install SOA on an emulator since the offline version was released? I've had no luck with it through the Google Play store or with apk files using either BlueStacks or Nox. I'd just like to extract the weapons and the handful of new characters they'd released in the last months before it shut down (mainly Gabriel, Filia, Ashlay, and Dorne).

The furthest I've been able to get is installing it in BlueStacks 5 through APKPure, but the game throws an unknown error after I enter my username and I can't get past the title screen.

[edit] Actually, never mind. You don't need to emulate the game to extract the files... just download the apk, rename the extension to zip, and unzip it. Voila, there are your files.

Are you able to find the files for weapons? If so, what's the file names or location?
## Post #232
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-16T21:06:02+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from CuchiPol ↑Sat Jul 17, 2021 1:44 am at Sat Jul 17, 2021 1:44 am
>
> 
Are you able to find the files for weapons? If so, what's the file names or location?

They're in the "Weapons" folder. Unfortunately, the offline apk only had 17 weapons; out of those, only 12 extracted, and only 4 of those actually loaded in the model viewer. I'm not sure if anyone has the weapon files from when the game was online—luckily for me, one of 4 in the offline apk was the exact model I needed, so I haven't done a lot of hunting in older apks.
## Post #233
- Username: DobleC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 17, 2021 4:21 pm
- Post datetime: 2021-07-17T09:41:48+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Did someone save a copy of the weapon folder before the offline version? I want to rip some weapons but I can't download the game assets anymore
## Post #234
- Username: DobleC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 17, 2021 4:21 pm
- Post datetime: 2021-07-23T06:25:41+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Characters: [https://mega.nz/folder/vkh1EAII#gnklpqvJPEPAC4SjN4jMwQ](https://mega.nz/folder/vkh1EAII#gnklpqvJPEPAC4SjN4jMwQ)
Weapons: [https://mega.nz/folder/d5lRjY6Q#zcrWYE0Mxa1qwvvqEatVDQ](https://mega.nz/folder/d5lRjY6Q#zcrWYE0Mxa1qwvvqEatVDQ)
## Post #235
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-23T07:18:01+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Excuse me.
Sorry, I can only speak a little English. But I was watching here all the time. Thank you for making a wonderful tool!
I unable to import the iqe & nexs file exported from SOAExporter U5 to Noesis.
I also use V3. But There is something that can only be exported with U5.
Noesis is version 4.452. Some people say they can import iqe & nexs file to Noesis. Is there something missing?
## Post #236
- Username: chunchasku
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 24, 2021 8:50 pm
- Post datetime: 2021-07-24T13:00:14+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Mon Jul 12, 2021 9:14 am at Mon Jul 12, 2021 9:14 am
>
> 
Has anyone been able to install SOA on an emulator since the offline version was released? I've had no luck with it through the Google Play store or with apk files using either BlueStacks or Nox. I'd just like to extract the weapons and the handful of new characters they'd released in the last months before it shut down (mainly Gabriel, Filia, Ashlay, and Dorne).

The furthest I've been able to get is installing it in BlueStacks 5 through APKPure, but the game throws an unknown error after I enter my username and I can't get past the title screen.

[edit] Actually, never mind. You don't need to emulate the game to extract the files... just download the apk, rename the extension to zip, and unzip it. Voila, there are your files.

Hey there, I was just wondering if u were able to pull Gabriel (im hoping from Star Ocean 2) from the apk?
I've been on a mission to get all the Star Ocean 2 characters out of this so i can make a fan series out of them, and thanks to this forum have been able to get everyone.....except for Gabriel.
Going back over stuff, the unpacker, even new downloads dont seem to be working for me for some reason. However, i can still view unpacked models with the exporter....
My big question to you is, if you were able to snag Gabriel, if you could perhaps toss his unpacked asf my way. So i could pop him into the exporter and make some good stuff with him. Or maybe even a zip with his GLB and textures. Either way would be a big help.
Thanks for your consideration fam, and again, big thanks to everyone in this forum helping to explain things.
## Post #237
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-24T15:06:14+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from chunchasku ↑Sat Jul 24, 2021 9:00 pm at Sat Jul 24, 2021 9:00 pm
>
> 
Hey there, I was just wondering if u were able to pull Gabriel (im hoping from Star Ocean 2) from the apk?
I've been on a mission to get all the Star Ocean 2 characters out of this so i can make a fan series out of them, and thanks to this forum have been able to get everyone.....except for Gabriel.
Going back over stuff, the unpacker, even new downloads dont seem to be working for me for some reason. However, i can still view unpacked models with the exporter....
My big question to you is, if you were able to snag Gabriel, if you could perhaps toss his unpacked asf my way. So i could pop him into the exporter and make some good stuff with him. Or maybe even a zip with his GLB and textures. Either way would be a big help.
Thanks for your consideration fam, and again, big thanks to everyone in this forum helping to explain things.

I don't have it offhand since I've already extracted the files from it, but Gabriel's model is cm506_b01a. He and the other Ten Wise Men are labeled as monsters instead of characters. Unfortunately, it doesn't look like Filia's model is among them, at least not as far as I've found.

If you still can't find it, let me know and I'll go back and re-extract the asf.
## Post #238
- Username: chunchasku
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 24, 2021 8:50 pm
- Post datetime: 2021-07-24T22:54:13+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Sat Jul 24, 2021 11:06 pm at Sat Jul 24, 2021 11:06 pm
>
> 
chunchasku wrote: ↑Sat Jul 24, 2021 9:00 pm
Hey there, I was just wondering if u were able to pull Gabriel (im hoping from Star Ocean 2) from the apk?
I've been on a mission to get all the Star Ocean 2 characters out of this so i can make a fan series out of them, and thanks to this forum have been able to get everyone.....except for Gabriel.
Going back over stuff, the unpacker, even new downloads dont seem to be working for me for some reason. However, i can still view unpacked models with the exporter....
My big question to you is, if you were able to snag Gabriel, if you could perhaps toss his unpacked asf my way. So i could pop him into the exporter and make some good stuff with him. Or maybe even a zip with his GLB and textures. Either way would be a big help.
Thanks for your consideration fam, and again, big thanks to everyone in this forum helping to explain things.


I don't have it offhand since I've already extracted the files from it, but Gabriel's model is cm506_b01a. He and the other Ten Wise Men are labeled as monsters instead of characters. Unfortunately, it doesn't look like Filia's model is among them, at least not as far as I've found.

If you still can't find it, let me know and I'll go back and re-extract the asf.

Lookin thru all the files i was able to download, i cant seem to find cm506_b01a. I have cm506_b01b and other files i think aroudn it, but somehow missed on that one.
Was able to find mathew and lucifer in the monster segment thanks to ur pointing out that they are in the monsters so thanks for that!
Would love to snag that gabriel from ya for sure, thanks so much for offering to extract it for me fam! If i could bother u to unpack it and put it thru the exporter to get the GLB and textures, would be a massive help.
Thanks again fam, and pls take ur time, no rush. Gonna take me a hot minute to get these other guys into Blender and unity so i can start making particle effects for them and stuff. I'm so excited to get my Fan project underway XD
Im off to replay my old Star ocean 2 save. Gotta refresh my memory on thier movesets and stuff.
## Post #239
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-24T23:01:38+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from chunchasku ↑Sun Jul 25, 2021 6:54 am at Sun Jul 25, 2021 6:54 am
>
> 
Lookin thru all the files i was able to download, i cant seem to find cm506_b01a. I have cm506_b01b and other files i think aroudn it, but somehow missed on that one.
Was able to find mathew and lucifer in the monster segment thanks to ur pointing out that they are in the monsters so thanks for that!
Would love to snag that gabriel from ya for sure, thanks so much for offering to extract it for me fam! If i could bother u to unpack it and put it thru the exporter to get the GLB and textures, would be a massive help.
Thanks again fam, and pls take ur time, no rush. Gonna take me a hot minute to get these other guys into Blender and unity so i can start making particle effects for them and stuff. I'm so excited to get my Fan project underway XD
Im off to replay my old Star ocean 2 save. Gotta refresh my memory on thier movesets and stuff.

I’ll shoot you a DM later, actually, because I’ve been working on bringing all the SO1 and SO2 models into Blender myself. No need to double the workload when we could just share resources instead!
## Post #240
- Username: 987654321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 23, 2021 6:43 pm
- Post datetime: 2021-07-25T10:12:43+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

すみません。
自分もフィリアのモデルを探しているのですがもしかしてバトルスキルのエフェクトとして扱われているのではないかと思ったのですがどうでしょうか?
ラッシュコンボの時だけ出てきた白いドレスのリリアや堕天使の服を着たファリンとタイネーブ等がどこにあるかというのも気になります。
## Post #241
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-07-25T16:43:44+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

im late for the latest model files could someone please upload them?
## Post #242
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-25T17:32:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from wansf ↑Mon Jul 26, 2021 12:43 am at Mon Jul 26, 2021 12:43 am
>
> 
im late for the latest model files could someone please upload them?

Someone just shared them all a few posts before yours.
## Post #243
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-25T17:48:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Sun Jul 25, 2021 6:12 pm at Sun Jul 25, 2021 6:12 pm
>
> 
すみません。
自分もフィリアのモデルを探しているのですがもしかしてバトルスキルのエフェクトとして扱われているのではないかと思ったのですがどうでしょうか?
ラッシュコンボの時だけ出てきた白いドレスのリリアや堕天使の服を着たファリンとタイネーブ等がどこにあるかというのも気になります。

残念だけどオフライン版にラッシュコンボが見られないのでそのモデルはV3.8.0のAPKにはいません。

Does anyone have the extracted Effects folder from before the offline version? Maybe the models for Filia and the other characters who only appeared in rush combos are there. Since the offline version doesn’t let you view the rush combos anymore, the Effects folder is pretty bare.
## Post #244
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-07-25T18:03:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Mon Jul 26, 2021 1:32 am at Mon Jul 26, 2021 1:32 am
>
> 
wansf wrote: ↑Mon Jul 26, 2021 12:43 am
im late for the latest model files could someone please upload them?


Someone just shared them all a few posts before yours.

that folder is kinda old as the folder title said
## Post #245
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-07-26T10:49:59+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

@akderebur
is it normal that 95% of the apk animation files only show "idle" "win" "win loop"?
## Post #246
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-26T13:25:54+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Sun Jul 25, 2021 6:12 pm at Sun Jul 25, 2021 6:12 pm
>
> 
すみません。
自分もフィリアのモデルを探しているのですがもしかしてバトルスキルのエフェクトとして扱われているのではないかと思ったのですがどうでしょうか?
ラッシュコンボの時だけ出てきた白いドレスのリリアや堕天使の服を着たファリンとタイネーブ等がどこにあるかというのも気になります。
You're right. Everyone is in Effect folder.
## Post #247
- Username: 987654321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 23, 2021 6:43 pm
- Post datetime: 2021-07-27T00:23:49+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from xentax*A ↑Mon Jul 26, 2021 9:25 pm at Mon Jul 26, 2021 9:25 pm
>
> 
987654321 wrote: ↑Sun Jul 25, 2021 6:12 pm
すみません。
自分もフィリアのモデルを探しているのですがもしかしてバトルスキルのエフェクトとして扱われているのではないかと思ったのですがどうでしょうか?
ラッシュコンボの時だけ出てきた白いドレスのリリアや堕天使の服を着たファリンとタイネーブ等がどこにあるかというのも気になります。

You're right. Everyone is in Effect folder.
調べていただきありがとうございます。
やっぱりそこにあったのですね…
すみませんがエフェクトのフォルダごと貼ってもらえないでしょうか？
どうかよろしくお願いします。
## Post #248
- Username: 987654321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 23, 2021 6:43 pm
- Post datetime: 2021-07-27T00:53:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Tue Jul 27, 2021 8:23 am at Tue Jul 27, 2021 8:23 am
>
> 
xentax*A wrote: ↑Mon Jul 26, 2021 9:25 pm
987654321 wrote: ↑Sun Jul 25, 2021 6:12 pm
すみません。
自分もフィリアのモデルを探しているのですがもしかしてバトルスキルのエフェクトとして扱われているのではないかと思ったのですがどうでしょうか?
ラッシュコンボの時だけ出てきた白いドレスのリリアや堕天使の服を着たファリンとタイネーブ等がどこにあるかというのも気になります。

You're right. Everyone is in Effect folder.

調べていただきありがとうございます。
やっぱりそこにあったのですね…
すみませんがエフェクトのフォルダごと貼ってもらえないでしょうか？
どうかよろしくお願いします。

自分の日本語→英語→日本語に翻訳された文章が意味不明になっていますが問題無いでしょうか?
もしも訳の分からない文章になっていたら指摘して下さい
## Post #249
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-28T05:34:12+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Tue Jul 27, 2021 8:53 am at Tue Jul 27, 2021 8:53 am
>
> 
987654321 wrote: ↑Tue Jul 27, 2021 8:23 am
xentax*A wrote: ↑Mon Jul 26, 2021 9:25 pm

You're right. Everyone is in Effect folder.

調べていただきありがとうございます。
やっぱりそこにあったのですね…
すみませんがエフェクトのフォルダごと貼ってもらえないでしょうか？
どうかよろしくお願いします。


自分の日本語→英語→日本語に翻訳された文章が意味不明になっていますが問題無いでしょうか?
もしも訳の分からない文章になっていたら指摘して下さい

No problem. I was able to understand. I upload only once because I also got help from various people, Me too. The deadline is one week.
I only do this once because the extracting itself is essentially forbidden.

[https://53.gigafile.nu/0804-md591ac72ce ... 7b94977464](https://53.gigafile.nu/0804-md591ac72ced13a228f82b47b94977464)
password：soat
## Post #250
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-28T06:12:19+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Effect folder can also be downloaded by other people. 
Let's be careful and have fun because the extracting itself is essentially forbidden.

By the way, Is there anyone who have SOAExporter version V2 and can upload it?
## Post #251
- Username: 987654321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 23, 2021 6:43 pm
- Post datetime: 2021-07-28T11:09:04+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from xentax*A ↑Wed Jul 28, 2021 1:34 pm at Wed Jul 28, 2021 1:34 pm
>
> 
987654321 wrote: ↑Tue Jul 27, 2021 8:53 am
987654321 wrote: ↑Tue Jul 27, 2021 8:23 am

調べていただきありがとうございます。
やっぱりそこにあったのですね…
すみませんがエフェクトのフォルダごと貼ってもらえないでしょうか？
どうかよろしくお願いします。


自分の日本語→英語→日本語に翻訳された文章が意味不明になっていますが問題無いでしょうか?
もしも訳の分からない文章になっていたら指摘して下さい


No problem. I was able to understand. I upload only once because I also got help from various people, Me too. The deadline is one week.
I only do this once because the extracting itself is essentially forbidden.

https://53.gigafile.nu/0804-md591ac72ce ... 7b94977464
password：soat

thank you
I'm sorry for causing you to act unwillingly because of me
I'm really thankful to you
## Post #252
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-28T12:04:26+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Wed Jul 28, 2021 7:09 pm at Wed Jul 28, 2021 7:09 pm
>
> 
xentax*A wrote: ↑Wed Jul 28, 2021 1:34 pm
987654321 wrote: ↑Tue Jul 27, 2021 8:53 am


自分の日本語→英語→日本語に翻訳された文章が意味不明になっていますが問題無いでしょうか?
もしも訳の分からない文章になっていたら指摘して下さい


No problem. I was able to understand. I upload only once because I also got help from various people, Me too. The deadline is one week.
I only do this once because the extracting itself is essentially forbidden.

https://53.gigafile.nu/0804-md591ac72ce ... 7b94977464
password：soat


thank you
I'm sorry for causing you to act unwillingly because of me
I'm really thankful to you

No problem! I also got help from various people. Me too.
Effect folder has over 3000 files. Good luck ! Everyone definitely is in there.
I use SOAExporter version U5 to browse Effect folder.

For your information, Fhilia is ew079_a01a and es506_b51a.
## Post #253
- Username: 987654321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 23, 2021 6:43 pm
- Post datetime: 2021-07-28T12:08:31+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from xentax*A ↑Wed Jul 28, 2021 2:12 pm at Wed Jul 28, 2021 2:12 pm
>
> 
Effect folder can also be downloaded by other people. 
Let's be careful and have fun because the extracting itself is essentially forbidden.

By the way, Is there anyone who have SOAExporter version V2 and can upload it?

I had it so I uploaded it The password is soat

[https://firestorage.jp/download/d977e08 ... 9368f7ff59](https://firestorage.jp/download/d977e08bf70c63d54b1925b7a3ce979368f7ff59)
## Post #254
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-28T12:10:08+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from xentax*A ↑Wed Jul 28, 2021 1:34 pm at Wed Jul 28, 2021 1:34 pm
>
> 
No problem. I was able to understand. I upload only once because I also got help from various people, Me too. The deadline is one week.
I only do this once because the extracting itself is essentially forbidden.

https://53.gigafile.nu/0804-md591ac72ce ... 7b94977464
password：soat

Thank you SO much for sharing these!!
## Post #255
- Username: 987654321
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 23, 2021 6:43 pm
- Post datetime: 2021-07-28T14:13:33+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from xentax*A ↑Wed Jul 28, 2021 8:04 pm at Wed Jul 28, 2021 8:04 pm
>
> 
987654321 wrote: ↑Wed Jul 28, 2021 7:09 pm
xentax*A wrote: ↑Wed Jul 28, 2021 1:34 pm


No problem. I was able to understand. I upload only once because I also got help from various people, Me too. The deadline is one week.
I only do this once because the extracting itself is essentially forbidden.

https://53.gigafile.nu/0804-md591ac72ce ... 7b94977464
password：soat


thank you
I'm sorry for causing you to act unwillingly because of me
I'm really thankful to you


No problem! I also got help from various people. Me too.
Effect folder has over 3000 files. Good luck ! Everyone definitely is in there.
I use SOAExporter version U5 to browse Effect folder.

For your information, Fhilia is ew079_a01a and es506_b51a.

Thank you for telling me which file it is.
I am very grateful for your kindness
## Post #256
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-29T13:02:24+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Wed Jul 28, 2021 8:08 pm at Wed Jul 28, 2021 8:08 pm
>
> 
xentax*A wrote: ↑Wed Jul 28, 2021 2:12 pm
Effect folder can also be downloaded by other people. 
Let's be careful and have fun because the extracting itself is essentially forbidden.

By the way, Is there anyone who have SOAExporter version V2 and can upload it?


I had it so I uploaded it The password is soat

https://firestorage.jp/download/d977e08 ... 9368f7ff59
Thank you ! Thank you very much !
I was looking for this version ! I appreciate it !
## Post #257
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-29T13:03:16+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Wed Jul 28, 2021 8:10 pm at Wed Jul 28, 2021 8:10 pm
>
> 
xentax*A wrote: ↑Wed Jul 28, 2021 1:34 pm
No problem. I was able to understand. I upload only once because I also got help from various people, Me too. The deadline is one week.
I only do this once because the extracting itself is essentially forbidden.

https://53.gigafile.nu/0804-md591ac72ce ... 7b94977464
password：soat


Thank you SO much for sharing these!!
Thank you for your politeness.
Please keep it a secret and cherish these data.
## Post #258
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-07-29T13:05:18+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from 987654321 ↑Wed Jul 28, 2021 10:13 pm at Wed Jul 28, 2021 10:13 pm
>
> 
xentax*A wrote: ↑Wed Jul 28, 2021 8:04 pm
987654321 wrote: ↑Wed Jul 28, 2021 7:09 pm


thank you
I'm sorry for causing you to act unwillingly because of me
I'm really thankful to you


No problem! I also got help from various people. Me too.
Effect folder has over 3000 files. Good luck ! Everyone definitely is in there.
I use SOAExporter version U5 to browse Effect folder.

For your information, Fhilia is ew079_a01a and es506_b51a.


Thank you for telling me which file it is.
I am very grateful for your kindness
You can surely find everyone !
## Post #259
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-30T19:40:39+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Here are the character models I've found in Effects so far. I’ll be updating this post with new info as I come across it. 

Ethereal Queen: ef010_a10a
Gabriel Celeste: ef303_a10a (same as cm301_b01a)
Shujin Evelysse and Tika: ew007_a38b (face textures can be pulled from base models, outfit textures can be pulled from Shujin Rena)
Maid Faize, Myuria, and Sarah: ew009_a24b (face textures can be pulled from base models, outfit textures can be pulled from Maid Reimi)
Onsen Celine, Chisato, Opera, Claude, and Dias: ew018_a32a (face textures can be pulled from base models, skin textures are very small, towel texture does not exist. Flip UVs vertically and export from Noesis as .dae if you’re going to import it into Blender. Exporting as the default .fbx will give you a glitched file)
T'nique Werewolf: ew011_a26c (textures need to be applied on the LightUV map, not the DiffuseUV map)
Arsene: ew072_a01p
Cendrillon: ew073_a01p

The model for the bunny is included in em081_b01a. The texture is not, but you can extract it from Noel's model (cp0211_b01a) and apply it.

Unfortunately, the extracted textures for Ethereal Queen and Arsene are so small they're basically useless. I'm still trying to see if I can find bigger versions somewhere else in the files.

[updated 8/1]
## Post #260
- Username: sDynamo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 07, 2021 6:52 am
- Post datetime: 2021-07-30T22:26:30+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

[https://docs.google.com/spreadsheets/d/ ... =564736327](https://docs.google.com/spreadsheets/d/1FAts9jY__LEMIAuBKu7MuIrYX9ttZghGsLUUTmpHPcw/edit#gid=564736327)

I believe this sheet could help you guys too, it's very useful to find stuff quickly. Thanks to BAC_BAC#8171 from SOA dead Discord.
## Post #261
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-07-31T02:14:55+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from sDynamo ↑Sat Jul 31, 2021 6:26 am at Sat Jul 31, 2021 6:26 am
>
> 
https://docs.google.com/spreadsheets/d/ ... =564736327

I believe this sheet could help you guys too, it's very useful to find stuff quickly. Thanks to BAC_BAC#8171 from SOA dead Discord.

Thank you! It doesn't cover the models in Effects, but that's very useful for navigating the character files.

There are a few models noted in the spreadsheet that weren't in the final APK or either of the folders people shared previously—does anyone have any of these and would be willing to share?

cc0040_b01a Mona (Morgana)
cc0041 Fox (Yusuke)
cp0025 Asmodeous
cp0416_b01a Puffy (SO4)
## Post #262
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-08-15T11:37:55+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Sat Jul 31, 2021 10:14 am at Sat Jul 31, 2021 10:14 am
>
> 
sDynamo wrote: ↑Sat Jul 31, 2021 6:26 am
https://docs.google.com/spreadsheets/d/ ... =564736327

I believe this sheet could help you guys too, it's very useful to find stuff quickly. Thanks to BAC_BAC#8171 from SOA dead Discord.


Thank you! It doesn't cover the models in Effects, but that's very useful for navigating the character files.

There are a few models noted in the spreadsheet that weren't in the final APK or either of the folders people shared previously—does anyone have any of these and would be willing to share?

cc0040_b01a Mona (Morgana)
cc0041 Fox (Yusuke)
cp0025 Asmodeous
cp0416_b01a Puffy (SO4)

cm507_b01a  is also Asmodeous.
Isn't Mona in Deco folder?
## Post #263
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-08-15T15:09:00+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from xentax*A ↑Sun Aug 15, 2021 7:37 pm at Sun Aug 15, 2021 7:37 pm
>
> 
cm507_b01a  is also Asmodeous.
Isn't Mona in Deco folder?

cm507_b01a wasn't in the Character folders that have been shared or in the offline APK, so I don't have that file. Would you be willing to share it?

Same with the Deco folder—it's not in the final APK and it hasn't been shared by anyone here either. I didn't have any interest in ripping the files til after the game went offline, so I never had the opportunity to extract the files when it was online.
## Post #264
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-08-15T22:09:35+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I'm having an issue with the KTX files extracted with SOAImgEx. There is no blue channel, and when I export it as PNG and load it into Photoshop, the blue channel is completely black. Is there a fix for this? I've been using this + SOAExporter_U5 to extract the weapons that don't load in SOAExporter_V3_U1, so I can't just export them straight to PNGs like usual.



I know it's a RG11 file and not an RGB, but U5 still manages to extract it with a blue channel, so I'm not sure how to make that happen with the KTX file.

[EDIT] The PVRTextTools team figured out a script to properly extract the normals from the KTX files, so that's solved.
## Post #265
- Username: xentax*A
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 23, 2021 2:48 pm
- Post datetime: 2021-08-20T16:27:37+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Sun Aug 15, 2021 11:09 pm at Sun Aug 15, 2021 11:09 pm
>
> 
xentax*A wrote: ↑Sun Aug 15, 2021 7:37 pm
cm507_b01a  is also Asmodeous.
Isn't Mona in Deco folder?


cm507_b01a wasn't in the Character folders that have been shared or in the offline APK, so I don't have that file. Would you be willing to share it?

Same with the Deco folder—it's not in the final APK and it hasn't been shared by anyone here either. I didn't have any interest in ripping the files til after the game went offline, so I never had the opportunity to extract the files when it was online.

That makes sense...I'm Sorry, I'm very Sorry.
I decided to upload only once, it is effect folder.
Because creators hate that act.
I said something unnecessary.
I'm very Sorry, I'd appreciate it if you could give me your understanding about that.

Would you please wait for somebody else comes forward?
## Post #266
- Username: kotatsu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 18, 2021 9:17 pm
- Post datetime: 2021-08-23T20:40:43+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hi, excuse me if I ask, but could someone be so kind to post a link to download the model files? 
I know that this is an unpopular request, but I love this game so I ask help to someone, because I'd like to have access to these wonderful models of this awesome game. Thanks!!
## Post #267
- Username: sDynamo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 07, 2021 6:52 am
- Post datetime: 2021-08-23T22:32:55+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from kotatsu ↑Tue Aug 24, 2021 4:40 am at Tue Aug 24, 2021 4:40 am
>
> 
Hi, excuse me if I ask, but could someone be so kind to post a link to download the model files? 
I know that this is an unpopular request, but I love this game so I ask help to someone, because I'd like to have access to these wonderful models of this awesome game. Thanks!!
[viewtopic.php?p=165690#p165690](https://forum.xentax.com/viewtopic.php?p=165690#p165690)
## Post #268
- Username: kotatsu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 18, 2021 9:17 pm
- Post datetime: 2021-08-24T08:03:52+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from sDynamo ↑Tue Aug 24, 2021 6:32 am at Tue Aug 24, 2021 6:32 am
>
> 
kotatsu wrote: ↑Tue Aug 24, 2021 4:40 am
Hi, excuse me if I ask, but could someone be so kind to post a link to download the model files? 
I know that this is an unpopular request, but I love this game so I ask help to someone, because I'd like to have access to these wonderful models of this awesome game. Thanks!!

viewtopic.php?p=165690#p165690

Thanks!! I didn't see it before!
## Post #269
- Username: BACBAC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 23, 2020 7:27 pm
- Post datetime: 2021-08-25T10:42:22+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from Mihna ↑Sat Jul 31, 2021 10:14 am at Sat Jul 31, 2021 10:14 am
>
> 
sDynamo wrote: ↑Sat Jul 31, 2021 6:26 am
https://docs.google.com/spreadsheets/d/ ... =564736327

I believe this sheet could help you guys too, it's very useful to find stuff quickly. Thanks to BAC_BAC#8171 from SOA dead Discord.


Thank you! It doesn't cover the models in Effects, but that's very useful for navigating the character files.

There are a few models noted in the spreadsheet that weren't in the final APK or either of the folders people shared previously—does anyone have any of these and would be willing to share?

cc0040_b01a Mona (Morgana)
cc0041 Fox (Yusuke)
cp0025 Asmodeous
cp0416_b01a Puffy (SO4)

SOA models for Fox and Puffy do not exist. That spreadsheet contains entries for npcs and unreleased/placeholder characters, so there may not be a model for each entry.
## Post #270
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-08-25T12:26:43+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from BACBAC ↑Wed Aug 25, 2021 6:42 pm at Wed Aug 25, 2021 6:42 pm
>
> 
SOA models for Fox and Puffy do not exist. That spreadsheet contains entries for npcs and unreleased/placeholder characters, so there may not be a model for each entry.

Ahhh, that makes sense. I was wondering why it listed Puffy when I never saw her appear in the game.

I've also been labeling the weapon files as I extract them—would it help for me to upload that list anywhere?
## Post #271
- Username: Mihna
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jul 05, 2021 3:09 pm
- Post datetime: 2021-09-21T13:36:18+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Has anyone been able to figure out which texture affects metalness? I've managed to figure out which textures affect ambient occlusion and roughness, but for the life of me I can't figure out how they apply metal.
## Post #272
- Username: aska1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 06, 2021 4:32 pm
- Post datetime: 2021-12-06T08:37:49+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hello

Is anyone know how to decode this kind of text from the game?

```
dGKah0pL27x3khk7T+aEP8KYqS5dmcr5====
```


It was inside an XML file,  Game.xml ,  my guess is that this file could contains all the informations about the characters unlocked.

Example of the code

```
<map>
    <string name="dGKah0pL27x3khk7T+aEP8KYqS5dmcr5====">ztBP2w==&#10;    </string>
</map>
```
## Post #273
- Username: flyforfunk42
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 11, 2022 9:55 pm
- Post datetime: 2022-01-11T14:46:12+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

I have a problem with cp0015_b01a.asf

Is there a solution?
## Post #274
- Username: KTArima
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 18, 2022 2:34 am
- Post datetime: 2022-08-17T18:41:13+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

> Reply from DobleC ↑Fri Jul 23, 2021 2:25 pm at Fri Jul 23, 2021 2:25 pm
>
> 
Characters: https://mega.nz/folder/vkh1EAII#gnklpqvJPEPAC4SjN4jMwQ
Weapons: https://mega.nz/folder/d5lRjY6Q#zcrWYE0Mxa1qwvvqEatVDQ

So I'm rather new to this, but when I click on the Characters link. The etc2 file is empty and I only see the .apk file. Am I supposed to install that .apk file on my emulator? I am not able to
## Post #275
- Username: KTArima
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 18, 2022 2:34 am
- Post datetime: 2022-08-17T18:49:15+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

Hello all! Bumping this post. I'm new to extracting data from the game. Not sure if I'm looking in the wrong directory, but I followed the directions and I do not see anything in this directory:
/data/data/com.square_enix.android.android_googleplay.StarOceanj\files\download.
## Post #276
- Username: hunshimowangzhy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 04, 2019 4:53 am
- Post datetime: 2022-12-01T05:25:07+00:00
- Post Title: Re: Star Ocean Anamnesis Tools

It seems that all the link for game data has expired. Could someone share again？
