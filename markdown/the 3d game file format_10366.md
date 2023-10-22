## Post #1
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-04-26T10:37:04+00:00
- Post Title: the 3d game file format

12.jpg (147.44 KiB) Viewed 110 times



hey,i have extract a game file from a little game, the green part is the vertices ,the red maybe the face index, but the face index maybe is wrong,could any one help me? thank you veyry much

here is the maxscript and the modle file


fname = "D:\game\face.obj"
f = fopen fname "rb"
Vert_array = #()
Face_array = #()

fseek f 0xB0 #seek_set

a = 0xB0

for i = 1 to 9 do(	
vx = readfloat f
vy = readfloat f
vz = readfloat f	
append Vert_array[vx,vy,vz]

 a = a+48

fseek f a #seek_set	 

)

append Face_array [8,8,7]

msh = mesh vertices:Vert_array faces:Face_array
## Post #2
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-04-26T10:38:47+00:00
- Post Title: the 3d game file format

sorry here is the modle file


 face.rar
(218 Bytes) Downloaded 30 times
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-26T14:06:15+00:00
- Post Title: the 3d game file format

what is the name of the game?
## Post #4
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-04-26T16:46:33+00:00
- Post Title: the 3d game file format

this is the unity3d phone game,the format is all the same
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-04-27T00:05:38+00:00
- Post Title: the 3d game file format

Still needs a name though.
## Post #6
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-04-27T01:26:33+00:00
- Post Title: the 3d game file format

the game like TempleRun 2 is made by the unity3d engine,you can download it from googleplay.
## Post #7
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-04-27T01:35:13+00:00
- Post Title: the 3d game file format

ok,here is the gamedownload,
[http://pan.baidu.com/share/link?shareid ... 2402256101](http://pan.baidu.com/share/link?shareid=219999&uk=2402256101)

use the winrar extract it ,and find the assets then, you can use the UnityAssetsExplorer get the file,
## Post #8
- Username: glcat
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Feb 15, 2012 12:31 pm
- Post datetime: 2013-04-27T02:04:27+00:00
- Post Title: the 3d game file format

test.jpg (148.57 KiB) Viewed 66 times


now I get some  information ， but the face index is wrong...
