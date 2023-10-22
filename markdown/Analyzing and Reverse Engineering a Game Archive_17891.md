## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:42:31+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

Attention: This topic is subject to the Manual Researching Section under the tutorial An Imitable Workflow for Reverse Engineering A Game Model.

Part IV. Analyzing and Reverse Engineering a Game Archive

In Part III we've been able to extract the model from one of the nif files. But these files are orginally packed as a big .xpr archive. So in this part, I'll
show you how to reverse engineering the structure of the entire xpr package. It's more complicated than reversing a model. But that doesn't mean it's difficult.
Just follow my reasoning process.

Download the example xpr file [here](https://mega.nz/#!yQFgFSLa!aNd1kYDqzX4c_Pyq79pg-e7Gf3UJqB_RvNrtnOskmn0).
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:45:00+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

Let's open it with HexEdit. The first thing I usually do is to measure the size of the whole file. Press the EOF button at the lower left of the calculator
and it says 0x67F000. OK, let's analyze the data.

The first 4 bytes is the file magic: "SMX7", which's the only thing that can verify the archive. 



The 3 fields in the green retangles are easy to figure out, while those in the black frame are still unknown:



Then we measure the size from 0xA0 to where these data ends:



It's approximately 0x134F, which's close to 0x1354 from the header. And we can notice that there're a lot of zero bytes coming after and terminates at
offset 0x1800, where the magic "TX2D" starts. So we now know another two fields of the header:



And also the padding size referring to offset 0: 0x800 bytes.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:46:00+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

We continue the analysis from 0x1800, and measure the size from here to where this chunk ends. Note that the end offset must be a multiple of 0x800.
So we get it at 0x2800. 0x2800 - 0x1800 = 0x1000, which can be found at the header.

Here at 0x2800 we see another magic: "KFSQ". Again let's measure the size of this chunk. It seems difficult to located where it ends, so we measure it
till its last nonzero byte, which is 0x290155. That perfectly matches with the value 0x290800 at the header. 

Let's see how many bytes are left. We jump over 0x290800 bytes from 0x2800, and subtract the current address from the total file size: 
0x67F000 - 0x290800 - 0x2800 = 0x3EC000. Can you tell where this value is?
So we're getting closer now:
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:48:13+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

Now we have to figure out the structure of each chunk. Start with the "TX2D" chunk first. Jump to 0x1800, where we can see a lot of "TX2D" markers. 
For convenience of analysis, we need to align them like this:



Let's see how many markers there are: 0x12C / 0x14(20) = 0xF. So the 00 00 00 0F at the header is the count of these markers. Same thing can be applied to the "KFSQ" chunk. Therefore we get almost the entire header reversed.



Then we continue our research on the "TX2D" chunk. First we need to have an overall idea of how this chunk is organized:
the "TX2D" Table, a filename Table, then some more alignable data.

Let's try to have a look at the "TX2D" table and see if we can find something.



We notice that the values in each green frame are all in an increasing order. That means these values could be some offsets. And since they're all minner than the current position, they should be relative to somewhere around. 

Then what would these offsets direct to? Of course, the filename table, and the unknown data followed probably, what else? 
With some assumptions and validations soon we can figure out the answers:



All these offsets are relative to where the "TX2D" table begins. While the structure of the texture info header table is like:



But the offset is relative to where the textures data chunk starts.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-28T03:48:52+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

Similarly, we can also reverse the structure of the "KFSQ" chunk. But I'm not going to explore it here. Consider it as a task for practicing.
But in the BMS scripting part, I'll expose you the whole structure of the archive.

Finally, we have reached the end of this manual researching section. Thanks for reading!

[Return to the main tutorial.](https://forum.xentax.com/viewtopic.php?p=138998#p138998)
## Post #6
- Username: shaunanthonywheeldon
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 28, 2018 3:27 am
- Post datetime: 2018-08-27T19:35:10+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

Hello I am trying to extract models from Heroes of Might and Magic Quest for the Dragon Bone Staff, I have managed with help to get down to I believe perhaps the last set of files. I cannot access the models or textures as I believe knowledge in Hex is needed. I have attached a file and would really appreciate it if you would take a ganders. 

Thank you.  
[model_Giants.zip](https://xentaxbackup.github.io/file/14795_model_Giants.zip)
## Post #7
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T21:10:40+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

> Reply from Bigchillghost ↑Wed Mar 28, 2018 11:48 am at Wed Mar 28, 2018 11:48 am
>
> 
Let's see how many markers there are: 0x12C / 0x14(20) = 0xF.
I am not sure if it's allowed to post on this thread or not, but where did you get 0x14 from?
## Post #8
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T21:27:05+00:00
- Post Title: Analyzing and Reverse Engineering a Game Archive

Also how do I align them?
