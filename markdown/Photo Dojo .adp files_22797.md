## Post #1
- Username: kkzero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 29, 2016 3:49 am
- Post datetime: 2020-10-09T23:00:44+00:00
- Post Title: Photo Dojo .adp files

Hello, I've been spending time researching my old save data from the DSiWare title Photo Dojo. In doing so, I've been trying to figure out the weird format used for the user-recorded voice clips, the one with the extension ".adp".

Here's what I've been able to gather so far:
-Each .adp file that is able to be created is the same size, 23.9KB, and roughly 2 seconds long.
-It is 3-bit mono ADPCM sampled at 16,384hz. The data gets decoded as raw 16-bit PCM during the game's boot process.
-It seems to be a proprietary format made for the game. The closest I've come to decoding it with an existing program is with Vox Studio's 3-bit Rockwell import option, which decodes it audibly, but obscenely noisily at that.
-There is no header/footer whatsoever--it goes straight into the ADPCM data from the start of the file up to somewhere before offset 0x3000. After that is a bunch of additional data that goes up to 0x5FE0. This data is different depending on which fighter the audio file is for. Perhaps it could be data used in the decoding alogrithm? Beats me.

I have included some example material of the file format in the following zip:


 0sound.zip
(90.17 KiB) Downloaded 16 times


 The contents are as follows:
0sound.adp - The 3-bit ADPCM sound file stored in the game's save data.
0sound.bin - The 16-bit decoded raw PCM of 0sound.adp, as extracted from a no$gba RAM dump. The raw PCM data starts at offset 0x1C, and ends at 0xFFBB right before the "RF" footer.
0sound.wav - The raw PCM data from 0sound.bin copy-pasted into a wav file, so you can hear what it's supposed to sound like in-game.

I'd try taking a crack at coding a decoder myself, but the whole ADPCM thing is currently beyond me, especially for an unknown format like this, so any external assistance in figuring this out would be appreciated.

(also enjoy the quality voice acting from me when I was 8 years old)
