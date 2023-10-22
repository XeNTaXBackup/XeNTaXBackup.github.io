## Post #1
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-01-10T01:14:00+00:00
- Post Title: [Updated] XWC File Comparison (Starbreeze Engine)

[Note, this post is now updated with more current findings. I've since made progress in extracting the complex sound information, so I'll provide an update on that later as well.]
[I've written a decompiler and have recompiled this 'source' into a working XWC file. This post is no longer really relevant]

I'm curious if anyone can help me in either finding the differences between different XWC files, or a way to recover a series of values stored within the compiled XWC.

XWC files contain both the raw audio files (wavs that have been re-encoded into ogg files in the case of PC releases), as well as additional information for 'complex sounds' which further modify playback (including values for pitch, volume, and radius). Applications such as Dragon Unpacker can extract the audio data fine, but not the other information. If you load a XWC file in a hex editor, you can see the complex sound information towards the bottom.

I've recently discovered how old format XWC files can be compiled from source, and noted that a file with a single complex sound loads in the editor, while one with two or more does not. The goal is to either make these XWC files with more than one sound read in the editor, or find a way to deconstruct the complex sound values (pitch, volume, radius) so that I can create a workaround.

[Edit: I've made progress on this and am now able to decompile/recompile all the complex sound information. Will add details later]
## Post #2
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-02-21T16:39:26+00:00
- Post Title: [Updated] XWC File Comparison (Starbreeze Engine)

I'm now offering a bounty for information or success with this. Refer to [this topic](http://forum.xentax.com/viewtopic.php?f=10&t=11236) for more information.
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-21T17:31:03+00:00
- Post Title: [Updated] XWC File Comparison (Starbreeze Engine)

The biggest (and possibly only) difference I've noticed is the 2000-byte padding in the Enclave file starting at offset 0x30. I would have checked if deleting this would make the file load but none of the versions of Ogier work for me  whenever I try to load a sound file it gives me a "memory could not be read" error.

Also it might be necessary to adjust some of the pointers inside the file.
## Post #4
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-02-21T18:39:42+00:00
- Post Title: [Updated] XWC File Comparison (Starbreeze Engine)

> Reply from barti
>
> The biggest (and possibly only) difference I've noticed is the 2000-byte padding in the Enclave file starting at offset 0x30. I would have checked if deleting this would make the file load but none of the versions of Ogier work for me  whenever I try to load a sound file it gives me a "memory could not be read" error.

Also it might be necessary to adjust some of the pointers inside the file.

If you could upload or e-mail me the modified file I could give it a try as well. (I'll send my e-mail address via PM)

Although unlikely to be the cause of the error, I believe XWC files need to go into ..\Sbz1\Waves to be loaded as well.
## Post #5
- Username: Amran
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 01, 2010 1:53 pm
- Post datetime: 2014-05-07T03:13:04+00:00
- Post Title: [Updated] XWC File Comparison (Starbreeze Engine)

A secondary option has come up!

XWC files contain 'complex sound' information along with the actual audio files. This information consists of values relating to the pitch, volume, near and far range of each sound. If it's possible to read these four values in any way, I would actually be able to reconstruct the sound files in a working form. (Though a lot of work, it would solve the problem.) Currently it's possible to see some of the complex sound information if a XWC file is opened in a hex editor (towards the bottom), but not these values.

I have updated/rewritten the first post with more current and focused information.

Below is an example of what a XWC files source looks like before being compiled. Check the first post for downloadable examples of source and their resulting XWC.

```
{
	Log("-------------------------------------------------------------------");
	Log("Reading waveforms...");
	XWC_Begin();


	// -------------------------------------------------------------------
	// Waveforms (WaveName, Filename)		Supported: WAV, SND, SMP, RAW
	// -------------------------------------------------------------------
	XWC_AddWave("Rock_Big01"		, "WAVE\\Events\\Rock\\Rock_Big01.wav");
	XWC_AddWave("Rock_Big02"		, "WAVE\\Events\\Rock\\Rock_Big02.wav");
	XWC_AddWave("Rock_Big03"		, "WAVE\\Events\\Rock\\Rock_Big03.wav");
	XWC_AddWave("Rock_Big04"		, "WAVE\\Events\\Rock\\Rock_Big04.wav");

	Log("Parsing SFX descriptions...");


	// -------------------------------------------------------------------
	// Sound descriptions:
	// 		 	SoundName	, WaveName								, Prior	, Pitch	, RndAmp, Volume, RndAmp, Max/Min Distance
	// -------------------------------------------------------------------
	XWC_AddSFXDesc("Rock_Big01a"		, "Rock_Big01"		, 0	, 100	, 0.0, 0.9, 0.0	, 1500, 128);
	XWC_AddSFXDesc("Rock_Big01b"		, "Rock_Big01"		, 0	, 80	, 0.0, 0.9, 0.0	, 1500, 128);

	XWC_AddSFXDesc("Rock_Big01r1"		, "Rock_Big01;Rock_Big02;Rock_Big03;Rock_Big04"		, 0	, 100	, 0.0, 0.9, 0.0	, 1500, 128);
	XWC_AddSFXDesc("Rock_Big01r2"		, "Rock_Big01;Rock_Big02;Rock_Big03;Rock_Big04"		, 0	, 80	, 0.0, 0.9, 0.0	, 1500, 128);


/*
Notes / Comments:
*/


	// -------------------------------------------------------------------
	Log(XWC_GetNumWaves() + " Waveforms.");
	Log(XWC_GetNumSFXDesc() + " Sounds.");
	XWC_End("Events_Rock.XWC");
}

```
