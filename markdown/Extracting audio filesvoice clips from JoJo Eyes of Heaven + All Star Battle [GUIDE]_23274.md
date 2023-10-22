## Post #1
- Username: QuasiDetective
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2019 11:01 am
- Post datetime: 2021-01-07T19:27:00+00:00
- Post Title: Extracting audio files/voice clips from JoJo: Eyes of Heaven + All Star Battle [GUIDE]

EDIT 2: Below is the extraction guide of Eyes of Heaven. For All Star Battle's extraction guide, see this post: [viewtopic.php?f=21&t=23274#p171183](https://forum.xentax.com/viewtopic.php?f=21&t=23274#p171183)

EDIT: I've figured out how to extract all of these in playable forms, so I'll explain how I did it for other people who are interested! Note that this was all done with the PAL PS4 version of JoJo's Bizarre Adventure: Eyes of Heaven, though this process should work with other versions of the game as well as other CyberConnect2 games that use the same formats.

SOFTWARE USED:

YACpkTool
VGMToolbox (for ACB/AWB archives)
HxD (though any hex editor should work just as well)
QuickBMS (for XFBIN files, using one script, found below)
foobar2000 (+ vgmstream component)

PROCESS:

When you start off, you should have a few CPK files from the game. These are CriWare pack files. If you drag and drop a CPK onto the executable for YACpkTool, it will extract them to a new subfolder named after the CPK itself, in the folder where the CPK is.

The CPK files we are interested in for this process are:

sound0.cpk: contains BGM (in ACB/AWB format) and general battle/common sound effects (in XFBIN format)
sound1.cpk: contains sound gallery voice clips and all main story mode voice clips (all in ACB/AWB format)
stream0.cpk: contains character combat voice clips (e.g. attack noises, pain sounds) (in XFBIN format) and in-game character voice clips (in ACB/AWB format)

ACB/AWB Archives

To rip audio from ACB/AWB archives (another CriWare format, seemingly specifically as audio banks):

Open VGMToolbox.
In the side panel, under the "VGMToolbox" section, open up "Misc. Tools" -> "Extraction Tools" -> "Common Archives".
Select the "CRI ACB/AWB Archive Extractor".
Drag an ACB file (NOT THE AWB! The ACB file has all the file names and whatnot, so it must be used instead) onto the blank space of the window.
VGMToolbox should extract the files to a subfolder within the folder where the ACB was.
Inside should be HCA files. You can open these in foobar2000 if you've installed the vgmstream component.
By right-clicking on a file/files you've selected in foobar's playlist, you can select convert and convert them all to generic WAV files for use/conversion in other programs.

XFBIN Files

This is where the process gets a little tricky. XFBIN files are used all over this game as general containers. Most people seem to believe that it is not possible to rip audio from the audio container variants, as they use NUS3BANK containers, but... honestly, I'm not sure where that information came from. The raw file data for each audio file is just kind of in here, and you can yank it out with certain BMS scripts, for example.

As far as I can tell, audio-XFBIN files in this game contain two filetypes: BNSF (a Bandai Namco sound format) and AT3 RIFF (a compressed Sony audio format).

To check if a particular XFBIN file has either one of these, open it in HxD (or any other hex editor) and Find (Ctrl + F) both "BNSF" and "RIFF". If you find either one, it should be an audio-XFBIN, and should work with the following BMS script.

To export BNSF & AT3 files from XFBIN archives with their original file names, first copy this BMS script (by [DKDave](https://zenhax.com/memberlist.php?mode=viewprofile&u=9272)) into a TXT or BMS file and save it to your computer.

```
# JoJo's Bizarre Adventure: Eyes Of Heaven
# XFBIN extract
# QuickBMS script by Dave, 2021
# ================================================================================

IDString "NUCC"

FindLoc OFFSET String "TONE" 0 ""

If OFFSET = ""
	Break
Endif

Goto OFFSET
Get JUNK Long

FindLoc TONE_TABLE String "TONE" 0 ""				# 2nd occurence is the actual file table

If TONE_TABLE = ""
	Print "File table not found"
	Break
Endif

Goto TONE_TABLE
Get JUNK Long

FindLoc PACK_DATA String "PACK" 0 ""				# audio data

If PACK_DATA = ""
	Print "Data block not found"
	Break
Endif


Goto TONE_TABLE
Get JUNK Long
Get JUNK Long
Get ENTRIES Long
SavePos TONE_ENTRY

For A = 1 To ENTRIES
	Goto TONE_ENTRY
	Get INFO_OFFSET Long
	Get INFO_SIZE Long
	XMath INFO_OFFSET "INFO_OFFSET + TONE_TABLE + 12"
	Goto INFO_OFFSET
	Get FILE_TYPE Short
	Get JUNK Short
	Get JUNK Long
	Get TEXT_LEN Byte
	GetDString FILENAME TEXT_LEN

	Padding 4

	Get JUNK1 Long
	Get JUNK2 Long

	If FILE_TYPE = 0xFFFF
		Get OFFSET Long
		XMath OFFSET "OFFSET + PACK_DATA + 8"
		Get SIZE Long

		If SIZE > 0
			Goto OFFSET
			GetDString FILE_ID 4

			If FILE_ID = "BNSF"
				String FILENAME + ".bnsf"
			Elif FILE_ID = "RIFF"
				String FILENAME + ".at3"
			Endif

			Log FILENAME OFFSET SIZE

		Endif

	Endif

	Math TONE_ENTRY + 8
Next A
```


Once you have the BMS script saved, the extraction process can begin:

When prompted by QuickBMS, select the TXT or BMS file you saved DKDave's XFBIN script into.
Select the XFBIN archive that contains BNSF/AT3 files that you want to extract.
Select the folder you wish to extract the files into.
Voila! It should dump the BNSF and/or AT3 files with their original names. (If it says 0 files found, confirm that the XFBIN file you are extracting from does in fact have BNSF and/or AT3 files).
You can open these BNSF/AT3 files in foobar2000 if you've installed the vgmstream component.
By right-clicking on a file/files you've selected in foobar's playlist, you can select convert and convert them all to generic WAV files for use/conversion in other programs.


That should be all! If I missed anything or if you have any questions, feel free to ask and I'll try my best to help out.  

Here are some sample files:
"battle.xfbin", which contains both BNSF files and AT3 files: [https://mega.nz/file/mG4VUQgK#q5rAlcbRd ... wDote33VxA](https://mega.nz/file/mG4VUQgK#q5rAlcbRdiBGfjZkJ4yEKmnAry7fQ0elxwDote33VxA)
"gimmick.xfbin", which only contains AT3 files: [https://mega.nz/file/KagVTKIR#-BxBhOySC ... X2AJDODEsk](https://mega.nz/file/KagVTKIR#-BxBhOySCT8Vxwxqbr7ID5cScuHvnW_NEX2AJDODEsk)
## Post #2
- Username: QuasiDetective
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2019 11:01 am
- Post datetime: 2021-02-07T18:29:14+00:00
- Post Title: Extracting audio files/voice clips from JoJo: Eyes of Heaven + All Star Battle [GUIDE]

EDIT: I've figured out a rough method to export from All Star Battle, so here's a guide for that. This was tested with files from the NTSC and PAL versions of the game on PS3, and might work with other CyberConnect2 games released around the same time (ex. Naruto Shippuden: Ultimate Ninja Storm 3), however this hasn't been tested.

SOFTWARE USED:

YACpkTool
VGMToolbox (for ACB/AWB archives)
naru_nub (for XFBIN files)
NUBExt (for NUB files exported with naru_nub)
HxD (though any hex editor should work just as well)
Notepad (though any similar plain-text editor should work just as well)
One batch script (found below)
One Python script (found below, for Python 2.7, though it may work with later versions as well)
foobar2000 (+ vgmstream component)
PROCESS:

When you start off, you should have a few CPK files from the game. These are CriWare pack files. If you drag and drop a CPK onto the executable for YACpkTool, it will extract them to a new subfolder named after the CPK itself, in the folder where the CPK is.

The CPK files we are interested in for this process are:

sound.cpk: contains every sound file in the game (in XFBIN and ACB/AWB archives). Located in data\cpk_sound.
ACB/AWB Archives

To rip audio from ACB/AWB archives (another CriWare format, seemingly specifically as audio banks):

Open VGMToolbox.
In the side panel, under the "VGMToolbox" section, open up "Misc. Tools" -> "Extraction Tools" -> "Common Archives".
Select the "CRI ACB/AWB Archive Extractor".
Drag an ACB file (NOT THE AWB! The ACB file has all the file names and whatnot, so it must be used instead) onto the blank space of the window.
VGMToolbox should extract the files to a subfolder within the folder where the ACB was.
Inside should be HCA files. You can open these in foobar2000 if you've installed the vgmstream component.
By right-clicking on a file/files you've selected in foobar's playlist, you can select convert and convert them all to generic WAV files for use/conversion in other programs.
XFBIN Files

This is where the process gets pretty, uh... well, messy. These XFBIN files, unlike the ones in Eyes of Heaven, are encrypted. This means we need to rely on tools to decrypt them: namely, naru_nub and NUBExt.

As far as I can tell, audio-XFBIN files in this game contain only one filetype: BNSF (a Bandai Namco sound format). However, these are encrypted within NUB files, and there are several archives here that don't include audio. The ones that contain audio should be in the sound\data\sound\PS3 or sound\data\sound\PS3\JP (or sound\data\sound\[system]\[other language] if the game is on other platforms and has other languages, I presume) folder.

First, drag and drop an XFBIN onto naru_nub's executable. This should output a NUB file of the same name in the location of the original XFBIN file.
For this next step, I would recommend placing this NUB file into a separate folder. Place NUBExt's executable into the same folder as the NUB file(s) you want to extract from. It/they should show up in the list in the bottom left-side box.
Click on the NUB file that displays in this box (if you are doing multiple at once, check the "Process whole list" option in the Options section (found at top right-side)).
The Info section (bottom right-side) should show that it has found files to export if the NUB file contains BNSF files.
If so, click the button labeled "Split NUB file", and it will then dump all of the BNSF files it can find inside the file into the same folder as the NUB and itself are in.

Now, you might notice that the BNSF files that are output are a) named based on the NUB instead of their proper names and b) not all likely to play in foobar. We will return to b) later. For now, let's focus on the names.

If you're fine with the files being named after the NUB, then you can skip this section.

Naming the BNSF Files

Unlike with Eyes of Heaven, which kept the list of BNSF file names in the XFBIN alongside its contents, All Star Battle puts the file names into another folder entirely. This file is located in sound\data\sound, and is named sndcmnparam.xfbin. This file is not encrypted, however, and you can read the filenames inside. Though, it's a bit of a pain in the rear...

So, in order to rename the files, we have to skim the info in sndcmnparam.xfbin for the file names we're looking for. Then, we either need to rename all of the files manually or, perhaps a better option, automate the process of renaming them.

Here is a batch script that reads from "names.txt", which should be a list of file names one after another, each on a new line. Copy this script into a plain-text word processor like Notepad and save it (as a .bat file) in the folder with the BNSF files you want to rename.

```
setlocal EnableDelayedExpansion

rem Load the list of authors:
set i=0
for /F %%a in (names.txt) do (
   set /A i+=1
   set "name[!i!]=%%a"
)

rem Do the rename:
set i=0
for /F %%a in ('dir /b *.bnsf') do (
   set /A i+=1
   for %%i in (!i!) do ren "%%a" "!name[%%i]!.bnsf"
)

pause
```


Then, we can start the renaming process:

Open sndcmnparam.xfbin in a hex editor of your choice (I recommend HxD). The right-hand column should display the raw text data for the hexadecimal data to the left.
Skim the raw text until you find the file names for the file you want (this may require guessing, as BNSF file names do not follow their XFBIN sources in the list... They are, however, listed in the same order as the files are exported in).
Copy all of the file names for the files you want to rename and paste them into a plain-text word processor (e.g. Notepad).
Make sure that every individual file name is on its own line. Do not leave any blank lines.
It may help to use a line counter to match with the total number of BNSF files you have. Here is an online one you can paste your list into: https://www.tools4noobs.com/online_tools/count_lines/. Make sure that the number of lines matches up with the total number of BNSF files you want to rename. (Note: certain characters may have less BNSF files than others. It is fine to use the full list used on other characters: it should still match up and it will simply stop renaming when it runs out of files.)
Save your list of file names as "name.txt" in the same folder as the BNSF files and batch script.
Double-click on the .bat file, and it should rename all of the BNSF files according to their position in the folder and a position on the list.

Now that that nightmare's covered, let's cover another: the fact that some of these files won't load in foobar.

Truncating the BNSF Files

I believe it is NUBExt that has this problem: when the BNSF files are exported from the NUB archives, some of them are exported with a little bit of null data at the end. Often this is about 8 bytes of 0x00, but sometimes it's a little more. One way to fix this is to manually remove 8 (or 12, depending) bytes from the end of the file with a hex editor. However, I find this to be very time-consuming.

As such, I have written a simple Python script to remove 8 bytes from the end of a BNSF file if it detects the file ends with 8 bytes of 0x00. This is my first attempt at writing a Python script, so go easy on me if I made some mistakes. It seems to work, anyway.

Copy the following Python script into a plain-text word processor (or code editing software, e.g. Visual Studio) and save it as a .py file in the folder that the BNSF files you want to repair are in. (You don't need to separate them from ones that work in foobar, as this script won't touch ones that it doesn't need to fix).

```
# 2021.02.09
# Aims to fix BNSF files exported by NUBExt that have empty bytes at the end and therefore won't play in foobar2000.
# Place this script as a .py file into the folder with BNSF files you want to scan/truncate.
# Please make backups of the BNSF files if you want to revert any changes or in case there is an issue!

import os
import binascii
import sys

for fileO in os.listdir('.'):
    if fileO.endswith(".bnsf") and os.path.isfile(fileO):
        with open(fileO, "rb+") as f:
            print("File: %s" % str(fileO))
            f.seek(-8, os.SEEK_END)
            bytr = binascii.hexlify(f.readline(8))
            print("File position: %s" % str(f.tell()))
            print("Last 8 bytes of file: %s" % str(bytr))

            if bytr == '0000000000000000':
                print("BNSF file is too long!")
                sizeb = os.path.getsize(fileO)
                print("Full size of file in bytes: %s" % str(sizeb))
                sizeE = sizeb - 8
                print("Size of file - 8 bytes: %s" % str(sizeE))
                f.truncate(sizeE)
                print("BNSF file truncated to proper length.\n")
            else:
                print("BNSF file should work!\n")

            f.close()

try:            
    done = input("Truncation complete. Press any key to exit.")
except EOFError:
    done = "\n"
finally:
    sys.exit()
```


Then, simply double-click the .py file you've saved to run it. (KEEP IN MIND THAT THIS REQUIRES PYTHON 2.7! I have not tested it with newer Python versions.)

If BNSF Truncator runs properly and detects BNSF files in the folder it's in, it will scan the last 8 bytes of each one.
If the last 8 bytes of any file is 0x00 eight times, it will remove the final 8 bytes.
You can open these BNSF files in foobar2000 if you've installed the vgmstream component.
If certain BNSF files don't load (foobar says they're "corrupted"), then open them into a hex editor and try removing the last 4 bytes if they're also 0x00 (I've only found that I needed to do this with stage mob voice clips). Upon being reimported into foobar, they should then work fine.
By right-clicking on a file/files you've selected in foobar's playlist, you can select convert and convert them all to generic WAV files for use/conversion in other programs.

The process is a mess, but it gets the job done.   

Here are some sample files (including sndcmnparam.xfbin, where the filenames are stored): [https://mega.nz/folder/DCJjAA7I#68-IPASdbPvvMWXixh3LUQ](https://mega.nz/folder/DCJjAA7I#68-IPASdbPvvMWXixh3LUQ)
