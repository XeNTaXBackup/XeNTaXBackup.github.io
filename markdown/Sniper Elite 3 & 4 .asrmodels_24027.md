## Post #1
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-11T12:40:20+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

Hey, I was messing around with SE4 and was wondering if anyone ever figured out the models.

Textures are great and easily extracted with asura.bms but about the models, it just extracts them as generic files.
I've attached a model extracted from the game below, I played around with it with MR but couldn't get the right offsets etc. 
Was wondering if there's info about this format anywhere.


 carcano scope.rar
(60.76 KiB) Downloaded 22 times
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-11T14:06:39+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

Half floats are harder to track, this is not perfect but may serve as a starting point, using hex2obj:
.



l3#carcano_scope_camo.png (45.83 KiB) Viewed 230 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-11T17:54:53+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

Using AXE:



l3#carcano_scope.png (122.68 KiB) Viewed 226 times
## Post #4
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-12T11:06:10+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from Bigchillghost ↑Sat Jun 12, 2021 1:54 am at Sat Jun 12, 2021 1:54 am
>
> 
Using AXE:
l3#carcano_scope.png

Damn, I gotta figure out how to use mesh reaper :s.

Thank you both.
This was the result I was getting with model researcher, same for DJ Normality.

[https://i.imgur.com/l1JAVEp.png](https://i.imgur.com/l1JAVEp.png)

I'll try to use Ghost's AXE and see if I can work something out that way. Looks way more complicated than MR but hopefully I can understand how it works (time to read the wonderful tutorial posted by Ghost ) .
## Post #5
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-12T11:30:10+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

Here is the file from said screenshot from above. I used the same format as the one in your post but with the offsets that worked for me in model researcher. I get a same result, was wondering if it's not just me and if it is me using AXE wrong what the difference is with model researcher to get the models to actually work with AXE where-as with model researcher they're broken like in said screenshot above. If you could look at some point ghost since you know how to use AXE better that'd be nice. I also put a link in the bottom of this post to a download of more SE4 stuff including an actual human model if anyone's interested in having a go at that.

Offset I used was 2D7EC.


 kar98k_snow.rar
(93.91 KiB) Downloaded 20 times




More files: [https://mega.nz/file/thp0HLTK#dTlREBNr2 ... bnGtco9A4w](https://mega.nz/file/thp0HLTK#dTlREBNr2kFTe9HGBylE72PXRYUXFf4JQbnGtco9A4w)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-12T13:57:25+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from dimis9138 ↑Sat Jun 12, 2021 7:06 pm at Sat Jun 12, 2021 7:06 pm
>
> 
I'll try to use Ghost's AXE and see if I can work something out that way.
You know, it sounds kinda weird that you address me like that and I "officially" disapprove it.  

> Reply from dimis9138 ↑Sat Jun 12, 2021 7:30 pm at Sat Jun 12, 2021 7:30 pm
>
> 
I used the same format as the one in your post but with the offsets that worked for me in model researcher. I get a same result, was wondering if it's not just me and if it is me using AXE wrong what the difference is with model researcher to get the models to actually work with AXE where-as with model researcher they're broken like in said screenshot above.
AXE uses the low-level vertex index count to describe polygons as it's not possible to know the exact polygon amount for encodings like triangle strip without interpreting the data first. You should not just copy the params without adjusting them according to your circumstances, though some of them might still be the same. In your screen you forgot to adjust the relative address for vertex attributes. That's the only param you need to adjust for vertex attributes btw.

It took me a while to figure out what you mean by "broken" then I just realized the data type for positions should actually be unsigned short, which sadly had not been revealed by that previous sample.



kar98k_snow.png (138.7 KiB) Viewed 191 times
## Post #7
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-12T19:01:15+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from Bigchillghost ↑Sat Jun 12, 2021 9:57 pm at Sat Jun 12, 2021 9:57 pm
>
> 
dimis9138 wrote: ↑Sat Jun 12, 2021 7:06 pm
I'll try to use Ghost's AXE and see if I can work something out that way. 

You know, it sounds kinda weird that you address me like that and I "officially" disapprove it.  
dimis9138 wrote: ↑Sat Jun 12, 2021 7:30 pm
I used the same format as the one in your post but with the offsets that worked for me in model researcher. I get a same result, was wondering if it's not just me and if it is me using AXE wrong what the difference is with model researcher to get the models to actually work with AXE where-as with model researcher they're broken like in said screenshot above. 

AXE uses the low-level vertex index count to describe polygons as it's not possible to know the exact polygon amount for encodings like triangle strip without interpreting the data first. You should not just copy the params without adjusting them according to your circumstances, though some of them might still be the same. In your screen you forgot to adjust the relative address for vertex attributes. That's the only param you need to adjust for vertex attributes btw.

It took me a while to figure out what you mean by "broken" then I just realized the data type for positions should actually be unsigned short, which sadly had not been revealed by that previous sample.
kar98k_snow.png

Oh so the relative to address in AXE is the address for vertices? I didn't quite understand that hah. I will play around with some more samples and post something here. Thanks a lot man, I really appreciate it. Now all we need like Normality said is a tool that makes another tool off these settings hahah.
## Post #8
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-12T19:41:14+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

After using MR I could produce this result: 

After putting this in AXE I got this error: Polygon vertex index count could not evenly divide by 3. I realized by looking at your screenshots that you simply * 3'd the vertices amount (something I guess MR does automatically with shorts?) to get your results and did the same but I'm now just getting this error: Error occured while checking params, file too small for required size of polygon vertex index data which makes me think I've simply went out of the file's size but reducing it simply gives a pretty damaged result.

MR settings: 

File attached, sorry for being a pain but I'm just trying to learn how to use AXE better because it seems to be a really great tool and I'm not sure if there's a way to override it or not.




 kar98k_scope.rar
(17.36 KiB) Downloaded 15 times
## Post #9
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-13T01:56:06+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

I've also looked at another file which I linked (g43_snow in the picture & g43) which appears to be everything correctly set up such as vertices, faces etc but the end result is a flat plane with all the faces overlapping. If anyone knows what could be causing this please let me know.

AXE settings: 

End result: 

However the positions seem fine in the interpretation.

Also, this program is really great. Thank you for releasing this.


 g43.rar
(139.81 KiB) Downloaded 15 times
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-13T03:03:59+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from dimis9138 ↑Sun Jun 13, 2021 3:01 am at Sun Jun 13, 2021 3:01 am
>
> 
Oh so the relative to address in AXE is the address for vertices?
There're two modes for how vertex attribute addresses can be specified. You can either specify the absolute addresses for every vertex attributes, by enabling the "Absolute" radio button, in which way you'll have to modify the values every time for another file or sub-mesh. Or, you could just use the relative mode, to specify a base address for the vertex attributes, and then specify the offsets for corresponding attributes, relative to that address. In this way, so long as the vertex layout doesn't change, you don't need to change the offset for every attribute. Instead, you just need to reassign the base address (or called a relative address), which obvious will be a great relief for the lazy.

> Reply from dimis9138 ↑Sun Jun 13, 2021 3:41 am at Sun Jun 13, 2021 3:41 am
>
> 
After putting this in AXE I got this error: Polygon vertex index count could not evenly divide by 3. I realized by looking at your screenshots that you simply * 3'd the vertices amount (something I guess MR does automatically with shorts?)
As I wrote here:

> Reply from Bigchillghost ↑Sat Jun 12, 2021 9:57 pm at Sat Jun 12, 2021 9:57 pm
>
> 
AXE uses the low-level vertex index count to describe polygons as it's not possible to know the exact polygon amount for encodings like triangle strip without interpreting the data first.
It's not the "vertices amount" that you need to multiply with, it's the polygon amount. For ordinary triangle encoding you get the indices count by multiplying the polygon count with 3, or by dividing the total length of the indices data by 2 (for short indices).

The params you used for polygon vertex indices address and count aren't accurate btw.



kar98k_scope.png (122.35 KiB) Viewed 145 times



> Reply from dimis9138 ↑Sun Jun 13, 2021 3:41 am at Sun Jun 13, 2021 3:41 am
>
> 
sorry for being a pain but I'm just trying to learn how to use AXE better because it seems to be a really great tool
AXE inherited pretty much all features from AMR, which has a detailed document for how it works. Furthermore, AXE simply enhanced that, which's why I didn't bother to write another "specification". I'm just too lasy for that. You can however use that document as a reference for a better understanding of the entire workflow. Link attached below.
[AMR - Mesh Format Research Helper](viewtopic.php?f=33&t=20995)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-13T03:09:40+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from dimis9138 ↑Sun Jun 13, 2021 9:56 am at Sun Jun 13, 2021 9:56 am
>
> 
I've also looked at another file which I linked (g43_snow in the picture & g43) which appears to be everything correctly set up such as vertices, faces etc but the end result is a flat plane with all the faces overlapping. If anyone knows what could be causing this please let me know.
You were just using the wrong params. The relative address for vertex attributes should be 0xA4 and the address for polygon vertex indices is 0x2CB04, and the indices count, 14973.
## Post #12
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-13T03:11:12+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from Bigchillghost ↑Sun Jun 13, 2021 11:03 am at Sun Jun 13, 2021 11:03 am
>
> 
dimis9138 wrote: ↑Sun Jun 13, 2021 3:01 am
Oh so the relative to address in AXE is the address for vertices?

There're two modes for how vertex attribute addresses can be specified. You can either specify the absolute addresses for every vertex attributes, by enabling the "Absolute" radio button, in which way you'll have to modify the values every time for another file or sub-mesh. Or, you could just use the relative mode, to specify a base address for the vertex attributes, and then specify the offsets for corresponding attributes, relative to that address. In this way, so long as the vertex layout doesn't change, you don't need to change the offset for every attribute. Instead, you just need to reassign the base address (or called a relative address), which obvious will be a great relief for the lazy.
dimis9138 wrote: ↑Sun Jun 13, 2021 3:41 am
After putting this in AXE I got this error: Polygon vertex index count could not evenly divide by 3. I realized by looking at your screenshots that you simply * 3'd the vertices amount (something I guess MR does automatically with shorts?)

As I wrote here:
Bigchillghost wrote: ↑Sat Jun 12, 2021 9:57 pm
AXE uses the low-level vertex index count to describe polygons as it's not possible to know the exact polygon amount for encodings like triangle strip without interpreting the data first. 

It's not the "vertices amount" that you need to multiply with, it's the polygon amount. For ordinary triangle encoding you get the indices count by multiplying the polygon count with 3, or by dividing the total length of the indices data by 2 (for short indices).

The params you used for polygon vertex indices address and count aren't accurate btw.

kar98k_scope.png
dimis9138 wrote: ↑Sun Jun 13, 2021 3:41 am
sorry for being a pain but I'm just trying to learn how to use AXE better because it seems to be a really great tool

AXE inherited pretty much all features from AMR, which has a detailed document for how it works. Furthermore, AXE simply enhanced that, which's why I didn't bother to write another "specification". I'm just too lasy for that. You can however use that document as a reference for a better understanding of the entire workflow. Link attached below.
AMR - Mesh Format Research Helper

Thank you, that answers a lot of my questions. I will try to get into AMR this weekend first and then AXE to try and learn this workflow for reversing models.
## Post #13
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-13T03:12:21+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from Bigchillghost ↑Sun Jun 13, 2021 11:09 am at Sun Jun 13, 2021 11:09 am
>
> 
dimis9138 wrote: ↑Sun Jun 13, 2021 9:56 am
I've also looked at another file which I linked (g43_snow in the picture & g43) which appears to be everything correctly set up such as vertices, faces etc but the end result is a flat plane with all the faces overlapping. If anyone knows what could be causing this please let me know.

You were just using the wrong params. The relative address for vertex attributes should be 0xA4 and the address for polygon vertex indices is 0x2CB04, and the indices count, 14973.

Damn you're a legend man. I keep getting confused because last time I tried to do this was with cyberpunk models where I could at least see the general shape of the model even if the offsets were slightly wrong so when I see a flat plane I tend to get confused. By the way, you should definitely get a tip link or something where people (like me) can tip/thank you for your work and being this patient as a whole. Thanks a lot man.
## Post #14
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-13T06:28:53+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

Only last thing I'd like to ask if it is possible, is how is padding exactly decided/processed/dealt with in AXE? Is it by getting the correct amount of columns for stride so that they're held exactly in 1 row (I'm asking this after briefly reading your AXE demonstration and seeing you detail processing vertex attributes with stride)?

Main reason I'm asking is because I'm confused with the terminology from MR (padding) and assuming that the equal in AXE is stride for attributes.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-13T07:11:29+00:00
- Post Title: Sniper Elite 3 & 4 .asr/models

> Reply from dimis9138 ↑Sun Jun 13, 2021 2:28 pm at Sun Jun 13, 2021 2:28 pm
>
> Is it by getting the correct amount of columns for stride so that they're held exactly in 1 row (I'm asking this after briefly reading your AXE demonstration and seeing you detail processing vertex attributes with stride)?
Yes, AXE uses the size (or stride) of a vertex element structure (containing all the attributes for one vertex including positions, normals, texcoords, etc.) to determine how the data are aligned. Otherwise you'll have to measure and specify the amount of bytes to skip after reading each attributes, which'll definitely be a huge pain considering so many vertex attributes.
## Post #16
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-13T07:15:17+00:00
- Post Title: Re: Sniper Elite 3 & 4 .asr/models

> Reply from Bigchillghost ↑Sun Jun 13, 2021 3:11 pm at Sun Jun 13, 2021 3:11 pm
>
> 
dimis9138 wrote: ↑Sun Jun 13, 2021 2:28 pmIs it by getting the correct amount of columns for stride so that they're held exactly in 1 row (I'm asking this after briefly reading your AXE demonstration and seeing you detail processing vertex attributes with stride)?

Yes, AXE uses the size (or stride) of a vertex element structure (containing all the attributes for one vertex including positions, normals, texcoords, etc.) to determine how the data are aligned. Otherwise you'll have to measure and specify the amount of bytes to skip after reading each attributes, which'll definitely be a huge pain considering so many vertex attributes.

Gotcha, thanks a lot. Is there any forum / discord for AXE by any chance? I have so far at least understood how to properly get vertices + faces so I'm sorta satisfied for the time being. Anyhow, thank you for your time! I'm sure this topic will be really useful for many people who'll inevitably want to look into this game.

Also: 

We did it!
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-13T07:44:18+00:00
- Post Title: Re: Sniper Elite 3 & 4 .asr/models

> Reply from dimis9138 ↑Sun Jun 13, 2021 3:15 pm at Sun Jun 13, 2021 3:15 pm
>
> 
Is there any forum / discord for AXE by any chance?
I don't think so. But feel free to ask about anything related to the usage of the program or how to exploit its features, in the AXE release page.
## Post #18
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-15T21:58:29+00:00
- Post Title: Re: Sniper Elite 3 & 4 .asr/models

After doing some more research I was able to figure out that the UVs were flipped in comparison with the textures and I was also able to understand the structure better as a whole.

Faces start at 00 00 01 00 02 00 right after the vertices. Vertices start at the very top along with the UVs.
Only thing I haven't been able to figure out is why models do this: 

I tried to switch between different data types but that didn't work so I am now wondering if there's some rigging going on or something like that which would arrange these parts correctly. I've attached the model if anyone else can figure out or wants to. I did it with AXE but I've also attached the MR settings. Bare in mind that you could still manually put the model together by moving everything in place but I was wondering if there's anything else in there.

Model Researcher settings: [https://i.imgur.com/RmbYqTx.png](https://i.imgur.com/RmbYqTx.png)

AXE settings: [https://i.imgur.com/WVPMWuY.png](https://i.imgur.com/WVPMWuY.png)

Model above linked here.


 walther_ppk.rar
(58.13 KiB) Downloaded 16 times
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-16T11:25:12+00:00
- Post Title: Re: Sniper Elite 3 & 4 .asr/models

> Reply from dimis9138 ↑Wed Jun 16, 2021 5:58 am at Wed Jun 16, 2021 5:58 am
>
> 
I am now wondering if there's some rigging going on or something like that which would arrange these parts correctly.
There's very limited info in the mesh file. Actually the structure is utterly straightforward:

```

long	subMeshCount
long	totalVertexCount
long	totalIndexCount
long64	unknown
for i = 0 < subMeshCount // sizeof = 24
{
	long	unknown
	long	zero
	long64	subMeshIndexCount
	long64	unknown
}
float	scaling[3]
float	unknown[3] // translations?

byte	vertexData[totalVertexCount*40]
byte	indexData[totalIndexCount*2]

// end of file

```


There's no tranformation info for the submeshes, nor rooms for any skeleton data. They must have been stored somewhere else.
## Post #20
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-17T01:33:08+00:00
- Post Title: Re: Sniper Elite 3 & 4 .asr/models

> Reply from Bigchillghost ↑Wed Jun 16, 2021 7:25 pm at Wed Jun 16, 2021 7:25 pm
>
> 
dimis9138 wrote: ↑Wed Jun 16, 2021 5:58 am
I am now wondering if there's some rigging going on or something like that which would arrange these parts correctly.

There's very limited info in the mesh file. Actually the structure is utterly straightforward:
Code: Select all// begin of file

long	subMeshCount
long	totalVertexCount
long	totalIndexCount
long64	unknown
for i = 0 < subMeshCount // sizeof = 24
{
	long	unknown
	long	zero
	long64	subMeshIndexCount
	long64	unknown
}
float	scaling[3]
float	unknown[3] // translations?

byte	vertexData[totalVertexCount*40]
byte	indexData[totalIndexCount*2]

// end of file


i
There's no tranformation info for the submeshes, nor rooms for any skeleton data. They must have been stored somewhere else.

Sorry to be a pain but is there a thread where I can understand how to read/use this type of file translations (like the one you just posted) better? I saw you also make this type of translation in your demonstration topic - was wondering if I should just read that topic again. I have read this: [viewtopic.php?f=29&t=17889](https://forum.xentax.com/viewtopic.php?f=29&t=17889) so I know that long float byte etc mean but what I'm wondering is how I can actually read that within the file (so I can say like the submeshcount is a long so it's the first 4 bytes but then also be able to say how many submeshes there are) and actually find the vertex count accurately (how to actually read the totalvertexcount and say the vert count is 500) so for example translate the totalvertexcount long into decimal or do I still have to just find the start and the end and just do end minus start for example? Because I thought the actual amount of vertices is stored somewhere in the file by looking at the translation you posted (totalVertexCount) unless that isn't the case and the format above simply states that each vert is a long.

Oh another thing I noticed is that models are scaled incorrectly, saw you mention scaling as a float but not really sure where I could even find that sort of thing.
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-18T11:12:22+00:00
- Post Title: Re: Sniper Elite 3 & 4 .asr/models

You really should avoid embeding quotes like this. It's too messy.

> Reply from dimis9138 ↑Thu Jun 17, 2021 9:33 am at Thu Jun 17, 2021 9:33 am
>
> 
is there a thread where I can understand how to read/use this type of file translations (like the one you just posted) better?

"file translations"? I wouldn't exactly chose that phrase. A more appropriate term could be "definition", "layout", or "structure" etc.

> Reply from dimis9138 ↑Thu Jun 17, 2021 9:33 am at Thu Jun 17, 2021 9:33 am
>
> 
I have read this ... but what I'm wondering is how I can actually read that within the file
It's just some pseudo code in a mixed style of C and QuickBMS to describe the file structure. It's not difficult to understand if you have some basis knowledge of programming languages. Usually I use the notation "[data type] [variable name]" combined with some control structures to help representing the data layout properly. You can start by undertanding some terms like data types, arrays, loops, structures etc. Here's a site I just found which seems nice for beginners: [https://www.tutorialspoint.com/cprogramming/](https://www.tutorialspoint.com/cprogramming/)

> Reply from dimis9138 ↑Thu Jun 17, 2021 9:33 am at Thu Jun 17, 2021 9:33 am
>
> 
... and actually find the vertex count accurately (how to actually read the totalvertexcount and say the vert count is 500) so for example translate the totalvertexcount long into decimal or do I still have to just find the start and the end and just do end minus start for example?
It'd be enough to just understand the concept and leave the dirty work to your hex editor. For instance, if there's a 4-byte sequence "00 02 00 00" and you knew it's a "long" in little endian, you can interpret the value as 0x200 in hex with your hex editor, which would be 512 in decimal. So if this field is a vertex count, then you'll know there're gonna be 512 vertices. Apparently it's no longer necessary to calculate the count yourself, which is only served as a means during analysis, or when you couldn't figure out how to find that info in the file.

> Reply from dimis9138 ↑Thu Jun 17, 2021 9:33 am at Thu Jun 17, 2021 9:33 am
>
> 
Oh another thing I noticed is that models are scaled incorrectly, saw you mention scaling as a float but not really sure where I could even find that sort of thing.
"incorrectly" how? These scaling factors always seem to be 1.0 so they're actually meaningless.
