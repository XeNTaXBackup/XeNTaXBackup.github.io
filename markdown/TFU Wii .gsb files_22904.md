## Post #1
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-26T18:44:29+00:00
- Post Title: TFU Wii .gsb files

Hey,

I'm trying to rip the dialogue files from the wii version of the force unleashed, but I can't manage to get anything out of these .gsb files. The hex editor shows a SB01 header, whatever that means, and I'm not having any luck with vgmstream. 

I've attached a sample, any advice would be appreciated.
[CSWT001_00_16_P01PREN.rar](https://xentaxbackup.github.io/file/18900_CSWT001_00_16_P01PREN.rar)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-26T22:40:39+00:00
- Post Title: TFU Wii .gsb files

I wrote a small program to extract .gsb files from GameCube games (attached).  It worked with your attached .gsb file too, so looks like it's the same format.
[gsb.zip](https://xentaxbackup.github.io/file/18903_gsb.zip)
## Post #3
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-26T23:03:27+00:00
- Post Title: TFU Wii .gsb files

I appreciate the help.

When I drag my gsb files over your exe it doesn't seem to do anything? Not sure I'm using this right..
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-26T23:15:18+00:00
- Post Title: TFU Wii .gsb files

Ah, yes.  You will need to run it from the command line as follows:

gsb [command] [gsb file]

command is either l to list files, or x to extract files.

So just do gsb x CSWT001_00_16_P01PREN.gsb to extract them.  It will output the files into a folder based on the gsb name.
## Post #5
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-26T23:21:00+00:00
- Post Title: TFU Wii .gsb files

Amazing!

Is there a way to batch extract?
## Post #6
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-26T23:40:15+00:00
- Post Title: TFU Wii .gsb files

Also, oddly it only seems to be working with the file I sent you. Other files convert, but they show up as corrupted in foobar. I've attached an example.
[CSWT001_00_23_P02PREN.rar](https://xentaxbackup.github.io/file/18904_CSWT001_00_23_P02PREN.rar)
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-26T23:55:11+00:00
- Post Title: TFU Wii .gsb files

I've just tried it with that latest file, and it works ok for me.

But I'm wondering if there were some issues with it - it was a while ago when I wrote it.  As an alternative, try this QuickBMS script instead - it might work better, and you can use the quickbms batch function.
[gsb.zip](https://xentaxbackup.github.io/file/18905_gsb.zip)
## Post #8
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-27T00:09:05+00:00
- Post Title: TFU Wii .gsb files

Hmm, the script works, but with the same issue as the .exe. Many of the gsb files, including the one I sent a moment ago, show as corrupted in foobar.
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-27T00:23:05+00:00
- Post Title: TFU Wii .gsb files

Odd.  Here's the file I get from the QuickBMS script, if you want to compare with what you get, although it should be the same.

This file plays fine for me in Foobar, so see if it does for you.
[CSWT001_00_23_P02PRENl.zip](https://xentaxbackup.github.io/file/18906_CSWT001_00_23_P02PRENl.zip)
## Post #10
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-27T00:25:40+00:00
- Post Title: TFU Wii .gsb files

Interesting, maybe I need to reinstall foobar.
[Screenshot_12.png](https://xentaxbackup.github.io/file/18907_Screenshot_12.png)
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-27T00:30:27+00:00
- Post Title: TFU Wii .gsb files

Install the latest vgmstream plugin for Foobar as well, just in case.
## Post #12
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-27T00:37:14+00:00
- Post Title: TFU Wii .gsb files

Well shit, still doesn't work. What version of foobar/vgm do you have? 

I'm on foobar 1.6.2 with the Oct 19th build of vgm
## Post #13
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-27T12:32:11+00:00
- Post Title: TFU Wii .gsb files

I'm using Foorbar 1.6.1 and vgmstream from 26 September, with no problems.
## Post #14
- Username: Seven
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jun 17, 2016 2:14 am
- Post datetime: 2020-10-27T17:26:47+00:00
- Post Title: TFU Wii .gsb files

Just installed both and no change, very strange...
