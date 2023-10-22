## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-07-29T21:02:17+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

Ok, I know, another request from me, just somthing I thought I'd dig up, it's an oldie alright, it is a space shooter back from way then that just recently DosBox now supports. The closest thing to supporting it is Dragon Unpacker from back when I requested it, but that support got buggy somehow. In any case here is one of the GLs, broken up thanks to WinRAR.
[crusader.part1.rar](https://xentaxbackup.github.io/file/780_crusader.part1.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-07-29T21:03:59+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

Second part of RAR here. I wonder if there is a faster way than having to break them up? O_o

Edit: I'm in no hurry at all, I'm just quite interested, and it seems to have it's own texture format.
[crusader.part2.rar](https://xentaxbackup.github.io/file/781_crusader.part2.rar)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-08-01T18:24:28+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

Ok, found a place for the big files.

This is NSP4D.GL, the largest archive file for Star Crusader: [http://www.yousendit.com/transfer.php?a ... FC4E326AFA](http://www.yousendit.com/transfer.php?action=download&ufid=993DDCFC4E326AFA)

I'm not too sure what it contains, but what it seems to have is some WAVs but other than that it seems to have the largest portion of data, anything from textures to perhaps the main scripts. Whatever it contains, it is plenty large.

Edit: Ok I take that back, the BRIEFSND.SL is the largest. O_o But I know what that is I believe. The voices during briefing, I think o_O.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-10-19T23:38:55+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

I know this is a topic kick, I may reupload the big file if it is neccesary. I do not know if there is any compression. Not sure. Originally Dragon Unpacker's author looked into it. Ever since the silence it has been unable to read these datafiles.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-20T09:27:07+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

```
# by Mr.Mouse
# There is something odd at the back of the GL file 
# I investigated. There is a pointer to a tail, 
# along with the number of filenames, that fits the 
# tail section starting from the pointer nicely.
# However, before that pointer there seem to be 
# two more entries that overlap the others. 
# Interesting eh?
Get FNUM Int 0 ;
SavePos TailOffOff 0 ;
Get TailOff Long 0 ;
GoTo TailOff 0 ;
SavePos NO 0 ;
Math FNUM -= 1 ;
For T = 1 To FNUM ;
GoTo NO 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
GetDString FN 8 0 ;
SavePos NO 0 ;
Get SF Long 0 ;
Math SF -= FO ;
Log FN FO SF FOO 0 ;
Next T ;
# The final file 
GoTo NO 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
GetDString FN 8 0 ;
Math TailOff -= FO ;
Log FN FO TailOff FOO 0 ;

```


This will open and extract resources from that first GL file you attached. 

The picture data does seem compressed, and the format of the pictures is not clear to me, but then I'm no expert. The logo picture for instance is 320x200, that I can gather from the header of the file. And menuart has a number of pictures saved in there, of at least 16x16.
[gl.zip](https://xentaxbackup.github.io/file/940_gl.zip)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-25T19:24:30+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

By the way, I noticed you can also open some of the other files inside GL archives with this script. They have the same format. So, you can open "sound" from the NSP3D.GL file and listen to the sounds. And open "music" to extract midi tunes. Just rename them to <name>.mid and listen.

The .DAT files are actually DOS executables compressed using PKLITE. I don't know what they do in the game.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-03-28T00:19:08+00:00
- Post Title: Star Crusader (WIN95/DOS) Archive Formats (GL, PAK, VL, SL)

Been a while, sorry, but I finally got back to this.

Yeah, up until Star Crusader support became corrupted in Dragon Unpacker it would recognise the gl extension files within SC. Hm...

Ok, I found the purpose of the DAT files, I used UNP v4.11 to decompress a few and found they refer to the contents of the GL files with extensions. I do believe the DAT executables serve as data handlers and thus is their purpose.

The images I am uncertain of but I'll see what some of the image gurus here can figure out on it. 

> Content of NSP3D.GL as explained in NSP2D.DAT and much inspection by myself.
>
> 
>
> shapes.gl - 3D Meshes.
>
> textures.gl - textures for each ship.
>
> art.gl - Artwork other than textures, likely brief screens?
>
> vnfs.gl - Uncertain but has somthing to do with 3D objects, perhaps data on the objects such as strength?
>
> 3dscript.ptf - text file
>
> windress.gl - space background textures
>
> sound.gl - Contains standard RIFF WAV files for sound commons in gameplay like lasers and explosions. 
>
> faces.gl - Faces of people in the briefings and etc
>
> music.gl - standard MID files.
>
> boom1.gl - explosion animation?
>
> boom2.gl - explosion animation?
>
> boom3.gl - explosion animation?

I'll check into more of the datafiles later and produce more explanations.

Oh and thanks Mr. Mouse. This is pretty great! Right now I'm attempting to figure out what kind of textures this game uses. Considering the game uses MIDI and WAV files... hm... I'll go get a second opinion on this. O_o

All I've realised in images is that they end in 12345..etc and ABCDEF..etc serving purposes I have no clue about.

> Crusader.gl contents explained... sorta
>
> 
>
> logo.??? - SC image
>
> menuart.??? - SC image
>
> newfont.gl - (FONT.[fnt?] and IMAGE.??? [images of the fonts?])
>
> missions.??? - Mission data.
>
> rooms.gl - Rooms. Contains SC images.
>
> specs.tf - Ship specs file. What shows up in it's infoscreen.
>
> sb-main.mid - Sound Blaster version of main music.
>
> sC-main.mid - Sound Canvis version of main music.
>
> PDB.(tf or ptf) - Alien biographies/weapon info/etc
>
> MBSCRIPT.(tf or ptf) - Main Briefing Script
>
> pal_3d.(pal?) - Palette
>
> empire.??? - Unknown
>
> rebel.??? - Unknown
>
> debrief.gl - Contains 2 image files (cave and new)

Also I came across that the cinamatics used ingame are FLC and can be played on Quicktime.
