## Post #1
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2021-05-19T20:52:28+00:00
- Post Title: Sonic Generations modified .ar.00 files

I've been scratching my head over a problem with this somewhat old game.
Usually you'd extract the various .ar.00 files using the [https://github.com/sonicretro/Generatio ... ive-Editor](https://github.com/sonicretro/Generations-Archive-Editor) or ar0unpack.exe
Then go on to import .model files and whatever else with their respective scripts.

However, these .ar.00 archives I'm looking at have an "MSCF" in their header, signalling a Microsoft CAB compression. 
- So far no CAB tools I've tried could extract these either. 
- The usual modding tools will throw errors due to the first 12 bytes being different from the expected header content.
- still, the modified .ar.00 files work fine in the game itself

I suspect the compression was added by some mod repacker tool. Can anyone with more experience regarding compression formats tell me if there is any chance of tackling this stuff? 

Sample file link:
[https://mega.nz/file/cqgQRaSa#k84DfpAhN ... I_9RRcae98](https://mega.nz/file/cqgQRaSa#k84DfpAhNsywO5YShv9icucxQITsW6gZkI_9RRcae98)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-19T21:26:25+00:00
- Post Title: Sonic Generations modified .ar.00 files

It doesn't look like a 'proper' MS CAB file, as you say.  You can use the attached script to decompress the file.  This only contains 1 file.  I'm not sure if there are some archives with more than 1 file, so this might need updating in that case.


 sonic_mscf.zip
(361 Bytes) Downloaded 49 times
## Post #3
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2021-05-19T21:37:42+00:00
- Post Title: Sonic Generations modified .ar.00 files

Holy shit, didn't expect a reply so fast. Thank you very much!

For anyone wondering what to do after running the quickbms script above, here's the last steps to make it work:

1) rename the file output bla.ar_dec back to bla.ar.00
2) open with hex editor, change the following offsets: 0x04 -> 10 | 0x08 -> 14
  the first few bytes of the file should now look like "00 00 00 00 10 00 00 00 14"
3) open with Generations Archive Editor as usual

thanks again and happy modding
