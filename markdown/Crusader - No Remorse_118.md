## Post #1
- Username: Roswell
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-01-23T20:45:57+00:00
- Post Title: Crusader - No Remorse

I used your software to extract Crusader sound.flx file.
It found about 500 files and I selected Extract All
but when I get in the selected directory there was only 
*.mex files  

Q: How to convert them to *.wav files?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-24T07:43:01+00:00
- Post Title: Crusader - No Remorse

It depends. The files are .MEX files, because the FLX format has no filenames stored in the archives. They can be all kinds of sound files then, I don't remember what the sound format is in SOUND.FLX files from Crusader : No Remorse. It's been long. Anyway, you can try to rename all of them into .WAV files and open them with a good sound player. Perhaps they are by chance WAV files, but I don't think so, based on the age of the game, from the DOS era, so it's more likely they are in a different format. Open one of them with a good Hex-editor and check for identity strings at the start of the file. When I have time, I will check myself as well, if I can find the game somewhere.
## Post #3
- Username: Roswell
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-01-24T11:27:10+00:00
- Post Title: Crusader - No Remorse

The begining of file looks like :

ASFX.J..........

but i can't find an asfx to wav convertor
sfx2wav says "Incorrect SFX format"

Any idea on file format or convertor I can use
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-24T12:04:17+00:00
- Post Title: Crusader - No Remorse

I don't know which sound editor you have, but if you have something like Cool Edit you can open raw sounds and specify the format. 

The format I found closest to the true format is 
pcm, 
8bit, 
mono, 
signed 
11025 Hz 

If you open the .mex files with these settings they should work.
## Post #5
- Username: letoII
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 29, 2003 4:24 pm
- Post datetime: 2003-05-29T08:34:19+00:00
- Post Title: Crusader - No Remorse

There is a sound converter program, converts all kinds of files, you have to read the documents carefully though, its very confusing at first...

try going through each of the formats until you get the right one

[http://sox.sourceforge.net/](http://sox.sourceforge.net/)
## Post #6
- Username: paulus
- Rank: n00b
- Number of posts: 17
- Joined date: Thu May 13, 2004 6:49 am
- Post datetime: 2004-05-13T22:59:21+00:00
- Post Title: Crusader - No Remorse

hi, you can also try settings in goldwave, and awave (anawave) supports loads of formats, and i many cases is cabable of identifying the format for you
