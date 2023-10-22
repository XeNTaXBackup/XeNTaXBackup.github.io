## Post #1
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-01-19T14:28:46+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

Hello,

I did a little research about getting those .eix and .epk files found mainly in the Metin2 pack folder open. Youtube finally gave me the answer and the file extractors as well (link is available, if there's need for it; video maker does give the explanation in German, though...). So I went and searched for the warrior model I'm searching like forever. Found it as well with the right armor texture I wanted. Now I've encountered a new problem: When getting the file out of the packed one, I searched for a program to open up the .gr2 file and stumbled upon the Granny Viewer - file gets read easily and looks almost like in the game, but it doesn't seem to read the texture file (file extension is .dds) and display the model as it's supposed to be.
So, my new question is: How do I get the Granny Viewer to read the .dds texture file as well? And when this is done, how am I supposed to convert that model into a different file (e. g. .obj or .xps)?

Any help is greatly appreciated  See ya around!
## Post #2
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-01-19T16:09:20+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

Textures must be placed into specific path. Open your model in Granny Viewer and check texture tab for that path.

For warrior armor it propably is "D:\ymir work\pc\warrior"

For converting it to obj you must first convert gr2 to 3ds max script and then open it in 2007 3dsmax 7 and then finally export as obj
## Post #3
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-01-19T16:13:08+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

> Reply from glupiekonto
>
> Textures must be placed into specific path. Open your model in Granny Viewer and check texture tab for that path.

For warrior armor it propably is "D:\ymir work\pc\warrior"

For converting it to obj you must first convert gr2 to 3ds max script and then open it in 2007 3dsmax 7 and then finally export as obj

That's a good heads-up, but there comes the next problem on the screen: I don't have a HDD/SSD which is named D:, 'cause my DVD drive is named D:. The model/texture files are on the HDD starting on path E: - is there a way to change the connected path on the model file?
## Post #4
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-01-19T16:18:42+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

I'm not sure whether it works but check out this [http://aoe3wol.com/forum/viewtopic.php?t=397](http://aoe3wol.com/forum/viewtopic.php?t=397)

Once you convert your model to .obj that path doesn't really matters because you will have to create material manually.
## Post #5
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-01-19T16:24:18+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

You will propably need this - newest granny converter. I'm not sure where I found it but with 3dsmax7 I was able to use Metin models inside newest Blender.
[https://mega.nz/#!bVNSVQpb!6wm4a2vSazK3 ... QxuGoUyD_0](https://mega.nz/#!bVNSVQpb!6wm4a2vSazK37cc0L1CyZQX_I0gTNuTUsQxuGoUyD_0)
## Post #6
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-01-19T16:30:41+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

Now... Is there a 3ds max 7 somewhere on the web? Can't seem to find it...
## Post #7
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-01-19T16:41:55+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

Search for "metin2 3dsmax7"

Good guesses are mpcforum, metin2dev, elitepvpers, metin2downloads
There are also tutorials on things you want to do
## Post #8
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-01-20T06:20:44+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

The script importing works and I get to the Material selector, but then... The texture file doesn't get opened by 3dsmax. But my main problem is still there: I can't seem to open the .dds files - they seem to be broken. Is there a way to get them open/convert them? I already made the static object plus (since I need it for XPS/XNALara) the corresponding .mtl library. Now the question is: Are the bones visible in the Granny Viewer all deleted or are they still there?

Then getting up on this sentence here:

> Once you convert your model to .obj that path doesn't really matters because you will have to create material manually.

Now, in Blender (I think it is Blender) I need to create that material. Which material and are those the final textures?
## Post #9
- Username: glupiekonto
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 20, 2019 12:07 am
- Post datetime: 2019-01-20T11:10:34+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

As I haven't learnt 3ds max I wont be able to help you with that. I was only using it to run ms scripts.
I was able to open skeleton with some Neverwinter Nights 2 3dsmax plugin but exporting bones doesn't work for me.

Almost every plugin is listed on this archieved page [http://web.archive.org/web/*/http://gr2 ... vista.org/](http://web.archive.org/web/*/http://gr2decode.altervista.org/)

In Blender I've just used diffuse shader as only diffuse texture is provided with metin files.
Worth to note that basic warrior body consists hair, face, body and knee pads. (4 separate meshes, 1 texture for face, 1 for hair and 1 for body and knee pads)

I will PM you with my archives where I scrapped all I could find about Metin files.
## Post #10
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-05-25T09:55:40+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

*blows some dust away*
Seems like I've got a new problem here:
After all that hussle with the character was over, I was quite happy - until a couple of days ago... It hit me like lightning, but for all those comics I plan to make with that character, I completly forgot that he needs a weapon to fight! Now I wanted to get the model file for that (I plan on getting the Kyanite Blade, which is a two-handed weapon), got the file, but the granny viewer ruins it. It says that the file failed the CRC check and is likely corrupted.

So I did a little research to when that weapon found its way into the game - and I was able to dig that information out: The patch with that weapon was implemented on April 16, 2018 (which is a little over 13 months ago). That stuff is quite fresh, but yet, I fail to get the model file working... Can anyone please help me out again with that game model? Also, I can't seem to find the matching texture file... If there's no way to get this model, I'd switch to the Red Iron Blade instead (texture for that one is also available!)
## Post #11
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2019-05-28T15:31:25+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

Hey,

If it's corrupted, it means it wasn't extracted properly. Some packs can be extracted, but their content is corrupted by the crypt method used in the officiel client.
I highly recommend you to use the files you could find in other forums, someone shared a fully unpacked client from september 2018, and every unpacked update since then.
## Post #12
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-05-29T15:19:05+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

> Reply from illian ↑Tue May 28, 2019 11:31 pm at Tue May 28, 2019 11:31 pm
>
> 
Hey,

If it's corrupted, it means it wasn't extracted properly. Some packs can be extracted, but their content is corrupted by the crypt method used in the officiel client.
I highly recommend you to use the files you could find in other forums, someone shared a fully unpacked client from september 2018, and every unpacked update since then.

I searched for that, but now I can't track the way back to where I found the file for the weapon I want... I also did some research and that weapon was implemented (along with much more stuff) in April 2018. Otherwise I'm just using the other weapon where I found the model AND textures by myself, since the Kyanite Blade hasn't been available at all times - I think...
## Post #13
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2019-05-29T21:23:02+00:00
- Post Title: Metin2 to Granny Viewer reading .gr2 and .dds files

> Reply from LightXPS ↑Wed May 29, 2019 11:19 pm at Wed May 29, 2019 11:19 pm
>
> 
I searched for that, but now I can't track the way back to where I found the file for the weapon I want... I also did some research and that weapon was implemented (along with much more stuff) in April 2018. Otherwise I'm just using the other weapon where I found the model AND textures by myself, since the Kyanite Blade hasn't been available at all times - I think...

I've sent you a PM.
