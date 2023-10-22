## Post #1
- Username: chuso41
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 19, 2022 1:46 am
- Post datetime: 2022-03-07T20:36:59+00:00
- Post Title: Harry Potter and the Chamber of Secrets PS2 Models

Hi. I've trying to figure it out how to rip the models for this game but Im struggling

I can't find the faces
I can't find the uvs


I managed to write a console program in c# to extract the vertex [https://github.com/chusothe41/HPCSPS2DA ... master/HPM](https://github.com/chusothe41/HPCSPS2DATA/tree/master/HPM)
I also created a txt to anotate my finds:

```
HEADER:
	4	signature	same48 50 4D 4C		HPML

	2	???			same 1D 01
	2	???

	2	???
	2	???		#of objects inside?

	4	???

	2	???
	2	???			same 00 60

	4	???			same 00 00 00 00

Node:
	Header:
		2	???			same 01 80
		1	#vertex (count)					 
		1	???			same 68
	Vertex:
		Amount:
			N
		End:
			4	???		00 00 00 20
			4	???		3f 3f 3f 3f
	

End:
16 ??? 			igual 00 00 00 00 01 00 00 00 00 00 00 00 00 00 00 00

```


I also attach some files:
A flag: [https://drive.google.com/file/d/1OZT97t ... sp=sharing](https://drive.google.com/file/d/1OZT97t5fUNEurTFfG6vfs-cgF0WSLw_c/view?usp=sharing)
A character: [https://drive.google.com/file/d/1KWZN68 ... sp=sharing](https://drive.google.com/file/d/1KWZN68avbC3bvnMbd0OLdmlWp4XCreVn/view?usp=sharing)
A chest: [https://drive.google.com/file/d/1fulmsi ... sp=sharing](https://drive.google.com/file/d/1fulmsiTEcorXTA-yF14hFbxX443jON2J/view?usp=sharing)
Some file with comes with every .hpm (just in case): [https://drive.google.com/file/d/19T2fsz ... sp=sharing](https://drive.google.com/file/d/19T2fszeNnXOccW0hqLJXZSAnzvm2PaiL/view?usp=sharing)

If anybody could help me i'll be much appreciated

Thank u
## Post #2
- Username: chuso41
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 19, 2022 1:46 am
- Post datetime: 2022-03-08T18:16:52+00:00
- Post Title: Harry Potter and the Chamber of Secrets PS2 Models

Ok i just realice that this models are ps2 format with VIF on it, so i have to research more about it.

Many thanks I'll be posting the progress and updating the repository
## Post #3
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-03-14T01:52:01+00:00
- Post Title: Harry Potter and the Chamber of Secrets PS2 Models

Maybe this helps:



aa_con_none_chestalohomora.hpm.png (36.94 KiB) Viewed 95 times



The faces were generated automatically, you must do some treatment with the faces, to see the UVs use WordUV.
There is also a [script](https://github.com/leeao/Noesis-Plugins/blob/master/Model/fmt_HarryPotter_CS_PS2_hpm_tpk_ssh.py) for noesis made by Allen that opens these files.
## Post #4
- Username: chuso41
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 19, 2022 1:46 am
- Post datetime: 2022-03-14T16:04:49+00:00
- Post Title: Harry Potter and the Chamber of Secrets PS2 Models

Many thanks, I didn't know there was a noeses plugin for that.

Anyway i can still working on my program just to understand how vif works the script gives me some really good knoledge
