## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-14T02:17:45+00:00
- Post Title: [Doom] Looking for a way to find encryption key

Hi, is there a way to retrieve encryption "key" from exe file?
Here is the exe file. [https://drive.google.com/file/d/0B8JGJb ... sp=sharing](https://drive.google.com/file/d/0B8JGJb-FRy_bU2NPdDZ2UVRTbk0/view?usp=sharing)
And here is the encrypted lang files. [https://drive.google.com/file/d/0B8JGJb ... sp=sharing](https://drive.google.com/file/d/0B8JGJb-FRy_beWdkOWhHeUJxUTg/view?usp=sharing)

It seems that exe file contains encryption "key" for lang files.
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-06-14T17:26:39+00:00
- Post Title: [Doom] Looking for a way to find encryption key

Open the exe in disassembler then look for references the the debug/log strings.
## Post #3
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-14T18:44:14+00:00
- Post Title: [Doom] Looking for a way to find encryption key

> Reply from Sir Kane
>
> Open the exe in disassembler then look for references the the debug/log strings.

Uhm.. Ollydbg can't load 64-bit exe file.
## Post #4
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-06-14T19:01:55+00:00
- Post Title: [Doom] Looking for a way to find encryption key

Removed.
## Post #5
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-15T00:54:46+00:00
- Post Title: [Doom] Looking for a way to find encryption key

> Reply from atom0s
>
> http://x64dbg.com/#start
Thank you.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-06-15T16:01:51+00:00
- Post Title: [Doom] Looking for a way to find encryption key

Unfortunately, encryption key is dynamic.
## Post #7
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-06-15T20:38:29+00:00
- Post Title: [Doom] Looking for a way to find encryption key

> Reply from Ekey
>
> Unfortunately, encryption key is dynamic.

Oh my god.. Though the result is bad news, thanks for your research.
Hmm.. I have one question. Would the game read decrypted text which is extracted from dump file?
I mean extract text from dump file and rearrange it to original script form and replace it to encrytped game script.

Here is dump text section from Doom demo version(free).
[https://drive.google.com/file/d/0B8JGJb ... sp=sharing](https://drive.google.com/file/d/0B8JGJb-FRy_bcmNLd3QwcjNmOW8/view?usp=sharing)

And here is the original dump file from Doom demo version[English mode].
[https://drive.google.com/file/d/0B8JGJb ... sp=sharing](https://drive.google.com/file/d/0B8JGJb-FRy_bRkhhZnI3RkVoRmc/view?usp=sharing)
