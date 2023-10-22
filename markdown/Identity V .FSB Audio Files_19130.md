## Post #1
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2018-12-02T10:54:06+00:00
- Post Title: Identity V .FSB Audio Files

I really love the voice acting, and sound design in this game. I'd love to have these files. I was able to use regular FSB Extractors, but none seem to Really work, as They either output files that are 0 seconds long, or nothing at all, so it seems like it may be a newer/different type of FSB? I've left a link for the example zip here. Any help is appreciated! I'd like whatever program that can properly extract these, so let me know if you find one! 

[https://www.mediafire.com/file/0ravyfxo ... v.rar/file](https://www.mediafire.com/file/0ravyfxoyj10044/fsbexamplesidv.rar/file)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2018-12-02T12:24:14+00:00
- Post Title: Identity V .FSB Audio Files

If none of the FSB extractors work, it's more than likely FSB with vorbis encoding.

You can split the FSB5 file into the individual audio files inside the FSB5 file with a tool. I've attached the tool I used to do this to this post. Use the Batch.bat file to do multiple FSB files.

The only drawback to the tool is that if there are multiple files with the exact same file name, it will automatically overwrite them.


 FSB5 Splitter.zip
(5.46 KiB) Downloaded 72 times


Download [vgmstream](https://github.com/bnnm/vgmstream-builds/raw/master/bin/vgmstream-latest-test-u.zip) and you can use it with winamp or [foobar2000](https://www.foobar2000.org/components/view/foo_input_vgmstream) to playback the files. Use the test.exe to convert them into WAV if you want to as well.
## Post #3
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2018-12-02T23:53:19+00:00
- Post Title: Identity V .FSB Audio Files

> Reply from brendan19
>
> If none of the FSB extractors work, it's more than likely FSB with vorbis encoding.

You can split the FSB5 file into the individual audio files inside the FSB5 file with a tool. I've attached the tool I used to do this to this post. Use the Batch.bat file to do multiple FSB files.

The only drawback to the tool is that if there are multiple files with the exact same file name, it will automatically overwrite them.
FSB5 Splitter.zip
Download vgmstream and you can use it with winamp or foobar2000 to playback the files. Use the test.exe to convert them into WAV if you want to as well.

Hey there! Thank you SO MUCH! It worked! You're a beautiful genius!
## Post #4
- Username: needsb
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Aug 01, 2017 5:58 pm
- Post datetime: 2019-04-12T18:42:56+00:00
- Post Title: Identity V .FSB Audio Files

To extract all fsb and in subfolders with vgmstream, you can use this batch script 

```
FOR /R %%a IN (*.fsb) DO "(PATH TO test.exe)" -l 2 -f 10 -o "%%a.wav" "%%a"
```
## Post #5
- Username: tkwtan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 03, 2019 12:37 pm
- Post datetime: 2019-11-03T04:46:29+00:00
- Post Title: Identity V .FSB Audio Files

> Reply from brendan19 ↑Sun Dec 02, 2018 8:24 pm at Sun Dec 02, 2018 8:24 pm
>
> 
If none of the FSB extractors work, it's more than likely FSB with vorbis encoding.

You can split the FSB5 file into the individual audio files inside the FSB5 file with a tool. I've attached the tool I used to do this to this post. Use the Batch.bat file to do multiple FSB files.

The only drawback to the tool is that if there are multiple files with the exact same file name, it will automatically overwrite them.

FSB5 Splitter.zip
Download vgmstream and you can use it with winamp or foobar2000 to playback the files. Use the test.exe to convert them into WAV if you want to as well.

Hey, if anyone is sill reading this post may I just for some assistance in doing these step-by-step? I've already got all required files downloaded, with no idea on how to use them at all... :/
