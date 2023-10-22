## Post #1
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-08-16T16:34:50+00:00
- Post Title: how do i unzip the .hyasb mobile game archive?

I recently found a beta release of one game, I would like someone to help me extract the files from the archive.
I already used one of the .hyasb scripts but it was developed for another game.

This is the error script



Безымянный.png (3.8 KiB) Viewed 136 times



This is the script itself.

```
#   Will of Shinobi

get DUMMY long  # 0xb28e87c2
get DUMMY long  # 0x88d8bca5
for
    get NAMESZ byte
    if NAMESZ == 0
        break
    endif
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next

```

[https://drive.google.com/file/d/1tH2oIc ... sp=sharing](https://drive.google.com/file/d/1tH2oIcdP-KTQ8DwBqNPymB5SAXaFMRNj/view?usp=sharing) this is archive
## Post #2
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-08-18T23:32:10+00:00
- Post Title: how do i unzip the .hyasb mobile game archive?

please help, I really need these models, if anyone knows how to decrypt this archive from the soul samurai game, help
## Post #3
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-10-04T11:05:31+00:00
- Post Title: how do i unzip the .hyasb mobile game archive?

in general, I found a way to extract models, the archive after I looked through it turned out to be unencrypted, thanks to one friend I was able to extract all the resources of this game, he created a wonderful program that can extract all files, I will attach this program to the post so that anyone can extract game resources.


 UnityHyasabParser.rar
(4.92 KiB) Downloaded 22 times


You will need to place the program in the archive folder, then run it and drop the archive into it, it will extract all files with the UnityFs header.
