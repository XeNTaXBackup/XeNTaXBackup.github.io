## Post #1
- Username: otaviotr8765
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Nov 30, 2020 12:59 pm
- Post datetime: 2021-01-12T16:02:33+00:00
- Post Title: How edit aud FSB

I used fmod to extract the fsb file,when extracting it give me the wav audio, but how do reimport the audio after the modification?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-12T19:59:28+00:00
- Post Title: How edit aud FSB

You need program named FMOD Designer for that.
But it can't really reimport, you can use it to recreate whole FSB file from WAV.
## Post #3
- Username: otaviotr8765
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Nov 30, 2020 12:59 pm
- Post datetime: 2021-01-16T05:17:57+00:00
- Post Title: How edit aud FSB

> Reply from ikskoks ↑Wed Jan 13, 2021 3:59 am at Wed Jan 13, 2021 3:59 am
>
> 
You need program named FMOD Designer for that.
But it can't really reimport, you can use it to recreate whole FSB file from WAV.

how to recreate wav audio in FMOD Designer?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-16T10:24:57+00:00
- Post Title: How edit aud FSB

Here is the instruction:

1. Open FMOD Designer
2. Create new project
3. Go to "Sound definitions" tab
4. Drag your WAV to the left panel of this tab
5. Go to "Wave banks" tab and add WAV to a new bank (if it wasn't added automatically yet)
6. Go to "Events" tab
7. Add event group and then create a new event
8. Go to "Event editor" tab and drag your WAV to event parameter field
9. Go to Build > Build project
10. Select bank which you want to build and click "Build".


If you want to do all this automatically, you can use my FSB Batch generator
[https://github.com/bartlomiejduda/Tools ... 0Generator](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/FSB%20Batch%20Generator)
## Post #5
- Username: otaviotr8765
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Nov 30, 2020 12:59 pm
- Post datetime: 2021-01-16T14:52:17+00:00
- Post Title: How edit aud FSB

> Reply from ikskoks ↑Sat Jan 16, 2021 6:24 pm at Sat Jan 16, 2021 6:24 pm
>
> 
Here is the instruction:

1. Open FMOD Designer
2. Create new project
3. Go to "Sound definitions" tab
4. Drag your WAV to the left panel of this tab
5. Go to "Wave banks" tab and add WAV to a new bank (if it wasn't added automatically yet)
6. Go to "Events" tab
7. Add event group and then create a new event
8. Go to "Event editor" tab and drag your WAV to event parameter field
9. Go to Build > Build project
10. Select bank which you want to build and click "Build".


If you want to do all this automatically, you can use my FSB Batch generator
https://github.com/bartlomiejduda/Tools ... 0Generator

Thanks
