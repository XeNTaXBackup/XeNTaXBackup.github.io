## Post #1
- Username: pendeho
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 20, 2017 3:20 am
- Post datetime: 2017-02-19T20:22:17+00:00
- Post Title: Getting WAV files from Moto Racer to play

Hey guys,

Amazing forum, just found out about it seconds ago while googling for solution to my problem here. I just had a fit of nostalgia and wanted to get some sounds from this game for my phone, and I managed to extract it from BKF.

I have plenty of WAV files in 8-bit and 16-bit folder now, and they are properly named so my guess is this are the files that contain one of those sound effects. The thing is they don't play in WinAmp or any other player.

So I went to Audition and tried "Import Raw" but no matter what option I choose, I get buzzing noise. I presume I would need to know exact properties of the wav to get it to play, sample rate, encoding? I did set the byte order to Little-Endian (as per this page [http://wiki.xentax.com/index.php/Motoracer](http://wiki.xentax.com/index.php/Motoracer)) but that didn't help. 

I don't know if this is "illegal" - but here's one of the wav files from the extracted BKF. If this is not permitted I will delete it from Dropbox immediately. [https://dl.dropboxusercontent.com/u/47884416/YEAAH.WAV](https://dl.dropboxusercontent.com/u/47884416/YEAAH.WAV)

Thanks for any ideas on tackling this problem
## Post #2
- Username: Dosia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 20, 2018 3:52 am
- Post datetime: 2018-03-19T20:41:46+00:00
- Post Title: Getting WAV files from Moto Racer to play

Hello! Same here, nostalgia!    Sorry for my bad english, I'm from Russia.

I had the same question as you and tried to import these sound files with audacity. I was looking for the answer in internet and I've found this topic. I tried many options and got buzzy noise too. Then i tried to open the file (16_bits\voices\ouch.wav) with winhex. The header of this file is custom (not like WAVE's 0x52494646) and i haven't found any information about the format of the file. Then i tried to plot a graph that represents the audio data. I assumed that this is a wav-like raw audio format (PCM, with some kind of header), so i tried to get something that may look like an oscillogram of this audio signal, with some garbage in the beginning, of course (header, format, etc). I wrote some script in MathCad 15. The screenshot is attached. 



I open the file as binary with data format "uint16, big endian". And i skipped some bytes from the beginning. On the graph i noticed some kind of sawtooth pattern at those timings when the sound should be silent (in the beginning and middle of the file). And then I assumed that the interesting audio signal is layed on the sawtooth pattern (maybe some technical solution for playing audio in far 90's, idk). I generated an array with the pattern, then I tried to subtract my array from the initial audio data array. I skipped some bytes in the file to perfect, sample-to-sample alignment of my sawtooth pattern and the pattern in the initial file. 

I found that the saw repeats every 32 samples and the "height" of the sawtooth is 32x2048=65536 (obvious, the file resolution is 16 bits after all   ). After subtraction i got silence for the first few samples, and then got the desired signal. Then I cut this array to delete the first few samples and saved the array as .wav file with resolution of 16 bits and 4800 samples/sec. I tried to select the proper sample rate few times. 4800Hz works fine (This may be a standard frequency like 48000, 9600, etc). Now i can play this file with any player or convert it to .mp3 or other formats. 

However, for various files from this folder you must tune the parameters of the arrays (how many bytes do you cut to synchronize your pattern with the pattern in the file). For ouch.wav I had 71 bytes to cut. I didn't research the formula for the number of the bytes to cut, i made it manually for few files that i needed.

Hope I helped you. Best regards, Alexander.
