## Post #1
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-02-24T14:55:07+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

This is strange, but for those of you that own the NTSC version of Bloody Roar 4, there is a complete RenderWare PS2 SDK installer included in the files on the Disc. I nearly cried when I saw this,  and almost fainted when it installed correctly. Here is how you get the installer:
On my Bloody Roar 4 NTSC disc (which is named BR4), there is a folder called DUMMY. Inside that folder is a file called DUMMY00.DMM many PS1/PS2 games have "dummy" files on the disc that are large and empty (a friend told me its purpose is to give nice data loading properties to the pressed disc).
1. Install the free program 7zip.
2. Right click on DUMMY00.DMM and in the 7zip menu select "open Archive" you should then see the following:



Then you can unzip to the desktop, and install, and it will guide you, asking you what type of install, asking where you hve Maya and 3ds installed. The read me will pop up:


I have Windows 7 64-bit and everything installed perfectly.

So what are everyone's feelings about this? Is this not Awesome?
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-02-24T16:04:28+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

LOL omfg that is amazing!!
## Post #3
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2013-02-24T18:32:25+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

Will this let us get the models perfectly from it or any renderware games?
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-02-24T20:01:49+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

> Reply from DOTAPRINCE
>
> Will this let us get the models perfectly from it or any renderware games?
Yes I suppose it will. But if anyone was an FPK extractor that works for Bloody Roar 4 please send me the link, as FPK is a container that BR4 uses to hold dff models and animations, but FPK itself not a renderware format.

But yes there are many viewers in the C:\RW\Graphics\viewers folder. And I have confirmed that the C:\RW\Graphics\viewers\wrldview\wrldview_d3d8.exe "bsp viewer" does work on the BSP files from Monsters Inc.
Here are other viewers that are included note though that this is all highly technical and some work only from the commandline some by double clicking some by both, and some complain about wanting extra dlls, which I assume are in the :
"C:\RW\Shared\RWStudio DLL Installer\setup.exe" which will not install because I am assuming does not work with windows 7 or I did something wrong. You only get the DLL installer after installing the first part from the disc. But again when I installed the base program, I checked every box (programmer, artist ect)
Any there are lots and lots of pdf documents, explaining what each program does, and how to Optimize meshes for example the 16 page 
C:\RW\Graphics\docs\exporters\whitepapers\OptimizeStaticGeom.pdf
which tells you about PS2 Tri-Strips

And there are also many exporters, for both 3dsmax, and maya, and again many documents explaining how to use the exporters:
C:\RW\Graphics\docs\exporters\SDK\3dsmaxApiReference.chm which is a windows help file for the 3dsmax to dff exporter.

The size of everything after installing most of it is 400MB.
C:\RW\Graphics\docs\userguide\UserGuideVol1.pdf   is 280 pages, and there are 2 more volumes.
I just might install 3D Studio Max (In the United States all college students with an .edu email account can get a free limited version of 3d Studio Max), and play around to see if I can get exported meshes to work in renderware games.

But yes if anyone has an FPK extractor that works on BR4 send it to me, so I can test out the model/animation/texture viewer with it.
## Post #5
- Username: Seyiji
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Sep 20, 2011 11:37 pm
- Post datetime: 2013-02-26T04:29:19+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

> Reply from FurryFan
>
> But yes if anyone has an FPK extractor that works on BR4 send it to me, so I can test out the model/animation/texture viewer with it.[Noesis](http://oasis.xentax.com/index.php?content=home) can extract the fpk files on the BR4 disc.

I have no idea which viewer does what so when you find out please tell us
## Post #6
- Username: arcs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 24, 2012 2:51 am
- Post datetime: 2013-02-27T17:45:56+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

Turns out the PAL version of BR4 also contains the dummy directory with the SDK!

> Reply from Seyiji
>
> I have no idea which viewer does what so when you find out please tell us

Here's an extract from the chm file:

RenderWare Graphics has viewers for viewing models, streams and maestro. 

Clump Viewer for viewing .dff files 
Visualizer for viewing many types of RenderWare Graphics files 
World Viewer for viewing .bsp files 
Stream Viewer for viewing the contents of a binary stream files 
2d Viewer - a command line tool for use with Maestro.

Maestro seems to be associated with 2d menu items and such, so that's probably of less interest.

I unpacked the fpk with Noesis, but neither Clump Viewer nor Visualizer seem to be able to read the dff files that were output - "no clump loaded" & "error loading asset" errors given respectively.

However, [steve-m's RW Analyze](http://www.steve-m.com/downloads/tools/rwanalyze/) seems to be capable of reading them, and chrrox's maxscript (from [this post](http://forum.xentax.com/viewtopic.php?p=50401#p50401)) imports the meshes into Max more or less intact - so I dunno, on the basis that other tools are able to read the files it seems odd that the official ones can't. I have some GTA games in my steam library, maybe I'll install those later and see if I have any more success with the dff files from those.

I should probably also mention that there is source code for most of the viewers included in the SDK...
## Post #7
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-03-01T23:42:28+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

> Reply from arcs
>
> Turns out the PAL version of BR4 also contains the dummy directory with the SDK!
Seyiji wrote:I have no idea which viewer does what so when you find out please tell us 

Here's an extract from the chm file:

RenderWare Graphics has viewers for viewing models, streams and maestro. 

Clump Viewer for viewing .dff files 
Visualizer for viewing many types of RenderWare Graphics files 
World Viewer for viewing .bsp files 
Stream Viewer for viewing the contents of a binary stream files 
2d Viewer - a command line tool for use with Maestro.

Maestro seems to be associated with 2d menu items and such, so that's probably of less interest.

I unpacked the fpk with Noesis, but neither Clump Viewer nor Visualizer seem to be able to read the dff files that were output - "no clump loaded" & "error loading asset" errors given respectively.

However, steve-m's RW Analyze seems to be capable of reading them, and chrrox's maxscript (from this post) imports the meshes into Max more or less intact - so I dunno, on the basis that other tools are able to read the files it seems odd that the official ones can't. I have some GTA games in my steam library, maybe I'll install those later and see if I have any more success with the dff files from those.

I should probably also mention that there is source code for most of the viewers included in the SDK...

Here is the way to view the PS2 formatted dff models and animations (for the pc version you just drag in a ANIM file after you drag in the dff to see animations):
This is from RW\Graphics\docs\viewers\ClmpViewWrldView.pdf

On PlayStation 2 the viewer binaries are named clmpview_sky2.elf and wrldview_sky2.elf
To run the binaries you need to use a PC application that sends the viewer binary and your art assets to a PlayStation 2 development kit. This application is called pc-ps2d.exe
...
Use as follows in the commandline prompt:
pc-ps2d <hostname> clmpview_sky2d.elf yourfile.dff

where hostname is the IP address for the PS2 development kit.

Can someone with a PS2 Dev Kit test this (and also see what the arguments are for animations, because animations are viewable with PC formatted anim files)?
## Post #8
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2013-03-03T10:14:09+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

> Reply from FurryFan
>
> DOTAPRINCE wrote:Will this let us get the models perfectly from it or any renderware games?
 (In the United States all college students with an .edu email account can get a free limited version of 3d Studio Max).
I've known people who's gotten 3DS Max with just a regular professional e-mail address.
## Post #9
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-03-04T08:25:56+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

*Bumping* for subscribe to my interest list :p
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-03-04T17:22:05+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

When I run the sample ELF files on the PCSX2 Emulator, I either get the empty viewer, or I see some on screen geometry, such as a rotating ball, or special effects particles. The ELF viewers are meant to be burned to a disc, using the included IRX modules and other files that are supplied with the RenderWare SDK, When I burn them to an ISO image, most of the time PCSX2 crashes, but sometimes, I do get a display of the DISC on the memory card screen, which I do sometimes get, on a real PS2 console when a real PS2 disc has dust on it, or when using "Action Replay" or Gameshark or even an old "blue" PS2 CD (some low budget PS2 games are Blue CDs (and I do not mean the blue layer added by rental stores to discs to prevent theft)).

It is either me burning the ISO wrong, or because I am not using the official "Sony Image Burner" with official "Sony Hardware" which is mentioned in the manual.
## Post #11
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2013-03-20T11:40:16+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

'Tis sure is a bad way to leak confidential things. Wonder if it can import/export GTA model files properly... Kam's scripts seem to be a little crappy in some cases.
## Post #12
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-05-17T04:36:13+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

You can make ps2 iso's with CD/DVD-ROM Generator and iml2iso. I dont have them handy, sorry. It works something like this. [http://youtu.be/KzS88okFJSU?t=6m13s](http://youtu.be/KzS88okFJSU?t=6m13s)
## Post #13
- Username: aap
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 26, 2011 8:32 pm
- Post datetime: 2013-05-19T21:35:02+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

I'm wondering if anyone got the examples/viewers to work with pcsx2 or a regular ps2. I already found out the SDK was hidden on that disk a while ago but was always frustrated because I couldn't run most of the programs. So, does anyone know how to run this stuff on the ps2?
## Post #14
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-05-20T16:52:21+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

@aap yes, these should be working on a properly modified ps2 with a burned disc of your own creation. see my previous youtube link. I just tested the procedure with one of the examples that didn't work just running the ELF in PCSX2. Before it gave me the memory card screen from the BIOS. Now it gives me this  You will probably need a dummy file, try the ones from BR4, I hear it has RW SDK in it ;D

(edit)
you will need to create your own SYSTEM.CNF. The ELF file name MUST be in caps. Mine looks like this:

```
VER = 1.00
VMODE = NTSC

```
## Post #15
- Username: aap
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 26, 2011 8:32 pm
- Post datetime: 2013-07-01T14:10:13+00:00
- Post Title: RenderWare SDK Installer Included on BR4 Disc!

Have you by chance gotten the visualizer to work? The supplied iso didn't work (pcsx2 couldn't find the irx plugins, don't know if it worked better on my real ps2) so i built a new iso, from which pcsx2 and my ps2 could boot to a blank screen (it's supposed to show a splash screen). I could ping the ps2 but the visualizer couldn't establish a connection to the ps2. I'm suspecting I need a real debug or tool ps2 :/
## Post #16
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-24T02:41:34+00:00
- Post Title: Re: RenderWare SDK Installer Included on BR4 Disc!

-
## Post #17
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-07-24T17:17:24+00:00
- Post Title: Re: RenderWare SDK Installer Included on BR4 Disc!

> Reply from 41hc1
>
> I'm getting this error when I run the setup:

I don't have Maya or 3ds installed. Could that be the problem?

Do you think this would work with Manhunt 2? PS2 version uses DFF and PC version uses MDL.
That did not happen on my Windows 7 64bit computer. I do not have max nor maya installed.
Try this:
Copy the uncompressed files to your computer, and then run it.
You probably got an error because you tried to run it from the disc, and/or while it was still inside the zip file.
## Post #18
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-24T17:59:14+00:00
- Post Title: Re: RenderWare SDK Installer Included on BR4 Disc!

-
## Post #19
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-07-24T18:36:09+00:00
- Post Title: Re: RenderWare SDK Installer Included on BR4 Disc!

So did you try to run as administrator, or the compatibility options? Try that, and (though you may not like this), also try installing on another computer, and then if it installs there copy the installed folders to the computer you were having trouble with.
You REALLY need to try installing on another computer, so I can tell if it is you or your computer that is doing something wrong.
## Post #20
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-25T14:42:40+00:00
- Post Title: Re: RenderWare SDK Installer Included on BR4 Disc!

-
