## Post #1
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2005-05-31T18:41:26+00:00
- Post Title: Unreal Engine Formats support?

What about .utx, .u, .uax, .usx, .ugx (unreal 2 meshes), etc..?  I know for unreal tournament there was a program called Unreal Services Package Explorer.  it only gave you a very limited range of extraction and viewing options however, maybe if you could get a hold of the guys that created the program you could get them to help with the coding for these formats? the website was [Unreal Services](http://services.unreal.ru/)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-31T22:55:55+00:00
- Post Title: Unreal Engine Formats support?

There are already dll's available that do this.  Our current project will also allow these to be supported in coming versions of MultiEx Commander.
## Post #3
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2005-06-02T03:39:37+00:00
- Post Title: Unreal Engine Formats support?

Ah i didn't get a chance to take a look at Game Extractor until just now, which is quite impressive, I notice you've even got support for Pariah! Even the Splinter Cell Series!  That's awesome!  Did you have to come up with a separate dll for each game or did they leave the formats pretty much the same across Unreal, Splinter Cell and Pariah??
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-02T03:50:22+00:00
- Post Title: Unreal Engine Formats support?

Hi mate,

Actually, the unreal formats are quite annoying because they keep changing the structure alittle between each of the games. For each unreal-based game, I have had to detect the file version before opening them.

The most annoying thing is that some games use the same file version, but are actually 2 different structures - this means that to open these files I sometimes need to ask the user what game they are trying to open.

The plugin is alittle messy, and I do try to add support for as many of the Unreal-based games as possible - it would be nice if they could be consistant  - anyway, I just have to keep adding more to the plugin whenever a new game for this engine comes out.

The good news - if you are wanting to edit the Splinter Cell games, I have most of them and have thus done most of the plugin testing on those games. Those games should also extract the WAV audio files correctly if yuo want to use them.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2005-06-02T04:33:14+00:00
- Post Title: Unreal Engine Formats support?

Thanks, that's mainly what I was after too, I am an Audio engineer (self-taught) and I do a lot with pre-rendered sounds for non-profit mods.  I've been trying to look at tons of different games and i've found that the Unreal Engine is just so amazing, I mean of course there are the other 2 major engines like Valve's Steam Engine running HL2, and id's latest engine running Doom 3.  But the unreal engine i think is just sitting right in between them, with the unreal team working on actual realtime HDR lighting on their engine build long before Valve's team even thought to work it into their engine (which I hear they are doing now).  It's becoming significantly more popular among other major developers too, so more games will be using the engine (hence Pariah; Go Digital Extremes!... Good team), So i'm thinking of starting a mod of my own and distributing the resources throughout several of the games (mainly Splinter Cell series)  but i actually have several ideas in mind that i'm going to impliment, as long as i have an easy way to access the original GRAF's for these games I will have plenty of information i need for creating my own mods.  Thanks a bunch!  I'm purchasing the full version as we speak!
## Post #6
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-06-02T07:00:28+00:00
- Post Title: Unreal Engine Formats support?

where do i get the dlls for the unreal games to extract the .u files? i just aded the post to the black arrow post i made earlier but ifi can get them without having to bother mouse with making another file for me id appreciate it.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-02T07:33:50+00:00
- Post Title: Unreal Engine Formats support?

Here's what a lot of people use :

[http://www.acordero.org/projects/utpf/](http://www.acordero.org/projects/utpf/)

[http://sourceforge.net/projects/utpackages](http://sourceforge.net/projects/utpackages)

It's actually those guys that you should credit for the work
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-02T14:15:57+00:00
- Post Title: Unreal Engine Formats support?

There is another forum post somewhere about the unreal engine - it has an attachment plugin for Game Extractor in there.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-02T14:24:36+00:00
- Post Title: Unreal Engine Formats support?

I see the poll above, and we shall include it in MultiEx Commander, folks.
