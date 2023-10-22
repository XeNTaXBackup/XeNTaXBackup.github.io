## Post #1
- Username: bnnm
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Nov 10, 2017 6:43 am
- Post datetime: 2017-11-23T18:35:41+00:00
- Post Title: FMOD's FADPCM decoding

FMOD introduced a new ADPCM codec in ~2015 for FSB5 they call FADPCM. On a quick glance it looks somewhat like MS-ADPCM.

While this can be converted to WAV using daemon1's tools + FMOD's DLLs I was hoping somebody could figure out the decoding algorithm so it could be implemented into other players (namely [vgmstream](https://hcs64.com/vgmstream.html)).

It's used in some PC games like Dead Rising 4 and Forza Horizon 3. Here are some samples: [https://mega.nz/#!GNRlHSra!S7cTB3rlcefY ... NmT8m3JH7Q](https://mega.nz/#!GNRlHSra!S7cTB3rlcefYYy25UADxuYX4cvwXOxVbzNmT8m3JH7Q)

EDIT: vgmstream now decodes this
