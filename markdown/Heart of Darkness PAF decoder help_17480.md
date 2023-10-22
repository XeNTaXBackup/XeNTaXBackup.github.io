## Post #1
- Username: thesir
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 31, 2017 6:03 am
- Post datetime: 2018-01-01T01:40:34+00:00
- Post Title: Heart of Darkness PAF decoder help

Hi guys, I have been trying to pull files from HoD's paf file using the decoder found here:
[download/file.php?id=6140](http://forum.xentax.com/download/file.php?id=6140)
Source files:
[http://cyxdown.free.fr/pafdec/](http://cyxdown.free.fr/pafdec/)

Thing is though I have been unable to get the program to work correctly. The program would either result in the error "Unable to read .PAF file header" or would simply crash upon decoding the first of the 4095 files. I have swapped various versions of libpng3.dll and zlib1.dll and tried various versions of HoD but have had little success.

Anyone know how to get the decoder working or have the extracted files on hand? Any help would be very much appreciated.
## Post #2
- Username: thesir
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 31, 2017 6:03 am
- Post datetime: 2018-01-02T05:18:12+00:00
- Post Title: Heart of Darkness PAF decoder help

Nevermind, aluigi over at Zenhax managed to get things working. For those who want to decode HoD's PAF file, I'll leave some links and instructions here.

Link to the already extracted frames and sound (900mb):
[https://mega.nz/#!VvwVWRiK!kjODmZKPMReC ... go8yxPxRwQ](https://mega.nz/#!VvwVWRiK!kjODmZKPMReC7Ypgl-iMF89EFiVV8DrnCgo8yxPxRwQ)

For those who wish to extract the data themselves use quickbms and the script provided within on hod.paf to decode 50 smaller paf files:
[https://mega.nz/#!I25D0DIR!FMlucjZM39a8 ... ipkpKmimjA](https://mega.nz/#!I25D0DIR!FMlucjZM39a8hYLXB3hHwvc7Neh-ivyaqipkpKmimjA)

Then drag and drop one paf at a time onto this decoder:
[https://mega.nz/#!crR30Tpa!nh7sRVuiyWqP ... cMj-U-vs-4](https://mega.nz/#!crR30Tpa!nh7sRVuiyWqPVlFarwSxErjnz_XBTcUhscMj-U-vs-4)
You'll get each individual frame and a sound file.

Note: There are some issues with the decoder which include a weird yellow corruption on some frames that are supposed to be black and producing 50 minute wav files when the file is supposed to end within a couple.
