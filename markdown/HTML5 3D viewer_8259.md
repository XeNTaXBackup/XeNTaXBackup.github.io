## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T21:54:13+00:00
- Post Title: HTML5 3D viewer

I was exploring the various features available in HTML5 and noticed that they can render 3D models.
Anyone played with this?

I haven't looked into it too much, but it looks like I'll have to figure out all the syntax and stuff.

Anyone have a simple 1-2-3 guide that tells me exactly what I need?

Depending on how modular it can be done, maybe I can write a noesis export plugin that will generate some HTML markup that you could just copy paste or view directly.

Obviously, everyone should be getting HTML5-compatible browsers, and for those that don't, they should consider doing so.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-11T22:06:30+00:00
- Post Title: HTML5 3D viewer

this loads an obj file [http://www.canvasdemos.com/userdemos/to ... iewer.html](http://www.canvasdemos.com/userdemos/toxicgonzo/3dobjviewer.html)
there is also
[http://code.google.com/p/objloader/](http://code.google.com/p/objloader/)
step by step guide here
[http://learningwebgl.com/blog/?page_id=1217](http://learningwebgl.com/blog/?page_id=1217)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T22:16:01+00:00
- Post Title: HTML5 3D viewer

Hmm so it's just binding buffers, which is an array of floats or ints.
Doesn't look too bad.

Hopefully I can get something done in an hour or so.

EDIT: lol the graphics card on this machine doesn't support webGL o.O

Maybe webGL isn't what I'm looking for?

Maybe someone can just write up a simple viewer, and just let me paste the vertex/index buffers? LOL
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-12T00:02:18+00:00
- Post Title: HTML5 3D viewer

I mentioned this briefly I think in another thread about 3D web standards, but WebGL doesn't seem like a very promising standard. There's still a lot of resistance to it (by Microsoft in particular) because the architecture has some fundamental security problems and having an implementation directly execute unmanaged shader code is generally a bad idea.

I've actually had this general idea for Noesis too, though. I also had the thought to make a server-side module that lets people upload files and download converted formats and view jpeg previews and such. That's got lots of potential for security issues too, though, being server-side and accepting client data for processing on the server. So a client implementation would be best. As for your particular idea, the sample .noepy format wouldn't actually be a bad one to go with for supporting in your webgl client. It supports all of the core Noesis data types, although it could use some additions for storing material properties and possibly some other things I may be forgetting. You could just make the appropriate modifications to the format in that sample script that exports .noepy files, give it your own extension name, and be good to go.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T00:11:21+00:00
- Post Title: HTML5 3D viewer

I think a client-side implementation would be better overall considering how most upload speeds suck and how most files are probably in 1 MB range. From a user's POV I'd rather just have some javascript doing magic in the background.

There are security issues when sending stuff to a server for processing?
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-12T00:55:41+00:00
- Post Title: HTML5 3D viewer

As a general rule, you have to be careful when dealing with user-submitted data in a server environment, particularly when the data can be submitted by an anonymous source. In a project like Noesis which supports dozens/hundreds of input formats with no real concern for validity-checking beyond typically a quick header check, the potential for exploits via data is pretty terrifying.

In an interpreted language like PHP, the potential for danger isn't as high as it could be, but it's still there. But Noesis is written primarily in C/C++, and porting all of its loader modules to an interpreted language would be insane. Managed C++ is probably the best fit, but I expect that'd still require a significant overhaul of the codebase, and it would still be very exploitable. (although it could at least protect from most memory-based exploits)

Also, yeah, I think webgl not supporting hardware without shader support adds to its shittiness. Most integrated graphics hardware is at minimum DX9-compliant now, but there are still a lot of people using older integrated graphics like yourself. Given that the entire point of doing anything in a web browser *should* be compatibility and, to a lesser degree, ease of use, using a web standard that's so badly-supported by a mix of hardware and software seems a bit counter-productive. I could overlook the shader requirements if at least all browsers supported it, but Chrome is the only one I know of that even enables it by default, and quite a few browsers seem to still not support it at all.

Edit: Just did a bit of digging around, and it sounds like Opera actually has a software webgl fallback implementation. Might be worth looking into. It seems safer as well. But software performance is likely to be really bad.

Edit 2: Just had the thought that running each server request with Noesis in a new/clean VM instance with a few fixed methods of getting data in/out of the VM would work nicely and completely remove all of the security concerns. But the hardware you'd have to throw at it for it to be useful for more than ~30 people at a time would be unreasonable. Still, I like the idea.
