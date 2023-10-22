## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-12T03:55:07+00:00
- Post Title: History of DirectX

Here is the Wikipedia link about history and chronology of DirectX development by MS. 
[http://en.wikipedia.org/wiki/DirectX#History](http://en.wikipedia.org/wiki/DirectX#History)

But what were really their major and most important milestones, breaks or introduction of new things in D3D development?  Whatever someone knows in few words and how that impacted the graphics in the games. Or if that would be too much then what was the TOP major item spelling progress for D3D.
## Post #2
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-13T03:32:25+00:00
- Post Title: History of DirectX

Stealing technology and misinforming programmers and users with cryptic names such as ClearType and FlexibleVertexFormat, oh and making sure games are released only on windows by not supporting anything else :)

no seriously, Direct X/3D is just an API and like many APIs it doesn't bring anything new on its own, it just makes it easier to program.

real advancements in computing fields comes from implementation of ideas by individuals or orginizations such as universities, hobbyst and game devs :)

the ideas are latter incorporated into the new revision of the api 

try googling siggraph

> But what were really their major and most important milestones, breaks or introduction of new things in D3D development? Whatever someone knows in few words and how that impacted the graphics in the games. Or if that would be too much then what was the TOP major item spelling progress for D3D.
The most tedious set up in exsistance! :P I guess the greatest milestone will be how successful they are, I mean without them many games just wouldn't exist(became a standard)

the whole direct thingy is basicaly a framework, a base on which you build your program
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-14T04:31:36+00:00
- Post Title: History of DirectX

Controversy regarding M$ practices is well known. One would see them as "inconceivable" and another as "strictly business". I wanted to put this in some kind of general perspective and fish out the most prominent features of each iteration of D3D. All's found here:  

[http://en.wikipedia.org/wiki/Direct3D](http://en.wikipedia.org/wiki/Direct3D)

Reprint from above 

> Direct3D 5.0 introduced the DrawPrimitive API that eliminated the need for applications to construct execute buffers.
>
> 
>
> Direct3D 6.0 introduced numerous features to cover contemporary hardware (such as multitexture and stencil buffers) as well as optimized geometry pipelines for x87, SSE and 3DNow and optional texture management to simplify programming. Direct3D 6.0 also included support for features that had been licensed by Microsoft from specific hardware vendors for inclusion in the API, in exchange for the time-to-market advantage to the licensing vendor. S3 texture compression support was one such feature, renamed as DXTC for purposes of inclusion in the API. Another was TriTech's proprietary bump mapping technique. By including these features in DirectX, Microsoft virtually guaranteed that all PC graphics hardware vendors would support the feature at their earliest opportunity, driving industry standardization in a way that was inconceivable under the auspices of the OpenGL Architectural Review Board.
>
> 
>
> Direct3D 7.0 introduced the .dds texture format and support for transform and lighting hardware acceleration (first available on PC hardware with NVIDIA's GeForce), as well as the ability to allocate vertex buffers in hardware memory. Hardware vertex buffers represent the first substantive improvement over OpenGL in DirectX history. Direct3D 7.0 also augmented DirectX support for multitexturing hardware, and represents the pinnacle of fixed-function multitexture pipeline features: although powerful, it was so complicated to program that a new programming model was needed to expose the shading capabilities of graphics hardware.
>
> 
>
> Direct3D 8.0 introduced programmability in the form of vertex and pixel shaders, enabling developers to write code without worrying about superfluous hardware state. They wrote simple shaders to do simple tasks or more complicated shaders to do more complex tasks, and the display driver compiled those shaders to instructions that could be understood by the hardware. Direct3D 8.0 and its programmable shading capabilities were the first major departure from an OpenGL-style fixed-function architecture, where drawing is controlled by a complicated state machine.
>
> 
>
> Direct3D 8.0 also eliminated DirectDraw as a separate API. Direct3D subsumed all remaining DirectDraw API calls still needed for application development, such as Present(), the function used to display rendering results.
>
> 
>
> Direct3D was not considered to be user friendly, but as of DirectX version 8.1, many usability problems were resolved. Direct3D 8 contained many powerful 3D graphics features, such as vertex shaders, pixel shaders, fog, bump mapping and texture mapping.
>
> 
>
> DirectX version 9.0 added a new version of the High Level Shader Language, support for high dynamic range lighting, multiple render targets, and vertex buffer indexing.
>
> 
>
> DirectX version 10.0, included with Windows Vista, is described in the next section
## Post #4
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-14T07:50:27+00:00
- Post Title: History of DirectX

> Reply from Xela
>
> Controversy regarding M$ practices is well known. One would see them as "inconceivable" and another as "strictly business". I wanted to put this in some kind of general perspective and fish out the most prominent features of each iteration of D3D. All's found here:  

http://en.wikipedia.org/wiki/Direct3D

although I heavily disagree with the well known part, I would say that the rework of the api was one of the most important steps for microsoft, it made it as easy as opengl and in many areas alot easier.

also d3d advances progressively in a nice way... I can't say the same about opengl* >.>

I am not sure what you mean by general but like I said before, most of the stuff added to an api is old stuff, like shaders is an old concept(I believe it was somewhere in the 80s with renderman a program made by pixar)
it is all about standards**, nothing else

if you want a general picture you should really look at the history of siggraph or computer graphics in general, that way you will know when how and why the algorithms and structures for dx3d or ogl where chosen

I don't see how you can research dx3d history and specially its impact on the graphics*** and games without getting into the whole war thing

* [http://en.wikipedia.org/wiki/OpenGL](http://en.wikipedia.org/wiki/OpenGL) - lagging behind because it never decided on a standard

** [http://www.theinquirer.net/default.aspx?article=8556](http://www.theinquirer.net/default.aspx?article=8556)(please forgive the title) - an interesting article about the "battle for the standard" I remember it quite well I must say - it tells you when dx3d really took off and why

*** Opengl is preferred by professionals graphic developers because of its openness and because most don't use microsoft windows for anything serious.
game graphics are reimplementation of algorithms used in professional computer graphics(movies-science) for real-time use in customer equipment.

--
After a little reasearch I learned that what I called "battle for the standard" is considered the "API wars" by many
