## Post #1
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-18T12:22:21+00:00
- Post Title: varint decoding

Hi

How decode this files?. They are from google cache.

I use this scripts but with no luck.

[https://code.google.com/r/avenka-co1/so ... e86c47ec4b](https://code.google.com/r/avenka-co1/source/browse/src/python/varint.py?spec=svn2b97a552eb2c39cfe62b62dbc303b6e86c47ec4b&name=series34&r=2b97a552eb2c39cfe62b62dbc303b6e86c47ec4b)

[https://github.com/dowski/misc/blob/master/varints.py](https://github.com/dowski/misc/blob/master/varints.py)

files: [http://www.mediafire.com/download/m29kk ... roblem.zip](http://www.mediafire.com/download/m29kkod19d54ykt/varinproblem.zip)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2017-02-23T18:31:13+00:00
- Post Title: varint decoding

Here is a trick how to decode varint.
I needed varint decoding to get models from Sketchfab.
So here is a way:
1.select Sketchfab site with your favorite model (best lowpoly) 
2.save this site as complete html (it creates html file and folder with the same name as html file)
3.close web browser (best use mozilla firefox)
4.go to folder with saved site and doubleclick on html
5.change web browser mode to offline.
6.open web browser console
6.from saved html folder open file "viewer-c077fc97f229ec2c2f73.js" in notaped++
In offline mode and with "viewer-c077fc97f229ec2c2f73.js" you can control how translate data from function to function


7.in js file find something like that

```
       //data 't','e','i' on in
        console.log('t='+t)
        console.log('e='+e)
        console.log('i='+i)
	"use strict";
	var 
	n=i(1205),
	r=n.osg,
	a=function(t,e,i)
		{
		for(var n=new r[i](e),a=0,s=0;a!==e;){var o=0,u=0;do o|=(127&t[s])<<u,u+=7;while(0!==(128&t[s++]));n[a++]=o}if("U"!==i[0])
			for(var l=0;l<e;++l)
				{
				var h=n[l];n[l]=h>>1^-(1&h)
				}
			console.log(n)	
                       //or write console.log('n='+n)
                       //data "n" on out
			return n};t.exports=a},
```


8.in js write  command "console.log(...)" you can see data in console 
 - example in code
9.refresh web browser and see what happen in console.
10.this method need time and patience.

deleted:2019-03-26
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-24T03:51:36+00:00
- Post Title: varint decoding

well, nice, as always  

btw there's many "doubles" in the Uint16Arrays:



varint.JPG (30.44 KiB) Viewed 1546 times


These are the face indices? Do I miss something?
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2017-02-24T06:21:35+00:00
- Post Title: varint decoding

Bytes are still encoded after unvarint.
It needs undelta, unimplicit and others use function to decode to indices.
But vertices need indices to decode and function like unpredict, unquantize.
All depend too if there are triangle_strip or triangles.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-28T11:17:59+00:00
- Post Title: varint decoding

> Reply from Szkaradek123
>
> Bytes are still encoded after unvarint.
It needs undelta, unimplicit and others use function to decode to indices.well, ok, thanks (sry, forgot this thread for a while).
I was a little bit confused because you wrote in your previous post (after that browser js action ):

> Reply from Szkaradek123
>
> Here is a finally script to import decoded models from Sketchfab.As you may know I've extracted an orc some months ago using simple RAM logging ([viewtopic.php?f=16&t=10668&p=117317&hil ... ng#p117317](http://forum.xentax.com/viewtopic.php?f=16&t=10668&p=117317&hilit=+digging#p117317)).
The problem was to find the (decoded!) face indices in tons of data.
(not sure whether this approach would be successful 11 months later  )
## Post #6
- Username: feber13
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 28, 2017 4:54 am
- Post datetime: 2017-07-01T21:00:42+00:00
- Post Title: varint decoding

> Reply from Szkaradek123
>
> Here is a trick how to decode varint.
I needed varint decoding to get models from Sketchfab.
So here is a way:
1.select Sketchfab site with your favorite model (best lowpoly) 
2.save this site as complete html (it creates html file and folder with the same name as html file)
3.close web browser (best use mozilla firefox)
4.go to folder with saved site and doubleclick on html
5.change web browser mode to offline.
6.open web browser console
6.from saved html folder open file "viewer-c077fc97f229ec2c2f73.js" in notaped++
In offline mode and with "viewer-c077fc97f229ec2c2f73.js" you can control how translate data from function to function


7.in js file find something like that
Code: Select allfunction(t,e,i){
       //data 't','e','i' on in
        console.log('t='+t)
        console.log('e='+e)
        console.log('i='+i)
	"use strict";
	var 
	n=i(1205),
	r=n.osg,
	a=function(t,e,i)
		{
		for(var n=new r[i](e),a=0,s=0;a!==e;){var o=0,u=0;do o|=(127&t[s])<<u,u+=7;while(0!==(128&t[s++]));n[a++]=o}if("U"!==i[0])
			for(var l=0;l<e;++l)
				{
				var h=n[l];n[l]=h>>1^-(1&h)
				}
			console.log(n)	
                       //or write console.log('n='+n)
                       //data "n" on out
			return n};t.exports=a},

8.in js write  command "console.log(...)" you can see data in console 
 - example in code
9.refresh web browser and see what happen in console.
10.this method need time and patience.

Here is a finally script to import decoded models from Sketchfab.
Install Blender249 and Python266, doubleclick Blender249.blend, in Text Window press alt+p and select file.osgjs.
To import model you need model_file.bin and file.osgjs in the same folder.
To skip bindposing change line BINDPOSE=1 to BINDPOSE=0

Hello master, I wanted to know if you can make a video tutorial about maybe I got confused in some steps and it would be great help try the blender script produces an error or maybe I am very clumsy
## Post #7
- Username: M0fD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 02, 2014 5:05 am
- Post datetime: 2019-03-13T17:49:03+00:00
- Post Title: varint decoding

Aaaand a second method but who keeps the animation, love it !
## Post #8
- Username: tpcrew
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Jan 08, 2012 7:36 pm
- Post datetime: 2019-03-14T08:29:44+00:00
- Post Title: varint decoding

> Reply from Szkaradek123 ↑Fri Feb 24, 2017 2:31 am at Fri Feb 24, 2017 2:31 am
>
> 
edit:2019-02-18

here is a script which can not use to view textured models - for Blender version 2.49:
password:15 in polish language with english letters
How don't use:

3.clear chrome cache ctrl+shift+del - clear only cache

5.with "chrome cache view"  export needed files: html, model, osgjs, and images to ONE folder

It'd be great if you could explain this a little better. Thanks.
## Post #9
- Username: RetroGEO
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 19, 2019 4:35 am
- Post datetime: 2019-03-18T21:15:51+00:00
- Post Title: varint decoding

Keeps giving me illegal character errors clicking the html file with the model name
## Post #10
- Username: slipknot25
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 19, 2019 2:06 pm
- Post datetime: 2019-03-21T16:08:29+00:00
- Post Title: varint decoding

it extract animation as .action file , how i can unpack .action file or how to use it ?
