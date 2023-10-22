## Post #1
- Username: FAKEAXlS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 08, 2022 1:11 pm
- Post datetime: 2022-06-08T05:33:22+00:00
- Post Title: Tomotoru - .SXR files - SakanaGL/CyberStep Engine?

Hello, I've been trying to extract data from this lost game.

Game: Tomotoru
Publisher: CyberStep
Developer: CyberStep
Engine: Inhouse
Platform: Android

It is a mobile game and has references to "SakanaGL"

It has similairities to Dawn of the Breakers as it uses SXR files and made by CyberStep as well. (Windows + Mobile game)

I've tried using GARbro that references SakanaGL but it doesn't seem to like my files.

There is also a quickbms script "breakers_sxr.bms" but it is not compatible.



Screenshot 2022-06-08 012721.png (150.63 KiB) Viewed 50 times



It seems to have some plain text data inside of it as well.

samples:
[https://www.mediafire.com/file/6b1s8efb ... n.sxr/file](https://www.mediafire.com/file/6b1s8efbt0q9i6z/main.sxr/file)
[https://www.mediafire.com/file/rseh0s7j ... 1.sxr/file](https://www.mediafire.com/file/rseh0s7jvuu5jbd/1-0101.sxr/file)
## Post #2
- Username: FAKEAXlS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 08, 2022 1:11 pm
- Post datetime: 2022-06-09T03:45:11+00:00
- Post Title: Tomotoru - .SXR files - SakanaGL/CyberStep Engine?

After digging into logcat logs on android, it seems to have a very similar file structure to Breakers: Dawn of Heroes.



Screenshot 2022-06-08 233952.png (38.07 KiB) Viewed 38 times


I've tried modifying the script for breakers, but I will have to do more research on how to write scripts since I keep hitting errors.

putting the Sakana library in ghidra also references lz4 compression too.

here is a link to the breakers script
[http://aluigi.org/bms/breakers_sxr.bms](http://aluigi.org/bms/breakers_sxr.bms)
