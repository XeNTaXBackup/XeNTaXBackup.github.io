## Post #1
- Username: Ali03
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 31, 2018 6:30 am
- Post datetime: 2018-07-30T23:01:29+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

Hi, does anybody know how i can get the sound files from Diamond Rush and Guitar Rock Tour ?
I downloaded the JAR files and unpacked them with WinRAR, but no audio or MIDI files came out. In other Java mobile games I found MIDI files.

Here are the download links for the JAR files:

[Diamond Rush JAR](http://dedomil.net/games/123/screen/8)
[Guitar Rock Tour JAR](http://dedomil.net/games/572/category/1)


I hope there is a way to extract the sound files, maybe they are inside a .CLASS or .F file, but there are also other file extensions and files without an extension,
Or has anyone here the audio or MIDI files of Diamond Rush and Guitar Rock Tour?

Please help!
## Post #2
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2018-07-31T17:43:51+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

Guitar Rock Tour:
 extract snd0-7 files, open one by one in hex editor and remove first 10 bytes, the result is a midi file.

Diamond Rush JAR
 midi are in snd.f , you need a ripper which can extract midi files to get these
## Post #3
- Username: Ali03
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 31, 2018 6:30 am
- Post datetime: 2018-07-31T19:03:23+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

I made this:

Guitar Rock Tour:
I removed the first 10 bytes in s1-4 with HxD, then I added a .mid extension and opened them in Anvil Studio, the result: I can hear more songs in one midi file

Diamond Rush:
I renamed snd.f to snd.f.mid and opened it in Anvil Studio, the result: All sounds in one midi file

I think I made something wrong!

But here are the two midi files in my added .zip file:
[midi_files.zip](https://xentaxbackup.github.io/file/14686_midi_files.zip)
## Post #4
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2018-07-31T19:28:51+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

Guitar Rock Tour:
Each snd file is a separate midi track, most likely you in Anvil Studio messed up something, do it one by one.

Diamond Rush:
You need a tool which rips all midis from the snd.f file(you can do it by hand, but it's more complicated).
## Post #5
- Username: Ali03
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 31, 2018 6:30 am
- Post datetime: 2018-07-31T20:52:01+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

Guitar Rock Tour:
Sorry, I downloaded and extracted an other version of the game.
Now I solved this problem.

Diamond Rush
I don't know a tool yet, which rips the midis from snd.f, but how to do it by hand?

EDIT:
Thanks for your help! Now I could rip the MIDI files of Diamond Rush!
## Post #6
- Username: KaleshChauhan96
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 23, 2020 2:15 pm
- Post datetime: 2020-02-23T06:26:24+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

Hello. 
Can You please extract Assassins creed : Brotherhood, City of rome. From Jar games.
I am unable to do so. 
 because Vendor Is Gameloft. What to do ????
## Post #7
- Username: paul91
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 14, 2021 7:51 pm
- Post datetime: 2021-01-14T12:10:51+00:00
- Post Title: Audio/MIDI files from Java mobile games (Nokia)

Hello,
is it possible to extract music also from this game?
[http://dedomil.net/games/3238/screen/7](http://dedomil.net/games/3238/screen/7)
In structure theare are actually 11 files without extension (a to k). First 9 are actually png images but last 2 are unknown binary files. I think it could be also midi files with some encription. Any suggestion what to do for extract music files from this .*jar?
