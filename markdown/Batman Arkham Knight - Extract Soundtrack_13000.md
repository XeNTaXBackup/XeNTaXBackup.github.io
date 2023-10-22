## Post #1
- Username: pjxentaxpj
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 25, 2015 1:02 am
- Post datetime: 2015-06-27T23:03:02+00:00
- Post Title: Batman Arkham Knight - Extract Soundtrack

Greetings, first post here.

Would like to share the steps that I took in order to extract Arkham Knight's soundtrack, which was only possible due to research from other posters and tools from this forum.

The process is not perfect, the extracted files don't have proper file names, and the music comes in bits (some tracks don't have percussion, which is stored in a separate track) due to how it's stored and used in the game, with the dynamic music. However, this process still allows extraction and conversion to playable formats.


Tools needed:
Batman Arkham Knight
[batman_bnk](http://forum.xentax.com/viewtopic.php?f=17&t=12934), kindly provided by daemon1 from this forum.
[RavioliGameTools](http://www.scampers.org/steve/sms/other.htm#ravioli_download)
[ww2ogg](http://www.hcs64.com/vgm_ripping.html) and packed_codebooks* files that come with it. I used version 0.22.
[revorb.exe](http://www.hydrogenaud.io/forums/lofiversion/index.php/t64328.html) to fix .ogg files having no time information.

The steps:

Extract "Music" file from inside SFX_1.wad:
Music is located in file:
<Main Game Folder>\BMGame\CookedPCConsole\SFX\SFX_1.wad

Put batman_bnk and banklist_knight.txt (that came inside batman_bnk's .zip) in the same folder as SFX_1.wad. (I recommend creating a separate temporary folder and copying SFX_1.wad and all others that will be further mentioned there, easier to manage and helps prevent accidents in the game folder).

Open a command line, navigate to the folder you've copied. 

Run the following command: batman_bnk SFX_1.wad banklist_knight.txt

This will extract all sound files inside SFX_1.wad. I believe all music is stored inside a single extracted file called "Music", haven't checked any of the many others. You can look at a listing of tracks inside the SFX*.wad files if you open file "AudioWad_SFX.log" that resides in the same folder.

If you want, delete all files except "Music".

Extract RavioliGameTools, and open RScanner or RExplorer, any will do. These will help extract all the tracks inside "Music" file, which are in .wwise format.

Drag and drop "Music" file into RScanner, let it process. Extract all .wwise files to a folder.

Now we convert the .wwise to .ogg using ww2ogg. Copy ww2ogg and packed_codeblocks* to the same folder as the .wwise files. To convert in a batch, type:

for %a in ("*.wwise") do ww2ogg.exe "%a" --pcb packed_codebooks_aoTuV_603.bin

This will take a while, and will convert .wwise to .ogg files that you can now play. However, they have no time signature information, so you can't seek in them or know their duration. Now copy revorb.exe to that folder, and run:

for %a in ("*.ogg") do revorb "%a" "out_%a"

This will create files "out*", which now have time information. You're done! Delete all files except these ones.


Hope this works for you, and is helpful. This beautiful soundtrack, and previous soundtracks from the Arkham games, deserve to be fully appreciated, inside or outside the games.
## Post #2
- Username: moppsbreak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 09, 2015 8:19 pm
- Post datetime: 2015-08-09T13:36:51+00:00
- Post Title: Batman Arkham Knight - Extract Soundtrack

Hello pjxentaxpj

I tried this tutorial but unfortunately it didn't work out for me 

Maybe I'm a bit stupid here but e.g. the txt file in the bnk.zip archive isn't called banklist_knight.tct but hashlist.txt I tried to rename it but when I run the commandline I get the error message "file not found". All in all I'm a bit desperate and I don't know what to do. With another tool I manged to extract many wem files but I can't decode them in a common audioformat. Do you ahve any hints for me? I would really appreciate soem help
## Post #3
- Username: MikeManiac61
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 17, 2015 12:17 pm
- Post datetime: 2015-08-17T05:02:08+00:00
- Post Title: Batman Arkham Knight - Extract Soundtrack

I'm trying to do everything but nothing is working for me. Is it possible someone can upload this somewhere?
