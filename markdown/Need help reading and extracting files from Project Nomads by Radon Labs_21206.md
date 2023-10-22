## Post #1
- Username: Deadworker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 05, 2019 11:14 pm
- Post datetime: 2019-10-05T15:44:31+00:00
- Post Title: Need help reading and extracting files from Project Nomads by Radon Labs

Hey guys,

i am new to this forum and hope this thread is right for my request. I'm trying to access files from the game Project Nomads by Radon Labs. With a friend i was able to read and modify alot of .n and .tcl files, the game heavily relies on, though we are stuck now with an archive "data.npk" and it's contents. This data.npk holds a directory of each object in the game, these directories again contain alot of .nvx .ntx and .nax files, which are the texture and animation files, and each a "_main.n"-file. This _main.n is what i wanna get access to, as i hope it contains the code we are looking for. Though being a .n file, which we could read till now, this one seems to be encrypted. there is readable text but unsorted with alot of weird signs and symbols inbetween, making it quite impossible to understand it. we extracted the data.npk with a tool "nnpktool" i found somewhere on the internet, it could be, that it extracted the directories wrong, though i doubt it. i will attach only one of these _main.n for now and hope that you guys can help me or give some advice and ideas, how i might access these. we usually work with notepad+ to read .tcl and .n files.

Best Regards
Deadworker
[_main.rar](https://xentaxbackup.github.io/file/16867__main.rar)
## Post #2
- Username: grox777
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 22, 2016 5:54 pm
- Post datetime: 2019-10-15T01:02:19+00:00
- Post Title: Need help reading and extracting files from Project Nomads by Radon Labs

Wait, how do you even UNPACK the .NPK file?
when ill try to run nnpktool it show me empty cmd for half second and then it just closing...
same happens if i drag .npk file on nnpktool.exe
## Post #3
- Username: grox777
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 22, 2016 5:54 pm
- Post datetime: 2019-10-15T05:24:00+00:00
- Post Title: Need help reading and extracting files from Project Nomads by Radon Labs

Ok, i figured out how to unpack/pack .NPK... And now i even can convert .nvx2 models to .n3d2. But how on earth i needs convert .n3d2 into .obj using default Nebula Device 2 SDK features? P/S I tried external soft for these pourposes - "3d object converter" But bone data (?) was lost and so it was impossible to convert back to .nvx2 due to an "nmeshtool" error.
## Post #4
- Username: Deadworker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 05, 2019 11:14 pm
- Post datetime: 2019-10-21T10:22:24+00:00
- Post Title: Need help reading and extracting files from Project Nomads by Radon Labs

Hey thank you for your response. I did find the nnpktool with a batchfile somewhere online, that way i could unpack the .npk. I also tried the nebula sdk, but there i had the same problem as you, it seems the SDK is not usuable on Win 10, but i don't know that. i would like to know how you managed to unpack it now? Could you somehow open a _main.n-file and read it? one is in each directory.
