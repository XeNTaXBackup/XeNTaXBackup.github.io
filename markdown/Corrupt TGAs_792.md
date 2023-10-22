## Post #1
- Username: Nohbody
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-06T08:18:05+00:00
- Post Title: Corrupt TGAs?

Greetings;

I downloaded Multiex 4.00 and was working on the MW4 Mercenaries Tesxtures.mw4 file.

Multiex has no difficulty viewing the "archive" but cannot seem to extract anything,well it extracts but the file shows up blank if I try to save, and if I preview it says its corrupt."Adobe photoshop could not parse the file."

The version of mercs I am running is MP1.1, that is MekTek expansion 1.1.

Thoughts?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-06T10:56:48+00:00
- Post Title: Corrupt TGAs?

I created it with the trial version of MW:MERCS. 

1. Make sure to ignore "File ascending check" in Options. 
2. Realise that some of the files in the mw4 files are compressed using a method I don't know. MultiEx can extract them, but viewing them as TGA files will not work, because they should be inflated first. 

Extraction should work. Also, set the autopreview option ON, and browse through the archive. Some TGA files will be shown, these are the ones that are not compressed.
## Post #3
- Username: Nohbody
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-06T17:08:56+00:00
- Post Title: Corrupt TGAs?

Thanks Mouse for the fast reply, I think your the first coder? Ive ran across that doesnt have a god complex.

Anyway I have a theory regarding Mw4.

You said that your extracting script is based off of the trial version of mercs which had a more complicated engine then the retail version.

or if you are familiar with the game, pre PointRelease1.

Pre Pr1 and Pr1 utilized strictly miscrosoft compression techniques.
But I believe not all of MS's files inside the core,textures and props.mw4 were compressed.Specifically most of the .tga files.

Then comes MekTek, who for all intents and purpose raw hacks the game.They are able to get inside the .mw4 files and alter those very same uncompressed files but to keep there work quiet they utilize their own compression technique, hence why your program cannot extract alot of the .tga files that it seems it should.The compressed them not because they had to but because they didnt want someone else going behind them and doing what they did.

So heres my thought.

Install a fresh Mw4 mercs,inspect the .mw4 files.See what files are uncompressed and able to be altered, compare to MP1.1 version.If secured in newer version.Alter them in the fresh install then patch to present.My thought is that the MP1.1 security doesnt check the specific files they now have compressed,that it just assumes that they are unaltered.Which would allow editing of files not currently editable.

I dunno, any thoughts?
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-07T06:48:15+00:00
- Post Title: Corrupt TGAs?

Yes, you are right to say that there are compressed files, (in the Script - scripts - .. thread I reported that the support was not 100% in MW4 files, as I did not know the compression method.)

I still have not figured out them. It might be, though, that they use some kind of RLE compression technique, as we are talking about TGA files, and I have read somewhere (I believe on MekTek sites) that they talk about RLE compression and TGA files. That compression technique is not so complex, as it will only shorten repeats of a certain character to three variables. Like : AAAAAAAAAAABBCDE would become X A 11 BBCDE (X telling the decruncher to expect a repeat, A the repeated character, and 11 times). But there are many ways to implement such a compression technique, as the order and magnitude of the variables may vary. 

What you say is interesting though, if all they did was compress files that have already been published uncompressed in MW4 files, then theoretically you could simply replace the compressed files with the uncompressed files. I am not sure if that would be all they did, surely they also added new files?
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-12T11:26:00+00:00
- Post Title: Corrupt TGAs?

did you ever find a way to look at the tga files
## Post #6
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-12T11:26:54+00:00
- Post Title: Corrupt TGAs?

did you ever find a way to look at the tga files
## Post #7
- Username: Nohbody
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-07-17T17:38:02+00:00
- Post Title: Corrupt TGAs?

Yes I did.

Extraction as well as viewing.
## Post #8
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-15T22:19:09+00:00
- Post Title: Corrupt TGAs?

can you share it with the rest of us ????

> Reply from Nohbody
>
> Yes I did.

Extraction as well as viewing.
