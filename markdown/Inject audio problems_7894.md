## Post #1
- Username: bien1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 02, 2011 6:17 pm
- Post datetime: 2011-12-19T19:40:56+00:00
- Post Title: Inject audio problems

Hello there

I used dragon unpacker to extract the *.wav files within a file. but when using the wave injector by class/backslash I get an error it says so:
"file has changed size during wav-mp3-wav".
I used nero aac encoder and decoder to compress. File size changes   

can anyone help me?
## Post #2
- Username: bien1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 02, 2011 6:17 pm
- Post datetime: 2011-12-24T18:44:42+00:00
- Post Title: Inject audio problems

anyone?
## Post #3
- Username: aeon
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 14, 2006 8:20 pm
- Post datetime: 2011-12-28T19:31:07+00:00
- Post Title: Inject audio problems

anyone understands?
## Post #4
- Username: rambohazard
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 27, 2009 9:33 am
- Post datetime: 2012-07-15T21:12:29+00:00
- Post Title: Inject audio problems

Size changes because the conversion. You can only inject the wavs back if the size be the same, or you have to rename each individual file with the size in hexadecimal. I make a little app in C# to do this work for me. I will try to explain. The ripped wav (ripped with dragon unpacker with the correct settings) are named like this: Stream.pak_0000000FC34B_00000867BD9F0.wav.
First you have to remove the "extras" zeros from the files (all of them) using some multi renamer (like Total Commander).
Next, find a way to rename all the files, getting each hexadecimal sizes and replacing the last string chain. The structure name is:

Stream(Filename).pak(Format Source)_0000000FC34B(Offset in Hexadecima)_00000867BD9F0(Size of wav, must rename in Hex to, after encode-decode).wav(Format file)

Hope this help.
Sorry for my bad english, am brazilian.
