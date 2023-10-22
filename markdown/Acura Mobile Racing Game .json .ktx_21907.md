## Post #1
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-03-20T19:41:43+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

Hi! I extracted files from Acura Mobile Racing Game, 3d models in .json, textures in .ktx. I looking converter from json to obj but I didn't find. Textrures can't open using PVRTexTool.
Here is all files of this game: [https://mega.nz/#!GkF12a6b!yOftbmzcS9kl ... yYVhUnSZTU](https://mega.nz/#!GkF12a6b!yOftbmzcS9klQwxQc1mwPP3oTMvrNzN3UyYVhUnSZTU)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-20T22:53:19+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

wheel and arx body:
.



wheel.png (120.2 KiB) Viewed 119 times


Some preparations required: remove "position": [, ']' etc from the json file, replace commas by blanks
then conversion to .obj is simple in case you can code (stream1: input file, .json; stream: output file: .obj):

```
FILE *stream, *stream1 ;
    [...]
    while (fscanf( stream1, "%f", &x) != EOF) {
	fscanf( stream1, "%f %f", &y, &z) ;
	fprintf(stream, "v %f %f %f\n", x*10.0,y*10.0,z*10.0) ;
    }
    [...]
```
(Added automatic created face indices to the obj file.)
Files need to be opened/closed, of course.
## Post #3
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-03-21T13:02:27+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

> Reply from shakotay2 ↑Sat Mar 21, 2020 6:53 am at Sat Mar 21, 2020 6:53 am
>
> 
wheel and arx body:
.
wheel.png
Some preparations required: remove "position": [, ']' etc from the json file, replace commas by blanks
then conversion to .obj is simple in case you can code (stream1: input file, .json; stream: output file: .obj):
Code: Select allfloat x, y, z ;
FILE *stream1, *stream1 ;
    [...]
    while (fscanf( stream1, "%f", &x) != EOF) {
	fscanf( stream1, "%f %f", &y, &z) ;
	fprintf(stream, "v %f %f %f\n", x*10.0,y*10.0,z*10.0) ;
    }
    [...](Added automatic created face indices to the obj file.)
Files need to be opened/closed, of course.

Probably I'm stupid but where I need replace all "," or ['] to blanks and what next? I need past this code?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-21T15:37:52+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

You need to be a coder to understand what to do. (The replacement of commas by blanks has to be done in the .json file.)
## Post #5
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-03-22T04:05:21+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

Maybe this will help:

 delete-bms.zip
(770 Bytes) Downloaded 13 times


It contains three bms scripts for use with Quickbms.
The first "delete-1.bms" script deletes "{.." position ": [ ";
The second script "delete-2.bms" replaces  "," with "white space";
The last script "delete-3.bms" should delete " ].} ", But it is not working, I recommend deleting it manually, from what I saw, it only appears at the end of the file.
When you run the scripts with quickbms and see "the following output file already exists: ..." press "y" and "enter" to replace the file or "r" to rename it automatically.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-22T09:08:03+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

There's some ], and I'd suggest to split the json.
Load it into notepad (whatever), replace all commas by blanks
and save the block up to "uv": [ as vertices.txt.
Then save the the block behind "uv": [ up to  "normal": [ as uvs.txt.
(Be sure not to have any [, ] or  :  in them. Also don't leave the strings "uv" and "normal".)
Copy those .txt files into the folder where json2obj.exe resides and start it.

I've appended a codeblocks project json2obj with a 9kB exe and source code.
.


 json2obj.zip
(80.39 KiB) Downloaded 20 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-22T10:24:10+00:00
- Post Title: Acura Mobile Racing Game .json .ktx

old_nsx.png (118.21 KiB) Viewed 81 times


.
Important:No commas allowed in vertices.txt and uvs.txt. The exe will produces a giga bytes file otherwise!
.
Don't forget to "remove doubles" in blender for example. There's plenty of them.

Try out submeshes and look how the devs built the meshes:

```
{
	DWORD i, sm=0 ;			//

	for (i=1; i< (cnt - 3);i++) {	    
        	if ( (i%2000) ==0) {
            		fprintf( stream, "g sm_%d\n", sm) ; sm++ ;
        	}		
        	fprintf( stream, "f %ld/%ld %ld/%ld %ld/%ld\n", i,i, i+1,i+1, i+2,i+2) ;
		i += 2 ;
	}
}
```
