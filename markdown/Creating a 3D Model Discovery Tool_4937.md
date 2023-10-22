## Post #1
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-08-28T11:00:56+00:00
- Post Title: Creating a 3D Model Discovery Tool

Alright so I've been working on a basic 3d file exploration tool for the past few days. It's main feature would be the ability to see the preview as you change the offset of the vertexes in real time. But right now I'd like to ask some questions to the people who would actually use it before I get to programming the core stuff.

So here's the list of questions:

Performance or Features?
It's easy to throw together stuff and not care about performance but should it be considered and how much?
How important is it to be multiplatform?
Sticking to windows would simplify things tremendously but linux is doable if demand is high enough.
DirectX or OpenGL?
Kinda ties into the last question. OpenGL would allow for multiplatform but directX would provide faster speed and easier programming for windows. Both with a choice between the two?
Supported export filetypes?
.Obj is simple, but what else would be expected?
If a coding system is implemented what language should it be?
C# would be easy since there's parsers out there but C++ or even C would be a lot more difficult. Maybe even a custom specialized one?
Is it better to get beta's out right away or flush out the design first?
Basically do you want unstable things soon or would you wait for a well oiled machine?


Here's a list of possible features to be prioritized and maybe implemented:

[Unknown] Custom Coded Data Formats
Allowing for custom vertex structs and the like.
[Unknown] Plugin System
Allowing others to add support for file types and wha-ev.
[Unknown] Multi-threaded Design
Taking advantage of mutli-core processors basically.

I'd like to prioritize them on a scale of [Low] [Medium] [High] [Required]

If you can think of any other features that are to be expected or even required please feel free to post a reply!
## Post #2
- Username: tkGr33N
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Sep 26, 2010 3:43 am
- Post datetime: 2010-09-30T21:36:03+00:00
- Post Title: Creating a 3D Model Discovery Tool

IMO

> Reply from invisghost
>
> 
Performance or Features?
It's easy to throw together stuff and not care about performance but should it be considered and how much?
Keep it simple, don't make some state of the art tool if you're working alone, most tools that are great and flawless* are made by giant corporations
* Flawless to an extent where you can put your own plug-ins in.

> Reply from invisghost
>
> 
How important is it to be multiplatform?
Sticking to windows would simplify things tremendously but linux is doable if demand is high enough.
Multiplatform is not really all that great, regarding that most extracting tools are made for windows.

> Reply from invisghost
>
> 
DirectX or OpenGL?
Kinda ties into the last question. OpenGL would allow for multiplatform but directX would provide faster speed and easier programming for windows. Both with a choice between the two?
Supported export filetypes?
Although, as stated above, some people already have extracted game files and just need to view it in someway, OpenGL is Complicated in different ways, but so is DirectX, but simpler.

> Reply from invisghost
>
> 
.Obj is simple, but what else would be expected?
.dae, .3ds and .fbx is more common in the current industry, but .obj is leading atm.

> Reply from invisghost
>
> 
If a coding system is implemented what language should it be?
C# would be easy since there's parsers out there but C++ or even C would be a lot more difficult. Maybe even a custom specialized one?
C# has a load of things that make other things simpler

> Reply from invisghost
>
> 
Is it better to get beta's out right away or flush out the design first?
Basically do you want unstable things soon or would you wait for a well oiled machine?
Get the design later, first do all the coding, makes things simpler, and the probability to screw up is reduced

Also some sort of bms-like system, because really, you can't keep updating things.
## Post #3
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-10-01T05:19:27+00:00
- Post Title: Creating a 3D Model Discovery Tool

Thanks for your opinions 

Ya, I've kinda been re-re-re-re-creating the program for the past few weeks. Each time getting a little more abstract. I'm probably going to go with directX just for the sake of being able to say "its directx". Lol I am indifferent to either one so flipped a coin and directx it is.

I was first thinking about coding it in C++ but that just is a headache in its own when trying to implement a plugin system so I'll just go with C#. C# is great with dynamics and has enough parsing libraries to more then meet the need of some sort of BMS system. I've just been trying to figure out how I'd implement something like that. It's simple enough for something like "here's my array of poly vectors (x,y,z) and here's how many there are" but some formats have (z,y,x), there's no way to predict what formats will be needed so i'll have to supply the tools to design your own but here's the challenging part, when working with an emulator's memory dump of that can be 300mb+ you need something that can quickly go through that file. Trying to do some benchmarks on different approaches atm.

Obviously it'll be open source since anything C# is open source .
## Post #4
- Username: tkGr33N
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Sep 26, 2010 3:43 am
- Post datetime: 2010-10-01T06:09:27+00:00
- Post Title: Creating a 3D Model Discovery Tool

> Reply from invisghost
>
> 
Obviously it'll be open source since anything C# is open source .

Not everything made with C# is open source, but a lot of things are
EDIT: A simple solution for the custom data format, make something like

```
-1.000, 0.500, 1.000
texture002.dds;
0.250, 0.125, -0.250

```

And so on, Naming the textures, and where they need to be stuck on, each line that starts with a numeral is a xyz vector line
