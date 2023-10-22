## Post #1
- Username: ShamanSmithy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 28, 2021 1:20 am
- Post datetime: 2021-08-27T19:34:05+00:00
- Post Title: Black and White 2 - Unknown Data Preceding Primitives

Hello,

For the past several months I've been hard at work decoding a 3D model format for a game I use to play all the time when I was young. The game was Black and White 2, created by Lionhead studios.

Their game uses a custom model format, the vast majority of which I've decoded. To the point where I've been able to use Panda3D to display the models in all their glory and even convert OBJ files into working models for the game using python. However, there is a chunk of data prior to the primitive data that I haven't yet been able to decode. I'm wondering if there is anyone here who might be able to assist me with decoding this information?

The model geometry first starts with primitive structure information, like how many pieces of information there is and what order they are in. Most of them appear to follow: Vertex, Normal, UV1, UV2, UV3 type of organization, with triangular faces. The second chuck of data is the section I require help with (generally 92 bytes long). Then we have the primitives, organized based on the information above. Followed finally by the indices.

Here is an example (little endian format):



UnknownSection.PNG (28.79 KiB) Viewed 46 times


In the header of the file there is an offset value that points to the location boxed with the green rectangle. I've highlighted it because I assume there must be something of import regarding that particular number - but I might be wrong.

An individual who worked on decoding these models before me referred to this unknown section as a stride. However, they weren't entirely sure themselves what this section was or how to decode it. For most models it is only 92 bytes long and inconsequential. For several models to set all the values in this section to 0; there were no observable differences in how the model looked in game. Which is way I've been relatively successful at generating our own custom models that actually work while setting this whole section to zero.

My attempts to analyze this section has produced some results. In the above example the value 69 00 00 00 = 105 which is the same the number of indices in the last mesh of the model. The last mesh is generally a small wire frame (I think that's what you call it) that surrounds the object. I suspect for physics related mechanics, like when the object hits the ground and rolls over. Furthermore, the value 23 00 00 00 = 35 is the number of faces the last mesh has. This is consistent across 10 other models that I've checked.

For some models this section appears quite differently and is much less inconsequential. For these models, rather than a mere 92 bytes of information, there's 1196 bytes. The guy previously decoding these files identified what he believed to be a value in the header that specifies how many "strides" there are. For these models that value is 9, for models like the one the above example was taken from that value is 1. The data in these other models is also very receptive nor does 1196 divide nicely into 9, bringing into question the validity of there being 9 "strides" or they are of variable length.

From the tests I've run, these models with the much larger sections have incomplete list of indices. Which makes me think that this section outlines either compression information, or multiple reads of the primitive data.

Is there anyone here they might know what this information is and how to decode it?
## Post #2
- Username: ShamanSmithy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 28, 2021 1:20 am
- Post datetime: 2021-09-01T17:40:45+00:00
- Post Title: Black and White 2 - Unknown Data Preceding Primitives

An update:

I spent the last few days analyzing the data, and some of the revelations have rendered the majority of my speculations in the original post invalid.

The model files support a multitude of strides. Each stride is 136 bytes or 34 integers. For example (little endian):



Stride2.PNG (20.95 KiB) Viewed 27 times



The first integer is the number of items that make up the data. What each item is and the size are specified by the values that follow, where the first value is the item type, the second is the size. For the above example, there are 4 items. The next zero is vertex position, the value of 2 indicates that this item is 3 floats in length. The next item has an id of 1, meaning normal, has the same size value as the previous, so 3 floats. Then we have two UV items each with a size of 1, meaning 2 floats.

```
Item 1{
    00 00 00 00 -> Item id, 0 = vertex
    02 00 00 00 -> item size, 2 = 3 floats
}
Item 2{
    01 00 00 00 -> Item id, 1 = Normal
    02 00 00 00 -> item size, 2 = 3 floats
}
Item 3{
    02 00 00 00 -> Item id, 2 = UV
    01 00 00 00 -> item size, 1 = 2 floats
}
Item 4{
    02 00 00 00 -> Item id, 2 = UV
    01 00 00 00 -> item size, 1 = 2 floats
}

```


The rest of the data is very likely garbage. Whether there is 1 item or 5 the data remains 136 bytes. This would suggest that there is a limit to the number of items a stride may have, which would be roughly 16. My mistake in the original post was assuming the vertex structure was separate from the following data.

However, there are more questions.

Those models that possess multiple strides are those that contain some sort of joint system. These particular files contain a set of data near the beginning of the file that is in the format of 4x3 floats. The 4th set of floats appears to be a position on the model, I suspect these are joint definitions. However, there are no details as to the skeletal structure. So, I'm confused what this matrix means.

```
    float unknown1[3];
    float unknown2[3];
    float unknown3[3];
    float Position[3]; //x,y,z
}

```


These models contain 9 strides. the first stride contains the vertex structure just like the example above. The next 4 strides have 1 item, identified as 6 with a size identifier of 4. Essentially, for each vertex there are 4 bytes of data, for each of these strides. The last four have an id of 7 and size 0. For some strange reason there are only 4 strides with the 6,4 item, but there are 5 sets of data that follows after the vertex data.

Essentially, each vertex has a position, normal, UVs, 4 bytes, 4 bytes, 4 bytes, 4 bytes, and 4 bytes. These are likely some sort of matrix.

The first set of 4 bytes seems to connect to the joints, they reference the index of a particular joint. For example the first four bytes of a file, with 12 bones, is 05 0A 08 08. These values are never greater than the number of joints.

Does anyone here know what these matrices are? and how they work?
