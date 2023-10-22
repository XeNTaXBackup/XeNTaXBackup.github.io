## Post #1
- Username: BlueDrake
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 11, 2012 1:19 pm
- Post datetime: 2012-01-11T05:57:48+00:00
- Post Title: [Wii] Eurocom's Rio (.Bin & .000)

Hello there!

I have Rio for Wii and for fun I'm trying extract what I can. But unfortunately Google came up with nothing.
After about a week of trying to figure out how to extract this archive myself I have officially given up.
I'm pretty sure it's something like changing a few values in another Eurocom script, but I am at a loss.

The file structure looks exactly the same as other eurocom games, a bin file with the encrypted file names and the actual 000 archive.
Sphinx Thread [viewtopic.php?f=10&t=6245](viewtopic.php?f=10&t=6245)
G-Force thread [viewtopic.php?f=10&t=3614](viewtopic.php?f=10&t=3614)

But those scripts result in "Error: the requested amount of bytes to allocate is negative (-3288203280)"
I have attached the dastardly filelist.bin and parts of the filelist.000.

Any help would be greatly appreciated.
[FILELIST.zip](https://xentaxbackup.github.io/file/4974_FILELIST.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T11:08:20+00:00
- Post Title: [Wii] Eurocom's Rio (.Bin & .000)

it's necessary to know the encryption key for doing something otherwise there is no way to know at least the needed offsets and sizes.
you can try to post the executable of the game, maybe we are lucky.
## Post #3
- Username: BlueDrake
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 11, 2012 1:19 pm
- Post datetime: 2012-01-11T21:52:28+00:00
- Post Title: [Wii] Eurocom's Rio (.Bin & .000)

That doesn't sound promising but it is worth a shot.

```
http://www.filehosting.org/file/details/300579/Rio.dol
```
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T23:47:36+00:00
- Post Title: [Wii] Eurocom's Rio (.Bin & .000)

you are lucky, I found the key :)
[http://aluigi.org/papers/bms/rio.bms](http://aluigi.org/papers/bms/rio.bms)

note that the extracted files don't have names just because they are not available in the index file.
## Post #5
- Username: BlueDrake
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 11, 2012 1:19 pm
- Post datetime: 2012-01-13T00:07:56+00:00
- Post Title: [Wii] Eurocom's Rio (.Bin & .000)

Wow that was fast, thank you. Works great with no problems.
Now for the fun part, opening hundreds of files and renaming them.
