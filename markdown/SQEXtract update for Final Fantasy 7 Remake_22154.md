## Post #1
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-05-15T18:25:12+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

I anyone wants it, I've updated old SQEXtract tool to rip SAB audio files from UAssets and added support for MAB as well.

Just give it a path or place into the directory with UEXP files and it will try and extract them all. A tad slow but no biggie.

[https://www.dropbox.com/s/rzjhnhp5lk8ry ... RT.7z?dl=1](https://www.dropbox.com/s/rzjhnhp5lk8rymt/SABMABRipRT.7z?dl=1)
## Post #2
- Username: R5GAMER
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Jun 08, 2015 5:41 am
- Post datetime: 2020-08-03T19:27:37+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

Is possible to extract on KH3 ? Because is working with BGM but SE (Weapon & other) he showing :
No known SAB/MAB header.
## Post #3
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2020-08-03T19:30:29+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

I thought KH3 had plenty of tools developed for it, huh.
Do you have an example file you are trying to extract? If it is an UE's uasset then I need both *.uasset and *.uexp and if there is any - *.ubulk
## Post #4
- Username: Bobbyboy88
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 16, 2021 6:45 am
- Post datetime: 2021-02-17T13:56:25+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

Hello! I'm a complete noob with no experience, and no access to the game.

Am I reading this right that you're able to extract audio files from the game? Does that mean, for example, individual voiced dialogue for each character?

Apologies, but this post is one of the only references I've found online to FF7R audio - I'm trying to figure out if the voice files are readily obtainable or if its a pipe dream... please let me know, thanks.
## Post #5
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2021-02-17T14:41:01+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

> Reply from Bobbyboy88 ↑Wed Feb 17, 2021 9:56 pm at Wed Feb 17, 2021 9:56 pm
>
> 
Hello! I'm a complete noob with no experience, and no access to the game.

Am I reading this right that you're able to extract audio files from the game? Does that mean, for example, individual voiced dialogue for each character?

Apologies, but this post is one of the only references I've found online to FF7R audio - I'm trying to figure out if the voice files are readily obtainable or if its a pipe dream... please let me know, thanks.

Is the tool not dowloadable for you?
## Post #6
- Username: Bobbyboy88
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 16, 2021 6:45 am
- Post datetime: 2021-02-18T14:34:14+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

I didn't try - I thought it's the tool to be used on the game folder, and I don't have the game... I believe I know of people that do and have been extracting models from it, so I was just trying to understand if I've understood what this tool does and it'd be straight forward to ask them to fish out, say, all voice audio for a particular character, or if its not possible or just very complex.
## Post #7
- Username: Kein
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Nov 06, 2009 7:57 pm
- Post datetime: 2021-02-18T16:32:40+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

You just need the files, the tool will process them
## Post #8
- Username: ardivian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 29, 2022 10:08 pm
- Post datetime: 2022-06-29T18:23:23+00:00
- Post Title: SQEXtract update for Final Fantasy 7 Remake

New to this, but after a few/way too hours of research and trying things, I figured out that once you process using the file above to get the SAB from the Unreal assets you can open them in [Foobar](https://www.foobar2000.org/) as long as you have the [vgmstream component](https://github.com/vgmstream/vgmstream/releases/download/r1745/foo_input_vgmstream.fb2k-component) installed for it. It will process the SAB and you can see all the goodies inside of it. Yuffie's vo-asset had 331 audio files that I was able to convert to mp3 as a test.

Sorry for the necro, but I wanted to post this info in case someone from the Steam release gets the same idea after hearing Yuffie hum the victory fanfare. Trying to use cmd prompt for vgmstream test.exe was only extracting a single 22kb of audio from the voice over SABs I extracted, so then I went down the rabbit hole.
