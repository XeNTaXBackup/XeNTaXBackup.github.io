## Post #1
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-13T14:57:01+00:00
- Post Title: Need help.

Hello, Community. I'm new in this forum. And this is my first post.

So i was once a gamer, I play a game called Fung Wan Online. Until now I'm still playing that game
even the real server died 7 year ago. So now i want to try to modify the game, make it look better and stuff.

So i want to try 3d modeling as I heard some of my friends start 3d modeling too and they have a good time with it.
I tried myself too, And i admit, It was fun; playing with our imagination. But that's not the true reason i tried this.

I want to play around with the game model i was playing. So i try searching the game file.No .obj what so ever. What i think was the model file was (Yeah i was a noob) and try to import it in to the 3Ds MAX. And i found out, It was just a 
direct draw surface file.

Then i ask my friends then they said the .file was the model file and they have no idea how it works. I've been trying 
to find the converter but none works.   

I really need someone that can help me find or create a converter for model file *.to *.Obj.


The game's name is . It's made around 2000. Please help me with this.

This is the model file, animation file and direct draw surface file.
[File](https://www.mediafire.com/?949l15g113s3wlm)

If someone can help me with this, I would be really grateful.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-10-13T16:43:39+00:00
- Post Title: Need help.

It looks like some research has already been done on this.
[viewtopic.php?f=16&t=10618](http://forum.xentax.com/viewtopic.php?f=16&t=10618)

A standalone exporter was supposedly available at one time in this post, but the link is dead now.
[viewtopic.php?p=87044#p87044](http://forum.xentax.com/viewtopic.php?p=87044#p87044)

shakotay2 is still active here, maybe he still has the file.
## Post #3
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-13T16:56:08+00:00
- Post Title: Need help.

My friend is yuredacy. he recommended me to this forum.
Yes I plan to get in contact with him if i can.

I already have the converter he made. My friend gave it to me, But it's not converting stuff right. I've tried everything but it didn't seems to work. So i came here and ask again.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-13T20:11:05+00:00
- Post Title: Need help.

> Reply from WazerHD
>
> But it's not converting stuff right. I've tried everything but it didn't seems to work. So i came here and ask again.could you be more precise, please?

For me the FWanExtractor is working as expected for the vkm from your rar:



PC01Body_vkm.jpg (43.15 KiB) Viewed 125 times
## Post #5
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-14T00:18:54+00:00
- Post Title: Need help.

> Reply from shakotay2
>
> WazerHD wrote:But it's not converting stuff right. I've tried everything but it didn't seems to work. So i came here and ask again.could you be more precise, please?

For me the FWanExtractor is working as expected for the vkm from your rar:
PC01Body_vkm.jpg

I'm sorry. I didn't mean it's not working, I mean I don't understand how it works. For model PC18 it's working fine when i insert the adress 0x60ED. But on this ones it just crash the extractor.

Can you explain to me how it works?


EDIT:
what i mean is, I can't extract the leg part. the top is all fine just like your picture. But i can't figure out what adress to enter for the bottom
## Post #6
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-16T04:27:55+00:00
- Post Title: Need help.

Please reply A.S.A.P. i really need your help, shakotay2.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-16T12:58:00+00:00
- Post Title: Need help.

> Reply from WazerHD
>
> Please reply A.S.A.P.My tools are for free and don't have a built-in
asap support.  

At least you seem to have read the vertsCnt_at_ readme...
Search for the vertex count of the lower body (544 dec.) - its address is the one to be entered.



PCMaleLower01.jpg (20.26 KiB) Viewed 78 times
## Post #8
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-16T16:32:43+00:00
- Post Title: Need help.

But i don't get any of these  

> address of the vertex count for KIRIN is 0x74
>
> 
>
> Offset 0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
>
> 
>
> 0000  56 4B 59 4D 69 00 00 00  01 00 00 00 34 00 00 00  VKYMi.......4...
>
> 0010  01 00 02 00 00 00 00 00  77 E0 01 00 4B 72 69 6E  ........wà..Krin
>
> 0020  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00
>
> 0030  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00
>
> 0040  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00
>
> 0050  00 00 00 00 00 00 00 00  00 00 00 00 00 00 40 37
>
> 0060  A9 96 42 42 00 49 16 C0  39 10 EC 41 AF 96 42 42
>
> 0070  D6 21 80 42<13 06 00 00> 00 D3 88 35 F9 36 64 42
>
> 
>
> ------------------------------------------------------
>
> 
>
> For the first submesh in PC18 it's also 0x74 but
>
> for the second one (Lower Body) it's not so easy.
>
> 
>
> As a rule you might find the address counting 4 lines down 
>
> from the position of the 'a' in .max.
>
> 
>
> The address of the vertex count for Lower Body being 0x60ED:
>
> 
>
> 
>
> Offset  0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
>
> 
>
> 06090  00 7F 92 00 00 50 43 31  38 5F 4C 6F 77 65 72 20  .’..PC18_Lower 
>
> 060A0  42 6F 64 79 00 00 00 74  30 30 30 2E 6D 61 78 00  Body...t000.max.
>
> 060B0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00
>
> 060C0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00
>
> 060D0  00 00 00 00 00 00 00 B0  37 BE 70 E2 41 8C C4 F6
>
> 060E0  BF 2C 08 04 41 E7 00 E2  41 37 3D DB 40<D7 01 00
>
> 060F0  00>DC 4B C6 36 99 7E 51  42 AB B3 A6 C0 50 F8 7B
>
> 
>
> 
>
> You'll have to rename the first submesh/obj of PC18 manually 
>
> otherwise it will be overwritten when exporting the second one.
## Post #9
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-18T13:31:24+00:00
- Post Title: Need help.

I don't know what those things means. Please explain it to me.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-18T16:03:03+00:00
- Post Title: Need help.

you'll need to find the address of the vertex count. This address (7E26) to be entered in the FungWan extractor tool.
The vertex count to be found 4 (or 5) lines below the submesh string (PC Male Lower 01 in the attached picture).

The vertex count to be identified by containing 00 00 (it's very unlikely that there's a float in that line hitting this condition. If so, well, then you're lost, I guess...)



PC01_öowerBody_VertexCount.jpg (76.43 KiB) Viewed 49 times
## Post #11
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-18T16:47:27+00:00
- Post Title: Need help.

> Reply from shakotay2
>
> you'll need to find the address of the vertex count. This address (7E26) to be entered in the FungWan extractor tool.
The vertex count to be found 4 (or 5) lines below the submesh string (PC Male Lower 01 in the attached picture).

The vertex count to be identified by containing 00 00 (it's very unlikely that there's a float in that line hitting this condition. If so, well, then you're lost, I guess...)
PC01_öowerBody_VertexCount.jpg

How do i find the vertex address? is there any tool to check that?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-18T17:23:17+00:00
- Post Title: Need help.

the vertices start after the vertex count. (The only tool I know for getting the vertices' start address is the braintool. But sadly it can't be downloaded anywhere.  )
## Post #13
- Username: WazerHD
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 13, 2014 10:20 pm
- Post datetime: 2014-10-18T18:08:40+00:00
- Post Title: Need help.

> Reply from shakotay2
>
> the vertices start after the vertex count. (The only tool I know for getting the vertices' start address is the braintool. But sadly it can't be downloaded anywhere.  )

I got it figured out. Thank you shakotay you've been a big help for me.
If you hasn't shown me the Hex editor thing a couple times, i wont find out where to find those things xD
topic closed. thanks again, shakotay.
