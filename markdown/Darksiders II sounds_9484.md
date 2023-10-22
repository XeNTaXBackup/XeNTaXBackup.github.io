## Post #1
- Username: MrSnail
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 9:00 pm
- Post datetime: 2012-08-15T13:47:46+00:00
- Post Title: Darksiders II sounds

So I've extracted the sounds from the core.pck and I've stumbled upon a bunch of .wav files. These obviously needs converting to .ogg. I'm currently using this script. 

```
:getfile
if "%~1"=="" goto end
ww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin "%~1"
shift
goto getfile
:end
```


First of all, how do I convert all files instead of just one at a time?

Second of all, what codec do I need to play this .ogg files? I'm using VLC which has native support for .ogg yet it's unable to play them.
## Post #2
- Username: MrSnail
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 9:00 pm
- Post datetime: 2012-08-15T14:19:56+00:00
- Post Title: Darksiders II sounds

I answered my own first question.

```
FOR %%a in (*.wav) do ww2ogg.exe --pcb packed_codebooks_aoTuV_603.bin "%%a" 
```


This script runs all files with a certain extention through the ww2ogg.exe.
## Post #3
- Username: MrSnail
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Aug 15, 2012 9:00 pm
- Post datetime: 2012-08-15T14:27:43+00:00
- Post Title: Darksiders II sounds

And I've answered my second question. 

foobar can play these .ogg files, although no seek bar works.
