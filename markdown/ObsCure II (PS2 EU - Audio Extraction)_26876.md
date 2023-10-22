## Post #1
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2023-06-18T18:48:42+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

Hi to everyone. I'm trying to extract the audio tracks of this game, but I have a problem, each extracted track is afflicted by large problems of stuttering, pops and clicks present for the entire duration of the track every few seconds (who more, who less ). The exact same problems also afflicted the previous game which I tried to solve by setting parameters that helped me significantly reduce the problem but not completely solve it. I tried to use the same settings for this game, and the result is the same as the previous one.

The program used is "Cube Media Player 2" which I used to analyze the "STRMPACK.HVP" archive and report all the tracks present. 
Once finished, I highlighted all the tracks and set them, in the "Properties" section (right click), with the following parameters:
Audio Type: ADPCM
Frequency: 44100Hz
Channels: 2
Interlative: 65536


These instead are the parameters used in "VGMToolbox r1017" on the sample extracted from the archive using the "Cube Media Player 2":
Frequency: 44100Hz
Channels: 2
Interlative: 10000
Unfortunately the result, although different, is the same.


I attach several files below:
Archive: [https://mega.nz/folder/piADxRxa#SopnfIKzIQHyf8ZQWOfHHw](https://mega.nz/folder/piADxRxa#SopnfIKzIQHyf8ZQWOfHHw)
Track sample (extracted with CMP 2): [https://mega.nz/folder/4nJ3GBSD#u1RCbqgSKEceVND-wjpyYQ](https://mega.nz/folder/4nJ3GBSD#u1RCbqgSKEceVND-wjpyYQ)
Track sample (converted with CMP 2): [https://mega.nz/folder/9vIX3DJa#R6_a7U0dICyOmEleq7l7Og](https://mega.nz/folder/9vIX3DJa#R6_a7U0dICyOmEleq7l7Og)
## Post #2
- Username: Carro2000
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-18T22:52:44+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

It's better to use my extractor for getting files from HVP archives.
[https://github.com/bartlomiejduda/Tools ... VP%20Tools](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/ObsCure%202/ObsCure%202%20HVP%20Tools)
In most cases you will get files with proper filenames, but for STRMPACK.HVP from PS2 version hashes are still unknown.

Once you'll extract data with my tool, you'll get a lot of BIN files in "\STRMPACK.HVP_out\sounds\streams" directory.

Copy this script:

```

codec = PSX
interleave = 0x10
sample_rate = 44100
channels = 1
start_offset = 0x00
num_samples = data_size
```


and save it as ".bin.txth" file inside "streams" directory.



screenshot000481.png (9.98 KiB) Viewed 84 times



Then you'll need to launch foobar2000 with vgmstream plugin enabled. [https://github.com/vgmstream/vgmstream/releases](https://github.com/vgmstream/vgmstream/releases)
Remember to check these options in foobar's preferences window:



screenshot000482.png (69.13 KiB) Viewed 84 times



And then you can just drag and drop your BIN files to foobar's window to play them.
## Post #3
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2023-06-19T00:07:45+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

iksos, first of all thank you very much for your immediate response and availability granted, unfortunately I'm having problems running your script. 
On my PC, Python 3.9.13, ReverseBox 0.3.1 and lzokay 1.1.2 are installed but unfortunately, whenever I try to run the script I get the following error message:

python Obscure_2_hvp_extractor.py -e STRMPACK.HVP
Traceback (most recent call last):
  File "C:\Users\Generic\Desktop\Arch2\Obscure_2_hvp_extractor.py", line 23, in <module>
    from constants import STR_ENCODING
ImportError: cannot import name 'STR_ENCODING' from 'constants' (C:\Users\Generic\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.9_qbz5n2kfra8p0\LocalCache\local-packages\Python39\site-packages\constants.py)

I apologize for that, but unfortunately I don't have the faintest idea what the problem could be.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-19T04:34:09+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

Weird error. One way to fix this may be to use virtualenv. There are some tutorials on the web explaining how to set it up.
Then you can run the script directly from PyCharm IDE.

If that doesn't help you can try to rename file "constants.py" to something else like "constants_x.py"
And then adjust this line with the new name [https://github.com/bartlomiejduda/Tools ... tor.py#L23](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/ObsCure%202/ObsCure%202%20HVP%20Tools/Obscure_2_hvp_extractor.py#L23)

I'll try to remember this in the future and if it really causes such issues i'll remove this file completely 
and i'll put my constants somewhere else. 


EDIT: Oh, I think I know what you did wrong. You've only downloaded main script file,
but you need to download whole tool's directory from Github to run the script.
## Post #5
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2023-06-19T11:35:36+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

> Reply from ikskoks ↑Mon Jun 19, 2023 12:34 pm at Mon Jun 19, 2023 12:34 pm
>
> 
EDIT: Oh, I think I know what you did wrong. You've only downloaded main script file,
but you need to download whole tool's directory from Github to run the script.

iksos, thank you, the problem was exactly what you thought, I didn't download the whole tool, just the script because I ignorantly thought they didn't concern what I was supposed to do. Consequently, I proceeded following your detailed guide correctly, managing to extract all the files and have them recognized and reproduced by the program thanks to the text file created, but there is one last problem, the output. All the tracks are in mono channel when in reality they are stereo together with the fact that also in this case it presents all the problems I was talking about like the other methods used before.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-19T20:37:18+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

Ok, I've updated the script. Try this:

```
# version 2

codec = PSX
interleave = 65536
sample_rate = 44100
channels = 2
start_offset = 0x00
num_samples = data_size

```
## Post #7
- Username: Carro2000
- Rank: advanced
- Number of posts: 64
- Joined date: Fri Mar 25, 2016 4:43 am
- Post datetime: 2023-06-20T01:25:08+00:00
- Post Title: ObsCure II (PS2 EU - Audio Extraction)

> Reply from ikskoks ↑Tue Jun 20, 2023 4:37 am at Tue Jun 20, 2023 4:37 am
>
> 
Ok, I've updated the script. Try this:
Code: Select all# ObsCure II (PS2) BIN Audio files
# version 2

codec = PSX
interleave = 65536
sample_rate = 44100
channels = 2
start_offset = 0x00
num_samples = data_size

ikskoks, as always thank you. The actual output now it's like mine, but it sounds better. The parameters are the same as those I entered in CMP 2, 
but inserting them in the files extracted with your script, some of them sound almost perfect, others unfortunately badly.

Below I attach an example of two imperfect audio tracks (music and voice):
Music: [https://mega.nz/file/grYkUQiK#U4ZitKHWQ ... oOh5cLxPpE](https://mega.nz/file/grYkUQiK#U4ZitKHWQRDzs5AqGo-LKhRb_RkCy-8GzoOh5cLxPpE)
Voice: [https://mega.nz/file/Z2J1xCxD#O6qEcp6uM ... Lks4Xc7y64](https://mega.nz/file/Z2J1xCxD#O6qEcp6uMIXeZ40Xk94ZLLvm4UCPeb6j7Lks4Xc7y64)
