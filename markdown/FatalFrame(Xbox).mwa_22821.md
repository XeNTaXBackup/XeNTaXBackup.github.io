## Post #1
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-14T04:48:12+00:00
- Post Title: FatalFrame(Xbox).mwa

I want to convert these files into a format that can be played, but I can’t find a way, I'm trying to play them with vgmstream but they don't work,please help
## Post #2
- Username: kaimuangel
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Oct 07, 2020 2:13 pm
- Post datetime: 2020-10-14T04:50:02+00:00
- Post Title: FatalFrame(Xbox).mwa

.mwa files
[se.zip](https://xentaxbackup.github.io/file/18818_se.zip)
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-10-18T16:57:15+00:00
- Post Title: FatalFrame(Xbox).mwa

If you rename the files to .vgmstream and copy this into a .vgmstream.txth file, they should play in Foobar with the vgmstream plugin.

codec = XBOX
sample_rate = @0x38:LE$4
channels = @0x36:LE$2
start_offset = 0x48
num_samples = data_size
