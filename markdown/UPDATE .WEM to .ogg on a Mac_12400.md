## Post #1
- Username: AlphaCenturia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 17, 2014 8:57 pm
- Post datetime: 2014-12-17T13:02:47+00:00
- Post Title: <UPDATE> .WEM to .ogg on a Mac

Hi guys, I'm new here, and I know there are already threads out there about .WEM to .ogg convertion, but the problem is that those guides are for Windows users. I tried finding a guide that is tailored for the Mac, but with no luck. They say it is easy but I have downloaded several audio converter but they don't support .WEM files.

The files I am talking here now are .WEM files from the game Alien Isolation, so I have sorted them out now but I just have to get them converted. There must be a way, so please help me out with this one. THANKS IN ADVANCE!



-AlphaCenturia
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2014-12-18T08:03:28+00:00
- Post Title: <UPDATE> .WEM to .ogg on a Mac

Mac's are in minority so nobody(?) has ported over the windows converter and trying generic audio converters on closed source format of wwise's (wem) is pointless.
## Post #3
- Username: AlphaCenturia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 17, 2014 8:57 pm
- Post datetime: 2014-12-18T13:16:07+00:00
- Post Title: <UPDATE> .WEM to .ogg on a Mac

> Reply from Apollo
>
> Mac's are in minority so nobody(?) has ported over the windows converter and trying generic audio converters on closed source format of wwise's (wem) is pointless.

So I guess the only option is to use a virtual machine to use those Windows-only converter to convert those WEM files? Can be done, but I was hoping for a more simple solution...thanks anyway.
## Post #4
- Username: AlphaCenturia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 17, 2014 8:57 pm
- Post datetime: 2014-12-19T15:44:13+00:00
- Post Title: <UPDATE> .WEM to .ogg on a Mac

So I got Parallels 10 for my Mac, and running Windows XP as a virtual machine. I followed the steps to convert WEM files to ogg, but nothing happened.

I looked through various sites and all showed the same guide, to make sure I did it right, but my WEM files are still not converted.

Extract from the forums:

Guide: Converting .wem to .ogg
1. Go to the folder where you have your *.wem files.
2. Download ww2ogg019.zip and revorb.exe. Extract the ZIP archive. Then copy ww2ogg.exe, packed_codebooks_aoTuV_603.bin and revorb.exe into the folder with your *.wem files.
3. Now create a new text document in this folder, rename it to convert.bat. Open this .bat file with notepad, then copy & paste the following lines. Then save and close Notepad.

Code:
for %%f in (*.wem) do ww2ogg.exe %%f --pcb packed_codebooks_aoTuV_603.bin
pause
for %%f in (*.ogg) do revorb.exe %%f
pause
4. In the folder, double-click on the .bat file. Now you will find—in addition to your .wem files—.ogg files in the folder. These files can be played in any .ogg player. I recommend foobar2000 as it is easy to create playlists there, but any other programs (except Windows Media Player) will work as well.

PLEASE HELP!!! THANKS!
## Post #5
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2014-12-29T10:42:39+00:00
- Post Title: <UPDATE> .WEM to .ogg on a Mac

Well, was there any error reported on the first step that would be good starting point to know.

Unfortunately since I do not own the game (or Mac with emulator either...)  I can not test if there is actual problem with the files or otherwise in dos/windows emulation.

The guide is perfectly correct way to do it in windows however despite how crude it is given dos batch appliance and as far it stands, your mostly on your own I am afraid unless get someone with actual windows set up do it if emulator isn't up to the task.
