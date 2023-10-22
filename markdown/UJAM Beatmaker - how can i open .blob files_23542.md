## Post #1
- Username: civilizedproducer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 04, 2021 4:36 pm
- Post datetime: 2021-03-04T08:45:22+00:00
- Post Title: UJAM Beatmaker - how can i open .blob files?

newbie here, i'm trying to extract a .blob file of a music production software/plugin. i know this section is for game archives but i'm sure this .blob file is also an archive as when i opened it using a text editor, it showed some paths of the audio files that i want to extract. the only issue is that i don't know what type the archive is. i tried identifying it through a hex editor but still no luck   

Hex:
00000000   67 45 B1 62 EC 00 00 00 7B 22 69 6E 73 74 72 75   gE±bì...{"instru

i then used QuickBMS to extract, no luck there too.

if anyone can help me with it, i'll be grateful!

thanks in advance!
## Post #2
- Username: civilizedproducer
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-04T09:11:06+00:00
- Post Title: UJAM Beatmaker - how can i open .blob files?

Can you upload a sample?

Also, what is the name of this "music production software/plugin"?
## Post #3
- Username: civilizedproducer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 04, 2021 4:36 pm
- Post datetime: 2021-03-04T10:29:55+00:00
- Post Title: UJAM Beatmaker - how can i open .blob files?

> Reply from ikskoks ↑Thu Mar 04, 2021 5:11 pm at Thu Mar 04, 2021 5:11 pm
>
> 
Can you upload a sample?

Also, what is the name of this "music production software/plugin"?

yeah here you go : [https://drive.google.com/file/d/1fUIfje ... sp=sharing](https://drive.google.com/file/d/1fUIfje5LSkSAAKv4NFpIedW4W8tIznzk/view?usp=sharing)

the name of the music production software/plugin is UJAM Beatmaker, and there are many editions of it for different sounds, but all of them work on the same code base and all of their .blob files are encoded in the same way (source : found a lot of similarities by opening them in a text editor).
## Post #4
- Username: civilizedproducer
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-04T21:01:43+00:00
- Post Title: UJAM Beatmaker - how can i open .blob files?

So I was able to prepare some documentation about this format
[http://wiki.xentax.com/index.php/UJAM_Beatmaker_BLOB](http://wiki.xentax.com/index.php/UJAM_Beatmaker_BLOB)

It seems that file data is on the end, divided to some small pieces,
but I am not an audio expert, so I don't know how to help you play them.
I've only checked if those contain PCM data, but it appears that they are something else. 
(I would say that they look like MIDI data for me)


There are also some scripts defined on the end of second json.
They may help you analyze the file when you format them properly
[https://i.imgur.com/xrmNrUF.png](https://i.imgur.com/xrmNrUF.png)


I'm also moving this thread to Audio section as it is clearly the issue with audio files.
## Post #5
- Username: civilizedproducer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 04, 2021 4:36 pm
- Post datetime: 2021-03-05T10:22:23+00:00
- Post Title: UJAM Beatmaker - how can i open .blob files?

> Reply from ikskoks ↑Fri Mar 05, 2021 5:01 am at Fri Mar 05, 2021 5:01 am
>
> 
So I was able to prepare some documentation about this format
http://wiki.xentax.com/index.php/UJAM_Beatmaker_BLOB

It seems that file data is on the end, divided to some small pieces,
but I am not an audio expert, so I don't know how to help you play them.
I've only checked if those contain PCM data, but it appears that they are something else. 
(I would say that they look like MIDI data for me)


There are also some scripts defined on the end of second json.
They may help you analyze the file when you format them properly
https://i.imgur.com/xrmNrUF.png


I'm also moving this thread to Audio section as it is clearly the issue with audio files.

you're right that there is MIDI data too in the blob file, but there are audio files/samples also. to be precise, the audio samples should be really short in length, if that might help you in some way (as you said they are in small pieces, they actually are small files cause they are just drum sounds. i assume you did not mean fragmented or chunk data).

also, when i open this file up on a text editor, i can see some paths to some .wav files which are the sounds which i need. but i think they are paths inside of the .blob file so i can't access them without extracting the file.

and the json file's screenshot you provided and also the instruments.json file you mentioned in the wiki article, i guess it is the script for the parameters inside of that software, which are used to modify the sounds (cause it says FX Bus, AMT DRY, AMT WET, etc which are the parameters in the software.)

i'm attaching a zip with all the other files (a lot of .json files that may help you) that is associated with the software (i.e. everything that got copied to the Program Files folder when i installed the software). the .dll file inside of the zip is the actual software/VST plugin, which is run inside of a Digital Audio Workstation software.

Zip with all the files : [https://drive.google.com/file/d/1hhQADX ... sp=sharing](https://drive.google.com/file/d/1hhQADX1ERHQ2m0HKs7vewfxqquDRHOYQ/view?usp=sharing)

thanks once again!
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-06T13:32:28+00:00
- Post Title: UJAM Beatmaker - how can i open .blob files?

Best I could do is to try to parse the file.
Here is my tool 
[https://github.com/bartlomiejduda/Tools ... OB_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/UJAM%20Beatmaker/UJAM_Beatmaker_BLOB_Tool.py)
You can extract the files and try to decode them in foobar if you want.

I don't think I can help you more with this without debugging.
