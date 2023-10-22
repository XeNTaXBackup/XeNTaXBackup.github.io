## Post #1
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-07-29T06:30:56+00:00
- Post Title: Some info on MOTORM4X Files

I've collected some info that may be useful to people decrypting/extracting the files inside of [MOTORM4X](http://www.theeasyco.com/projects.html) Game..

First off for people un-aware the DTF Archives this game uses can be easily extracted using something like 7zip.
After you have extracted those you are then presented with some folders which i will explain below... Please feel free to correct me on any of this 

----------------------------------------------------------------------------------
shadersI
shadersII
= Both of these folders contain Source codes for HLSL
----------------------------------------------------------------------------------
sound
= These are obviously sound files in WAV & OGG format.
----------------------------------------------------------------------------------
st
st_low
st_norm
= These are the Speed Tree files
----------------------------------------------------------------------------------
table
= These appear to be XML Config Tables used by the game for things such as Weight of props
----------------------------------------------------------------------------------
texture_low
texture_norm
texture_uni
= These are the game Textures in DDS format.
----------------------------------------------------------------------------------

Before you can edit/use/view these files you will need to Decrypt them using Mr. Auriemma's EXE Decrypter found [here](http://aluigi.altervista.org/papers/motorm4xdec.zip)

I've written quite a long batch script to do this for you, after extracting all of the files make a folder called "Decoded" in the same location and you will be able to use this script 

[http://xer2k8.googlepages.com/decode.txt](http://xer2k8.googlepages.com/decode.txt) (Save this AS .BAT where you extracted the game files & Mr. Auriemma's EXE Decrypter)

All you will need to change is;

```
SET OUT=%M4X%\Decoded
SET EXE=%M4X%\motorm4xdec.exe
```

To reflect your directories

Oh and also you will need to create a "mirror" of the extracted folders in the "Decoded" directory, to do that add this to the top of my decode script;

```
MKDIR Decoded\shadersII
MKDIR Decoded\sound
MKDIR Decoded\st
MKDIR Decoded\st_low
MKDIR Decoded\st_norm
MKDIR Decoded\table
MKDIR Decoded\texture_low
MKDIR Decoded\texture_norm
MKDIR Decoded\texture_uni
```


If all goes well, you should then have a perfect "mirror" of the original encrypted files in the "Decoded" directory.

This is where it gets a little tricky ...

As i mentioned above, each folder basically contains the one type of file, but in order to rename them all at once you need something like [Flash Renamer](http://www.rlvision.com/downloads.asp)
As of the nature of this forum, i strongly suggest to any of you to buy this program, because it s very very useful for mass-renaming anything from MP3s to what i'm about to mention....

As i'm not fully familiar with shader programming, i renamed all of the shader files in both folders to have the extension .HLSL..
The sound folder has two types of files in it, .OGG and .WAV.. Thankfully i've been able to discover which is which, and will also tell you guys that 

Here is the list of OGG files that basically make up the Soundtrack;

```
201287115
410407682
416881873
427603413
645018496
670050554
671980235
838822963
973192840
1595218299
2070719845
2157850769
2314588459
2502528236
2526356612
2640532474
2757221826
2918024175
2948976456
2996578166
3323928166
3404111530
3444543696
3454396275
3799559185
3910468355
3969270802
4204753495
4282431164
```


I made 2 folders in the Decoded "sound" folder called "OGG" and "WAV", and moved the above files to the OGG folder and it was much easier to then move the WAV files.

st
st_low
st_norm
From what i can see are all the Speed Tree files in the game, i do not know what the file extension would be for these but they appear to be exported from something like 3DS Max..
Here is an example of one of the files; (Decoded\st\2726382486)

```
WindResponseAndLimit 1.0 0
MaxBendAngle 45
BranchExponent 2
LeafExponent 1
GustStrengthFreqDuration 0.25 0.5 1.0

BranchOscillationX_LaLsHaHs -15 15 0.4 4
BranchOscillationY_LaLsHaHs -10 10 0.4 4

LeafRocking_LaLsHaHs -10 10 2 4
LeafRustling_LaLsHaHs -40 40 2 4

```


The Table folder appears to contain all of the games XML config files, another example being; (Decoded\table\4053822770)

```
    <frame name="tent01_wall05" props="WEIGHT: 200;ENTBAEKED:tent01_wall02" />
    <frame name="tent01_wall01" props="WEIGHT: 50;SPDMIN:30;SPDMAX:100;RESIST:80" />
    <frame name="tent01_wall02" props="WEIGHT: 50" />
    <frame name="tent01_wall03" props="WEIGHT: 50;SPDMIN:30;SPDMAX:100;RESIST:80" />
    <frame name="tent01_wall04" props="WEIGHT: 50;SPDMIN:30;SPDMAX:100;RESIST:80" />
    <frame name="tent01_top" props="WEIGHT: 100;SPDMIN:30;SPDMAX:100;RESIST:80" />
    <frame name="tent01Coll01" props="COLL BOX" />
    <frame name="tent01Coll02" props="COLL BOX" />
    <frame name="tent01Coll03" props="COLL BOX" />
    <frame name="tent01Coll04" props="COLL BOX" />
    <frame name="tent01Coll05" props="COLL BOX" />
    <frame name="tent01Coll06" props="COLL BOX" />
    <frame name="tent01Coll07" props="COLL BOX" />
    <frame name="tent01Coll08" props="COLL BOX" />
</root>

```


However, looking at another file from this same folder, it appears to be similar to C++ code for displaying shaders, for exmaple; (Decoded\table\2532410410)

```
	float4 position			: POSITION,	
	out float4 outPos		: POSITION,	
	out float3 resultToPS : TEXCOORD0,	
		
	uniform float4x4 world,	
	uniform float4x4 worldViewProj,
	uniform float4 texelOffsets,
	uniform float3 CameraPositionWorld
	)
{
	float4 Wpos;
	Wpos.xyz = mul(world, position).xyz-CameraPositionWorld.xyz;
	//Wpos.y+=0.05;
	outPos = mul(worldViewProj, position);

	// fix pixel / texel alignment
	outPos.xy += texelOffsets.zw * outPos.w;
	
	float PRESNETER = 1024;
	
	float height = clamp(Wpos.y, -24, 8);
	double finalDepth = 1-(height+24.0)/32.0;
	
	double X;
	double Y;
	
	double rest = modf(finalDepth*PRESNETER, X);	
	rest = modf(rest*PRESNETER, Y);	
	double Z = rest*PRESNETER;
	
	resultToPS = float3(X/PRESNETER, Y/PRESNETER, Z/PRESNETER);		
}



void AngelOfShadowCasterPS(	
	float3 position		: TEXCOORD0,		
	out float4 result		: COLOR)
	
{	
	result = float4(position.x, position.y, position.z, 1);				
}

```


And last but not least, the Texture folder contain all of the game textures in DDS format, i have not found any yet that aren't DDS however when converting with Imagemagick i do get a few errors;

> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\1544372202.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\1780544411.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\1863309771.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\1885645860.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\2477739845.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\2610875898.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\2873935326.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\3268294991.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\3270169217.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\4219829727.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\4683000.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_low\61211162.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\1544372202.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\1780544411.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\1863309771.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\1885645860.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\2477739845.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\2610875898.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\2873935326.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\3268294991.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\3270169217.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\4188884934.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\4219829727.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\4683000.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\61211162.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: image type not supported `F:\Gaming\Temp\M4X_TMP\Decoded\texture_norm\906252839.dds' @ dds.c/ReadDDSImage/346.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1033609888.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\113307133.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1218989904.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1370487583.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1541308564.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1667736035.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1706241735.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1756425296.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1805701300.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\183525020.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\1930636957.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\2119726841.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\274433149.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\283321059.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\288865812.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\3088368116.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\3448819463.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\3463632435.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\3470747961.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\3594334226.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\3994859792.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\4004902540.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\4070729627.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\4270309164.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\744685157.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\858011546.dds' @ dds.c/ReadDDSImage/280.
>
> mogrify.exe: Improper image header `F:\Gaming\Temp\M4X_TMP\Decoded\texture_uni\958323176.dds' @ dds.c/ReadDDSImage/280.

I haven't checked yet, but the "Improper image header" errors may be from the files being TGA and not DDS, but the "image type not supported" files are definately DDS and some load in Photoshop.

That's about all i've found so far, i hope this helps people who are interested in modding this game because i'm certainly interested in seeing some mods for it!  

Peace, Jenx
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-30T13:15:04+00:00
- Post Title: Some info on MOTORM4X Files

Way to join the forum !  Thanks very much for your info! Hope you can stick around.
## Post #3
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-08-06T16:33:14+00:00
- Post Title: Some info on MOTORM4X Files

> Reply from Mr.Mouse
>
> Way to join the forum !  Thanks very much for your info! Hope you can stick around.

Thanks Mr.Mouse!

As the old saying goes, "Caring is Sharing" 

Game File Research & Development has been a passion for mine for many years now, i'm very happy that i stumbled across this forum one day, as the people here seem to be very forthcoming in their info and input. 
I thought i would share the love and post what the info i had about this game. Although it may be overlooked by some, if i can make 1 person's life easier than mission accomplished 

I have alot more info that i can share here, and will definitely stick around to learn and share as much as i can 

While my coding skills aren't great, i'm more of a "Digger and research" kinda guy. I would love to have the skills that some people have on this forum but my time is put towards making the games not just pulling them apart   

Thanks for the reply, have an awesome day!

-Jenx
## Post #4
- Username: Xofroggy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 30, 2012 2:07 am
- Post datetime: 2012-06-29T18:12:22+00:00
- Post Title: Some info on MOTORM4X Files

cool does anyone have the english txt files i got the russian version and i cant read it can anyone please help me
