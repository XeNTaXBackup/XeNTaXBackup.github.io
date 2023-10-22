## Post #1
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2006-06-20T07:59:31+00:00
- Post Title: Black & White

hi 
 file is any mpeg2 (sound file) . extract this file to have any wav and rename *.wav to *.mp3 and play by winamp .
but when pack file with : mp3 , wave (any formay) , ogg ,.... game not paly file .. do u help about this ?

i uploading  some file about this qustion now  and write link's tomarrow...
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-17T22:23:30+00:00
- Post Title: Black & White

You never did get round to uploading that file, did you  ?
## Post #3
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2006-07-22T08:58:47+00:00
- Post Title: Black & White

it 's example sound file

[http://rapidshare.de/files/26600255/sample.rar.html](http://rapidshare.de/files/26600255/sample.rar.html)

for play most rename to mp3 file ....
extract and play file is ok but when put wav (any format) or mp3  game not paly ...
i want to knows codec and build wav's to play in game...
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-07-22T14:52:43+00:00
- Post Title: Black & White

I "played" with the example (the wav) and it's an mp2 embedded with a wav container, you can try to unpack/pack with ffmpeg

The data of the wave it's:
 Duration: 00:00:03.2, start: 0.000000, bitrate: 95 kb/s
 Stream #0.0: Audio: mp2, 22050 Hz, mono, 96 kb/s

You can converto to pcm with: 
"ffmpeg -i namepackedwav test13.wav"

And for reconvert the wav pcm to wav mp2 use: 
"ffmpeg -i test13.wav -acodec mp2 tryme.wav"

Here is the download of ffmpeg:
[http://esby.free.fr/CelticDruid/mirror/ ... rev5570.7z](http://esby.free.fr/CelticDruid/mirror/ffmpeg/ffmpeg.rev5570.7z)

[http://esby.free.fr/CelticDruid/mirror/ffmpeg/](http://esby.free.fr/CelticDruid/mirror/ffmpeg/)

You need 7-zip for unpack [http://www.7-zip.org](http://www.7-zip.org)

Good luck
