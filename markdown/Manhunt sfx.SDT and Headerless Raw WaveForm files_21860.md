## Post #1
- Username: KarmaKrow
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Feb 06, 2020 6:58 am
- Post datetime: 2020-03-09T22:28:10+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

Hello there, I'm looking for the voice sfx used in a hidden message, that plays out on the main menu screen for Manhunt PS2.

I have reason to believe that they could be stored in some files found within said game, under the name(s): "SFX0.Headerless Raw WaveForm, SFX0.SDT, SFX1.Headerless Raw WaveForm, and SFX1.SDT." Is there any way at all that I can extract/convert those 2 specific file formats to a playable audio format, such as wav?

Here's a shareable link for the folder containing the SFX files I'm talking about:

[https://drive.google.com/open?id=1yXs0I ... Ql6psAvYme](https://drive.google.com/open?id=1yXs0Ij6PQVjh0QpJAmTAY2Ql6psAvYme)

(May have to copy and paste into google search)
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2020-03-11T18:27:39+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

Hello, attached is your solution.

Download QuickBMS:

[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Download latest "test.zip" of vgmstream:
[https://github.com/losnoco/vgmstream/releases](https://github.com/losnoco/vgmstream/releases)

Run the BMS script opening the SDT as your INPUT ARCHIVE. Note: The *.raw file must be in the same folder as the SDT. Script should output a few hundred "*.sdtaud" files. Wherever you output those to, make sure your you put ".sdtaud.txth" in the same folder. Make sure the dot is in front of it, or it will not work. Drag and drop sdtaud onto test.exe and it will convert. Have fun.


 set_sdtraw.zip
(752 Bytes) Downloaded 20 times
## Post #3
- Username: KarmaKrow
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Feb 06, 2020 6:58 am
- Post datetime: 2020-03-14T00:57:45+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

Yeah, there was a wee-bit of a problem Pingu. the sdtraw.bms didn't extract properly from the zip folder, but the txth file did. So, I don't at all know what's wrong here exactly.
## Post #4
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2020-03-14T23:26:44+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

I don't understand but here's the raw script code:

```
open FDDE RAW 1
get ARKSIZE asize 0
xmath FCOUNT "ARKSIZE/0xC"

for i = 0 < FCOUNT
	get OFFSET long 0
	get SIZE long 0
	get NULL long 0
	set NAME string ""
	string NAME p "%s_%s.sdtaud" BASENAME i
	log NAME OFFSET SIZE 1
next i 

```


Copy and save in text file for bms script.
## Post #5
- Username: KarmaKrow
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Feb 06, 2020 6:58 am
- Post datetime: 2020-03-15T02:53:43+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

alright, worked out pretty well indeed, thanks. Only one problem, the sound effects sound all high pitched for some reason, like the high pitch voice cheat from Manhunt itself. Is there something wrong here?
## Post #6
- Username: KarmaKrow
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Feb 06, 2020 6:58 am
- Post datetime: 2020-03-15T02:58:30+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

Here's an example of one of the file's I'm talking about, so you can understand what I mean:

[https://drive.google.com/open?id=1kXgiY ... vH2_N9b-JB](https://drive.google.com/open?id=1kXgiYn_0cLPcdaDsbYp1ICvH2_N9b-JB)

(May have to copy and paste link into google search.)
## Post #7
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2020-03-15T16:40:06+00:00
- Post Title: Manhunt sfx|.SDT and Headerless Raw WaveForm files

Yes you need to change the sample rate value within the txth itself and mess around with it until you get the right one. Not all of them are going to be at the same sample rate. I would've been able to pull the proper ones had it been stored in the files, but they were not. Just fiddle around with the value until you get the right pitch.
