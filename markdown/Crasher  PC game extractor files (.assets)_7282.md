## Post #1
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-03T08:22:04+00:00
- Post Title: "Crasher" : PC game extractor files (*.assets)

Hi folks,

do someone know how to extract the .assets files of this game (unity engine) ?

I've searched everywhere but still not able to find a way to do this.

Here is a file : [http://dl.free.fr/j017qv4Nk](http://dl.free.fr/j017qv4Nk)

Thanks again !
## Post #2
- Username: Tabris
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Jan 27, 2011 9:56 am
- Post datetime: 2011-09-05T09:06:56+00:00
- Post Title: "Crasher" : PC game extractor files (*.assets)

Hi,

apparently WRS was able to extract some audio files from *.assets unity's packages, but the script only works for audio files for now :

> Reply from WRS
>
> as you just wanted the audio, i decided to try something a little different with my bms script contribution.

firstly,
i only found references to OGG and WAV files, so my scripts just look for these file signatures

filenames (and file data) is stored in 4-byte blocks - which this format enforces with padding. due to this, i was able to work backwards to extract the filenames correctly 

also,
as the game was made with unity, this script may even work on other .assets files (untested, bold claim)

ogg-wav_bmses.rar : download/file.php?id=2810

Could someone take a look on this script and modify it ? I've tried to PM him directly, but didn't get any anwser yet.

Regards,

Tab.
