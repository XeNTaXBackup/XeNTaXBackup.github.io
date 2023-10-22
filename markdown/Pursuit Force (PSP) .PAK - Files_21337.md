## Post #1
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-03T23:34:30+00:00
- Post Title: Pursuit Force (PSP) .PAK - Files

Hey Guys,
I stumbled across a video that said that it would be super easy to rip psp models......sadly its like with almost every game: the archive is special....
After searching for a while I found a quickbms script for Motorstorm: Arctic Edge


 MotorstormArcticEdge_PSP_pak.zip
(670 Bytes) Downloaded 34 times



The game was produced by the same developer, but it doesnt work on the pursuit force .pak file.
I was hoping that theres only slight differences and it can be opened easy by using the motorstorm script as a reference.
Heres a download link for the pak-file: [https://we.tl/t-x8Y7lMBBOR](https://we.tl/t-x8Y7lMBBOR) (The link will only work for 7 days!)
So I kindly ask anybody for help and a updated script to unpack its contents.
Thank you for listening
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-05T11:01:51+00:00
- Post Title: Pursuit Force (PSP) .PAK - Files

Try this QuickBMS script:


# Pursuit Force - ALL.PAK extract
# By Dave, 2019

IDString "\x02PAK"

Goto 0x4
Get ENTRIES Long
Set FILE_TABLE 0x8C
XMath TEXT_TABLE "FILE_TABLE + (ENTRIES * 0x10)"

For A = 1 to ENTRIES

	Goto FILE_TABLE
	Get OFFSET Long
	Get SIZE Long
	Get MISC1 Long
	Get TEXT_OFFSET Long
	Math TEXT_OFFSET + TEXT_TABLE
	Goto TEXT_OFFSET
	Get FILENAME String

	Log FILENAME OFFSET SIZE

	Math FILE_TABLE + 0x10

Next A
## Post #3
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-11-05T16:36:30+00:00
- Post Title: Pursuit Force (PSP) .PAK - Files

Thank you so much for giving this a shot!
Whenever I try to use the script on the All.PAK quickbms gives me this error:


EDIT:
I`m a fool......i used an old version of quickbms ^^ It works fine with the most recent.

THANKS SO MUCH AGIAN MAN!


 pursuitforce_PAK.zip
BMS-Script for Pursuit Force .PAK (408 Bytes) Downloaded 52 times


I packed your script in a .bms so its easier for everybody to use
## Post #4
- Username: UTV
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 02, 2023 9:03 pm
- Post datetime: 2023-04-02T13:35:17+00:00
- Post Title: Pursuit Force (PSP) .PAK - Files

Hi!
Pardon me for replying to this old post but could use a help with a similar problem.
It's related to the sequel, Pursuit Force: Extreme Justice.
Was trying to extract the cutscene files specifically.
For a reference, cutscenes from the previous game were located in a separate folder (PSP_GAME/USRDIR/MOVIES)
In the sequel however, they seem to be located inside the MAIN.PAK file (PSP_GAME/USRDIR/MAIN.PAK)
Here's a link for the .PAK file from that game: [https://www.dropbox.com/s/wmyau9loethhh ... k.zip?dl=0](https://www.dropbox.com/s/wmyau9loethhh94/pfextremejusticepak.zip?dl=0)
I know what to do with the .pmf video files, just could use a help with their extraction.
