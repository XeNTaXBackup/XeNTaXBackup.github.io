## Post #1
- Username: matty45
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Sep 06, 2018 7:29 am
- Post datetime: 2019-11-02T01:08:19+00:00
- Post Title: Headhunter (Dreamcast) .AHF file

Headhunter on the dreamcast has these .AHF files which seem to be packages that contain audio, textures and models.

It would be nice if anyone could have a look at them.

Samples: [https://drive.google.com/file/d/1midlxK ... p=drivesdk](https://drive.google.com/file/d/1midlxK7tagPHS5yvYhALvi2yl_KEQcxO/view?usp=drivesdk)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-11-02T23:36:23+00:00
- Post Title: Headhunter (Dreamcast) .AHF file

Try this QuickBMS script:

# Headhunter (Dreamcast)
# By Dave, 2019

IDString "AHFF"

Goto 0x0008
Get ENTRIES Long
Get NAME_SIZES Long
Math NAME_SIZES + 0x10

For A = 1 to ENTRIES

	Goto NAME_SIZES
	Get FILE_ENTRY Long
	Math FILE_ENTRY + 0x10
	Goto FILE_ENTRY
	Get OFFSET Long
	Get SIZE Long
	Get MISC Long

	Get FILENAME String

	Log FILENAME OFFSET SIZE

	Math NAME_SIZES + 4

Next A
