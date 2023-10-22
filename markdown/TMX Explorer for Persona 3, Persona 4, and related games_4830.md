## Post #1
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-08-01T01:29:59+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

TMX Explorer 1.0

Update 10/14/2013: Lots of people keep asking me where to get this since my website went down a few years ago. Here you go: http://www.mediafire.com/download/3ibi3 ... plorer.zip

Note for anyone who was familiar with this tool in the original thread "TMX File Format Help," all releases will now be in this post, which will be updated as required.

Hello everyone, I had been posting this tool in another topic where we (and by "we" I mean mostly other people who I learned from!) basically figured out the TMX format. Instead of me making a new post in that mostly dead thread every month or so when I make a new release, I decided to incorporate all of that information over here. With that I proudly release TMX Explorer 1.0

Overall features
-Capable of opening and displaying 4 or 8 bpp TMX files, including stand alone TMX files and ones contained in BIN, CVM, or SPR files.

-Capable of exporting any of the aforementioned images into PNG format(including transparency).

-Code is as optimized as I (an admitted novice) can make it. Even reading CVM files is fast now.

Note: I know the directory navigation is a big sketchy. If you have some files you want to open in say a directory called "Persona 4 Data" then in the program you would navigate to that folder using the "SPACE" and arrow keys until you find the directory. Then when the "<---" cursor is pointing at the "Persona 4 Data" folder, you would push "ENTER." You would NOT push SPACE on the folder you want to open. Also for any that don't know ".." selection moves you to the parent directory of the current directory, I.E. one directory back. I know this is confusing, and I COULD change it, however I have gotten used to using the application in this way and I suspect maybe anyone else who has used it might have as well. Changing it after so many releases doesn't seem to be a great idea. Comments on this and anything else are appreciated!

Written in FreeBASIC 0.20.0

Small changes since 1.0
-Added ISO to allowed file types, so you can read TMX directly from the ISO of a valid game. Be careful with this because if you open some other ISO you'll be waiting a long time with little result. You can break from reads and exit with ESCAPE still.

-Minor code correction with likely no implications. 

Changes in 1.0:
-The position of some of the information displayed on screen was changed for better readability.

-It is no longer possible for file names to clash, the file names are now generated with (filename_image position within file) If the file clashes, underscores are added to the file name until it does not.

-I looked at more of the game data files in a hex editor and discovered SPR files also contain TMX graphics. Thus SPR was added to the list of allowed file extensions.

-You can now change drives in the directory explorer by pressing V. The interface is very simple, requiring you to type a new drive in the format C: - If the new typed drive is invalid, the application will silently return to where you previously were. This is because the only way I could have made an interactive list of drives to choose from was to include the Windows headers. Though I have not yet tried it since I don't have a working Linux box, the source should compile on Linux with zlib dependency. This attempt at portability is also why the directory navigation is as it is.

-Quick search is now fully implemented. While this is active for all file types, it has the most effect on CVM files. While files are still scanned "on the fly" for the TMX0 signature and TMX files, once a file has been found and loaded, its position is stored in an array. That way if you navigate away from it and back to it, it does not need to be scanned for again. This has less impact than I originally intended because of the next change listed, but it is still quite useful. This information is only saved PER CONTAINER FILE and PER SESSION. So if you load a different container or close the app, we start from scratch.

-Files are no longer read in 1 byte increments, they are now read in chunks based on the file size. This has the following effects: Reading small files(BIN,TMX,SPR) is slightly slower than it could otherwise be, but still much faster than 0.8 version. Big files(CVM) are many, many times faster than in 0.8

Also the memory usage for the application has changed because of this. What this means is that programs memory usage will very briefly increase from time to time as determined by this formula:

Base memory usage in MB + (0.005 * size of file being read in MB)

Base memory usage is around 6.5MB so for the Persona 4 DATA.CVM(2862.4 MB) the memory will briefly spike to:

6.5 + (14.312)

20.812MB

This is not a lot of memory by today's standards for sure, but it is roughly a triple increase on big files, so I thought I'd mention it.

-I added a catch all solution for cases where the program gets confused and wants to read strange data or the user opens a file of valid extension(such as BIN, a reasonably common extension) that is in fact not the kind of BIN from these games and thus contains no image data. In this case the application will present the error:
"Fatal error. Unable to find TMX signature. Exit in 5 seconds."
and properly terminate itself.

Important note: This error will happen when you reach the end of CVM files since I am still having trouble catching EOF on large files. So if you are viewing a CVM and get this message, you probably hit the end of file. I am working on this.

-I cleaned up the code as much as I could: Removed unused variables, fixed spacing and indenting, improved commenting etc.

Features new to 0.8

Major changes:
You can now directly open the CVM files without having to extract them with IsoBuster first!

Note: At the moment, this can be a bit slow. When you first load a CVM expect to wait 20+ seconds for the first image to appear. This is due to the large size of the CVM file (2 Gigabytes+ for some of them) and the fact it is being scanned per byte for the TMX0 signature. However, once you reach the first image and are using S/W keys to move around, the time in between images should be less than one second. If for some reason (I.E. you opened a 2GB CVM on a slow computer) you find it loading and loading and loading (there is a progress update on screen, so as long as it keeps updating the app is not locked), you can break out of the application with ESCAPE.

File name is no longer read from the container file as that was pretty sketchy anyway. It is now generated with this formula:

Container file name + position within container file + current date

Also, a feature was implemented that will prevent you from overwriting already exported files of the same name. If you push ENTER to save a PNG and get a RED message confirmation, the filenames clashed and you did not save the file. This would only happen if A - You already saved a PNG of that same file or B - If you did something unlikely, like opened the DATA.CVM from Persona 3, exported the 5th file, then opened the DATA.CVM from Persona 4 and tried to export the 5th file. Regardless, I would suggest you move your exported PNG files to somewhere other than the application directory after each use. For instance, if you extract a bunch of stuff from Persona 3, and then are going to extract a bunch of stuff from Persona 4, move the extracted Persona 3 stuff out of the main program directory before you move on to avoid clashes.

A quick searching feature is partially implemented to speed up reading of CVM files. Any TMX you have already navigated to within the CVM has its position stored (per session only!) so it is quicker when you navigate "backwards."

Minor Changes:
Should be faster, as files are no longer read from the start each time you move further in, the position is saved. This was necessary to allow efficient reading of large CVM files.

Changed the file index variable from a regular integer to an unsigned long integer. This was part of the reason I was having trouble reading the CVM files as their size was larger than the limit of the variable.

You can no longer select directories without valid files.

Instead of displaying a partial list of files a directory contains, you now either see the message:
"This directory contains readable files." in GREEN if the directory can be opened

or

"This directory does not contain readable files." in RED if the directory cannot be opened"

Known Bug:
I don't think the progress indicator that says "Reading byte X of Y" is correct, but really it's only there to assure the user the application is doing something and not locked.

Compatability:

Confirmed working with:
Persona 3: FES (confirmed by me)
Persona 3 Portable (confirmed by taleds)
Persona 4 (confirmed by me)

Disclaimer:
You use this at YOUR OWN RISK. The author disclaims any and all liability arising from any and all uses of this application.

License:
[http://myriaddreams.com/index.php?optio ... 4&Itemid=9](http://myriaddreams.com/index.php?option=com_content&view=article&id=4&Itemid=9)

Credits:
PersonaRipper for his help with some programming problems and providing me the source to his and bbrchers extractors which I converted to FreeBASIC code for large parts of the program
Simon Nash for FreeBASIC PNG Library and Jean-loup Gailly and Mark Adler for zlib library
taleds for the compatibility report for P3P

Request:
So far the TMX explorer has been successfully used with Persona 3, Persona 3:FES, Persona 3 Portable, and Persona 4. If you own another game which uses the TMX format and try this application, please let me know whether it works or not at my e-mail address which is in the about section of the program, or through a PM on this message board.

Screenshot:


Enjoy!

~Blyss

Download
Use the attachment or [http://myriaddreams.com/projects/applic ... plorer.zip](http://myriaddreams.com/projects/applications/TMX_Explorer.zip)
[TMX Explorer.zip](https://xentaxbackup.github.io/file/3291_TMX Explorer.zip)
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-08-01T02:45:52+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

> Reply from Blyss
>
> So far the TMX explorer has been successfully used with Persona 3, Persona 3:FES, Persona 3 Portable, and Persona 4. If you own another game which uses the TMX format and try this application, please let me know whether it works or not at my e-mail address which is in the about section of the program, or through a PM on this message board.TMX and variants are used in Atlus in-house developed games on PS2/PSP. P3FES/P3P/P4 are the only ones I've observed with the TMX format itself so far. The original P3 most certainly has TMX textures as well.

Persona Portable is a port of the PS1 game, which has TIM textures (PS1 format).
Trauma Team / Trauma Center, etc (Wii) have its own format (TPK, probably "texture package"), which is probably a variant of TMX.
Strange Journey (NDS) has another format (GFNT, GTSH).
Devil Survivor (NDS) probably has the same format as Strange Journey, though I have not bothered to write an unpacker for its data container (BIN, IDX, NDX).

I would imagine any other in-house developed PS2/PSP games by Atlus (such as Digital Devil Saga) would have TMX textures.

All of these games share other file formats (most notably, the scripting engine they use). I've been slowly working on these formats (BF, BMD, BM2).
## Post #3
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-08-01T17:41:47+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

That's good information, Rick. I am familiar with the TIM2 subset of the TIM format from my experiments with Ar tonelico 1 and 2. 

The TMX format as I've encountered it is simple enough, 16 or 256 color palette (the 256 color palette is tiled), and then the image is stored as a string of bytes from the bottom right to the upper left corner. So the only real tricks are the tiling of the palette and the fact the image is stored flipped horizontal and vertical.

They are often stored inside containers with BIN extension, which usually contain 2 or more related TMX files. I.E. One main character image and one small image of that characters eyes closed e.g. for blinking animations.

And the whole thing is stored inside files with the CVM extension, which as anyone who has tinkered with it probably knows can be opened with IsoBuster if you show all files in the open dialog box. Interesting question, is a CVM file really just a renamed ISO or similar, or is it just so similar to one that IsoBuster can open it? Actually I doubt it's a renamed ISO, I just looked an ISO and a CVM side by side in hex, and their headers at least are in no way similar. Maybe some other disc image format with a special extension then? I wonder. Maybe perhaps CVM is short for container volume or something. 

Anyway I have made some more updates which I will post later, as soon as I figure out how to get the enigmatic FreeBASIC "DIR" command to return drive volumes so you can select a drive to read from and thus allowing the TMX explorer to load TMX directly off of the original game disc.
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-08-01T18:37:49+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

> Reply from Blyss
>
> The TMX format as I've encountered it is simple enough, 16 or 256 color palette (the 256 color palette is tiled), and then the image is stored as a string of bytes from the bottom right to the upper left corner. So the only real tricks are the tiling of the palette and the fact the image is stored flipped horizontal and vertical.Yeah, I plan to eventually write some code that can load TMX files when I get around to it, been too busy with the scripts and other data.

> Reply from Blyss
>
> They are often stored inside containers with BIN extension, which usually contain 2 or more related TMX files. I.E. One main character image and one small image of that characters eyes closed e.g. for blinking animations.Yeah, I've encountered three glob bin formats that Atlus uses (BIN, ABIN, PAC, though they don't stay consistent in using those extensions) and wrote an unpacker which can handle them all.

> Reply from Blyss
>
> And the whole thing is stored inside files with the CVM extension, which as anyone who has tinkered with it probably knows can be opened with IsoBuster if you show all files in the open dialog box. Interesting question, is a CVM file really just a renamed ISO or similar, or is it just so similar to one that IsoBuster can open it? Actually I doubt it's a renamed ISO, I just looked an ISO and a CVM side by side in hex, and their headers at least are in no way similar. Maybe some other disc image format with a special extension then? I wonder. Maybe perhaps CVM is short for container volume or something.CVM is an earlier CriWare format. It does reuse an ISO standard to some degree, which is why IsoBuster can handle it, there's [a good page about the CVM format](http://www.gshi.org/wiki/CRI_ROFS) that describes it in detail.
## Post #5
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-08-01T20:51:00+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

Wow! You have a lot of really good information Rick. I have been working on the TMX explorer all morning and I have it reading CVM files MUCH faster, and I noticed many TMX images that I did not see when I was just reading BIN and TMX files. I know there are some PAC within the CVM and maybe these TMX are in there. I'll have to look into it and if so add the format to the list of allowed openable files. I am going to quit working on it for a while though, my head is so filled with code it is driving me nuts, I am stuck on three pretty elementary problems that probably have simple answers I may even think of once I walk away. The problems being:

A. Don't know how to generate a list of drives/volumes to allow drive changing with FreeBASIC code and don't want to use platform specific SHELL commands which just pass a command to the command prompt.

B. For some reason, I can't catch end of file on large files, no matter what I try it works fine on smallish < 512MB files but reads past end of file on larger files.

C. Before data was read and compared in 4 byte increments, with a new read for every compare. I realized I could buffer a larger amount of data and then compare in that, so maybe only 1 read for every X amount of compares. Problem is, this works fine with smallish data chunks (<208 bytes) but larger chunks like the 1024 (e.g. a kilobyte) chunk I want to use cause the application to become "offset" by 1 byte when reading BIN but not when reading CVM. Since they are handled the same, I am lost.

If anyone knows FreeBASIC (really any BASIC type language) and wants to take a crack at that, my post with code is:
[http://www.freebasic.net/forum/viewtopi ... 816#140816](http://www.freebasic.net/forum/viewtopic.php?p=140816#140816)

Lastly, thanks for the abundant good information Rick!

Edit: actually someone seems to have answered my question about end of file, but I am not messing with it now.

I will probably post an update in 1-2 days.

~Blyss
## Post #6
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-08-02T19:56:11+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

I have uploaded the very much improved and probably 40% rewritten TMX Explorer. The changes and the download are available in the first post.

Also @Rick:

I discovered TMX files hiding within SPR files in the Persona 4 Data.  I also looked at PAC, RMD, and myriad other files, many of which were container formats. Seems like they have quite a few. Also I tried to look at that page on CVM, but the link seems dead.

~Blyss
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-08-02T20:27:37+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

> Reply from Blyss
>
> Also @Rick:

I discovered TMX files hiding within SPR files in the Persona 4 Data.  I also looked at PAC, RMD, and myriad other files, many of which were container formats. Seems like they have quite a few. Also I tried to look at that page on CVM, but the link seems dead.

~BlyssSPR are basically TMX packages with additional metadata.
## Post #8
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-10T08:43:48+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

program shutdown with an error on 18 file deep in Persona 3 Portable
## Post #9
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-09-17T01:24:28+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

> Reply from sprayer
>
> program shutdown with an error on 18 file deep in Persona 3 Portable

Is it an error message generated by the program itself or Windows? I need as much info as possible because I do not have P3P myself.
~Blyss
## Post #10
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-09-18T18:51:34+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

program say "error occur and program will be shutdown in 5 sec" something like that
## Post #11
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-09-19T00:34:52+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

> Reply from sprayer
>
> program say "error occur and program will be shutdown in 5 sec" something like that
 That happens when the program cannot find the HEX(0x02) file start signature. The program attempts to set a variable pointing exactly to that signature for any given TMX file within a container, but for some reason in different types of containers that signature is offset from where my code expects it to be. To combat this, the program first looks where it expects to find 0x02 and if it isn't there, it tests the 10 bytes before and 10 bytes after the expected position. If it cannot find it at all, it generates the error message you see. I know this is a product of my weak programming skills but I can't seem to fix it completely. 

Lastly, I do not have P3P to test this myself, but I do have reports from other people saying that the program works correctly with P3P. It is possible you have a "bad" or simply different dump of the game than them.  For the record, TMX Explorer was not in any way designed to work with P3P, it just so happens that it does. Sort of, apparently. I have tested it extensively with P3:FES and P4 for the PS2. Sorry I can't be of more help,

~Blyss
## Post #12
- Username: Kinoli
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 20, 2011 8:08 pm
- Post datetime: 2011-01-20T12:14:26+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

Thank you for doing such work with the TMX^^

I'm in a translation team and we are translating Persona 3 FES to spanish, so we want to put all the accents our language has.

Thanks to your viewer I could extract the font (and modify it), but I want to ask if I could convert in TMX again.

Thanks again for all and keep the good work!!!
## Post #13
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-01-29T11:47:24+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

Just to give you a heads up, Catherine, a new game from Atlus, contains a new version of SPR/TMX files, I have not had a chance to look at them directly yet (working on script changes at the moment), here's a few samples.
[catherine.zip](https://xentaxbackup.github.io/file/3851_catherine.zip)
## Post #14
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2011-01-29T15:25:30+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

I took a real quick look at that, its all pretty foreign looking to me. I know there is no TMX anything signature in it. The only signatures that caught my eye were SPR0 and DXT5. Anyway my life has pretty much gone to hell, I haven't done any coding in quite a while. Maybe one day I'll take a look at it.
## Post #15
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-01-29T15:55:17+00:00
- Post Title: TMX Explorer for Persona 3, Persona 4, and related games

Ah so they're probably reusing SPR container for DDS textures then (the game has other DDS textures sitting around outside of SPRs).
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-29T16:50:07+00:00
- Post Title: Re: TMX Explorer for Persona 3, Persona 4, and related games

the game Catherine is using the nif file format.
so they are using the gamebryo engine.
## Post #17
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-01-29T17:02:50+00:00
- Post Title: Re: TMX Explorer for Persona 3, Persona 4, and related games

Yes, of course. It even shows that on startup. Aside from DDS/NIF they're still using the standard Atlus formats found in earlier games of theirs.
## Post #18
- Username: IronShoujo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 13, 2011 2:31 pm
- Post datetime: 2011-02-19T13:18:26+00:00
- Post Title: Re: TMX Explorer for Persona 3, Persona 4, and related games

-EDIT-

I just failed. Sorry about that. I hope you guys can manage to open the files. I've got the game already so if anyone needs any file in Catherine I'd be willing to share.

-EDIT 2-

Er.. I tried using NifSkope, I can only see the bones. I do see a bunch of files in the list on the bottom though. Textures and some other stuff.
