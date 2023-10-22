## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T05:17:50+00:00
- Post Title: Vertex colors

What's the point of vertex colors? I know they have an NP-complete problem for vertex coloring, but other than that...
How are they used?
Are there any practical uses that one should be aware of?
## Post #2
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2012-02-06T05:37:19+00:00
- Post Title: Vertex colors

PSX games use vertex colouring to improve the detail of models while keeping the load times and possibly disk space low. See the Crash Bandicoot series, for example.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-02-06T21:25:05+00:00
- Post Title: Vertex colors

its not uncommon to see current gen games use vc, it does inpack shading but I'm no expert.
## Post #4
- Username: huckleberrypie
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-07T00:41:56+00:00
- Post Title: Vertex colors

They're cheaper than lightmaps or other forms of texture-based baked lighting. (fill-wise, and on some hardware lightmaps can only be done in multiple passes, or not at all due to insufficient hardware blending options) That's the primary benefit, and the reason tons of PSP games still use vertex colors for baked in lighting. Most current-gen games have switched to textures or pixel/fragment shader variables (shader variables are often ideal because custom colorization is often sufficient to have on a per-mesh/draw basis), although I do still come across people using vertex colors occasionally.
## Post #5
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-07T05:41:23+00:00
- Post Title: Vertex colors

I think I explained all this in the guide, didn't I?

[http://wiki.xentax.com/index.php/3D_Mod ... rtex_color](http://wiki.xentax.com/index.php/3D_Model_Guide#Vertex_color)

> Vertex colors are color values assigned to vertices. It's not hard to imagine a colored dot in 3d space, but what happens when vertices connect and form lines or triangles? It would be practically useless to have colored dots on your mesh. Luckily, that's not how they are rendered by OpenGL or DirectX when connected. The colors of the neighboring vertices are interpolated over the surface, so you get a nice gradient. This makes vertex colors very useful for things like skydomes because they take up far less memory than gradient textures. Vertex colors are also used on map models to simulate shadows. Some old games use vertex colors on characters instead of textures (usually only the face of the character will use a texture image).
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-07T06:09:56+00:00
- Post Title: Vertex colors

I didn't notice the vertex color section lol
## Post #7
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-07T07:52:53+00:00
- Post Title: Vertex colors

> Reply from MrAdults
>
> They're cheaper than lightmaps or other forms of texture-based baked lighting. (fill-wise, and on some hardware lightmaps can only be done in multiple passes, or not at all due to insufficient hardware blending options) That's the primary benefit, and the reason tons of PSP games still use vertex colors for baked in lighting. Most current-gen games have switched to textures or pixel/fragment shader variables (shader variables are often ideal because custom colorization is often sufficient to have on a per-mesh/draw basis), although I do still come across people using vertex colors occasionally.

L.A. Noire still uses vertex lighting for vehicle headlights and distant streetlamps. The III-era Grand Theft Auto games also made extensive use of this, especially since I haven't seen any lightmaps (ala-Source or LS3D/Mafia) being used for simulating shadows on outdoor areas in those games, just coloured verts and nothing else. Which probably explains why buildings don't seem to cast any noticeable shadows.
## Post #8
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-07T11:31:12+00:00
- Post Title: Vertex colors

Vertex lights in OpenGL and DirectX color the vertices which they influence, but they are realtime lights, in other words they manipulate the vertex colors in real time, so they aren't stored in the 3d files. We shouldn't care about them.
## Post #9
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-07T22:23:52+00:00
- Post Title: Vertex colors

It seems a bit silly to be writing new explanations of what common rendering components are, when you can instead pick and pull from pages with rather complete information on their use and behavior. Like official OpenGL/D3D implementation documentation from any given vendor. Microsoft docs are usually a good source. Some problems with the description I see quoted on vertex colors here:

1) OpenGL and Direct3D are not required to interpolate vertex colors. In fixed function OpenGL this is dictated by glShadeModel (this affects interpolation of vertex colors even when lighting is disabled), ShadeModel when writing in Cg, and the list goes on. Most graphics API's have some means of dictating interpolation on a per-component basis, although the means may and often will vary based both on the component and the API. Flat shading is often used (in older games particularly) where more than 1 color per face was not needed or desired, yet in many of these cases colors were still baked into vertex lists and occasionally interleaved as we often see in data sets meant for modern graphics pipelines. This was particularly common in custom software renderers.

2) Way too subjective. It actually wouldn't be practically useless to have colored dots on your mesh (and many people use sprites or even rasterized points in conjunction with vertex colors for this purpose), nor is flat shading useless for many reasons. You should explain what vertex colors are, then explain how they're actually treated by common graphics API's like OpenGL and Direct3D, keeping in mind their conditional uses and not just the common ones that you're used to seeing.

3) Explaining how vertex colors are used to solve common problems (like lighting) is a good idea, but belongs in another paragraph, if not another article, and should have more relevant information depending on which aspects of vertex colors you want to talk about. For example, the practice of simulating lighting and shadows with vertex colors is mentioned in your paragraph, but the process of tessellating and cutting is not, which is very relevant to that specific topic. It often makes lightmaps a performance win even on older systems and rendering architectures, and it's a required procedure for representing any reasonably-complex lighting model with vertex colors. I'm not sure I would mention this topic at all, but if you're going to mention it, be thorough. In the long-term information like this belongs in its own article (because doing lighting with vertex colors is actually a very involved topic), so you can just link to the relevant parts of that article from your vertex color info. Otherwise, if you feel it deserves to be mentioned but you don't want to or can't offer a detailed explanation, you should include it in an itemized "common real-world uses for vertex colors" list where it can be linked to a descriptive article on the topic by someone who cares in the future.

This advice applies pretty generically to anything you end up describing there. You should really be able to basically copy-paste most of your base explanations and descriptions right out of OpenGL/D3D documentation. Anything subjective should be mentioned without invalidating other not-common-but-still-valid uses.
## Post #10
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-02-07T23:25:11+00:00
- Post Title: Vertex colors

The most practical use for them i've found is for adding color to a textured model prior to render baking.
If your not that artistic, it's possible to produce a more professional looking texture from a simple bland texture.
[http://i1235.photobucket.com/albums/ff4 ... l/tms1.jpg](http://i1235.photobucket.com/albums/ff428/codex34/general/tms1.jpg)
[http://i1235.photobucket.com/albums/ff4 ... l/tms2.jpg](http://i1235.photobucket.com/albums/ff428/codex34/general/tms2.jpg)

I've also misused them to add vertex weights to models, which was outside of the scope of the software used at the time.
## Post #11
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-07T23:53:49+00:00
- Post Title: Vertex colors

> Reply from gjinka2
>
> Vertex lights in OpenGL and DirectX color the vertices which they influence, but they are realtime lights, in other words they manipulate the vertex colors in real time, so they aren't stored in the 3d files. We shouldn't care about them.

Either that, or it can be baked too. The ones in L.A. Noire that I mentioned earlier were realtime vertex lights.
## Post #12
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-08T13:45:22+00:00
- Post Title: Vertex colors

> Reply from MrAdults
>
> It seems a bit silly to be writing new explanations of what common rendering components are, when you can instead pick and pull from pages with rather complete information on their use and behavior. Like official OpenGL/D3D implementation documentation from any given vendor. Microsoft docs are usually a good source.
Firsly, it seems rude to say we are doing silly things.
Secondly, you are basically asking "what is the point of reading a general philosophy book if you can just read the works of all the famous philosopers?" maybe we don't have the time nor the knowledge?
Finally, why don't you just edit the wiki page yourself? You did take the time to post it here, the wiki doesn't require any registration.

> 1) OpenGL and Direct3D are not required to interpolate vertex colors. In fixed function OpenGL this is dictated by glShadeModel (this affects interpolation of vertex colors even when lighting is disabled), ShadeModel when writing in Cg, and the list goes on. Most graphics API's have some means of dictating interpolation on a per-component basis, although the means may and often will vary based both on the component and the API. Flat shading is often used (in older games particularly) where more than 1 color per face was not needed or desired, yet in many of these cases colors were still baked into vertex lists and occasionally interleaved as we often see in data sets meant for modern graphics pipelines. This was particularly common in custom software renderers.
I have never seen non-interpolated vertex colors for meshes consisting of faces. Again, feel free to edit the wiki.

> 2) Way too subjective. It actually wouldn't be practically useless to have colored dots on your mesh (and many people use sprites or even rasterized points in conjunction with vertex colors for this purpose)
(So do I.) I'm talking about colored dots on mesh consisting of only faces and rendered as such. Maybe my wording isn't good, again its a wiki, feel free to improve it. 

> 3) Explaining how vertex colors are used to solve common problems (like lighting) is a good idea, but belongs in another paragraph, if not another article,
This is a brief guide to what data is stored in 3d files and how it's stored, not a defnitive guide on how OpenGL and DirectX work. I disagree.

> For example, the practice of simulating lighting and shadows with vertex colors is mentioned in your paragraph, but the process of tessellating and cutting is not, which is very relevant to that specific topic.
Hm, maybe because Ive never heard of "tessellating and cutting"? Again, you can add it yourself if you want, or at least post it in the talk page.

But really, cut me some slack, will ya??
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-08T19:18:17+00:00
- Post Title: Vertex colors

When I see someone doing something silly, I will tell them they are doing something silly, explain why I think this, and if possible advise them such that what they're doing can be made less silly or perhaps even not silly at all. I should think going and tearing your wiki entries up myself would've been far more "rude". Your options at this stage are:

1) Take the advice.
2) Ignore the advice.
3) Act like the way in which the advice was delivered has offended your delicate sensibilities.

3 can be combined with 1 or 2 as you see fit. I recall you were big on 3 in another thread with mariokart64, so I'm not surprised you've chosen this marvelous and appealing option in your dealings with me. Let me be the first to congratulate you on a path well-chosen.

I personally think that re-describing core rendering components is pretty redundant, like I already said, so I see no reason to edit what you've written short of removing it entirely and just linking directly to existing documentation and wiki articles that cover the same information. I should think you might be interested in improving it yourself instead of inviting me to come in and destroy it all. If you want to at least make the information consistent and accurate yourself, then I've just given you some fairly good guidelines for doing so. If you have no interest in any of that, I or someone else will probably fix it eventually, sure.
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-08T21:17:02+00:00
- Post Title: Vertex colors

I think it was someone else...  Like ganjii or something like that got into it with mc.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T22:54:41+00:00
- Post Title: Vertex colors

> Reply from MrAdults
>
> 
linking directly to existing documentation and wiki articles that cover the same information.

Anything technical that requires specialized knowledge and some experience with it goes over my head.

Most of the articles I've read regarding 3D are very technical and specialized and assume you know something about 3D and have played around with 3D and made your own 3D.

Or talk about how they are implemented.
Or the physics and maths behind it.
## Post #16
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-08T23:37:19+00:00
- Post Title: Re: Vertex colors

> Reply from howfie
>
> I think it was someone else...  Like ganjii or something like that got into it with mc.
Oh, my bad. So we have ganjul, gjinka, and gjinka2. And only 2 of them are the same person? What the hell is with these names.

> Reply from finale00
>
> Anything technical that requires specialized knowledge and some experience with it goes over my head.
That's why I like to recommend Microsoft docs when it's an option. They usually do a good job with descriptions and occasionally even examples. Their OpenGL and D3D docs in particular are very readable and don't tend to rely on obscure terminology at all.

By the way, unrelated again, but not sure if I'll get to Queen's Blade or not tonight after all, having some unexpected issues on my contract project. And I kind of want to write the UV previewer for Noesis before I get to it. I apologize for any inconvenience this may cause for our forum members in delaying their plans to masturbate horribly from the depths of emotional and sexual depravity to crude models of cartoon girls. In the mean time, feel free to use and contribute to Mr.Mouse's babe thread, although I realize that for many 2D representations of real women simply can't compare.
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T23:39:47+00:00
- Post Title: Re: Vertex colors

I guess microsoft docs are ok. I've tried reading their DDS docs but it was still pretty technical to me. Then again those were specs and not really "what is it?"

lol no rush. There's plenty of services that will provide sufficient amounts of entertainment for the night   
But ya if you get that done, that's three games in one.
## Post #18
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-09T17:55:30+00:00
- Post Title: Re: Vertex colors

> Reply from MrAdults
>
> When I see someone doing something silly, I will tell them they are doing something silly...
Really? That's your argument? "I say what I think"? Giving "constructing criticism" after it doesn't change what you said before.
I, for example, after what you said in these posts find you a douchebag, or drunk, or both, but I don't tell you you are one, not because your username is painted green, but because there is this thing many people call "politeness". 

BTW, I only contributed to the page, I didn't write all of it. So I'm not the only one who should get offended. And dinoguy gave permission to finale to link the page from the main wiki page, so it doesn't seem he finds a guide like this "silly" either.

> 1) Take the advice.
I did. It doesn't mean I agreed with all of it, but I didn't ignore it as well. I did agree on some points, but like I said, I simply don't have the required knowledge to make the changes myself (ex. don't know what tessalation and cutting are).

> I recall you were big on 3 in another thread with mariokart64, so I'm not surprised you've chosen this marvelous and appealing option in your dealings with me. Let me be the first to congratulate you on a path well-chosen.
Sir, whatcha talkin bout?

> I personally think that re-describing core rendering components is pretty redundant, like I already said, so I see no reason to edit what you've written short of removing it entirely and just linking directly to existing documentation and wiki articles that cover the same information.
And I personally don't. It seems I'm not the only one who thinks this way.

> I should think you might be interested in improving it yourself instead of inviting me to come in and destroy it all.
Like I said, others find it useful and if by "destroying" it you mean removing the page, I'm sure most people will be disappointed. However, if you mean rewriting most of it, then yeah, it's a wiki. However, as some people find it useful the way it is, maybe we should discuss it in the talk page.


Anyway, you know we spent our time because we wanted to help others and you come here and tell us it's trash and useless, only then suggest how to improve it. So I say, cut us some slack.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-09T18:05:57+00:00
- Post Title: Re: Vertex colors

I'm still split between "understanding what it is" vs "knowing what I'm seeing/what to find"
Some people find it easier to understand the theory behind it and then go for it, while others like me just want to know what there is and will figure out some patterns along the way.

Maybe the first part should just be "this is what you might see" and then a link to another page that goes into detail about what it is. At least if this were programming, I'd arrange it that way.

Like, seeing that I only need this and that for animations doesn't make it any easier to actually load them lol
## Post #20
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-09T19:55:53+00:00
- Post Title: Re: Vertex colors

I love how you can so easily take "It's a bit silly, but here's what you should be doing" and turn it into "It's trash and useless!" in order to justify a mini-lecture on "politeness" which is completely invalidated by your own childish passive-aggressive remarks. Are you sure you aren't ganjul? You'd have to be pretty far-removed from reality to take genuine offense at anything I said. It's also very constructive and focuses on telling you your mistakes and how to present information in an organized, useful manner. You seem to focus on being upset over the fact that I called re-inventing the wheel "silly." Well, sorry, but re-inventing the wheel is something I think of as rather silly.

finale00, it sounds like you need exactly what I suggested in the itemized "common real-world uses" list. An itemized list for this purpose is also so much more useful than a jumbled up paragraph mentioning random tidbits which are somewhat inaccurate and not particularly related to each other in the same sub-context. There is good reason to have this page (mainly for those real-world uses - we can already look in plenty of places to figure out what these components *are*), it just makes little to no sense to be re-inventing (partially inaccurate) descriptions of the components.

Anyway, my 2 cents. Feel free to be terribly offended at my refusal to walk on eggshells for you.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-09T20:55:46+00:00
- Post Title: Re: Vertex colors

A list of things that I should be looking out for, along with how they are usually represented (vertex coords as 4 byte floats or 2 byte floats, 4x4 matrices, etc) would probably be nice.

When I see that coords could be floats or half-floats it probably automatically makes me go "ok if floats don't work then let's try throwing half-floats at it"

I will move all of the explanations into a "glossary" of sorts, where each concept would contain some summary as well as a link to appropriate references.
No one likes to have to look around thousand-pages of docs to find what they care about, and that's usually what reading these kind of docs is about. Saves myself from having to look around trying to decide if it's useful information, since I don't even know where to start.

I don't think it is too important for a reverse engineer to completely understand how they are used, though it might provide insight on why the format was stored that way I guess.
## Post #22
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-10T00:14:53+00:00
- Post Title: Re: Vertex colors

Common storage methods is a good thing to have too, yeah. But again, you can get most common types right out of OpenGL/D3D API docs. There are some additional types you may not find in non-hardware-specific API docs, though, which are still worth mentioning generically. Like the X10Y10Z10/X10Y11Z10/etc. types ideally/commonly used for storing normals. (and occasionally tangent vectors - but technically they can be used to store lots of different data types) If you start getting too much into platform-specific types, though, you'll want to be careful not to bloat the main components page with overly-elaborate explanations. So I'd keep it limited to raw data types rather than getting into specific storage conventions with custom headers or whatever else. (like if you wanted to cover PS2 VIFcode, I wouldn't put the actual specs on the same page as your common data types, but I'd probably link to it from that page because it does relate to the topic and linking to it lets the reader know that it's a possible means of data storage to be aware of... although VIFcode in particular relates to the storage and rendering of all components and not any one in particular, it just also happens to be a standard which also dictates the actual component formats)
## Post #23
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-10T15:34:38+00:00
- Post Title: Re: Vertex colors

> Reply from MrAdults
>
> I love how you can so easily take "It's a bit silly, but here's what you should be doing" and turn it into "It's trash and useless!"
Nope, you said just a bit later that you found it useless and would probably end up removing it all if it was for you.

> You seem to focus on being upset over the fact that I called re-inventing the wheel "silly." Well, sorry, but re-inventing the wheel is something I think of as rather silly.
"You look ugly! Sorry, just being honest."

And again, arguing this to be "reinventing the wheel" seems wrong anyway:

> Reply from gjinka2
>
> ...you are basically asking "what is the point of reading a general philosophy book if you can just read the works of all the famous philosopers?" maybe we don't have the time nor the knowledge?
finale00 seems to give the same reasons:

> Reply from finale00
>
> 
No one likes to have to look around thousand-pages of docs to find what they care about, and that's usually what reading these kind of docs is about.

But apparently, I'm just overreacting and not taking criticism which you so generously provide. And of course you are not being rude now by calling me childish.
Puh-lease.
## Post #24
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-10T16:22:18+00:00
- Post Title: Re: Vertex colors

Can we just forget anyone ever said anything lol? Don't worry gjinka, Rich has even been critical of a thing or two that I have done (like in the Tekken Hybrid thread), but we all get along. I don't get offended; it happens all the time. I've been to CS poster presentations at conferences and let me tell you them visiting Chinese professors will walk up to your work and try and rip you a fucking new one. I've even seen it get so bad that other professors have had to step in and intervene. It doesn't matter if your work is 100% right or not. The worst thing we can do is get into a massive back and forth. So let's just forget everything and continue on having fun ripping games. Besides, I think Rich mistook you for someone else who gave mariokart a hard time in the DOA thread which is why he might have come across as being somewhat mean.
## Post #25
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-10T19:56:17+00:00
- Post Title: Re: Vertex colors

> Reply from howfie
>
> Besides, I think Rich mistook you for someone else who gave mariokart a hard time in the DOA thread which is why he might have come across as being somewhat mean.
That really isn't the case. At least, I've been no more mean than I'm "mean" to anyone who I feel a need to correct in whatever they're doing. If you look back at what I actually said, it doesn't even resemble what this guy is accusing me of.

Claim:

> Reply from gjinka2
>
> Nope, you said just a bit later that you found it useless and would probably end up removing it all if it was for you.
Reality:

> Reply from MrAdults
>
> I personally think that re-describing core rendering components is pretty redundant, like I already said, so I see no reason to edit what you've written short of removing it entirely and just linking directly to existing documentation and wiki articles that cover the same information. (further note that this refers specifically to what *you* wrote in that jumbled paragraph about vertex colors, which from an objective standpoint does not have any content that I could keep with the goal of presenting that information correctly - and is only in reply to you telling me that it's a wiki, so I should be the one to go edit what you've written... I guess instead of engaging in the terrible sin of making suggestions to you)

Claim:

> Reply from gjinka2
>
> Anyway, you know we spent our time because we wanted to help others and you come here and tell us it's trash and useless
Reality:

> Reply from MrAdults
>
> It seems a bit silly to be writing new explanations of what common rendering components are, when you can instead pick and pull from pages with rather complete information on their use and behavior. Like official OpenGL/D3D implementation documentation from any given vendor. Microsoft docs are usually a good source.

> Reply from gjinka2
>
> But apparently, I'm just overreacting and not taking criticism which you so generously provide. And of course you are not being rude now by calling me childish.
Puh-lease.

> Reply from gjinka2
>
> I, for example, after what you said in these posts find you a douchebag, or drunk, or both, but I don't tell you you are one, not because your username is painted green, but because there is this thing many people call "politeness".
I'm sorry, your blatantly self-defeating statement may have been more appropriately classified as ironic and naive, instead of childish.

I had no issue with you personally when I first posted a critique of your documentation methods here, but with the bizarre way in which you've internally twisted my meaning and intention and repeatedly accused me of saying things that I simply did not say or even imply, you've demonstrated to me that you're not someone I should be interacting with or assisting in any way. So good luck writing poor documentation and getting pissed off at people that make suggestions to you in the future, I won't be one of them!
## Post #26
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-10T20:25:54+00:00
- Post Title: Re: Vertex colors

1)

> Reply from MrAdults
>
> 
Claim:
Reality:
uhh

> gjinka2 wrote:Nope, you said just a bit later that you found it useless and would probably end up removing it all if it was for you.
>
> MrAdults wrote:so I see no reason to edit what you've written short of removing it entirely and just linking directly to existing documentation and wiki articles that cover the same information.

2)

> Claim:
>
> Reality:
Nope, this is the "reality":

> Reply from MrAdults
>
> I personally think that re-describing core rendering components is pretty redundant, like I already said, so I see no reason to edit what you've written short of removing it entirely and just linking directly to existing documentation and wiki articles that cover the same information. I should think you might be interested in improving it yourself instead of inviting me to come in and destroy it all.

> self-defeating statement
Nope. Just saying I *didn't* just say what I think of you prior to that post.

> So good luck writing poor documentation
See below.

> and getting pissed off at people that makes suggestions to you in the future
I like how you misrepresent that if I'm getting pissed off at your suggestions, not the other stuff you said like it seeming silly and you likely ending up removing it. I know that I did write some wrong (and "jumbled") things, but like I said, I don't know enough to correct it.
## Post #27
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-10T20:42:32+00:00
- Post Title: Re: Vertex colors

I'm not misrepresenting anything. I didn't say anything offensive at all in my initial post, yet you immediately got your panties in a bundle and twisted my sentiment that re-inventing the wheel is silly into somehow meaning that all of your work is trash and useless, then invited me to fix it myself. I clearly explained to you why I thought re-inventing the wheel is silly and explained that I would indeed destroy all (or perhaps most) of your writing if I were to rewrite it myself, and for good, constructive reasons. Not simply because I hate you. Because I didn't hate you, until a post or 2 ago when you confirmed to me that you're a man with a fragile ego who is unable to take helpful criticism unless it's presented to you as it would be to a 10 year old.

> Reply from gjinka2
>
> uhh
Enough said, really.
## Post #28
- Username: gjinka2
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jan 30, 2012 12:54 am
- Post datetime: 2012-02-11T11:16:07+00:00
- Post Title: Re: Vertex colors

> twisted my sentiment that re-inventing the wheel is silly into somehow meaning that all of your work is trash and useless
That's what I mean when I say you misrepresent what happened. You are claiming (again) that all I said was directed to your initial post, but it's not, I posted that after your second post.

> I clearly explained to you why I thought re-inventing the wheel is silly
>
> ...
>
> and for good, constructive reasons.
So? I asked for explanation of why you were rude? Does explaining why one was rude make him not rude? Or does being constructive justify being rude?

> Enough said, really.
Well, I don't see why I should care reading what you will say either then.
## Post #29
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-11T18:59:02+00:00
- Post Title: Re: Vertex colors

> Reply from gjinka2
>
> Does explaining why one was rude make him not rude? Nope.

> Reply from gjinka2
>
> does being constructive justify being rude? Nope.

> Reply from Smarter, more honest gjinka
>
> Does accusing someone of being rude mean make them rude? Nope.

> Reply from Smarter, more honest gjinka
>
> Is falsely quoting someone under the guise of a passively insulting handle a rude thing to do? Why yes, it certainly is.

> Reply from Smarter, more honest gjinka
>
> Well, now you're just proving my point. You poor, simple, drunken douchebag. That's because I hate your lesser self now, because he's attempted to take his butthurt reaction to legitimate criticism and justify it by claiming that a completely reasonable comment about the silliness of re-inventing descriptions of 3D rendering components is "rude". As if that wasn't enough, he invited me to fix his work, and then turned around and accused me of calling it useless trash when I explained that I would end up destroying all of his work. (and as such chose to offer him criticism to give him the chance to correct his own work, likely learning and growing as a person in the process)

> Reply from Smarter, more honest gjinka
>
> I'm sorry. It's all because of mother. She had such high expectations of me, and I feel every day of my life is just another disappointment to her. I know, son. I know. I forgive you.

I'm happy that this is resolved now. You seem like a good guy after all, gjinka. I'm sorry I hurt your feelings, and now I understand that you're just another person, like me, and I empathize with you. I'm glad we had this talk, and I hope there are no hard feelings.
