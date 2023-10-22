## Post #1
- Username: enricodandolo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 23, 2020 7:22 pm
- Post datetime: 2020-08-23T11:24:40+00:00
- Post Title: Mass Converting VAG files with MFAudio using a bat file

Hey, I'm not great with .bat files, so I was wondering how I would write a .bat file to mass convert 3,500 files from VAG to wav, instead of doing them manually, one by one.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-08-23T12:34:37+00:00
- Post Title: Mass Converting VAG files with MFAudio using a bat file

As far as I know MFAudio is GUI Tool and it has no support for batch conversion.

Only way I see it hapen is to write a custom coverter, compile it to exe
and write something like this [https://github.com/bartlomiejduda/Tools ... FOLDER.BAT](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/DO%20FOR%20ALL%20FILES%20IN%20FOLDER.BAT)
Or even don't use BAT file and make loop in converter itself.

Edit: Oh, nevermind. It seems that batch conversion is supported xd
[https://imgur.com/a/KjigJGI](https://imgur.com/a/KjigJGI)

So just make for loop in BAT file with those parameters specified
