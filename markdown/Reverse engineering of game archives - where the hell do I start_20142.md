## Post #1
- Username: nmkd
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 15, 2017 10:59 pm
- Post datetime: 2019-04-29T12:49:50+00:00
- Post Title: Reverse engineering of game archives - where the hell do I start?

I'm a hobbyist game developer and I can code in C#.

I really want to get into game reverse engineering, but I really don't know where to start.

To be more specific, I'd like to make level viewers or extraction tools. The main inspiration here was Silent Hill 2 - there is a level viewer, but it's totally barebones (locked to 800x600 fullscreen, no alt-tabbing, ...).

I played around with SH2's map files a bit, but all I could figure out was that the textures are stored in DXT3/5 format with a 512 width, but I still have no idea how I would extract them.

So, yeah, where do I get started? It can't be so hard considering hundreds of games have extraction tools or even level viewers, but I can't find many ressources, and a lot of tools (the Silent Hill one I mentioned, for example) are clsoed source. And open-source tools often don't have much documentation.

Hoping to get some tips, thanks in advance
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-04-29T21:18:54+00:00
- Post Title: Reverse engineering of game archives - where the hell do I start?

The only issue is I think you're wanting to start off too broad, and should try to narrow down. I usually split reverse engineering (for resources that is) into three categories:
Images
Audio
Models

Wanting to write a level viewer right off the bat is very difficult, and I really don't recommend going that route, because you'd have to be able to understand a lot of more in-depth stuff in terms of model reverse engineering that can take a really long time to grasp onto. For someone who has never reverse engineered, I'd recommend picking up QuickBMS and reading scripts other users have written. While it may be a pain, the best way to learn is from others, so I'd recommend tracing the script with an example archive, such as this:
[https://www.vg-resource.com/thread-28180.html](https://www.vg-resource.com/thread-28180.html)

It's a really good starting point, but just make a note that you can not modify this script to make other archives to work. A lot of people assume that if they edit the script in that post that it will work, but this is not the case. Hope this helped!
## Post #3
- Username: nmkd
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 15, 2017 10:59 pm
- Post datetime: 2019-04-30T08:02:35+00:00
- Post Title: Reverse engineering of game archives - where the hell do I start?

> Reply from Pingu ↑Tue Apr 30, 2019 5:18 am at Tue Apr 30, 2019 5:18 am
>
> 
The only issue is I think you're wanting to start off too broad, and should try to narrow down. I usually split reverse engineering (for resources that is) into three categories:
Images
Audio
Models

Wanting to write a level viewer right off the bat is very difficult, and I really don't recommend going that route, because you'd have to be able to understand a lot of more in-depth stuff in terms of model reverse engineering that can take a really long time to grasp onto. For someone who has never reverse engineered, I'd recommend picking up QuickBMS and reading scripts other users have written. While it may be a pain, the best way to learn is from others, so I'd recommend tracing the script with an example archive, such as this:
https://www.vg-resource.com/thread-28180.html

It's a really good starting point, but just make a note that you can not modify this script to make other archives to work. A lot of people assume that if they edit the script in that post that it will work, but this is not the case. Hope this helped!

Thanks for that link!

A level viewer is nothing I'd make right away, it's just my "end goal". Of course I'd start with single file formats first.
I'll check that tutorial out 

EDIT:

I didn't get far. 
The sample file link is dead and I already didn't quite understand the first step. "Say I find a value that looks like a size." - when does a bunch of Hex numbers "look like a size"? Also couldn't do anything with the next step as the file I had didn't start with any letters.

I really don't know what to do, all tutorials are obsolete it seems.
