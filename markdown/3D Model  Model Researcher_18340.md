## Post #1
- Username: Zenshin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 11, 2012 1:36 am
- Post datetime: 2018-07-08T18:43:01+00:00
- Post Title: 3D Model / Model Researcher?

Hi,


i started along time ago to extract a model from an unknown fileformat.
I only got the pointcloud.
Can someone help me? I can't find the faces   

That is my current progress:

I took: 
Offset:386000
Count:55367
Byte Order: little endian

Edit: I found now the faces and some others offsets and counts by reading out the header...

offset:208		//seems to be skyboxdata -- not important yet
Count:3014
____________________________
offset:29508		// programmable, maybe aidata - not important
count:40797
____________________________
Offset: 386000		//vertices
Count:  55367		
____________________________
offset: 2323268	//Faces, strangely not all?!?
count:     40797
____________________________
offset:1050404
____________________________
offset;15378308
Count:15860
____________________________
offset:15385136
____________________________
offset:15385664
____________________________
offset:15449280
____________________________
offfset:18142924
Count:42616960
____________________________
offset uvs maybe?:69601244	 //pretty sure UVS
Count uvs maybe?:8415736
____________________________
offset:60759884(dec)		 //think kind of lightmap
count:8248400
____________________________
Count of FE:592960
offset of FE:69008284		 //not Faces
____________________________
offset:17630400

I tried a whole day but can't get the right padding for the faces... If someone else might have a idea... be free to comment   

Thats the Model:
[https://ufile.io/zy0lv](https://ufile.io/zy0lv)
