## Post #1
- Username: Redead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 06, 2010 9:49 pm
- Post datetime: 2011-01-13T03:14:55+00:00
- Post Title: SNES Virtual Console PCM and BRR [Solved]

I would really like to know how I can patch the VC's raw PCM audio back into the VC rom. I was able to convert the raw PCM file into a WAV and then convert the WAV into a BRR file with snesbrr. However, the audio is all in a row (one after the other). You can see this if you've play the WAV file that I've included. The result BRR file is a bunch of files in one, but they do not include the loop or end flags. Those flags are included in the rom file that comes with the VC. The references to the PCM are in the rom file instead of the BRR audio.
The file references start with PCMF.

[https://github.com/Plombo/vcromclaim](https://github.com/Plombo/vcromclaim)

That application will take care of this issue and more!
