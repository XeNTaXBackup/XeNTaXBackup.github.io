## Post #1
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-12T14:56:22+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

Hey guys, i like this forum it helped me already alot but i got a few things where i got stuck.
I want to write a script (MAXscript, from 3dsmax 9) to import a model from a game. 
I can see the face/vertex sections when i open the model in a HEX-Editor but i dont know how should i continue in the script.
Are there any tutorials to write such a script? I have used the search and i found a tutorial to write a script to reverse a model but it didnt help me much.
I take every help i get, Tutorials/Videos/ or anything else
Thank you
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-12T14:58:48+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

Where exactly are you stuck? You don't know the syntax? You don't know how to read the data? Not sure how to store them? Not sure how to pass the data to MAX?
## Post #3
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-12T17:11:41+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

> Reply from finale00
>
> Where exactly are you stuck? You don't know the syntax? You don't know how to read the data? Not sure how to store them? Not sure how to pass the data to MAX?

the syntax is quite okay, the MAXscript manual helps me, but the loop maybe for-loop? makes me stuck there, and im not sure to store or how to get the data (model) displayed in 3dsmax
i was looking for tutorials also outside of youtube but i havent found anything, i had a 6 part big tutorial to write a script but the user deleted the videos
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-09-12T17:34:29+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

mariokart64n made some 3dsMax scripting videos but he made them private for some reason.   

[viewtopic.php?f=16&t=5644](http://forum.xentax.com/viewtopic.php?f=16&t=5644)
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-12T18:28:59+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

there are many examples in the manual on for loops.

to create the mesh object from the vertex/face index data you need to store them in an array before you can create the 3ds 'mesh' object:

```
for i = 1 to vertCount do
(
	append arr_v [readfloat(f), readfloat(f), readfloat(f)]
)

```

note face indices need to start from 1 (not 0)

you can create a mesh like so:

```

```
## Post #6
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-12T18:31:40+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

> Reply from AceWell
>
> mariokart64n made some 3dsMax scripting videos but he made them private for some reason.   

viewtopic.php?f=16&t=5644

the bad thing is, i cant see them, even if i login with my youtube account.
## Post #7
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-12T18:34:50+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

> Reply from WRS
>
> there are many examples in the manual on for loops.

to create the mesh object from the vertex/face index data you need to store them in an array before you can create the 3ds 'mesh' object:
Code: Select allarr_v = #()
for i = 1 to vertCount do
(
	append arr_v [readfloat(f), readfloat(f), readfloat(f)]
)

note face indices need to start from 1 (not 0)

you can create a mesh like so:
Code: Select allmesh vertices:arr_v faces:arr_f

okay this start looking good, but for example the section for face indices or vertices start at offset 0x26CA, how do i tell the script to skip the other things and start from there?
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-12T18:38:20+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

> Reply from Valerian
>
> WRS wrote:there are many examples in the manual on for loops.

to create the mesh object from the vertex/face index data you need to store them in an array before you can create the 3ds 'mesh' object:
Code: Select allarr_v = #()
for i = 1 to vertCount do
(
	append arr_v [readfloat(f), readfloat(f), readfloat(f)]
)

note face indices need to start from 1 (not 0)

you can create a mesh like so:
Code: Select allmesh vertices:arr_v faces:arr_f


okay this start looking good, but for example the section for face indices or vertices start at offset 0x26CA, how do i tell the script to skip the other things and start from there?

you might be familiar with fseek from other languages - the 3ds syntax is:

```
fseek f 0x26CA #seek_set
```


(to skip data, use #seek_cur)
## Post #9
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-12T18:48:12+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

> Reply from WRS
>
> Valerian wrote:WRS wrote:there are many examples in the manual on for loops.

to create the mesh object from the vertex/face index data you need to store them in an array before you can create the 3ds 'mesh' object:
Code: Select allarr_v = #()
for i = 1 to vertCount do
(
	append arr_v [readfloat(f), readfloat(f), readfloat(f)]
)

note face indices need to start from 1 (not 0)

you can create a mesh like so:
Code: Select allmesh vertices:arr_v faces:arr_f


okay this start looking good, but for example the section for face indices or vertices start at offset 0x26CA, how do i tell the script to skip the other things and start from there?

you might be familiar with fseek from other languages - the 3ds syntax is:
Code: Select allfseek f 0x26CA #seek_set

(to skip data, use #seek_cur)

thank you so much! Now i can try more  
when i need more help i will post it here but first i want to try it
## Post #10
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-19T06:38:05+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

so guys, my script looks like this:

```

vx = float
vy = float
vz = float

i = float
arr_v = #()
for i = 1 to 177 do
(
	vx = readfloat f
	vy = readfloat f
	vz = readfloat f
	append (arr_v) [readfloat(f), readfloat(f), readfloat(f)]
	print arr_v 

)
	mesh vertices:arr_v faces:arr_f

```


when i want to execute it i get the error:
-- Error occurred in i loop; filename: C:\Users\Admin\Desktop\test.ms; position: 329
--  Frame:
--   i: 1
-- Error occurred during fileIn in <File:C:\Users\Admin\Desktop\test.ms>
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Float <<

what am i doing wrong?
also whats this:
for i = 1 to "vertCount" do
what is the vertCount or any explanation?
## Post #11
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-09-19T08:54:57+00:00
- Post Title: [Need Advice] Looking for help (Scripts)

> Reply from Valerian
>
> so guys, my script looks like this:
Code: Select allfseek f 0x26CA #seek_cur

vx = float
vy = float
vz = float

i = float
arr_v = #()
for i = 1 to 177 do
(
	vx = readfloat f
	vy = readfloat f
	vz = readfloat f
	append (arr_v) [readfloat(f), readfloat(f), readfloat(f)]
	print arr_v 

)
	mesh vertices:arr_v faces:arr_f


when i want to execute it i get the error:
-- Error occurred in i loop; filename: C:\Users\Admin\Desktop\test.ms; position: 329
--  Frame:
--   i: 1
-- Error occurred during fileIn in <File:C:\Users\Admin\Desktop\test.ms>
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Float <<

what am i doing wrong?
also whats this:
for i = 1 to "vertCount" do
what is the vertCount or any explanation?

Your variables should be defined as follows

```
vy = 0
vz = 0
i = 0

```


Generally you can find the number of vertices somewhere else in the file.  Because not every model is created equal "vertCount" is a variable so that your script can work with more than one model.  If you can't pinpoint the number of vertices in the file, but you know that the number you are using is correct, then it's fine to hard-code that for testing your script.

The reading of the vertices I would do in this fashion

```
(
     vx = readFloat f
     vy = readFloat f
     vz = readFloat f

     arr_v[i] = (point3 vx vy vz)
)

```


From there move on to reading your faces in a similar manor.
