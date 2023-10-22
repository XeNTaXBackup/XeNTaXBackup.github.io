## Post #1
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2023-04-29T04:41:12+00:00
- Post Title: EA NHL (PC) MAD Files

One group of files I want to be able to edit are the MAD files in, for example, NHL 2000. These contain both video and audio files, in the MOV and SNG formats, respectively. using sx.exe, I can convert the sng files to a wav file. Here come the parts that I am stuck on:

1) I cannot open the mov files in any video editor I've tried (DaVinci Resolve, Windows Movie Maker, and even an old version of Premiere Pro from around that time period).
2) sx.exe does not have a way to convert any edited mov files back into the sng format.
3) I just attempted to convert an sng file to a .wav file, but now sx just doesn't do anything. Heck, I can't even ask for help because sx.exe just hangs itself.

[https://mega.nz/folder/LHZHWYbY#Uewl73Ul4E06g6FIe8NcuA](https://mega.nz/folder/LHZHWYbY#Uewl73Ul4E06g6FIe8NcuA)

Here is a link to some example files because, even though I CAN upload a .zip file, it would be too large for Xentax to handle- heck, even files in the hundreds of kilobytes are too large, for some odd reason.
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-04-29T05:59:00+00:00
- Post Title: EA NHL (PC) MAD Files

While the specification of the Madcow video data [does exist](https://wiki.multimedia.cx/index.php/Electronic_Arts_MAD), unfortunately the tools to convert the data doesn't. FFMPEG can convert MAD videos to other format but not the other way around. The only way is if only the tools that EA uses to create the MAD files miraculously leaked but I doubt that will happen (I don't think they even have the tools anymore) or hoping someone else actually wrote the converter.
