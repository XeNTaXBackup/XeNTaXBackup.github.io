## Post #1
- Username: StifleroGHD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 11, 2016 8:58 am
- Post datetime: 2016-07-20T22:25:16+00:00
- Post Title: Midnight Club: Los Angeles on PC [Project - Help needed]

First of all, hi all! Haha. I'm new here on this forum and I saw that you guys here are experts in everything, and I need your help with this project, as it
it's said in the title. 

I have exported all the data from the folders xarchive_audio.rpf, xarchive_audlo.rpf, xarchive_cache.rpf and xarchive_music.rpf. 
Now, we have this: [https://postimg.org/image/ognyez3hz/1a24e356/](https://postimg.org/image/ognyez3hz/1a24e356/) - All archives are out. 

There is .dat files, .sco files (scripts) with .scr header, .xml and many more. Now the audio;
Audio files are like this, with no header and no format: [https://postimg.org/image/8qofu9d6p/](https://postimg.org/image/8qofu9d6p/)
And when I open for example one file: [https://postimg.org/image/4de7tmccx/](https://postimg.org/image/4de7tmccx/)

Now there is a .dat file and .xml file: [https://postimg.org/image/9avot6x13/](https://postimg.org/image/9avot6x13/)
When I open .xml: [https://postimg.org/image/u8ld1l3yp/](https://postimg.org/image/u8ld1l3yp/)
And when I open .dat: [https://postimg.org/image/60bgnv2qv/](https://postimg.org/image/60bgnv2qv/)

Now, let's get to the scripts. When I open, for example 0x1c95663c.file, which is located in script_obj\game\career, I get this: [https://postimg.org/image/ndazflwg1/](https://postimg.org/image/ndazflwg1/) - .scr header? Hm, never 
heard of it. 
Now when I open for example beat_gh_04_muscle.sco file, which is located in script_obj\game\career\missions, I get this: [https://postimg.org/image/7k3hc5jpd/](https://postimg.org/image/7k3hc5jpd/) - .scr header again? Well..

I have exported all the data with RPF Tool maded by Twisted. When I was getting keys for the game, I saw many strings and how the game work when it's loading.
When I was dumping the "default.xex" file which I have extracted from the game, I saw many of libaries in there, D3D9, Kernel, etc. What I wanna say; I have
downloaded the DishwasherVC ported to PC with love from Barabus, hehe. I was checking the Dishwasher.exe, and I saw there that was same lines of loading
files just like in the "default.xex" of the Dishwasher X360 game. Yep, there was few .dll's to inject in the .exe and some other stuff which is not a big deal.
The big deal is that Barabus, I think, didn't touch anything with the game archive, because when I was exploring data files, they are the same as they were
packed: [https://postimg.org/image/na14dmudz/](https://postimg.org/image/na14dmudz/) - But hm, resources files? Dunno about them. 

Now I'm thinking to get the same thing with this one, because it's the X360 game. To reverse loading stuff and import it into the .exe to make the game think
that it is running on X360 and to import libaries there. Yeah, I said it like it's an easy job, but it is NOT.
I'm saying this because he didn't touched anything about the resoulution, it is running in the native one. Commands are the same like on the X360, and yes
keyboard is avaiable to use, remapped commands. It's not immposible job, but I need your advice and help about this one. 

Can someone make the QuickBMS script for the .dat files, audio and .sco (or .scr)? Just to try and extract them out, to see what is inside of it.
Here is an upload of all the files that I have mentonied in this post, and Dishwasher.exe file, to see what I was thinking: [http://www50.zippyshare.com/v/ztG81gcY/file.html](http://www50.zippyshare.com/v/ztG81gcY/file.html)

Tell me what you think, then I will tell you more ideas about it.
