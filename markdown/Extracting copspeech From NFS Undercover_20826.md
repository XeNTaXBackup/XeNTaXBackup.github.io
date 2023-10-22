## Post #1
- Username: WDMv2
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 26, 2018 11:41 am
- Post datetime: 2019-07-18T02:57:34+00:00
- Post Title: Extracting copspeech From NFS: Undercover

Hello.

I'm trying to extract the audio files from the copspeechdat_en.big and copspeechsth_en.big files contained in Need For Speed Undercover (PC).

I tried running  NHL 07-06 ASF Player on it but it gave me 0 results. This worked on NFSMW (2005) but for some reason it's not working with this one. I'm still new to extracting files. What else do you think I can try? Is there a script available I don't know about perhaps?

Am I even looking in the right place? I want to get the police scanner speeches used by the cops, so I assume it's in copspeech files to begin with.
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-07-19T18:47:04+00:00
- Post Title: Extracting copspeech From NFS: Undercover

This QuickBMS script should extract the files from the archive.  You can then use a program called "EALayer3" to decode the audio files.


# Need For Speed: Undercover - .BIG file extract

Endian big

Idstring "BIG4"

Goto 0x08
Get ENTRIES Long

Goto 0x10

For A = 1 to ENTRIES

	Get OFFSET Long
	Get SIZE Long
	Get FILENAME String

	Log FILENAME OFFSET SIZE

Next A
## Post #3
- Username: WDMv2
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 26, 2018 11:41 am
- Post datetime: 2019-07-20T02:38:36+00:00
- Post Title: Extracting copspeech From NFS: Undercover

Thank you. Will have a go at it.
## Post #4
- Username: WDMv2
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 26, 2018 11:41 am
- Post datetime: 2019-07-23T07:33:36+00:00
- Post Title: Extracting copspeech From NFS: Undercover

Should have posted back sooner but your script did the trick. It's also possible to do using a quickBMS .big script.
## Post #5
- Username: FelipeGamer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 09, 2022 2:45 am
- Post datetime: 2022-05-08T18:55:02+00:00
- Post Title: Extracting copspeech From NFS: Undercover

Could someone help me extract the audio files from need for speed undercover copspeechdat_en.big I tried to use the NHL 07-06 ASF Player on it but it didn't work I also tried using QuickBMS but it didn't work it kept giving error all the time I also used EALayer3 and it was also not be someone can help me extract the audios of copspeechdat_en.big and copspeechsth_en.big contained in Need For Speed Undercover I appreciate not being able to extract them if anyone can help I await the answer.
