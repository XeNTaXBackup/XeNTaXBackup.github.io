## Post #1
- Username: po1arBear
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 06, 2015 11:03 pm
- Post datetime: 2015-10-05T20:52:54+00:00
- Post Title: help pls (wem2ogg)

Hello!
Can me somebody to extract audio files from this file ?? [https://mega.nz/#!FUlVmLwZ!lyoniFd_reG0 ... 9qn39pd8G0](https://mega.nz/#!FUlVmLwZ!lyoniFd_reG0dCWdCZVKE9QINfdhTCoky9qn39pd8G0)
I used standard methods but every time I get an error
Parse error: expected 0x42 fmt if vorb Messing
or
parse error: unknown chunk type
file attached. if it Dirt Rally
thanks in advance to those who can help)
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-06T03:39:33+00:00
- Post Title: help pls (wem2ogg)

Use this tool
[wwise_ima_adpcm.rar](https://xentaxbackup.github.io/file/9836_wwise_ima_adpcm.rar)
## Post #3
- Username: po1arBear
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 06, 2015 11:03 pm
- Post datetime: 2015-10-06T07:34:20+00:00
- Post Title: help pls (wem2ogg)

> Reply from spider91
>
> Use this tool
ty but Could you help and tell at what point to use the tool?
I unpack .bnk and receive .wav files and then?
I just do not quite understand all these subtleties   

thanks in advance
## Post #4
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-06T11:54:58+00:00
- Post Title: help pls (wem2ogg)

When you unpack .bnk you receive .wem files. Then create bath file to decode them

```
for %%i in (*.wem) do wwise_ima_adpcm.exe -d "%%i" "%%~dpni.wav"
```
## Post #5
- Username: po1arBear
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 06, 2015 11:03 pm
- Post datetime: 2015-10-06T15:41:37+00:00
- Post Title: help pls (wem2ogg)

> Reply from spider91
>
> When you unpack .bnk you receive .wem files. Then create bath file to decode them
Code: Select allfor %%i in (*.wem) do wwise_ima_adpcm.exe -d "%%i" "%%~dpni.wav"
thank you, friend.
You rescued me very much !!!
 
and after the file changes, .bnk created in reverse order ??
