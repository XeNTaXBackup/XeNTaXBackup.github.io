## Post #1
- Username: Kerem123
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Dec 02, 2017 1:56 am
- Post datetime: 2019-12-01T20:25:05+00:00
- Post Title: Something wrong with the Wolf Among Us voice files.

We are making a dubbing project to Wolf Among Us with my team. But there is something wrong with the voice clips.
We extracted the ttarch files with the ttarch extractor. All of the voice files are .wav and they are not playing.
But it doesn't matter or important. When we changed the files with our .wav voice files and give a repack, the voice clip didn't played in the game. I think there's something wrong with the game's voice clips. And our .wav files may not be same with them I don't know.
This is only happened in Wolf Among Us. And our method was working good on the other Telltale games. So please if anyone knows something about it. Help. Here's one of the the game's orginal voice clips that we extracted : http://www.mediafire.com/file/4137f0glz ... 8.rar/file
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-12-01T20:50:17+00:00
- Post Title: Something wrong with the Wolf Among Us voice files.

There is nothing wrong with this file. It's not a wav file, it's an FSB version 4, which is why it isn't playing. Whenever you're ripping/modding, your extension won't ever normally matter, because the data may be different (like this for example). To decode, use foobar2000 + vgmstream component, which both of can be found here:
[http://foobar2000.org](http://foobar2000.org)

Rename to fsb and drop it in.

In order to re-pack files properly, you need to create most likely a PCM wav, and re-encode back to a FSB version 4 file. FFMPEG may have this capability, but don't quote me on that as I've never used it before. Also, I believe that the file for repacking needs to be the same size or small than the original file that was in the game's archive.
## Post #3
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-12-08T20:11:39+00:00
- Post Title: Something wrong with the Wolf Among Us voice files.

> Reply from Pingu ↑Mon Dec 02, 2019 4:50 am at Mon Dec 02, 2019 4:50 am
>
> 
There is nothing wrong with this file. It's not a wav file, it's an FSB version 4, which is why it isn't playing. Whenever you're ripping/modding, your extension won't ever normally matter, because the data may be different (like this for example). To decode, use foobar2000 + vgmstream component, which both of can be found here:
http://foobar2000.org

Rename to fsb and drop it in.

In order to re-pack files properly, you need to create most likely a PCM wav, and re-encode back to a FSB version 4 file. FFMPEG may have this capability, but don't quote me on that as I've never used it before. Also, I believe that the file for repacking needs to be the same size or small than the original file that was in the game's archive.

You can also use ToWav.
