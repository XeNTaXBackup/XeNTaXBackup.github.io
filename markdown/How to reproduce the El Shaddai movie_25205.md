## Post #1
- Username: 000mb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 08, 2021 1:30 pm
- Post datetime: 2022-03-29T11:16:28+00:00
- Post Title: How to reproduce the El Shaddai movie

Purpose: I want to be able to cut through the background of a [video](https://drive.google.com/file/d/13WSRO2HZLnH_ATxQOLF5KILLPAi2jsOK/view) with a chromakey color.

First, I used this [CSV](https://drive.google.com/file/d/1uZo3uX-Hu8nUv4z9NiIFXNwtMnzXuyPs/view) file as a reference to find the [motion files (.kf)](https://drive.google.com/file/d/1iZWFdG7NuNzpSgBmrJuwBYIyQ-OSvyOH/view) and [models (.nif)](https://drive.google.com/file/d/1ff92mIkqrIEbmcJhQqk2roAtNOOFwiVB/view) needed
Image

Even with blender with the nif plugin, I could not read the nif and kf files (they looked like lumps of wire), so I converted the nifs to fbx using noesis.
The nifs were readable with the textures reflected, but the kf files did not play properly in noesis, and this is now a problem.
Image

I also tried NifSkope, but even though the file was displayed, both the model and the file were not displayed, and it was not an option([I also tried this method](https://wiki.nexusmods.com/index.php/Installation_of_Blender)).

I'm not sure if it's a problem with the tool or if I have the wrong file in the first place...
This CSV helped me a lot when I was looking for audio, so I assumed the same would be true for the models...
Making motions from scratch is tough for an amateur, and since I have pre-rendered videos in addition to these, I'll probably have my hands full clipping them out.
## Post #2
- Username: 000mb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 08, 2021 1:30 pm
- Post datetime: 2022-03-30T15:58:00+00:00
- Post Title: How to reproduce the El Shaddai movie

Hmmm, don't ask for a bone you don't know...  
It's in the binary, but I don't know why they don't recognize it.

```
WARNING: Could not find bone object luc:lucifer NonAccum
```




luc.PNG (19.67 KiB) Viewed 70 times
## Post #3
- Username: 000mb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jun 08, 2021 1:30 pm
- Post datetime: 2022-04-25T10:34:57+00:00
- Post Title: How to reproduce the El Shaddai movie

I thought I had blanked this article, but it looks like it's been replaced, so I'll reuse it.

I tried it with the steam version data and it worked normally, so the above two problems were solved (although the camera motion didn't work).
But this time I came across a scene with a different object (umbrella).
The solution I came up with is to replace the object (cell phone) that comes with the model, but when I load the famous NifSkope in that area, it becomes a creature and I can't use it.
Is there any other way?

[Model](https://drive.google.com/file/d/1dBr-jM3Uz0cHq5bDm-I5_u_2TmiCwYer/view)
[Motion](https://drive.google.com/file/d/1UQKfx-4D7lOtkfDeYGvQt2RqdQZNg47K/view)
[Umbrella folder](https://drive.google.com/file/d/1oRtUVb1lLR80HT9dUS0JrT4OyNl7F8jF/view)
[Noesisv4464 Screenshot 2022.04.25 - 19.27.08.92.png](https://xentaxbackup.github.io/file/22146_Noesisv4464 Screenshot 2022.04.25 - 19.27.08.92.png)
