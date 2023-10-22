## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-30T06:27:07+00:00
- Post Title: Does anyone interested in webgl?

Hi all
Can anyone help me to convert this format ?

Here are some samples.
<link removed due forum rules violation>
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T06:43:09+00:00
- Post Title: Does anyone interested in webgl?

Just open it in a regular text editor. All they have here is the mesh defined in javascript array.

It's a lot easier if you just provide the link to the site cause you use plain HTML5 and javascript for webgl.
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-30T06:57:14+00:00
- Post Title: Does anyone interested in webgl?

Is this the right you are saying?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T07:14:08+00:00
- Post Title: Does anyone interested in webgl?

No that is just jquery and some css.

Just post the link to the site.
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-30T07:20:48+00:00
- Post Title: Does anyone interested in webgl?

Ok, [here](http://www.3dcg-arts.net/)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T07:59:04+00:00
- Post Title: Does anyone interested in webgl?

Oh, I didn't look at the rest of the javascript file lol I just saw the jquery and moved on.
Then again, I don't even want to look at it simply because it's minimized code.

It looks like they used features from MQO and miku miku dance in it.
All of the information required is stored in the array. It's quite a mess really, but straightforward. It even looks like they used an export script from MQO since every material has the name "mqo" somewhere.

Though, I'd rather use a javascript parser to first parse the file...

How did you download from the site? Do I have to log in?
## Post #7
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-30T08:25:11+00:00
- Post Title: Does anyone interested in webgl?

Internet Explorer will not support WebGL, that is not correct
Open In Chrome and you don't need login.
Use a ChromeCacheView when it's finished loading.
It is gzip compressed.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T08:29:13+00:00
- Post Title: Does anyone interested in webgl?

Hmm, for the most part I am kind of lazy to find a library to parser javascript.
If anyone knows any that would make it easier.

On the other hand, I'd probably just take their viewer and write a noesis exporter and then you can load up whatever models you want on the web lol
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T08:46:31+00:00
- Post Title: Does anyone interested in webgl?

Here's the link to the model file

[http://www.3dcg-arts.net/api/model/get/three_format/132](http://www.3dcg-arts.net/api/model/get/three_format/132)
(just change the number at the end to look at a different model)

In chrome you can just hit ctrl+shift+j to open the debugger, go to resources and you should see all the images.

I don't really want to parse it directly though. Since the entire model is stored in a single variable m, and it is pretty much a dictionary in python, if you cut out all the other javascript stuff I can read that in and convert it into a dictionary, then parse it normally.
## Post #10
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-30T09:34:58+00:00
- Post Title: Does anyone interested in webgl?

> Reply from finale00
>
> How should I save the file?
Maybe I can lend a hand.
My English is bad, as you probably understand.
Let me explain with a picture.
Here is a chromecacheview.[http://www.nirsoft.net/utils/chromecacheview.zip](http://www.nirsoft.net/utils/chromecacheview.zip)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T10:07:53+00:00
- Post Title: Does anyone interested in webgl?

I figured out that I should just hit ctrl+s and I got the file lol

EDIT: wow I don't know how they store the faces. Some tri strip?

```
c(E,v[F],y.b,v[J],y,["123","12","2","23"]),c(E,v[J],y.c,v[L],y,["123","23","3","31"]),c(E,v[L],y.a,v[F],y,["123","31","1","12"])):y instanceof THREE.Face4?(F=e(y.a,y.b),J=e(y.b,y.c),L=e(y.c,y.d),I=e(y.d,y.a),c(E,v[F],y.b,v[J],y,["1234","12","2","23"]),c(E,v[J],y.c,v[L],y,["1234","23","3","34"]),c(E,v[L],y.d,v[I],y,["1234","34","4","41"]),c(E,v[I],y.a,v[F],y,["1234","41","1","12"])):console.log("face should be a face!",y);var f=p,D={},Q={},p=function(b,c){void 0===D[b]&&(D[b]=[]);D[b].push(c)},v=function(b,

```


I can't follow it at all lol

It looks like the webgl viewer supports animation as well.

Here's the script I wrote. Just rename the file with ".webgl" extension and remove all of the unnecessary javascript and just have the array there.

Attached with script and sample
[http://www.mediafire.com/?bb5zd6sj1p5crbw](http://www.mediafire.com/?bb5zd6sj1p5crbw)

I am pretty amazed at how quickly they rendered the thing...in javascript!
## Post #12
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-30T11:05:14+00:00
- Post Title: Does anyone interested in webgl?

```
NOESIS_VER		"3.865"
EXCEPTION_CODE		"c0000005"
EXCEPTION_ADDR		"100a1995"
EXCEPTION_EIP		"100a1995"
EXCEPTION_LFL		"F:\132.webgl"
EXCEPTION_LCF		"F:\132.webgl"
ERR_LOG			"Failed to open process."

```

Thanks finale00.
But, 132.webgl failed to open error in Noessis.
What do you think the trouble is?
## Post #13
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-30T17:24:17+00:00
- Post Title: Does anyone interested in webgl?

I thought it was entertaining, not perfect.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-30T18:14:02+00:00
- Post Title: Does anyone interested in webgl?

Ya, it crashes when it tries to draw the faces.
The indices are weird. 

```

```


If you load them as straight triangles, it'll fail.
I can't figure out what the indexing pattern is based on the code snippet I put up there, with the whole ["123","23","3","31"] etc.
## Post #15
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-31T04:40:41+00:00
- Post Title: Does anyone interested in webgl?

You can say that again.
It looks like as triangles.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-31T05:24:25+00:00
- Post Title: Re: Does anyone interested in webgl?

A regular list of triangles didn't work for a lot of the models.
## Post #17
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-04-01T01:35:06+00:00
- Post Title: Re: Does anyone interested in webgl?

Look at the patterns at the start and further in

```
42, 18,19,0, 1  ,0,1,2,    0,1,2,
42, 1,18,0,  1  ,3,0,2,    3,0,2,
42, 8,18,1,  1  ,4,0,3,    4,0,3,
42, 2,8,1,   1  ,5,4,3,    5,4,3,
42, 3,8,2,   1  ,6,4,5,    6,7,5,
42, 3,10,8,  1  ,6,7,4,    6,8,7,
42, 14,15,4, 1  ,8,9,10,   9,10,11,
42, 5,14,4,  1  ,11,8,10,  12,9,11,


42, 1095,1093,980,  1  ,555,541,556,  2463,2465,2458,
42, 1084,1094,1082, 1  ,527,530,531,  2466,2462,2438,
42, 1084,1096,1094, 1  ,527,554,530,  2443,2467,2462,
42, 1094,1096,987,  1  ,530,554,557,  2462,2467,2460,
42, 1096,1084,1097, 1  ,554,527,513,  2467,2468,2469,

```


42 followed by 3 numbers followed by a 1 followed by 3 numbers and 3 more numbers.
Guessing one of the sets of 3 numbers is the triangle list(referencing the vertices), one is the normals?, and one is the UV sets(pairs?)?
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T08:31:37+00:00
- Post Title: Re: Does anyone interested in webgl?

The normals and UV's are stored as separate lists so I guess that would make sense.
It would be nice if the list is consistent, otherwise parsing it would end up being checking each value one at a time...

lol ok I went and parsed it as you said and here's something..



[http://db.tt/6WIjjqPK](http://db.tt/6WIjjqPK)

This one: [http://www.3dcg-arts.net/art/132](http://www.3dcg-arts.net/art/132)
## Post #19
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-01T09:24:27+00:00
- Post Title: Re: Does anyone interested in webgl?

Awesome~
Does your script cover the other sample?
132's texture files here.
[http://www.3dcg-arts.net/s3/motionarts_ ... tc.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_Etc.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... cA.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_EtcA.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... ce.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_Face.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... ir.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_Hair.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... rA.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_HairA.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... ow.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_Low.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... wA.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_LowA.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... rt.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_Skirt.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... tA.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_SkirtA.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... Up.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_Up.png.png)
[http://www.3dcg-arts.net/s3/motionarts_ ... pA.png.png](http://www.3dcg-arts.net/s3/motionarts_content_textures/cd35210a6d6cc50b5d1fa1d0634726409b7f349f_186/high/Mis_UpA.png.png)
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T10:21:27+00:00
- Post Title: Re: Does anyone interested in webgl?

It should.
## Post #21
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-04-01T11:50:41+00:00
- Post Title: Re: Does anyone interested in webgl?

This is a great script! Thanks, finale00.
But, this script does not support all, and obj export is missing UVs.
[http://www.mediafire.com/?phq3ja2hx56l5y5](http://www.mediafire.com/?phq3ja2hx56l5y5)
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T12:19:21+00:00
- Post Title: Re: Does anyone interested in webgl?

I never added materials normals or UV because UV's are per-face and not per-vertex.

If I brute-forced it by creating new vertices it will take too long to process all that data.
## Post #23
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-01T15:04:21+00:00
- Post Title: Re: Does anyone interested in webgl?

I'm not sure what's wrong.
[http://www.3dcg-arts.net/api/model/get/three_format/307](http://www.3dcg-arts.net/api/model/get/three_format/307)
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-01T15:20:08+00:00
- Post Title: Re: Does anyone interested in webgl?

That one has even more indices.

Just look at the 43's and you'll see that there are 13 more values before the next 43.

The ones that start with 42 have only 10 values after.

They might even be quads.

```

```
## Post #25
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-04-11T16:48:29+00:00
- Post Title: Re: Does anyone interested in webgl?

An error has occurred while opening some *.webgl with Noesis.
[http://www.3dcg-arts.net/api/model/get/ ... ormat/1067](http://www.3dcg-arts.net/api/model/get/three_format/1067)
Here is some information that will help you.
[viewtopic.php?p=65628#p65628](http://forum.xentax.com/viewtopic.php?p=65628#p65628)
## Post #26
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-11T17:39:48+00:00
- Post Title: Re: Does anyone interested in webgl?

The file is too big I'm not going to bother going through it and seeing where it messes up.
I pretty much assume they use JSON-like structure to store the model data and convert that to a dictionary in python.
## Post #27
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-04-19T14:34:27+00:00
- Post Title: Re: Does anyone interested in webgl?

[https://github.com/mrdoob/three.js/](https://github.com/mrdoob/three.js/)
Is that site very different from 3dcg-arts?
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-19T15:40:36+00:00
- Post Title: Re: Does anyone interested in webgl?

I don't know. I would assume 3dcg wrote their own parser/viewer as well.

EDIT: nvm LOL it looks like they're using his library, or at least something that looks like it. Could be coincidence though, since minimizers probably spit out the same sort of things...
## Post #29
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-04-24T11:32:14+00:00
- Post Title: Re: Does anyone interested in webgl?

Unfortunately most of the models can't be converted with the script and some of them are really high poly.
Sorry for this stupid question,but is theorically possilble to create a offline opengl viewer form the informations we have and ripp the model with opengl ripper like 3dvia? 
Or we need to know more about the format to create a viewer?
I tried to dump directly from the web viewer in firefox, but the browser crashes when 3dvia starts ripping .
## Post #30
- Username: o0DemonBoy0o
- Rank: veteran
- Number of posts: 106
- Joined date: Tue Apr 03, 2012 1:02 pm
- Post datetime: 2012-04-24T13:52:22+00:00
- Post Title: Re: Does anyone interested in webgl?

how exactly did you get the model to show?
I tried but failed at getting these two
[http://www.3dcg-arts.net/art/1222](http://www.3dcg-arts.net/art/1222)
[http://www.3dcg-arts.net/art/317](http://www.3dcg-arts.net/art/317)
## Post #31
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-05-04T08:25:36+00:00
- Post Title: Re: Does anyone interested in webgl?

> I tried to dump directly from the web viewer in firefox, but the browser crashes when 3dvia starts ripping .

Have you tried another web browser ? like Chrome ? I know that webkit and Geko doesn't use the same render processing method for Webgl....

If even with another Web Browser its doesn't work, let's try this :

[https://addons.mozilla.org/fr/firefox/addon/scrapbook/](https://addons.mozilla.org/fr/firefox/addon/scrapbook/)

Its a very great addon for FF, IT CAN CAPTURE EVERYTHING !!! but can take some time and place (be sure to have at less 4go free on HDD)
## Post #32
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-06-10T11:33:46+00:00
- Post Title: Re: Does anyone interested in webgl?

Hi, I'm bumping this thread because I'm actualy trying to download 3D models from that exact site.
So there are some things I don't understand.

First how do you save the webgl file from the site? Because when I try to import it in noesis it doesn't allow me.
And I can't seem to find anything in the ressource tab.

What should I search for in google cache view?
## Post #33
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-06-10T14:50:51+00:00
- Post Title: Re: Does anyone interested in webgl?

Ok I've found the textures with a webgl device, but that's realy strange, for some reason the texture links wouldn't save in the cache.
Do you happen to know why?

Also the 3D models are saved elsewhere, there is absolutely no way to capture them like if it was a normal 3D renderer.


edit : sorry, I didn't read all the details.
It seems the script doesn't import everything, and that noone gives a crap about it.

So there is absolutely no way to rip the models.
## Post #34
- Username: Motumoyo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 12, 2012 9:47 am
- Post datetime: 2012-06-12T04:50:34+00:00
- Post Title: Re: Does anyone interested in webgl?

I can not figure out what I put the index of the code fragment mode.
## Post #35
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-06-14T10:20:14+00:00
- Post Title: Re: Does anyone interested in webgl?

> Reply from zaykho
>
> I tried to dump directly from the web viewer in firefox, but the browser crashes when 3dvia starts ripping .


Have you tried another web browser ? like Chrome ? I know that webkit and Geko doesn't use the same render processing method for Webgl....

If even with another Web Browser its doesn't work, let's try this :

https://addons.mozilla.org/fr/firefox/addon/scrapbook/

Its a very great addon for FF, IT CAN CAPTURE EVERYTHING !!! but can take some time and place (be sure to have at less 4go free on HDD)

I know it, its a great addon for firefox but i think it's useless in this case because even if u ripp all that site offline, then u need firefox to see the models. I tried with all browser that support webgl format but i didn't managed to ripp anything. Obviulsy the textures are quite easy to ripp, but nothing else at the moment.
## Post #36
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-14T10:26:16+00:00
- Post Title: Re: Does anyone interested in webgl?

> Reply from Vashey
>
> Ok I've found the textures with a webgl device, but that's realy strange, for some reason the texture links wouldn't save in the cache.
Do you happen to know why?

Also the 3D models are saved elsewhere, there is absolutely no way to capture them like if it was a normal 3D renderer.


edit : sorry, I didn't read all the details.
It seems the script doesn't import everything, and that noone gives a crap about it.

So there is absolutely no way to rip the models.

The 3D models are stored in a text file that contains a huge json-like array that defines all of the vertices, normals, UV's, weights and bones (if animated), materials, etc for a single model.

I've already given links to the source file containing the model data, unless they changed how the structure of the website.

[http://www.3dcg-arts.net/api/model/get/three_format/132](http://www.3dcg-arts.net/api/model/get/three_format/132)

I don't see much point in ripping them.
## Post #37
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-06-20T19:43:52+00:00
- Post Title: Re: Does anyone interested in webgl?

> I know it, its a great addon for firefox but i think it's useless in this case because even if u ripp all that site offline, then u need firefox to see the models. I tried with all browser that support webgl format but i didn't managed to ripp anything. Obviulsy the textures are quite easy to ripp, but nothing else at the moment.

No, No, No, you don't see the point.

The goal is:

1 - rip everything from the source into a folder 

2 - find the folder, and look what is the format used, .txt ? .json ? etc....

3 - After find the file, open him with a notepad or bloc-note, and see the header, what is the detailed format used ? json-2.15 ?

4 - Then search a converter, like this:

[http://www.softpedia.com/get/Others/Mis ... rter.shtml](http://www.softpedia.com/get/Others/Miscellaneous/OBJ-and-JSON-Converter.shtml)
## Post #38
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-11-05T01:52:14+00:00
- Post Title: Re: Does anyone interested in webgl?

> The 3D models are stored in a text file that contains a huge json-like array that defines all of the vertices, normals, UV's, weights and bones (if animated), materials, etc for a single model.
>
> 
>
> I've already given links to the source file containing the model data, unless they changed how the structure of the website.
>
> 
>
> http://www.3dcg-arts.net/api/model/get/three_format/132
>
> 
>
> I don't see much point in ripping them.



I have my reasons to rip some of them.
I understand what you mean, but the page to the source code concerns only one model (that I don't care about) and this source code, what am I supposed to do with?
Because I already tried to import the .webgl on noesis, it doesn't work, makes noesis crash (I obviously used your script).
## Post #39
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-14T16:41:55+00:00
- Post Title: Re: Does anyone interested in webgl?

[viewtopic.php?f=16&t=9978](http://forum.xentax.com/viewtopic.php?f=16&t=9978)
here what i found, hope finale could look into this
all model are presented in a three.js format

[model sample](http://p3d.in/C4roc/shadeless)
## Post #40
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2014-04-02T15:44:28+00:00
- Post Title: Re: Does anyone interested in webgl?

I hate to resurrect an old thread, but I hacked out a quick Ruby script for converting the 3dcg-arts models into a standard .obj file.

It's not perfect, but seems to work pretty well, at least for the older format files. You have to manually add the correct images to the materials, but the UVs and material entries should get created correctly. I haven't found how to find the image name to link to each material yet, but I assign different random colors to each material to make it easier to see which part of the model uses which material.

Use of the script is a little convoluted. From the developer console, save the javascript file with all the vertex data for the model (usually the filename is the model number), then run this script on that file. It's a Ruby script, so call it from the command line, passing the filepath to the saved javascript file as an argument. It will batch multiple if you pass multiple file paths in at once.

EDIT: I should've used a larger test sample before posting. This doesn't work for all files, so caveat emptor. I'll post a fixed version when I figure out why some files work and some don't.

```
require 'rubygems'
require 'json'

def write_verts(vertices, file)
	puts "Writing Vertices…"

	vertex_counter = 0
	vertices.each do |one_vertex|
		if vertex_counter % 3 == 0
			file.write("v ")
		end
		
		file.write("#{one_vertex.to_s} ")
		vertex_counter = vertex_counter + 1
		
		if vertex_counter %3 == 0
			file.write("\n")
		end
	end
	puts "\tVertices written: #{vertices.length / 3}"
end

def write_uvs(uvs, file)
	puts "Writing UVs…"
	vertex_counter = 0
	uvs.each do |one_uv|
		if vertex_counter % 2 == 0
			file.write("vt ")
		end
		file.write("#{one_uv.to_s} ")
		vertex_counter = vertex_counter + 1
		if vertex_counter % 2 == 0
			file.write("\n")
		end
	end
	puts "\tUVs written:#{uvs.length / 2}\n"
end
def write_normals(normals, file)
	puts "Writing Normals…"

	vertex_counter = 0
	normals.each do |one_normal|
		if vertex_counter % 3 == 0
			file.write("vn ")
		end
		
		file.write("#{one_normal.to_s} ")
		vertex_counter = vertex_counter + 1
		
		if vertex_counter %3 == 0
			file.write("\n")
		end
	end
	puts "\tNormals written:#{normals.length / 3}\n"
end

def write_triangle(faces, offset, file)
	x = faces[offset]
	y = faces[offset+1]
	z = faces[offset+2]

	file.write("f #{x}// #{y}// #{z}//\n")
end
def write_quad(faces, offset, file)
	x = faces[offset]
	y = faces[offset+1]
	z = faces[offset+2]
	w = faces[offset+3]
	file.write("f #{x}// #{y}// #{z}// #{w}\n")
end
def write_faces(vertex, faces_string, file, materials_array)
	puts "Writing Faces…"
	
	
	faces = faces_string.scan(/(42,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+)|(43,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+,\d+)/)
	x = y = z = w = 0
	face_count = 0
	
	material_count = 1
	last_material_index = -1
	
	faces.each do |one_face|
		face_parts = one_face.compact[0].split(",")
		
		if face_parts[0] = 42
			material_index = face_parts[4]
			
			if (material_index != last_material_index)
				file.write("usemtl texture#{material_index}\n")
				materials_array.push("texture#{material_index}") unless materials_array.include?("texture#{material_index}")
				last_material_index = material_index
				
			end
			x = face_parts[1].to_i + 1
			y = face_parts[2].to_i + 1
			z = face_parts[3].to_i + 1
			xt = face_parts[5].to_i + 1
			yt = face_parts[6].to_i + 1 
			zt = face_parts[7].to_i + 1
			xn = face_parts[8].to_i + 1
			yn = face_parts[9].to_i + 1
			zn = face_parts[10].to_i + 1
			file.write("f #{x}/#{xt}/ #{y}/#{yt}/ #{z}/#{zt}/\n")
		elsif face_parts[0] = 43
			material_index = face_parts[5]
			if (material_index != last_material_index)
				file.write("usemtl texture#{material_index}\n")
				materials_array.push("texture#{material_index}") unless materials_array.include?("texture#{material_index}")
				last_material_index = material_index
				
			end
			x = face_parts[1].to_i +1
			y = face_parts[2].to_i +1
			z = face_parts[3].to_i +1
			w = face_parts[4].to_i +1
			xt = face_parts[6].to_i +1
			yt = face_parts[7].to_i +1
			zt = face_parts[8].to_i +1
			wt = face_parts[9].to_i +1
			xn = face_parts[10].to_i +1
			yn = face_parts[11].to_i +1
			zn = face_parts[12].to_i +1
			wn = face_parts[13].to_i +1
			file.write("f #{x}/#{xt}/ #{y}/#{yt}/ #{z}/#{zt}/ #{w}/#{wt}/\n")
		end
		face_count = face_count + 1
	end
	puts "\tFaces written: #{face_count.to_s}"
end

ARGV.each do|a|
	input_file_path = a
	puts "Processing file: #{a}"
	json_file = File.open(input_file_path, "r")
	json_text = json_file.read
	json_file.close

	start_token = "var m = "
	end_token = "]]};"
	data_start_index = json_text.index(start_token) + start_token.length
	data_end_index = json_text.index(end_token) + end_token.length

	json_text = json_text[data_start_index, data_end_index - data_start_index - 1]

	json_data = JSON.parse(json_text)

	vertices = json_data["vertices"][0]
	faces = json_data["faces"]
	uvs = json_data["uvs"][0][0]
	normals = json_data["normals"][0]
	materials = json_data["materials"][0]

	puts "Raw Vertices: #{vertices.length}"
	puts "Raw Faces:    #{faces.length}"
	puts "Raw UVs:      #{uvs.length}"

	mtl_filepath = "#{input_file_path}.mtl"
	mtl_localfile = mtl_filepath.split(File::SEPARATOR)[-1]
	output_file_path = "#{input_file_path}.obj"

	materials_array = []
	File.open(output_file_path, 'w') do |file|

		file.write("mtllib #{mtl_localfile}\n")
		write_verts(vertices, file)
		write_uvs(uvs, file)
		
		write_faces(vertices, faces.join(","), file, materials_array)
	end

	File.open(mtl_filepath, 'w') do |file|
		materials_array.each do |one_material|
			file.write("newmtl #{one_material}\n")
			file.write("Kd #{rand} #{rand} #{rand}\n");
			file.write("Ka 0.600 0.600 0.600\n");
			file.write("Ks 0.000 0.000 0.000\n");
			file.write("Tr 1.0\n");
			file.write("#{one_material}.png\n");
		end
	end
end

```
## Post #41
- Username: Seventyseven
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 13, 2007 5:28 pm
- Post datetime: 2014-06-21T12:28:59+00:00
- Post Title: Re: Does anyone interested in webgl?

^ There are two more face types.

40 - triangle without the material index I assume since followed by 9 numbers

41 - quad without the material index I assume since followed by 12 numbers

Edit:

Also there can be more than one face array and I assume vertex and uvs arrays.

Seems one face array can hold about 262 144 numbers and then another list is needed. 
The arrays split at the 262 144 th entry even if that is the middle of a face. 
The rest of that face data is start of next array.
## Post #42
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2015-07-20T02:58:21+00:00
- Post Title: Re: Does anyone interested in webgl?

any fix for this
[noname.jpg](https://xentaxbackup.github.io/file/9436_noname.jpg)
