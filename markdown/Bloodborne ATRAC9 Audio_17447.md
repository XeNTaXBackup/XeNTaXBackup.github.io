## Post #1
- Username: aldem
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 07, 2017 4:57 am
- Post datetime: 2017-12-22T23:50:51+00:00
- Post Title: Bloodborne ATRAC9 Audio

I have spent some time looking into the audio files for Bloodborne which were recently decrypted and have made a quick tool that's able to extract the audio files from the FMOD sound banks (FSB5) and reconstruct their ATRAC9 headers.

I found some good information on the FSB5 header structure in a binary template file made by Simon Pinfold for use with the "010 Editor" hex editor, but it doesn't have anything about the ATRAC9 headers. ([https://gist.github.com/synap5e/3ff84ce731c3ee1afe2e](https://gist.github.com/synap5e/3ff84ce731c3ee1afe2e))

I found detailed information about the ATRAC9 headers in the documentation that came with the leaked PS4 SDK.

I am by no means a good programmer, so if the code is horrible, that's why. I compiled it using g++ (gcc) on windows with cygwin. The cpp file is attached.

It takes one input, which is the .fsb file (must be FSB5; there are a couple FSB4 files in the Bloodborne sound files that will not work with this program) and outputs all of the .at9 sound files contained therein. Some of the header info is probably not correct, but these files will still decode using at9tool (found in the PS4 SDK). There's more work to be done to make this tool complete, but it's a good starting point. Someone else could probably write a better tool.

Examples:
[https://clyp.it/ifho5eiz](https://clyp.it/ifho5eiz) unused audio for the blood minister
[https://clyp.it/5fwtvrla](https://clyp.it/5fwtvrla) gascoigne saying "umbasa"; previously heard in that network test video from before the game's release

Thanks.
[getFSB5Header.zip](https://xentaxbackup.github.io/file/13726_getFSB5Header.zip)
## Post #2
- Username: Sanadsk
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 20, 2014 5:25 am
- Post datetime: 2017-12-23T09:24:39+00:00
- Post Title: Bloodborne ATRAC9 Audio

Thanks so much for this! We have been waiting a long time for this.
I have uploaded all of the unused dialogues in a video:
[https://youtu.be/uM2K-ue_2k0](https://youtu.be/uM2K-ue_2k0)
