## Post #1
- Username: PlanK69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2015 5:32 am
- Post datetime: 2017-07-05T14:33:16+00:00
- Post Title: Total War Warhammer .vp8 format

Hi there

So, here are some of the video files from the game: [https://www.dropbox.com/sh/63t91n5xtwsg ... UMbTa?dl=0](https://www.dropbox.com/sh/63t91n5xtwsgbwm/AACbYqLacCWZqeWiOgTNUMbTa?dl=0)

From the little reading that I've done, "vp8" is apparently a version of the "webm" format, but everything I've tried (ffmpeg, handbrake, RADtools) doesn't recognize the files, so I'm hoping somebody here can convert these to something watchable like .avi or mp4. The extension of the files is ".ca_vp8" but don't worry about the "ca" bit, that's simply a suffix that the developers 'Creative Assembly' (ca) put in there. The real extension should just be ".vp8", not ".ca_vp8"

The files were originally housed inside a ".pack" file in the game files, but I extracted them using the official 'total war' modding tool called "PackFileManager".
## Post #2
- Username: simonlsp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 23, 2019 4:12 pm
- Post datetime: 2019-01-23T08:20:27+00:00
- Post Title: Total War Warhammer .vp8 format

Tried VSCode-HexDump
File Head like this:
00000000: 43 41 4D 56 00 00 20 00 56 50 38 30 80 07 38 04    CAMV....VP80..8.
00000010: FE 54 05 42 01 00 00 00 3E 11 00 00 D8 DE 65 06    ~T.B....>...X^e.
00000020: 3F 11 00 00 45 AE 02 00 30 B7 01 9D 01 2A 80 07    ?...E...07...*..
00000030: 38 04 00 47 08 85 85 88 85 84 88 02 02 00 06 16    8..G............
00000040: 04 F7 06 81 64 9F 6B DB 9B 27 38 7B 27 38 7B 27    .w..d.k[.'8{'8{'
00000050: 38 7B 27 38 7B 27 38 7B 27 38 7B 27 38 7B 27 38    8{'8{'8{'8{'8{'8
00000060: 7B 27 38 7B 27 38 7B 27 38 7B 27 38 7B 27 38 7B    {'8{'8{'8{'8{'8{
So, you **might** have made a mistake, for that "ca" **might** stands for CAMV.
BUT WHAT IS CAMV??????

---------------------------------------------------------------------

Sorry I didn't found this topic years old.
But, ca_vp8 is still used in TW:WH2, so it would be nice being able to encode\decode.
## Post #3
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-04-02T00:25:14+00:00
- Post Title: Total War Warhammer .vp8 format

VP8 is open-source video codec by Google.

Decoder can be found here:
[https://github.com/webmproject/libvpx/t ... p8/decoder](https://github.com/webmproject/libvpx/tree/master/vp8/decoder)

Header is custom, but you can make out some values:

```
DWORD unk1;
DWORD codec_id;	// VP80  (VP 8.0 codec)
DWORD unk2;
WORD  frame_width;	// 1920 (video width)
WORD  frame_height;	// 1080	(video height)
FLOAT fps;	// 33.33 (video frame rate)
DWORD unk3;
DWORD unk4;
DWORD data_size;	// this looks like video data

```
## Post #4
- Username: kenson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 21, 2019 4:55 pm
- Post datetime: 2019-08-21T08:56:45+00:00
- Post Title: Total War Warhammer .vp8 format

> Reply from roswell ↑Tue Apr 02, 2019 8:25 am at Tue Apr 02, 2019 8:25 am
>
> 
VP8 is open-source video codec by Google.

Decoder can be found here:
https://github.com/webmproject/libvpx/t ... p8/decoder

Header is custom, but you can make out some values:
Code: Select allDWORD id;	// CAMV  (CA movie video)
DWORD unk1;
DWORD codec_id;	// VP80  (VP 8.0 codec)
DWORD unk2;
WORD  frame_width;	// 1920 (video width)
WORD  frame_height;	// 1080	(video height)
FLOAT fps;	// 33.33 (video frame rate)
DWORD unk3;
DWORD unk4;
DWORD data_size;	// this looks like video data

Thanks for the link!
