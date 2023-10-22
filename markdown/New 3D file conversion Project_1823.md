## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-04-08T02:44:43+00:00
- Post Title: New 3D file conversion Project

Here is is short introduction to another interesting project I have to deal with. In order to gather some interest and possibly your kind and greatly appreciated assistance I'll try to briefly describe what is all about. 

I am a member of TSH modding group doing some work on pretty good and rather well known military flight simulation of F/A-19 Hornet by Janes and published back in 1999 by EA. The sim has a priopriatory format of file called 3DG. Some time ago someone made converter to 3DS and viewer called ZEdit. It is available and has entire source code consisting of many files. The program converts 3DS to 3DG and viceversa and also is capable of additional import of X and SRF format files and conversion to 3DG. 

The problem is that ZEdit it is not fully capable of importing animation and LODs (level of detail models) . This is not supported and not implemented. We are looking for any advice and support in our mission to correct it and our goal is to have it. 

At the moment I would like myself and whoever else interested here just to get acquainted with precise structure of 3DS and 3DG formats just by looking and analysing those pieces of code on this forum. 
So, shall we try
## Post #2
- Username: Homer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 14, 2006 1:04 am
- Post datetime: 2006-04-13T17:31:40+00:00
- Post Title: New 3D file conversion Project

Just surfing through... here you go.....

[http://www.geocities.com/aliens_can_dunk/3dlinks.html](http://www.geocities.com/aliens_can_dunk/3dlinks.html)
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-04-13T20:55:18+00:00
- Post Title: New 3D file conversion Project

Thank you for interesting and what I call "kitchen" link. I stumbled accross that once before the resources pertaining to 3DS documentation very good indeed. 

Just without going into the details, but how do you think such a converter is being made? Do you think that general terms there must be a fields of data comparison between two formats? Then similar fields are identyfied "highlighted" and linked.  Information from one format is then "fed" into the fields of another format. The sequence and order of such similar fields do not matter, but the the content does. 

Is this more or less your understanding how such a converters are written up?
## Post #4
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-11T01:02:34+00:00
- Post Title: New 3D file conversion Project

Essentially what a converter will do is read the raw geometry and UVW coordinates (remember, it's in binary >.<) from your file to be converted, and will try and re-arrange them as best it can in order to create a file that conforms to the specifications of the new format. You'd also need to know a bit about how the game works before importing anims, as they may use bones. LOD should be pretty easy, I'd be willing to bet you could find locations to begin reads in the header somewhere... If you know how it designates where to begin reading the main model data, you could probably compare that to the rest of the header and look for similarities in other chunks.
## Post #5
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-11-11T21:49:35+00:00
- Post Title: New 3D file conversion Project

It is indeed happy coincidence that after so much time ( my post was made in April), just day before yesterday I decided to go back to revisit this project. 

And in fact after few hours of gawking into the hex code of an example file I managed to decipher some details.  I have recognised in the detail how geometry is recorded and written - first as a list of binary coordinates for all vertices , and then it has been "fleshed" out and grouped into the polygons outlining true shape of the model.  

That list contains: the main most detailed 3D object and then lower iterations of the same as LOD 2 and 3 ever simple and simple.
The list is even using the same vertexes of the complex shape, but the polygons are new. 

However, as you write :

> LOD should be pretty easy, I'd be willing to bet you could find locations to begin reads in the header somewhere... If you know how it designates where to begin reading the main model data, you could probably compare that to the rest of the header and look for similarities in other chunks.

I FAIL to see how the game engine and possible the exporter may differentiate and recognise when to use or separate them cleanly?

I am willing to copy here all what was deciphered so far as the best would be to look at the real example. Stand by ....
## Post #6
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-11-11T21:58:41+00:00
- Post Title: New 3D file conversion Project

Which, without further ado.... I do   
Below is the file in its "native" form  except that I formated it a little for better understanding whats there.
 
> BUNKERB.3dg FROM F18 
>
> 
>
> 6f 2a 79 41 
>
> 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 00 80 03 00 02 00 00 00 
>
> 
>
> 52 55 53 54 30 31 2e 50 43 58 00 00 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 80 3f 
>
> 00 00 80 3f 
>
> 
>
> 43 4f 4e 30 33 2e 50 43 58 00 00 00 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 b5 b4 
>
> 00 00 80 3f 
>
> 00 00 80 3f 
>
> 
>
> 00 00 00 00 
>
> 0c 00 00 00 
>
> 
>
> db 49 b2 40 
>
> 3d 25 27 40 
>
> 16 93 48 c1 
>
> db 49 b2 40 
>
> 3d 25 27 40 
>
> 00 00 00 00 
>
> db 49 b2 c0 
>
> 3d 25 27 40 
>
> 00 00 00 00 
>
> db 49 b2 c0 
>
> 3d 25 27 40 
>
> 16 93 48 c1 
>
> 52 dc de c0 
>
> 00 00 00 00 
>
> 52 dc 5e c1 
>
> 52 dc de c0 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 52 dc de 40 
>
> 00 00 00 00 
>
> 52 dc 5e c1 
>
> 52 dc de 40 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> db 49 b2 40 
>
> 3d 25 27 40 
>
> 16 93 48 41 
>
> db 49 b2 c0 
>
> 3d 25 27 40 
>
> 16 93 48 41 
>
> 52 dc de c0 
>
> 00 00 00 00 
>
> 52 dc 5e 41 
>
> 52 dc de 40 
>
> 00 00 00 00 
>
> 52 dc 5e 41 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 
>
> 06 00 00 00 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 00 00 00 
>
> 3d 25 27 40 
>
> e1 e1 61 bf 
>
> f3 f0 f0 3e 
>
> 00 00 00 00 
>
> 48 a4 c4 40 
>
> 00 00 00 00 
>
> f7 f0 f0 3e 
>
> e0 e1 61 bf 
>
> 47 a4 44 41 
>
> e1 e1 61 3f 
>
> f3 f0 f0 3e 
>
> 00 00 00 00 
>
> 48 a4 c4 40 
>
> 00 00 00 00 
>
> f7 f0 f0 3e 
>
> e0 e1 61 3f 
>
> 47 a4 44 41 
>
> 
>
> 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 00 00 00 00 00 00 00 
>
> 09 00 00 00 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 
>
> 04 00 01 00 00 00 00 00 
>
> 06 00 02 00 00 00 00 00 
>
> 07 00 03 00 00 00 00 00 
>
> 01 00 00 00 00 00 00 00 
>
> 05 00 01 00 00 00 00 00 
>
> 0b 00 03 00 00 00 00 00 
>
> 0a 00 04 00 00 00 00 00 
>
> 06 00 00 00 00 00 05 00 
>
> 0c 00 00 00 00 00 00 00 
>
> 
>
> 33 a3 d9 44 
>
> 00 00 05 00 
>
> 89 00 01 00 
>
> 33 a3 d9 44 
>
> 66 3a a3 45 
>
> 00 00 05 00 
>
> d6 00 02 00 
>
> 66 3a a3 45 
>
> 53 0b 26 4d 
>
> 00 00 00 00 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 04 
>
> 00 00 00 00 00 00 00 00 80 3f 
>
> 01 00 00 00 00 00 00 00 00 00 
>
> 02 00 00 00 80 3f 00 00 00 00 
>
> 03 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 01 00 00 00 00 04 
>
> 04 00 00 00 00 00 00 00 80 3f 
>
> 03 00 00 00 00 00 00 00 00 00 
>
> 02 00 00 00 80 3f 00 00 00 00 
>
> 05 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 02 00 02 00 00 00 00 04 
>
> 06 00 00 00 80 a4 00 00 80 3f 
>
> 00 00 cd cc cc 3d 40 8e 63 3d 
>
> 03 00 66 66 66 3f 40 8e 63 3d 
>
> 04 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 03 00 00 00 00 04 
>
> 07 00 00 00 80 3f 00 00 80 3f 
>
> 01 00 00 00 80 3f 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 00 00 
>
> 06 00 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 00 00 01 04 
>
> 01 00 00 00 80 3f 00 00 80 3f 
>
> 08 00 00 00 80 3f 00 00 00 00 
>
> 09 00 00 00 00 00 00 00 00 00 
>
> 02 00 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 05 00 00 00 00 04 
>
> 05 00 00 00 80 3f 00 00 80 3f 
>
> 02 00 00 00 80 3f 00 00 00 00 
>
> 09 00 00 00 00 00 00 00 00 00 
>
> 0a 00 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 06 00 00 00 00 04 
>
> 0b 00 00 00 00 00 00 00 80 3f 
>
> 08 00 00 00 00 00 00 00 00 00 
>
> 01 00 00 00 80 3f 00 00 00 00 
>
> 07 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 07 00 00 00 00 04 
>
> 0a 00 00 00 80 3f 00 00 80 3f 
>
> 09 00 66 66 66 3f 40 8e 63 3d 
>
> 08 00 cd cc cc 3d 40 8e 63 3d 
>
> 0b 00 00 00 80 a4 00 00 80 3f 
>
> 
>
> 00 00 00 00 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 04 
>
> 00 00 00 00 00 00 00 00 80 3f 
>
> 08 00 00 00 00 00 00 00 00 00 
>
> 09 00 00 00 80 3f 00 00 00 00 
>
> 03 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 01 00 00 00 00 04 
>
> 04 00 00 00 00 00 00 00 80 3f 
>
> 03 00 00 00 00 00 00 00 00 00 
>
> 09 00 00 00 80 3f 00 00 00 00 
>
> 0a 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 02 00 02 00 00 00 00 04 
>
> 06 00 00 00 80 a4 00 00 80 3f 
>
> 00 00 cd cc cc 3d 40 8e 63 3d 
>
> 03 00 66 66 66 3f 40 8e 63 3d 
>
> 04 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 06 00 00 00 00 04 
>
> 0b 00 00 00 80 3f 00 00 80 3f 
>
> 08 00 00 00 80 3f 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 00 00 
>
> 06 00 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 07 00 00 00 00 04 
>
> 0a 00 00 00 80 3f 00 00 80 3f 
>
> 09 00 66 66 66 3f 40 8e 63 3d 
>
> 08 00 cd cc cc 3d 40 8e 63 3d 
>
> 0b 00 00 00 80 a4 00 00 80 3f 
>
> 00 00 00 00 
>
> 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 05 00 08 00 00 00 01 04 
>
> 06 00 00 00 00 00 00 00 80 3f 
>
> 0b 00 00 00 00 00 00 00 00 00 
>
> 0a 00 00 00 80 3f 00 00 00 00 
>
> 04 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 00 00 00 00 00 00 00

And now the same but with my commentary what 
I know   , 
I think I know   and 
I'm dumb about     :

> BUNKERB.3dg FROM F18 
>
> 
>
> 
>
> 
>
> 6f 2a 79 41 //here is ID 
>
> 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 00 00 00 00 02 00 00 00 //surely many things here, but it ends on that there are 2 materials which in this case are textures 
>
> 
>
> 52 55 53 54 30 31 2e 50 43 58 00 00 //name of the 1st material, which here is texture RUST01.PCX, 
>
> 00 00 00 00 00 00 00 00 //I think also that 8x00 which follow are part of this string 20 char long ...saw somewhere 
>
> 
>
> 00 00 80 3f //now this is little mystery but I think this is float = 1.00 and it indicates that full size of texture is used lengthwise and then hightwise 
>
> 00 00 80 3f 
>
> 
>
> 43 4f 4e 30 33 2e 50 43 58 00 00 00 //same as above for the 2nd material / texture, 20 char for name 
>
> 00 00 00 00 00 00 00 00 
>
> 00 00 b5 b4 //new element here, not sure 
>
> 00 00 80 3f 
>
> 00 00 80 3f //same as above for the 2nd texture 
>
> 
>
> 00 00 00 00 //??????? 
>
> 
>
> 0c 00 00 00 //here is total number of vertices 12 for the model in its higher LOD (level of detail, pls ref. sketch) 
>
> // here go floats with XYZ coordinate for each of 12 vertices, I have manually verified that on the model and I will translate to DEC and label them on sketch 
>
> 
>
> db 49 b2 40 //vertex 00 
>
> 3d 25 27 40 
>
> 16 93 48 c1 
>
> db 49 b2 40 //vertex 01 
>
> 3d 25 27 40 
>
> 00 00 00 00 
>
> db 49 b2 c0 //vertex 02 
>
> 3d 25 27 40 
>
> 00 00 00 00 
>
> db 49 b2 c0 //vertex 03 
>
> 3d 25 27 40 
>
> 16 93 48 c1 
>
> 52 dc de c0 //vertex 04 
>
> 00 00 00 00 
>
> 52 dc 5e c1 
>
> 52 dc de c0 //vertex 05 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 52 dc de 40 //vertex 06 
>
> 00 00 00 00 
>
> 52 dc 5e c1 
>
> 52 dc de 40 //vertex 07 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> db 49 b2 40 //vertex 08 
>
> 3d 25 27 40 
>
> 16 93 48 41 
>
> db 49 b2 c0 //vertex 09 
>
> 3d 25 27 40 
>
> 16 93 48 41 
>
> 52 dc de c0 //vertex 0A 
>
> 00 00 00 00 
>
> 52 dc 5e 41 
>
> 52 dc de 40 //vertex 0B 
>
> 00 00 00 00 
>
> 52 dc 5e 41 
>
> 
>
> // here goes long block I do not understand - need help !!! 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 00 00 00 00 
>
> 
>
> 06 00 00 00 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 00 00 00 
>
> 3d 25 27 40 
>
> e1 e1 61 bf 
>
> f3 f0 f0 3e 
>
> 00 00 00 00 
>
> 48 a4 c4 40 
>
> 00 00 00 00 
>
> f7 f0 f0 3e 
>
> e0 e1 61 bf 
>
> 47 a4 44 41 
>
> e1 e1 61 3f 
>
> f3 f0 f0 3e 
>
> 00 00 00 00 
>
> 48 a4 c4 40 
>
> 00 00 00 00 
>
> f7 f0 f0 3e 
>
> e0 e1 61 3f 
>
> 47 a4 44 41 
>
> 
>
> 00 00 00 00 00 00 80 3f 
>
> 
>
> 00 00 00 00 00 00 00 00 
>
> 09 00 00 00 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 
>
> 04 00 01 00 00 00 00 00 
>
> 06 00 02 00 00 00 00 00 
>
> 07 00 03 00 00 00 00 00 
>
> 01 00 00 00 00 00 00 00 
>
> 05 00 01 00 00 00 00 00 
>
> 0b 00 03 00 00 00 00 00 
>
> 0a 00 04 00 00 00 00 00 
>
> 06 00 00 00 00 00 05 00 
>
> 0c 00 00 00 00 00 00 00 
>
> 
>
> 33 a3 d9 44 
>
> 00 00 05 00 
>
> 89 00 01 00 
>
> 33 a3 d9 44 
>
> 66 3a a3 45 
>
> 00 00 05 00 
>
> d6 00 02 00 
>
> 66 3a a3 45 
>
> 53 0b 26 4d 
>
> 00 00 00 00 
>
> 
>
> 
>
> // here goes lis of the surfaces for enitre model and all LODS .Basically it says that vertex 00 01 02 03 make 4 vert surface and material it is 01 wchich is 1st texture RUST01. There are other important flags here but I did not deciphered them yet. Again, 80 3f tells that full extend of texture is used ... I think. I will also label them and show on sketch. NOTE: the same vertices are used in 3 LODS 
>
> 
>
> //Here goes 12 vert and 8 polygons for VERY HIGH DETAIL LOD 
>
> //Poly A 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 04 
>
> 00 00 00 00 00 00 00 00 80 3f 
>
> 01 00 00 00 00 00 00 00 00 00 
>
> 02 00 00 00 80 3f 00 00 00 00 
>
> 03 00 00 00 80 3f 00 00 80 3f 
>
> //POLY B 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 01 00 00 00 00 04 
>
> 04 00 00 00 00 00 00 00 80 3f 
>
> 03 00 00 00 00 00 00 00 00 00 
>
> 02 00 00 00 80 3f 00 00 00 00 
>
> 05 00 00 00 80 3f 00 00 80 3f 
>
> //POLY C 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 02 00 02 00 00 00 00 04 
>
> 06 00 00 00 80 a4 00 00 80 3f 
>
> 00 00 cd cc cc 3d 40 8e 63 3d 
>
> 03 00 66 66 66 3f 40 8e 63 3d 
>
> 04 00 00 00 80 3f 00 00 80 3f 
>
> //POLY D 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 03 00 00 00 00 04 
>
> 07 00 00 00 80 3f 00 00 80 3f 
>
> 01 00 00 00 80 3f 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 00 00 
>
> 06 00 00 00 00 00 00 00 80 3f 
>
> //POLY E 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 00 00 01 04 
>
> 01 00 00 00 80 3f 00 00 80 3f 
>
> 08 00 00 00 80 3f 00 00 00 00 
>
> 09 00 00 00 00 00 00 00 00 00 
>
> 02 00 00 00 00 00 00 00 80 3f 
>
> //POLY F 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 05 00 00 00 00 04 
>
> 05 00 00 00 80 3f 00 00 80 3f 
>
> 02 00 00 00 80 3f 00 00 00 00 
>
> 09 00 00 00 00 00 00 00 00 00 
>
> 0a 00 00 00 00 00 00 00 80 3f 
>
> //POLY G 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 06 00 00 00 00 04 
>
> 0b 00 00 00 00 00 00 00 80 3f 
>
> 08 00 00 00 00 00 00 00 00 00 
>
> 01 00 00 00 80 3f 00 00 00 00 
>
> 07 00 00 00 80 3f 00 00 80 3f 
>
> //POLY H 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 07 00 00 00 00 04 
>
> 0a 00 00 00 80 3f 00 00 80 3f 
>
> 09 00 66 66 66 3f 40 8e 63 3d 
>
> 08 00 cd cc cc 3d 40 8e 63 3d 
>
> 0b 00 00 00 80 a4 00 00 80 3f 
>
> 
>
> 00 00 00 00 
>
> 
>
> //Here goes 8 vert and 5 polygons for HIGH DETAIL LOD 
>
> //POLY I 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 04 
>
> 00 00 00 00 00 00 00 00 80 3f 
>
> 08 00 00 00 00 00 00 00 00 00 
>
> 09 00 00 00 80 3f 00 00 00 00 
>
> 03 00 00 00 80 3f 00 00 80 3f 
>
> //POLY J 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 00 01 00 00 00 00 04 
>
> 04 00 00 00 00 00 00 00 80 3f 
>
> 03 00 00 00 00 00 00 00 00 00 
>
> 09 00 00 00 80 3f 00 00 00 00 
>
> 0a 00 00 00 80 3f 00 00 80 3f 
>
> //POLY K 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 02 00 02 00 00 00 00 04 
>
> 06 00 00 00 80 a4 00 00 80 3f 
>
> 00 00 cd cc cc 3d 40 8e 63 3d 
>
> 03 00 66 66 66 3f 40 8e 63 3d 
>
> 04 00 00 00 80 3f 00 00 80 3f 
>
> //POLY L 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 03 00 06 00 00 00 00 04 
>
> 0b 00 00 00 80 3f 00 00 80 3f 
>
> 08 00 00 00 80 3f 00 00 00 00 
>
> 00 00 00 00 00 00 00 00 00 00 
>
> 06 00 00 00 00 00 00 00 80 3f 
>
> //POLY M 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 07 00 00 00 00 04 
>
> 0a 00 00 00 80 3f 00 00 80 3f 
>
> 09 00 66 66 66 3f 40 8e 63 3d 
>
> 08 00 cd cc cc 3d 40 8e 63 3d 
>
> 0b 00 00 00 80 a4 00 00 80 3f 
>
> 
>
> 00 00 00 00 
>
> 
>
> // and finaly 4 vert and 1 polygon for MEDIUM DETAIL LOD 
>
> 
>
> //POLY N 
>
> 00 80 00 00 00 00 00 00 00 00 00 00 00 00 00 00 05 00 08 00 00 00 01 04 
>
> 06 00 00 00 00 00 00 00 80 3f 
>
> 0b 00 00 00 00 00 00 00 00 00 
>
> 0a 00 00 00 80 3f 00 00 00 00 
>
> 04 00 00 00 80 3f 00 00 80 3f 
>
> 
>
> 00 00 00 00 00 00

and sketch to make it clearer (I add labels later). 



[/quote]
## Post #7
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-12T02:45:14+00:00
- Post Title: New 3D file conversion Project

> Reply from Xela
>
> 
However, as you write :
LOD should be pretty easy, I'd be willing to bet you could find locations to begin reads in the header somewhere... If you know how it designates where to begin reading the main model data, you could probably compare that to the rest of the header and look for similarities in other chunks.

I FAIL to see how the game engine and possible the exporter may differentiate and recognise when to use or separate them cleanly?

A loader is a lot less complex than many people think. Essentially it reads the locations of the ends of data streams from the initial file segment. (the header, to use a technical term.) Then, the program simply goes from the beginning of where you tell it to until it reaches the end of the specified stream, which doesn't even have to be the end of the file. In theory, you can encode as much info as you want into the model, you just have to explain to your program how to USE the read data. I realize this isn't the best explanation, but I know it's better than "Trust me." If anyone can come up with a better way to phrase it please do so.
## Post #8
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-11-12T04:00:55+00:00
- Post Title: New 3D file conversion Project

No your explanation is quite fine. I realise that the loader MUST have the info what model to load and when. In situation when LODs are involved that trigger is usally the distance from the observer. And I know from my previous experience that most of the time  this is encoded somewhere in the file usually on  the begining of the file. 

But here I have the entire file, I have 3 LODs, I know where the information about them reside. Yet so far, I failed to see where the distance or that trigger when to display LOD is hiding.
## Post #9
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-13T20:11:18+00:00
- Post Title: New 3D file conversion Project

Aaah-- That's usually within the game executable itself. Only rarely will models swap detail levels at different intervals, it's usually faster to say "If it's this far away use this model." Some simple stuff might have a 'flag' or something that says it doesn't have a LOD (maybe you're dealing with a cube or something) at which it will skip, but this is mostly dependent on the level of performance for the rest of the game.
