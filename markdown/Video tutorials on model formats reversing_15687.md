## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-06T08:14:51+00:00
- Post Title: Video tutorials on model formats reversing

Video tutorials on model formats reversing.

The Last of Us (PS4) remaster (2014)

Part 1 - basic file layout, vertices, faces
[https://www.youtube.com/watch?v=Q-BSLGHZZSs](https://www.youtube.com/watch?v=Q-BSLGHZZSs)
Part 2 - TLoU vs Uncharted 2, EDGE decompression, weights
[https://www.youtube.com/watch?v=VBqYEaqCzxY](https://www.youtube.com/watch?v=VBqYEaqCzxY)
Part 3 - skeleton
[https://www.youtube.com/watch?v=Cwji54Qmpos](https://www.youtube.com/watch?v=Cwji54Qmpos)

Far Cry Primal (2016)
[https://www.youtube.com/watch?v=-1b3bM7ih6Y](https://www.youtube.com/watch?v=-1b3bM7ih6Y)
This is an example of easy modern formats. Only 10 minutes to reverse the static geometry.

Planetside (2003) model format full reversing. Shows how to split and identify different parts of model data inside files: geometry, faces, UVs, normals, submeshes, materials, bones. Basic knowledge of hex data is required: how to read "little endian" integers and floats in hex.

This is an old game, and many format parts are different from modern standards, so this one is complex and takes more than an hour in 4 parts. Sorry for sound quality in first part, that was my first tutorial. Other parts have much better sound.

Part 1
[https://www.youtube.com/watch?v=LHWOp4YeeoQ](https://www.youtube.com/watch?v=LHWOp4YeeoQ)
Part 2
[https://www.youtube.com/watch?v=WtIY05ZdBvI](https://www.youtube.com/watch?v=WtIY05ZdBvI)
Part 3
[https://www.youtube.com/watch?v=znHaG38URp0](https://www.youtube.com/watch?v=znHaG38URp0)
Part 4
[https://www.youtube.com/watch?v=S4Fcdj4I12Q](https://www.youtube.com/watch?v=S4Fcdj4I12Q)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-11T15:57:32+00:00
- Post Title: Video tutorials on model formats reversing

Can I please have some feedback on this? 

Its a bit hard to make "puzzle solving" video when I already solved it, there may be mistakes. Also I know my English is far from perfect. I made a poll here. Maybe this Planetside was too complex. That's why I did it, it has so many interesting parts. But maybe show something easy?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-12T17:38:53+00:00
- Post Title: Video tutorials on model formats reversing

I'm more a reader than a watcher so I can't tell too much.
But 'yes', half an hour for part one is a little bit too long, I guess.

If the example were easier the video(s) would be shorter.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-14T14:21:19+00:00
- Post Title: Video tutorials on model formats reversing

> Reply from shakotay2
>
> But 'yes', half an hour for part one is a little bit too long, I guess.
If the example were easier the video(s) would be shorter.

Thanks for the comment! 

Yes, this was complex and interesting format, which actually encouraged me to finally record this. And yes, easy example is a good idea, so today I'm adding the 10 minutes easy tutorial.

p.s. Added Far Cry Primal tutorial to the first post.
## Post #5
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2017-01-14T15:36:38+00:00
- Post Title: Video tutorials on model formats reversing

> Reply from daemon1
>
> shakotay2 wrote:But 'yes', half an hour for part one is a little bit too long, I guess.
If the example were easier the video(s) would be shorter.

Thanks for the comment! 

Yes, this was complex and interesting format, which actually encouraged me to finally record this. And yes, easy example is a good idea, so today I'm adding the 10 minutes easy tutorial.

p.s. Added Far Cry Primal tutorial to the first post.

Thanks man, this should help lots.
## Post #6
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2017-01-14T15:39:04+00:00
- Post Title: Video tutorials on model formats reversing

And yes you should do more tutorials, but one thing, please use a modern hex editor and not a DOS based one.
## Post #7
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-14T16:56:03+00:00
- Post Title: Video tutorials on model formats reversing

Awesome! For myself, personally, I'm thinking a tutorial on how to go about identifying compression/data format of game files, making use of QuickBMS scripting and/or specifically using 010 Editor for hex editing and its scripting could help me get more insights. I specifically mention 010 Editor, because I'd like to see how creating a 010 Editor script/Binary Template such as [viewtopic.php?p=94871#p94871](http://forum.xentax.com/viewtopic.php?p=94871#p94871) could help in a workflow tutorial video. I'm suspecting it eases lots of manual translation/interpretation work.
I'm thinking an explanation video of your Far Cry Primal mammothcarcass_scavenged_01 using the 010 Editor (using its Inspector window to quickly see a type value, and/or possibly defining your own types to show there) might result in a shorter video. 

Oh, and if you ever need to do a hex comparison between files or something, an app called "Beyond Compare" may be useful for visualizing binary/hex differences.

Your English is understandable, so that's good! However, as someone who's just interested in modding games rather than merely extracting resources from them, I'm probably not really the intended audience; I'm no animator & I'm still getting my head wrapped around terms like LOD, (sub)meshes, materials vs textures, faces, geometry, UVs, normals?, bones. Perhaps a conceptual structure of a model format would help, something like (this is probably wrong:) a game object would typically include a model file (containing one or more LODs, each containing one or more materials, one or more vertices, materials), textures (sometimes defined as .dss files, having 4 distinct alpha layers, each of which also means something), animations, sounds, physics data. And then only focus on the 'models' part. But that could just be me requiring further studying. 

I assume you're doing some off-video background programming to read the binary data from the model into a file to import in 3D Studio Max or whatever it is you have there in the video? Can QuickBMS or a series of standard tools be used for that, rather than programming?
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-15T10:18:14+00:00
- Post Title: Video tutorials on model formats reversing

> Reply from eri619
>
> And yes you should do more tutorials, but one thing, please use a modern hex editor and not a DOS based one.
I'm not familiar with modern hex editors, if I'll try using them, tutorials will be slower and worse.

Whats the problem with this one? Colors, or anything else?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-15T10:35:45+00:00
- Post Title: Video tutorials on model formats reversing

Yes I know 010 editor can be useful for beginners. But it will not ease anything for me. I don't see how it can make video shorter. Of course, if I make a template, and just show it, it will be short. But the purpose of this tutorial is to show how you can analyse the data, not just show the already reversed files.

As for basics, a hex/data/term tutorial can also be done, but first I wanted to check how can I do that in general. Just a first example for a test. So maybe later.

> Reply from bouvrie
>
> I assume you're doing some off-video background programming to read the binary data from the model into a file to import in 3D Studio Max or whatever it is you have there in the video? Can QuickBMS or a series of standard tools be used for that, rather than programming?
Yes, I'm not showing the programming part. And writing a QuickBMS script IS actually a programming. Writing a standalone tool is not much different from BMS scripting. Moreover, I'd say "normal" programming is even easier. With all the free tools of today.
## Post #10
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-16T00:18:31+00:00
- Post Title: Video tutorials on model formats reversing

> Reply from daemon1
>
> Yes I know 010 editor can be useful for beginners. But it will not ease anything for me. I don't see how it can make video shorter.I don't know 010 editor much, I just assumed the Inspector would be handy, as you can skip the 'windows calculator' bit (all values the hex can translate to are in the Inspector window). And I thought perhaps a 010 Editor Binary Template would allow for a more insightful way of analyzing similar files in the future. It's kind of a step between analyzing hex and creating a BMS script, right? I figured making a Binary Template would be somewhat like taking 'notes', only in a more structured way; once the Template covers the file, you know you defined/researched it completely. At some point, the observations must be put in an algorithm or file definition, if that process were part of the tutorial you'd have documented the whole workflow. 
*edit* Ah, something like you did on the [Planetside .uber video @ 8m40s](https://www.youtube.com/watch?v=LHWOp4YeeoQ#t=8m35s). 

Basically in the video, you go from geometry to face data. You scroll down, and after a while you get to the "face data". All I see as a n00b is that the hex pattern changes a bit. I wouldn't have a clue what the fingerprint/pattern of face data is, or how to distinguish 32-/64 bits floats and (Unsigned)integers from just looking at their hex representation, let alone deal with data that is encrypted/compressed in some way... I just figured that if there's another (more graphical) hex editor, perhaps they can highlight/mark distinct patterns when it encounters them. That'd make looking through the file easier to understand. But I really appreciate the videos in HIEW already, I just need to do some more manual work and practice to get better at it!
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-16T18:02:47+00:00
- Post Title: Video tutorials on model formats reversing

It's good that you described your impression. It will be useful to me to improve tutorials.

No I can't skip calculator part, inspector will not help in this case. I'm not representing hex as other types, I'm making calculations there.

> Reply from bouvrie
>
> It's kind of a step between analyzing hex and creating a BMS script, right?
Yes, it's kind of step between, but this step is not needed. If the file is simple, you can write a tool without any templates. If the file is complex, it will take time to make a template, and then you have to rewrite it all again into the tool, so in any case you will only lose time. So as I said before, templates are only needed if you're a beginner, or if you have bad memory  

I'm making notes and pictures (on a paper), and this is more convenient for me than templates. The picture you see on the Planetside .uber video is what I had in my memory when reversing. This was only needed to explain it to the viewers, you can't make such a thing in 010 editor.

> Reply from bouvrie
>
> I just figured that if there's another (more graphical) hex editor, perhaps they can highlight/mark distinct patterns when it encounters them
No, there's no such a thing. No editor can tell faces from vertices, you have to do it all yourself.

> Reply from bouvrie
>
> All I see as a n00b is that the hex pattern changes a bit
That's right, I also only see this. I even said that in a video, I don't know where vertices end and where faces start. The only way is make an assumption, check it. If its wrong, make another one, and check again. With time and experience, you will usually be able to make it right from the first try. I'm trying to explain how do to that.
## Post #12
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-19T15:28:54+00:00
- Post Title: Video tutorials on model formats reversing

Ah ok, I was expecting too much advanced tooling for reverse engineering. I figured since there are file rippers that can (deep) scan unknown files for headers of possible known resources contained therein (i.e. wav/voc/MP3/png/etc) and extract them, having such a pattern searching/highlighting feature embedded in a hexeditor interface could speed up the process of identifying the data format. That's what I was hoping 010 Editor could do, guess I was wrong.

Personally, I also kinda used pen and paper (do screenshots annotated in Paint count?:P) for making sense of the Far Cry 4 Map Format. Part of the file (header) is easily identifyable (ASCII strings, PNG file), after which the actual map data comes in a segment with the "FC3M" header. I think that part is compressed as I can't make anything from it without using the Dunia tools to extract it to dat/fat.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-19T15:39:17+00:00
- Post Title: Video tutorials on model formats reversing

> Reply from bouvrie
>
> headers of possible known resources contained therein (i.e. wav/voc/MP3/png/etc)

Yes, these are easy to detect automatically. They can be easily seen in hex as well. But you need some practice to read any custom data. Do you think it will be useful if I make basic hex/int/float reading tutorial now? There's a comprehensive text tutorial here on xentax, but do you think visual example will be easier to understand?
## Post #14
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2017-01-20T12:59:06+00:00
- Post Title: Video tutorials on model formats reversing

> Reply from daemon1
>
> Do you think it will be useful if I make basic hex/int/float reading tutorial now? There's a comprehensive text tutorial here on xentax, but do you think visual example will be easier to understand?Well, I haven't even looked at textual tutorials for this yet, so your time could be better spent! 

A visual interface could just help researchers reverse data formats, IF they (an Inspector Window of sorts) would be able to intelligently scan and 'guess' some data based on known patterns, and try to display it as such a picture/texture, play it as such a sound/movie, etc. That way you don't have to manually re-invent the wheel all over again.

And while there is no such thing, HIEW does the job just fine. Although it isn't sexy and could scare off people who may want to start modding, but aren't all that accustomed to console windows.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-09T16:55:52+00:00
- Post Title: Video tutorials on model formats reversing

A new tutorial on "The Last of Us (PS4) remaster" (2014) added
[https://www.youtube.com/watch?v=Q-BSLGHZZSs](https://www.youtube.com/watch?v=Q-BSLGHZZSs)
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-12T14:00:40+00:00
- Post Title: Re: Video tutorials on model formats reversing

TLoU part 2. Includes TLoU vs Uncharted 2 part, EDGE decompression and weights. After all, EDGE proved to be different in different games, though, nothing impossible.

[https://youtu.be/VBqYEaqCzxY](https://youtu.be/VBqYEaqCzxY)
## Post #17
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2018-06-05T08:42:30+00:00
- Post Title: Re: Video tutorials on model formats reversing

It ended?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-05T08:47:52+00:00
- Post Title: Re: Video tutorials on model formats reversing

what exactly is ended?
## Post #19
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-06-06T03:30:12+00:00
- Post Title: Re: Video tutorials on model formats reversing

I think he's trying to find out if you ended the tutorials, or there will be more in the future in various ways/games and such.
## Post #20
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-07-29T21:57:03+00:00
- Post Title: Re: Video tutorials on model formats reversing

Hum interesting, I can already read and make tools to export mesh, the only thing I'm unable to do is : read/export Bones/Skeleton animation and sometimes textures/palettes, so I think it's time for me to watch those tutorials. ; )

Thank you again daemon1 for your contributions.
## Post #21
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-14T10:07:42+00:00
- Post Title: Re: Video tutorials on model formats reversing

Is it possible to do a tutorial on how to find encryption keys
or how to find out how exe read un-common structures
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-17T15:14:45+00:00
- Post Title: Re: Video tutorials on model formats reversing

> Reply from JohnHudeski ↑Tue May 14, 2019 6:07 pm at Tue May 14, 2019 6:07 pm
>
> 
Is it possible to do a tutorial on how to find encryption keys
or how to find out how exe read un-common structures
find encryption keys - not very good idea. Such things are better kept private.
As for "how exe read" - this is rather generic, so no need to do special video about game formats, there are many existing tutorials in reverse engeneering area to cover this.
## Post #23
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-18T16:27:03+00:00
- Post Title: Re: Video tutorials on model formats reversing

But if the archive file containing the model asset or the ai lua is in an encrypted file.
For example, there was a game that encrypted all the game settings xml in blowfish
It really sucked cos the game had broken AI
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-01-30T16:51:12+00:00
- Post Title: Re: Video tutorials on model formats reversing

People asked me to make a video of real reversing process, from start to finish, thinking, making mistakes and so on.
I take an example from Twisted Metal (2012) game on PS3.

[https://youtu.be/YXVuRl1QPrg](https://youtu.be/YXVuRl1QPrg)
[https://youtu.be/b9-kkkL8Q2s](https://youtu.be/b9-kkkL8Q2s)
## Post #25
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2020-02-13T21:30:47+00:00
- Post Title: Re: Video tutorials on model formats reversing

Thanks for you! For sharing tutorials and tips
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-02-18T16:04:46+00:00
- Post Title: Re: Video tutorials on model formats reversing

2 more tutorials using same twised metal game as an example, so you can better understand how the above work was done:

Basic things about 3d data reversing: how 3D data looks like in hex: compression, encryption, common data types (ints/floats), main data structures (geometry/bones/textures)
[https://www.youtube.com/watch?v=i_uWw-UDpEo](https://www.youtube.com/watch?v=i_uWw-UDpEo)

Finding geometry buffers and their properties
[https://www.youtube.com/watch?v=swdOXDVkGUU](https://www.youtube.com/watch?v=swdOXDVkGUU)
## Post #27
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-03-31T02:01:39+00:00
- Post Title: Re: Video tutorials on model formats reversing

Thanks for making the tutorials, I followed Twisted Metal PS3 reversing and wrote your code got the car .obj from ui.ngp
How can I make it work with little endian.

HJA_test

```
using System.Collections.Generic;
using System.IO;
using System.Text;
using System.Globalization;

namespace HJA_test
{
    class BinaryReaderBE : BinaryReader
    {
        private byte[] a16 = new byte[2];
        private byte[] a32 = new byte[4];
        private byte[] a64 = new byte[8];
        public BinaryReaderBE(System.IO.Stream stream) : base(stream) { }
        public override float ReadSingle()
        {
            a32 = base.ReadBytes(4);
            Array.Reverse(a32);
            return BitConverter.ToSingle(a32, 0);
        }
        public override UInt16 ReadUInt16()
        {
            a16 = base.ReadBytes(2);
            Array.Reverse(a16);
            return BitConverter.ToUInt16(a16, 0);
        }
        public override Int16 ReadInt16()
        {
            a16 = base.ReadBytes(2);
            Array.Reverse(a16);
            return BitConverter.ToInt16(a16, 0);
        }
        public override Int32 ReadInt32()
        {
            a32 = base.ReadBytes(4);
            Array.Reverse(a32);
            return BitConverter.ToInt16(a32, 0);
        }
        public override UInt32 ReadUInt32()
        {
            a32 = base.ReadBytes(4);
            Array.Reverse(a32);
            return BitConverter.ToUInt32(a32, 0);
        }
        public override long ReadInt64()
        {
            a64 = base.ReadBytes(8);
            Array.Reverse(a64);
            return BitConverter.ToInt64(a64, 0);
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            NumberFormatInfo nfi = new NumberFormatInfo();
            nfi.NumberDecimalSeparator = ".";

            float x = 0;

            var sw = new StreamWriter(Path.GetFileNameWithoutExtension(args[0]) + ".obj");
            sw.Write(x.ToString("0.######", nfi));
        }
    }
}
```


TM2012

```
using System.Collections.Generic;
using System.Linq;
using System.IO;
using System.Text;
using System.Globalization;

namespace TM2012
{
    class BinaryReaderBE : BinaryReader
    {
        private byte[] a16 = new byte[2];
        private byte[] a32 = new byte[4];
        private byte[] a64 = new byte[8];
        public BinaryReaderBE(System.IO.Stream stream) : base(stream) { }
        public override float ReadSingle()
        {
            a32 = base.ReadBytes(4);
            Array.Reverse(a32);
            return BitConverter.ToSingle(a32, 0);
        }
        public override UInt16 ReadUInt16()
        {
            a16 = base.ReadBytes(2);
            Array.Reverse(a16);
            return BitConverter.ToUInt16(a16, 0);
        }
        public override Int16 ReadInt16()
        {
            a16 = base.ReadBytes(2);
            Array.Reverse(a16);
            return BitConverter.ToInt16(a16, 0);
        }
        public override Int32 ReadInt32()
        {
            a32 = base.ReadBytes(4);
            Array.Reverse(a32);
            return BitConverter.ToInt16(a32, 0);
        }
        public override UInt32 ReadUInt32()
        {
            a32 = base.ReadBytes(4);
            Array.Reverse(a32);
            return BitConverter.ToUInt32(a32, 0);
        }
        public override long ReadInt64()
        {
            a64 = base.ReadBytes(8);
            Array.Reverse(a64);
            return BitConverter.ToInt64(a64, 0);
        }
    }
    class tm2012
    {
        static void Main(string[] args)
        {
            NumberFormatInfo nfi = new NumberFormatInfo();
            nfi.NumberDecimalSeparator = ".";

            int i;
            float x, y, z;

            var fs = new FileStream("C:\\ui.ngp", FileMode.Open, FileAccess.Read);
            var br = new BinaryReaderBE(fs);
            var sw = new StreamWriter("ui.obj");

            fs.Seek(0x29ef30, SeekOrigin.Begin);
            int nv = 0x12f8;
            for (i = 0; i < nv; i++)
            {
                x = br.ReadInt16() / 4096f;
                y = br.ReadInt16() / 4096f;
                z = br.ReadInt16() / 4096f;
                sw.Write("v " + x.ToString("0.######", nfi));
                sw.Write("  " + y.ToString("0.######", nfi));
                sw.Write("  " + z.ToString("0.######", nfi));
                sw.WriteLine();
            }

            fs.Seek(0x298500, SeekOrigin.Begin);
            int nf = 0x3513 / 3;
            int f1, f2, f3;
            for (i = 0; i < nf; i++)
            {
                f1 = br.ReadUInt16() + 1; f2 = br.ReadUInt16() + 1; f3 = br.ReadUInt16() + 1;
                sw.WriteLine("f " + f1 + " " + f2 + " " + f3);
            }

            sw.Close();
        }
    }
}

```
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-03-31T05:25:50+00:00
- Post Title: Re: Video tutorials on model formats reversing

Change this:

```
var br = new BinaryReaderBE(fs);
```


to this:

```
var br = new BinaryReader(fs);
```


It will use the "usual" BinaryReader, which is little endian.
## Post #29
- Username: EPYCSPYDER
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Feb 06, 2020 7:48 pm
- Post datetime: 2020-03-31T18:05:34+00:00
- Post Title: Re: Video tutorials on model formats reversing

Any chance you would do a code tutorial on the smd mesh/skeleton blender tools you used with The Last of Us?
## Post #30
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-02-25T06:19:10+00:00
- Post Title: Re: Video tutorials on model formats reversing

daemon's videos are very well organized, so alot of respect to him for making these videos because they are so clear and informative.

I would like to also share some information and videos, for those who may be interested.. If this is not okay to share here then please let me know and I will remove it. 


My Own Videos:
14:17 -> What is Binary
12:20 -> Hex Editing
21:41 -> Programming
14:36 -> Programming with Data Types
12:07 -> Hex Editor
09:43 -> Model Theory
24:58 -> Format Study
18:23 -> Writing C++ Byte Class
12:20 -> Writing C++ Mesh Reader / Exporter
34:51 -> Writing Maxscript Mesh Importer
34:12 -> Writing Noesis Python Mesh Importer


Simple Code Examples

Blender

```
import struct
from pathlib import Path

SEEK_ABS = 0
SEEK_REL = 1
SEEK_END = 2

class fopen:
    little_endian = True
    file = ""
    data = bytes()
    size = 0
    pos = 0
    isGood = False
    def __init__(self, filename = None, mode='rb', isLittleEndian=True):
        if filename != None and Path(filename).is_file():
            self.data = open(filename, mode).read()
            self.size = len(self.data)
            self.pos = 0
            self.file = filename
            self.little_endian = isLittleEndian
            self.isGood = True
        return None

    def read_and_unpack(self, unpack, size):
        '''
          Charactor, Byte-order
          @,         native, native
          =,         native, standard
          <,         little endian
          >,         big endian
          !,         network

          Format, C-type,         Python-type, Size[byte]
          c,      char,           byte,        1
          b,      signed char,    integer,     1
          B,      unsigned char,  integer,     1
          h,      short,          integer,     2
          H,      unsigned short, integer,     2
          i,      int,            integer,     4
          I,      unsigned int,   integer,     4
          f,      float,          float,       4
          d,      double,         float,       8
        '''
        value = 0
        if self.size > 0 and self.pos + size < self.size:
            value = struct.unpack_from(unpack, self.data, self.pos)[0]
            self.pos += size
        return value

    def set_pointer(self, offset):
        self.pos = offset
        return None

def fseek(bitStream, offset, dir):
    if dir == 0:
        bitStream.set_pointer(offset)
    elif dir == 1:
        bitStream.set_pointer(bitStream.pos + offset)
    elif dir == 2:
        bitStream.set_pointer(bitStream.pos - offset)
    return None

def readShort(bitStream, isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'h' if isSigned == 0 else 'H'
    return (bitStream.read_and_unpack(fmt, 2))

def readLong(bitStream, isSigned=0):
    fmt = '>' if not bitStream.little_endian else '<'
    fmt += 'i' if isSigned == 0 else 'I'
    return (bitStream.read_and_unpack(fmt, 4))

def readFloat(bitStream):
    fmt = '>f' if not bitStream.little_endian else '<f'
    return (bitStream.read_and_unpack(fmt, 4))

def mesh (vertices = [], faces = []):
    bpy.context.view_layer.objects.active = None
    msh = bpy.data.meshes.new('Mesh')
    msh.from_pydata(vertArray, [], faceArray)
    msh.update()
    obj = bpy.data.objects.new('Object', msh)
    bpy.data.collections[bpy.context.view_layer.active_layer_collection.name].objects.link(obj)



f = fopen('C:\\Users\\Corey\\Desktop\\grimlock\\models\\vis1\\geo_veh_c_sec_wheel.xgm', 'rb')

fseek(f, 0x1D8, SEEK_ABS)

# Reading Buffer Info
vertex_buffer_size = readLong(f)
index_buffer_size =  readLong(f)

# Calculate the Counts from Buffer Info
vertex_buffer_stride = 24
index_buffer_stride = 2
vertex_count = int(vertex_buffer_size / vertex_buffer_stride)
index_count = int(index_buffer_size / index_buffer_stride / 3)

# Read The buffers
vertArray = []
faceArray = []
fseek(f, 0x29C, SEEK_ABS)

for i in range(0, vertex_count):
    vertArray.append( (readFloat(f),  readFloat(f), readFloat(f)) )
    fseek(f, (vertex_buffer_stride - 12), SEEK_REL)
    
for i in range(0,index_count):
    faceArray.append((readShort(f),  readShort (f), readShort (f)))
    

# make mesh
mesh(vertArray, faceArray)

```

3ds Max (MaxScript)

```

SEEK_ABS = #seek_set
SEEK_REL = #seek_cur
SEEK_END = #seek_end

fseek f 0x1D8 SEEK_ABS

-- Reading Buffer Info
vertex_buffer_size = readLong f
index_buffer_size =  readLong f

-- Calculate the Counts from Buffer Info
vertex_buffer_stride = 24
index_buffer_stride = 2
vertex_count = vertex_buffer_size / vertex_buffer_stride
index_count = index_buffer_size / index_buffer_stride / 3

-- Read The buffers
vertArray = #()
faceArray = #()
fseek f 0x29C SEEK_ABS

for i = 1 to vertex_count do (
	append vertArray [-readFloat f,  readFloat f, readFloat f]
	fseek f (vertex_buffer_stride - 12) SEEK_REL
	)

for i = 1 to index_count do (
	append faceArray ([readShort f,  readShort f, readShort f] + 1)
	)

-- import to the scene
mesh vertices:vertArray faces:faceArray

fclose f

```

Cinema4D

```
import maxon
from c4d import *
from maxon import *

# Enums!
SEEK_ABS = 0
SEEK_REL = 1
SEEK_END = 2

class fopen: # reads file to buffer, and reads values from buffer
    byteStream = maxon.BaseArray(maxon.Char)
    size = 0
    pos = 0
    eof = False # End of Stream
    bebo = False # Big Endian Byte Order
    def __init__(self, filename = ""):
        if filename != "":
            fname = maxon.Url(filename)
            if (fname.IoDetect() ==  maxon.IODETECT.FILE):
                inputStream = fname.OpenInputStream()
                self.size = inputStream.GetStreamLength()
                if self.size > 0:
                    self.byteStream.Resize(self.size)
                    inputStream.ReadEOS(self.byteStream)
                    self.pos = 0
                inputStream.Close()
    def seek (self, offset, curdir = 0):
        if curdir == SEEK_ABS:
            self.pos = offset
        elif curdir == SEEK_REL:
            self.pos += offset
        elif curdir == SEEK_END:
            self.pos = self.size - offset
        if self.pos > self.size or self.pos < 0:
            self.pos = 0
            self.eof = True
        return not self.eof
    def tell (self):
        return self.pos
    def unsigned_to_signed (self, n, nbits):
        result = n
        if (n > pow(2, nbits) / 2):
            result = n - pow(2, nbits)
        return result
    def readByte (self, isSigned = True):
        val = -1
        if self.pos + 1 < self.size:
            val = ord(self.byteStream[self.pos])
            self.pos+=1
            if isSigned: val = self.unsigned_to_signed(val, 8)
        return val
    def readShort (self, isSigned = True):
        byteOrder = [0, 1]
        if self.bebo: byteOrder = [1, 0]
        val = -1
        if self.pos + 1 < self.size:
            val =  ord(self.byteStream[self.pos + byteOrder[0]]) * 0x0001
            val += ord(self.byteStream[self.pos + byteOrder[1]]) * 0x0100
            self.pos+=2
            if isSigned: val = self.unsigned_to_signed(val, 16)
        return val
    def readLong (self, isSigned = True):
        byteOrder = [0, 1, 2, 3]
        if self.bebo: byteOrder = [3, 2, 1, 0]
        val = -1
        if self.pos + 1 < self.size:
            val =  ord(self.byteStream[self.pos + byteOrder[0]]) * 0x00000001
            val += ord(self.byteStream[self.pos + byteOrder[1]]) * 0x00000100
            val += ord(self.byteStream[self.pos + byteOrder[2]]) * 0x00010000
            val += ord(self.byteStream[self.pos + byteOrder[3]]) * 0x01000000
            self.pos+=4
            if isSigned: val = self.unsigned_to_signed(val, 32)
        return val
    def readFloat (self):
        inputAsInt = self.readLong(False)
        fraction = 0.0
        for i in range(0, 23): fraction += (1 & (inputAsInt >> ((23 - i) - 1))) * (pow(2, -(i + 1)))
        sign = -1
        if (inputAsInt >> 31) & 0x00000001 == 0:
            sign = 1
        return (sign * (1 + fraction) * (pow(2, (((inputAsInt & 0x7F800000) >> 23) - 127))))

class mesh: # builds mesh into C4D
    def __init__(self, vertices = [], faces = []):
        if len(vertices) > 0 and len(faces) > 0:
            mypoly = c4d.BaseObject(c4d.Opolygon) #Create an empty polygon object
            mypoly.ResizeObject(len(vertices), len(faces)) #New number of points, New number of polygons
            for i in range(0, len(vertices)):
                mypoly.SetPoint(i, vertices[i])
            for i in range(0, len(faces)):
               mypoly.SetPolygon(i, faces[i])
            doc.InsertObject(mypoly,None,None)
            mypoly.Message(c4d.MSG_UPDATE)
            c4d.EventAdd()


f = fopen("C:\\Users\\Corey\\Desktop\\grimlock\\models\\vis1\\geo_veh_c_sec_wheel.xgm")

f.seek(0x1D8, SEEK_ABS)

# Reading Buffer Info
vertex_buffer_size = f.readLong()
index_buffer_size =  f.readLong()

# Calculate the Counts from Buffer Info
vertex_buffer_stride = 24
index_buffer_stride = 2
vertex_count = int(vertex_buffer_size / vertex_buffer_stride)
index_count = int(index_buffer_size / index_buffer_stride / 3)

# Read The buffers
vertArray = []
faceArray = []
f.seek(0x29C, SEEK_ABS)

for i in range(0, vertex_count):
    vertArray.append(c4d.Vector(f.readFloat(), f.readFloat(), f.readFloat()))
    f.seek(vertex_buffer_stride - 12, SEEK_REL)
    
for i in range(0,index_count):
    faceArray.append(c4d.CPolygon(f.readShort(), f.readShort(), f.readShort()))


# make mesh
mesh(vertArray, faceArray)

```

Noesis

```


def registerNoesisTypes():
    handle = noesis.register("load an xgm", ".xgm")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    noesis.logPopup()
    return 1


def noepyCheckType(data):
    if len(data) < 12: return 0
    f = NoeBitStream(data)
    f.seek(8)
    if f.readInt() != 0x4D534758: return 0
    return 1


def noepyLoadModel(data, mdlList):
    if len(data) < 12: return 0
    f = NoeBitStream(data)
    f.seek(8)
    if f.readInt() != 0x4D534758: return 0

    f.seek(0x1D8, NOESEEK_ABS)

    # Reading Buffer Info
    vertex_buffer_size = f.readInt()
    index_buffer_size = f.readInt()

    # Calculate the Counts from Buffer Info
    vertex_buffer_stride = 24
    index_buffer_stride = 2
    vertex_count = int(vertex_buffer_size / vertex_buffer_stride)
    index_count = int(index_buffer_size / index_buffer_stride / 3)

    # Read The buffers
    vertArray = []
    faceArray = []
    f.seek(0x29C, NOESEEK_ABS)

    for i in range(0, vertex_count):
        vertArray.append(NoeVec3((f.readFloat(), f.readFloat(), f.readFloat())))
        f.seek((vertex_buffer_stride - 12), NOESEEK_REL)

    for i in range(0, index_count):
        f1 = f.readShort()
        f2 = f.readShort()
        f3 = f.readShort()
        faceArray.append(f1)
        faceArray.append(f3)
        faceArray.append(f2)

    # import to the scene
    mdl = NoeModel()
    mdl.setMeshes([NoeMesh(faceArray, vertArray)])
    mdlList.append(mdl)

    return 1

```

QuickBMS

```


# Set File Number
f = 0

goto 0x1D8 f SEEK_SET

# Reading Buffer Info
get vertex_buffer_size long f
get index_buffer_size long f

# Calculate the Counts from Buffer Info
set vertex_buffer_stride long 24
set index_buffer_stride long 2

set vertex_count long vertex_buffer_size
set index_count long index_buffer_size
math vertex_count /= vertex_buffer_stride
math index_count /= index_buffer_stride
math index_count /= 3

# Set ObjFile
set obj string "o mesh"
set temp string ""
string temp p= "%c%c%c%c" 0x0D 0x0A 0x0D 0x0A
string obj += temp

# Read The buffers
set skip long 0
math skip = vertex_buffer_stride
math skip -= 12

goto 0x29C f SEEK_SET
for i = 0 < vertex_count
    
    get pos_x long f
    get pos_y long f
    get pos_z long f
    
    string temp p= "v %f" pos_x
    string obj += temp
    
    string temp p= " %f" pos_y
    string obj += temp
    
    string temp p= " %f" pos_z
    string obj += temp
    
    string temp p= "%c%c" 0x0D 0x0A
    string obj += temp

    goto skip f SEEK_CUR
next i

string temp p= "%c%c%c%c" 0x0D 0x0A 0x0D 0x0A
string obj += temp
for i = 0 < index_count
    get face_a short f
    get face_b short f
    get face_c short f
    
    math face_a += 1
    math face_b += 1
    math face_c += 1
    
    string temp p= "f %i" face_a
    string obj += temp
    
    string temp p= " %i" face_c
    string obj += temp
    
    string temp p= " %i" face_b
    string obj += temp
    
    string temp p= "%c%c" 0x0D 0x0A
    string obj += temp
    
next i

// write the OBJ
strlen obj_size obj
putvarchr MEMORY_FILE obj_size 0
put obj string MEMORY_FILE
get NAME basename
string file_name p= "%s.obj" NAME
log file_name 0 obj_size MEMORY_FILE

```

C++

```
#include <fstream>
#include <iomanip>

using namespace std;

#define SEEK_ABS 0
#define SEEK_REL 1
#define SEEK_END 2

struct bytes {
	ifstream file;
	bool isGood;
	bytes (string filename) {
		file.open (filename.c_str(), std::ifstream::binary);
		isGood = file.good();
		}
	~bytes () {
		file.close();
		}
	int16_t readInt16 () {
		int32_t input;
		file.read(reinterpret_cast<char*>(&input), sizeof(int16_t));
		return input;
		}
	int32_t readInt32 () {
		int32_t input;
		file.read(reinterpret_cast<char*>(&input), sizeof(int32_t));
		return input;
		}
	float readFloat32 () {
		float input;
		file.read(reinterpret_cast<char*>(&input), sizeof(input));
		return input;
		}
	void seek (int offset, int dir = 0) {
		if (dir == SEEK_ABS) {
			file.seekg(offset, file.beg);
			}
		else if (dir == SEEK_REL) {
			file.seekg(offset, file.cur);
			}
		else if (dir == SEEK_END) {
			file.seekg(offset, file.end);
			}
		}
	};

int main() {

	// Open File
	bytes f("C:\\Users\\Corey\\Desktop\\grimlock\\models\\vis1\\geo_veh_c_sec_wheel.xgm");


	// Check is open
	if (!f.isGood) {return 0;}

	// Read the Buffer Info
	f.seek(0x1D8);
	int vertex_buffer_size = f.readInt32();
	int index_buffer_size = f.readInt32();

	// Calculate the Counts from Buffer Info
	int vertex_buffer_stride = 24;
	int index_buffer_stride = 2;
	int vertex_count = vertex_buffer_size / vertex_buffer_stride;
	int index_count = index_buffer_size / index_buffer_stride / 3;


	cout << "vertex_buffer_size: " << vertex_buffer_size << endl;
	cout << "index_buffer_size: " << index_buffer_size << endl;

	// Read Buffer
	f.seek(0x29C);

	// write the OBJ
	std::ofstream out;
	out.open ("C:\\Users\\Corey\\Desktop\\grimlock\\models\\vis1\\geo_veh_c_sec_wheel.obj", std::ofstream::out);

	out << "o meshobject" << endl << endl;

	for (int i = 0; i < vertex_count; i++) {
		out  << std::setprecision(6) << "v " << f.readFloat32();
		out  << std::setprecision(6) << " " << f.readFloat32();
		out  << std::setprecision(6) << " " << f.readFloat32() << endl;
		f.seek(vertex_buffer_stride - 12, SEEK_REL);
		}
	out << endl;
	for (int i = 0; i < index_count; i++) {
		out << "f " << f.readInt16() + 1;
		out << " " << f.readInt16() + 1;
		out << " " << f.readInt16() + 1 << endl;
		}

	out.close();
    return 0;
	}

```

C#

```
using System.IO;
using System.Text;

namespace ModelDumper {
    class Program {
        static int readShort(ref Byte[] buffer, ref int ptr) {
            // Converts Unsigned 16bit Integer from the buffer
            int word = (buffer[ptr++] & 0xFF) | ((buffer[ptr++] & 0xFF) << 8);
            return word;
            }
        static int readLong(ref Byte[] buffer, ref int ptr) {
            // Converts Unsigned 32bit Integer from the buffer
            int dword = (buffer[ptr++] & 0xFF) | ((buffer[ptr++] & 0xFF) << 8) | ((buffer[ptr++] & 0xFF) << 16) | ((buffer[ptr++] & 0xFF) << 24);
            return dword;
            }
        static double readFloat(ref Byte[] buffer, ref int ptr) {
            int inputAsInt = readLong(ref buffer, ref ptr);
            double fraction = 0.0F;
            for (int i = 0; i < 23; i++) {
                fraction += (1 & (inputAsInt >> ((23 - i) - 1))) * (Math.Pow(2, -(i + 1)));
                }
            int sign = -1;
            if (((inputAsInt >> 31) & 0x00000001) == 0) {
                sign = 1;
                }
            return (sign * (1 + fraction) * (Math.Pow(2, (((inputAsInt & 0x7F800000) >> 23) - 127))));
            }
        static void Main(string[] args) {
            
            // Open File into a FileStream
            string file = "C:\\Users\\Corey\\Videos\\Captures\\Vghd\\geo_veh_c_sec_wheel.xgm";
            var fs = new FileStream(file, FileMode.Open);
            var fsize = (int)fs.Length;
            var buffer = new byte[fsize];
            fs.Read(buffer, 0, fsize);
            fs.Close();
            
            int ptr = 0x1D8;
            
            int vertex_buffer_size = readLong(ref buffer, ref ptr);
            int index_buffer_size = readLong(ref buffer, ref ptr);
            
            // Calculate the Counts from Buffer Info
            int vertex_buffer_stride = 24;
            int index_buffer_stride = 2;
            int vertex_count = vertex_buffer_size / vertex_buffer_stride;
            int index_count = index_buffer_size / index_buffer_stride / 3;
            
            // Set Obj File
            string objfile = "o mesh\ng mesh\n\n";
            
            // Read The buffers
            int f1;
            int f2;
            int f3;
            ptr = 0x29C;
            for (int i = 0; i < vertex_count; i++) {
                objfile += "v " + (readFloat(ref buffer, ref ptr)).ToString("0.000000");
                objfile += " " + (readFloat(ref buffer, ref ptr)).ToString("0.000000");
                objfile += " " + (readFloat(ref buffer, ref ptr)).ToString("0.000000") + "\n";
                ptr += vertex_buffer_stride - 12;
                }
            objfile += "\n";
            
            for (int i = 0; i < index_count; i++) {
                f1 = readShort(ref buffer, ref ptr);
                f2 = readShort(ref buffer, ref ptr);
                f3 = readShort(ref buffer, ref ptr);
                objfile += "f " + (f1 + 1).ToString("0");
                objfile += " " + (f3 + 1).ToString("0");
                objfile += " " + (f2 + 1).ToString("0") + "\n";
                }
            
            // write the OBJ
            using (StreamWriter outputFile = new StreamWriter(Path.Combine(Path.GetDirectoryName(file), Path.GetFileNameWithoutExtension(file) + ".obj"), false)) {
                outputFile.WriteLine(objfile);
                }
            }
        }
    }

```

Visual Basics (Microsoft Excel VBA)

```
    
    Dim file As String: file = "C:\\Users\\Corey\\Videos\\Captures\\Vghd\\geo_veh_c_sec_wheel.xgm"
    
    Dim F As Long: F = FreeFile
    Open file For Binary As F
    
    Seek F, 1 + &H1D8
    
    ' Reading Buffer Info
    Dim vertex_buffer_size As Long: Get F, , vertex_buffer_size
    Dim index_buffer_size As Long: Get F, , index_buffer_size
    
    
    ' Calculate the Counts from Buffer Info
    Dim vertex_buffer_stride As Long: vertex_buffer_stride = 24
    Dim index_buffer_stride As Long: index_buffer_stride = 2
    Dim vertex_count As Long: vertex_count = CLng(CSng(vertex_buffer_size) / CSng(vertex_buffer_stride))
    Dim index_count As Long: index_count = CLng(CDbl(index_buffer_size) / CDbl(index_buffer_stride) / 3#)
    
    
    ' Read The buffers
    Seek F, 1 + &H29C
    
    
    Dim objFile As String: objFile = "o mesh" + vbNewLine + "g mesh" + vbNewLine + vbNewLine
    Dim pos_x As Single, pos_y As Single, pos_z As Single
    Dim face_a As Integer, face_b As Integer, face_c As Integer
    
    Dim i As Long
    For i = 1 To vertex_count
        Get F, , pos_x
        Get F, , pos_y
        Get F, , pos_z
        objFile = objFile + "v " + Format$(pos_x, "0.000000")
        objFile = objFile + " " + Format$(pos_y, "0.000000")
        objFile = objFile + " " + Format$(pos_z, "0.000000") + vbNewLine
        Seek F, Seek(F) + (vertex_buffer_stride - 12)
    Next i
    objFile = objFile + vbNewLine
    
    For i = 1 To index_count
        Get F, , face_a
        Get F, , face_b
        Get F, , face_c
        objFile = objFile + "f " + CStr(face_a + 1)
        objFile = objFile + " " + CStr(face_c + 1)
        objFile = objFile + " " + CStr(face_b + 1) + vbNewLine
    Next i
    
    Close F
    
    ' Write Obj
    Open (file + ".obj") For Output As #1
    Print #1, objFile
    Close #1

End Sub

```



Here is the file that these programs work with:


 geo_veh_c_sec_wheel.zip
Binary Model Sample (5.97 KiB) Downloaded 32 times
