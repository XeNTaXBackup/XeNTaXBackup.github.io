## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-07-12T22:17:24+00:00
- Post Title: [PS2] Rayman Revolution *.VSC files

Hey,

I'd like to rip the music from Rayman Revolution for PS2. This game uses BF files to store its data - for example, the music is stored in an 1,8GB file named VSC.BF. Those BF (=BigFile) files are actually just uncompressed data stacked together, and Rayman Revolution's programmers made it really easy to split them again: in a separate text file, they included the filename, start offset and size of each separate file that was merged into the BF file. This made it really easy for me to obtain the files inside the BF, all named from BNK_0.VSC to BNK_121.VSC. I can confirm I split them correctly, because they don't start in the middle of a track when played with VGMStream. Here's a sample.

Sample file: http://www.box.net/shared/b2fh39bjaibxnfqhxala

Now, as the "BNK" in the name suggests, those files are sound bank files. This means that while they contain music, they are not audio formats but "collections" of multiple segments, along with the directions for the game when and in which order they should be played.
They are uncompressed, as the audio plays perfectly as PS2 ADPCM (tested with VGMToolbox). The problem is, the game uses segments and there is a pause after every segment. This can get really annoying as the segments are sometimes only a second long. And no, there is no ADPCM decoder that can magically split those segments. The only way is to actually extract the segments from the sound bank files... the proper way.

So, this is my request: I would like something to extract the ADPCM segments from the VSC files. It would extract all the segments separately, without the null data (=the pauses) and, if possible, with the filenames (the filenames would help greatly when recombining the segments).

Hope you can help! 

Thanks!
Droolie.
