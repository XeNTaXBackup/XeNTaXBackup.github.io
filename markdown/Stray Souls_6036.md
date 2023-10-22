## Post #1
- Username: felixthekat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 15, 2011 11:20 pm
- Post datetime: 2011-02-11T15:16:20+00:00
- Post Title: Stray Souls

Greetings!
I would greatly appreciate if someone could help me with a script for this game.
From here, you can download the file: [LOCALIZATION DOWNLOAD (7 MB)](http://www.sendspace.com/file/aqf5iw)

¡Thank You

!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-11T20:30:28+00:00
- Post Title: Stray Souls

i'm part way through a script but ran out of time

basically, the root folder has the names compressed, and those need decompressing to read what each of those names are.. etc
its another recursive format   

you're clearly looking to repack this for translation, which i dont care about. i haven't really handled the format right, but here's a non recursive dump script of some of the files:


removed script. see my post below



i haven't bothered handling the folder/folder/.. etc paths. those headers are dat files.

the png font tiles are visible though

so, incomplete script
## Post #3
- Username: felixthekat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 15, 2011 11:20 pm
- Post datetime: 2011-02-12T04:26:47+00:00
- Post Title: Stray Souls

Thanks friend!
exactly it is to translate a game, I'm still very noob to try and do something with these types of files.
I've done with others files, but more basic.
The script does not helped me, as I unpack everything as ***. dat and the game does not recognize the files.
For the game recognizes them must have its original name and extension.
but thank you very much for helping me. =)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-12T13:46:46+00:00
- Post Title: Stray Souls

> Reply from felixthekat
>
> Thanks friend!
exactly it is to translate a game, I'm still very noob to try and do something with these types of files.
I've done with others files, but more basic.
The script does not helped me, as I unpack everything as ***. dat and the game does not recognize the files.
For the game recognizes them must have its original name and extension.
but thank you very much for helping me. =)

if you could only understand my posts
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-12T15:20:54+00:00
- Post Title: Stray Souls

looking a little more, this format is simpler than i thought. no recursion at all   

this extracts with filenames. the folders and extensions are totally irrelevant. i only added them for better understanding. the files dont have either when their packed like this.
[straysouls.zip](https://xentaxbackup.github.io/file/3901_straysouls.zip)
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-02-12T21:45:07+00:00
- Post Title: Stray Souls

wrote a xml rebuilder for the packed xml data my script produces

quickbms was a real pain to get it to append binary data to strings (new line, tabs, etc) and would just crash with everything i tired.

pascal version, sourcecode, and broken bms script attached for reference.
[rebuildXML.zip](https://xentaxbackup.github.io/file/3903_rebuildXML.zip)
