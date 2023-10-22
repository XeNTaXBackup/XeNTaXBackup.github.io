## Post #1
- Username: MajinCry
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 01, 2015 4:30 am
- Post datetime: 2016-08-24T14:32:13+00:00
- Post Title: C# - Check If (BCn) .dds Has Alpha Channel

Got me quite the conundrum here.

I've made a tool that allows you to mass-resize .dds files from one resolution to another. I did this by cycling through all the .dds files in a given directory, checking the header @ +0c, +10 and +1c, to get the x resolution, y resolution and mipmap levels.

The program then gets the "destination" resolution set by the user, determines the correct number of mipmaps to generate, and then it runs texconv.exe, passing the info as string arguments. However, texconv will corrupt a .dds image if it has an alpha channel, and the argument (-pmalpha I think?) isn't included.

I uploaded the current state of the source code here: [https://github.com/MajinCry/Fallout-4-Texture-Resizer](https://github.com/MajinCry/Fallout-4-Texture-Resizer)

From what I can tell, the header of a .dds file doesn't have something akin to a "IsAlpha" flag. The presence of an alpha channel is dependent on the .dds format, which can be pulled from the bytes @ +54 to +57. However, there are a lot of ruddy formats, and it'd be an absolute nightmare generating all the combinations myself 'n' finding the correct sequence of bytes for them. Is there a reference kicking around that I can nab the hex values from?


Another avenue of approach would be to somehow use DirectXTex to pull the info from the .dds files, but, err, there's no tutorial on how to do such a thing. At most, I've been told to use C++/CLI, which I've gathered to be some sort of way to pass variables between C++ and C# code, but that's it. The MSDN documentation for it is atrocious as well; no examples, no comments, just a bunch of abstract concepts. Reads like it was written by someone who already knows how to use it, for people who already know how to use it.

Anyhow, DirectXTex can be found 'ere, for those curious. [https://github.com/Microsoft/DirectXTex](https://github.com/Microsoft/DirectXTex)

And here's the info I've found inside the .dds header: [http://pastebin.com/isBKwaas](http://pastebin.com/isBKwaas)


So aye. Any help lads? Kinda at a huge roadblock here.
