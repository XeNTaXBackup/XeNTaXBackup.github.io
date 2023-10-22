## Post #1
- Username: Flamingspaz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Dec 28, 2013 7:39 pm
- Post datetime: 2014-06-11T19:32:37+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

Hello,
ive been trying to rip audio from Ratchet and Clank Into the nexus lately..
but the problem is most of the files are with the same name and its kinda frustrating viewing all the files and searching for the file name in the hex editor, to know the file name or what it is used for..  
So my question is...
Is there is a script that can Rename all files to the Hex name, (View samples to understand).
Please help  
Thanks,
## Post #2
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-06-11T22:24:04+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

[https://gist.github.com/mgrandi/547d68114c0768edbbee](https://gist.github.com/mgrandi/547d68114c0768edbbee)

you will need python 3: [https://www.python.org/](https://www.python.org/)

```
usage: rename-file-to-parent-folder.py [-h] [--verbose]
                                       inputFolder fileToRenameRegex

renames files to include the parent folder's name

positional arguments:
  inputFolder        the folder that contains the files to rename
  fileToRenameRegex  the regex to use to figure out what files to rename, if
                     unsure just type the entire name (like
                     'resident_sound.dat')

optional arguments:
  -h, --help         show this help message and exit
  --verbose          use this to increase verbosity
```


so basically, just open up cmd.exe or whatever and run

```
python rename-file-to-parent-folder.py <FOLDER CONTAINING FILES> resident_sound.dat
```


and it should output for every file that was renamed:

> /Users/markgrandi/Temp/3a/3a2b289a/resident_sound.dat renamed to /Users/markgrandi/Temp/3a/3a2b289a/resident_sound_3a2b289a.dat

enjoy!
## Post #3
- Username: Flamingspaz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Dec 28, 2013 7:39 pm
- Post datetime: 2014-06-15T21:47:56+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

Hello ,
Thanks for your Reply .. but you still didn't get my point
What I meant was :
If you open file "resident_sound.dat" in a hex editor
you can find at 0x100 to 0x118 the file name
so what I'm seeking is something that can actually rename resident_sound.dat to prop_museum_doors_open_dj
or whatever name is in the file , 
thank you and Please help!
## Post #4
- Username: Flamingspaz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Dec 28, 2013 7:39 pm
- Post datetime: 2014-06-22T00:27:10+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

Bump, please help :/ ,as i am pretty low on scripting
## Post #5
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-06-24T10:01:33+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

i didn't know that the filename was in the file, i'll write up something to do that for you
## Post #6
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-06-24T10:39:08+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

try this:

[https://gist.github.com/mgrandi/e784f2365ac922b0e248](https://gist.github.com/mgrandi/e784f2365ac922b0e248)

```
usage: ratchet_and_clank_nexus_rename_soundfiles.py [-h] [--verbose]
                                                    inputFolder outputFolder
                                                    fileToRenameRegex

script to name audio files from 'ratchet and clank into the nexus' to human
readable names

positional arguments:
  inputFolder        the folder that contains the files to rename
  outputFolder       Where to output the resulting files
  fileToRenameRegex  the regex to use to figure out what files to rename, if
                     unsure just type the entire name (like
                     'resident_sound.dat')

optional arguments:
  -h, --help         show this help message and exit
  --verbose          use this to increase verbosity

Copyright Jun 23, 2014 Mark Grandi
```


You need [Python 3](http://www.python.org)

so basically, just open up cmd.exe or whatever and run:

```
python3 ratchet_and_clank_nexus_rename_soundfiles.py /Users/markgrandi/Temp/3a /Users/markgrandi/Temp/3atest "resident_sound.dat"
```


and it outputs stuff like this for every file that was renamed:

```
/Users/markgrandi/Temp/3a/3a1c603a/resident_sound.dat renamed to /Users/markgrandi/Temp/3atest/prop_museum_doors_open_dj.dat
/Users/markgrandi/Temp/3a/3a2b289a/resident_sound.dat renamed to /Users/markgrandi/Temp/3atest/cha_thugbrawler_gethit_large.dat
done!
```
## Post #7
- Username: mgrandi
- Rank: n00b
- Number of posts: 16
- Joined date: Tue May 20, 2014 1:55 pm
- Post datetime: 2014-06-25T02:53:35+00:00
- Post Title: Ratchet and Clank Into the nexus Audio

For people who can't deal with command line programs, here is a GUI for it:
[https://dl.dropboxusercontent.com/u/962 ... dfiles.zip](https://dl.dropboxusercontent.com/u/962389/ratchet_and_clank_nexus_rename_soundfiles.zip)

just browse for a input directory, browse for an output directory , you shouldn't have to touch the filename mask, and then just hit go.
