## Post #1
- Username: ExeiL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 11, 2010 5:47 am
- Post datetime: 2010-10-10T21:53:59+00:00
- Post Title: Please help Extract .gtf textures

Please help Extract .gtf textures. It's textures file format from PS3 Games (for example: God of War)...
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-11T07:05:04+00:00
- Post Title: Please help Extract .gtf textures

Sample?!
## Post #3
- Username: ExeiL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 11, 2010 5:47 am
- Post datetime: 2010-10-11T10:42:51+00:00
- Post Title: Please help Extract .gtf textures

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-11T11:52:34+00:00
- Post Title: Please help Extract .gtf textures

It seems it some kind of DDS or Tim format. Maybe Tim3. I can see the main character and some text on it, but I can't edit.
Channels: ARGB.
## Post #5
- Username: ExeiL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 11, 2010 5:47 am
- Post datetime: 2010-10-11T12:59:52+00:00
- Post Title: Please help Extract .gtf textures

> Reply from evin
>
> It seems it some kind of DDS or Tim format. Maybe Tim3. I can see the main character and some text on it, but I can't edit.
Channels: ARGB.
yes, PS3 SDK have convert tool DDS2GTF, but I want convert from gtf to dds...or other format what I can edit

> Reply from About GTF in PS3 SDK ReadMe
>
>   The GTF file format does not have a fixed pixel format. It corresponds to
  texture data saved in the DDS format that has been rearranged in a layout
  that can be easily handled by RSX(TM).

  Texture data is packed in DDS. To use with RSX(TM), its memory layout 
  must be changed on the CELL side. 
  GTF stores texture data exactly in the layout by which it is to be used 
  within RSX(TM). Thus, such a file can be directly referenced as a texture
  by merely placing it on memory.
[dds2gtf.zip](https://xentaxbackup.github.io/file/3512_dds2gtf.zip)
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-11T13:32:46+00:00
- Post Title: Please help Extract .gtf textures

Got it. I didn't know the dimensions, but now I have the DDS image. Just the byte order difference. (Little-Endian - Big-Endian)
DDS format of this image: 8.8.8.8, no mipmap
[gow.jpg](https://xentaxbackup.github.io/file/3513_gow.jpg)
## Post #7
- Username: ExeiL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 11, 2010 5:47 am
- Post datetime: 2010-10-11T13:40:40+00:00
- Post Title: Please help Extract .gtf textures

> Reply from evin
>
> Got it. I didn't know the dimensions, but now I have the DDS image. Just the byte order difference. (Little-Endian - Big-Endian)
DDS format of this image: 8.8.8.8, no mipmap

How I can edit this files (.gtf)? Have you any converter for this?
I just want transtlate this game, I want get image, edit it and bring it back(((
## Post #8
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-11T13:45:25+00:00
- Post Title: Please help Extract .gtf textures

I need more samples, with smaller images. Because maybe this DDS compression is not the only one, which the game uses.
## Post #9
- Username: ExeiL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 11, 2010 5:47 am
- Post datetime: 2010-10-11T14:42:26+00:00
- Post Title: Please help Extract .gtf textures

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-11T17:51:04+00:00
- Post Title: Please help Extract .gtf textures

This simple program support only the unswizzled .gtf files. Sorry, but I can't handle the swizzled mode.
[gtf2dds.zip](https://xentaxbackup.github.io/file/3514_gtf2dds.zip)
## Post #11
- Username: ExeiL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 11, 2010 5:47 am
- Post datetime: 2010-10-11T18:57:42+00:00
- Post Title: Please help Extract .gtf textures

> Reply from evin
>
> This simple program support only the unswizzled .gtf files. Sorry, but I can't handle the swizzled mode.
Thank you very much!!!!!
## Post #12
- Username: dimmid
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 30, 2011 6:57 pm
- Post datetime: 2011-04-30T10:58:25+00:00
- Post Title: Please help Extract .gtf textures

> Reply from evin
>
> This simple program support only the unswizzled .gtf files. Sorry, but I can't handle the swizzled mode.
Hi, any chance you could release the source of that? also what is this unswizzled/swizzled mode about? and finally, any chance it is possible to convert this to a jpeg?
many thanks

PS: i know this is an old thread, but i figured it would be better if it stayed in one place.
## Post #13
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-05-01T07:41:02+00:00
- Post Title: Please help Extract .gtf textures

C# 2.0

```
using System.Collections.Generic;
using System.Text;
using System.IO;
using System.Diagnostics;

namespace gtf2dds
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                Process p = Process.GetCurrentProcess();
                string assemblyName = p.ProcessName + ".exe";

                Console.Clear();
                Console.WriteLine("GTF to DDS converter\nTom Evin 2010.10.12.");
                if (args.Length < 1)
                {
                    Console.WriteLine("Only 8.8.8.8 compression supported.\nJust drag && drop a file or in command line: " + assemblyName + " filename.dds/gtf");
                    Console.Read();
                }
                else
                {
                    FileStream ins = File.OpenRead(args[0]);
                    byte[] b = new byte[4];
                    byte[] a = new byte[2];
                    int width = 0;
                    int height = 0;
                    ins.Read(b, 0, 4);
                    if (b[0] == 0x02 && b[1] == 0x01 && b[3] == 0xff)
                    {
                        FileStream outs = File.OpenWrite(Path.GetFileNameWithoutExtension(args[0]) + ".dds");
                        byte[] DDSHeader1 = new byte[12] { 0x44, 0x44, 0x53, 0x20, 0x7c, 0x00, 0x00, 0x00, 0x07, 0x10, 0x08, 0x00 };
                        byte[] DDSHeader2 = new byte[108]{0x00, 0x00, 0x04, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
                        0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
                        0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
                        0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x20, 0x00, 0x00, 0x00,
                        0x41, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x20, 0x00, 0x00, 0x00, 0x00, 0x00, 0xff, 0x00,
                        0x00, 0xff, 0x00, 0x00, 0xff, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0xff, 0x00, 0x10, 0x00, 0x00,
                        0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};

                        ins.Seek(0, SeekOrigin.End);
                        int vege = (int)ins.Position;
                        ins.Seek(32, SeekOrigin.Begin);
                        ins.Read(a, 0, 2);
                        Array.Reverse(a);
                        width = BitConverter.ToInt16(a, 0);
                        ins.Read(a, 0, 2);
                        Array.Reverse(a);
                        height = BitConverter.ToInt16(a, 0);
                        ins.Seek(128, SeekOrigin.Begin);
                        Console.WriteLine("Size: " + vege);
                        Console.WriteLine("\nDimensions");
                        Console.WriteLine("Width: " + width);
                        Console.WriteLine("Height: " + height);

                        outs.Write(DDSHeader1, 0, 12);
                        b = BitConverter.GetBytes(height);
                        outs.Write(b, 0, 4);
                        b = BitConverter.GetBytes(width);
                        outs.Write(b, 0, 4);
                        outs.Write(DDSHeader2, 0, 108);

                        for (int i = 0; i < (vege - 128)/4; i++)
                        {
                            ins.Read(b, 0, 4);
                            Array.Reverse(b);
                            outs.Write(b, 0, 4);
                        }
                        outs.Flush();
                        outs.Close();
                    }
                    else { Console.WriteLine("This is not a .gtf file or corrupt or just not supported by this program!"); Console.Read(); }
                    ins.Close();
                }
                //Console.Read();
            }
            catch (IndexOutOfRangeException exc)
            {
                Console.WriteLine(exc.Message);
                Console.Read();
            }
            catch (FileLoadException exc)
            {
                Console.WriteLine(exc.Message);
                Console.Read();
            }
        }
    }
}

```


The swizzle thing: Google -> texture swizzle
Basically this some kind of compression mode.

"any chance it is possible to convert this to a jpeg?"
Everything is possible. Just I don't have time to working on this. What is more, I don't have the game or ps3.
## Post #14
- Username: dimmid
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 30, 2011 6:57 pm
- Post datetime: 2011-05-04T01:51:45+00:00
- Post Title: Please help Extract .gtf textures

I understand completely, either way, thank you very much for the source. I will try and convert it to jpeg myself.
## Post #15
- Username: JU57FL1P
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 29, 2011 6:16 pm
- Post datetime: 2011-05-29T13:38:06+00:00
- Post Title: Please help Extract .gtf textures

I'll revive this thread... Shift 2 unleashed is one of those games taht use .gtf textures, but these tools do not work on this game unfortunatly...
i attached some files, any help would be nice 

can't attach 2 attacments, here's the link for another one(it has real liveries):  [http://www.upload.ee/files/1376419/s2u_ ... ..rar.html](http://www.upload.ee/files/1376419/s2u_more_files....rar.html)

note: I'd need .gtf to dds and dds to gtf
[shift 2 unleashed .gtf file examples.rar](https://xentaxbackup.github.io/file/4275_shift 2 unleashed .gtf file examples.rar)
## Post #16
- Username: JU57FL1P
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 29, 2011 6:16 pm
- Post datetime: 2011-06-04T16:48:05+00:00
- Post Title: Re: Please help Extract .gtf textures

no worries got it...
I'll upload new files down here that work!!
at least for PS3 game textures...
[GTF to dds and back files!.rar](https://xentaxbackup.github.io/file/4294_GTF to dds and back files!.rar)
## Post #17
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-08-16T19:17:32+00:00
- Post Title: Re: Please help Extract .gtf textures

I try gtf to dds in Tacchi Shiyo Love Application JPN PS3, the dds are in a damn form, help plz

converted sample of the game [gtf2dds]
[http://www.mediafire.com/?zp11luazzzsd45t](http://www.mediafire.com/?zp11luazzzsd45t)

original gtf of the game
[http://www.mediafire.com/?5b5t43zun3eve9v](http://www.mediafire.com/?5b5t43zun3eve9v)

edit: wrong files attached
[aoi_cg_01_1.jpg](https://xentaxbackup.github.io/file/5670_aoi_cg_01_1.jpg)
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-17T13:24:01+00:00
- Post Title: Re: Please help Extract .gtf textures

doesn't my ripper extract all textures and event images? the reason why that file you posted isn't working is because according to my code (which I haven't looked at in a long time), the data should be DXT1, not ARGB. that's why you see 1/8th of the image (DXT1 compression), and the rest is just repeating whatever was on the last line to fill in the blanks.
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-25T16:44:18+00:00
- Post Title: Re: Please help Extract .gtf textures

> Reply from JU57FL1P
>
> *attached samples*

> Reply from tomatopasta
>
> http://www.mediafire.com/?5b5t43zun3eve9v

made a Noesis python script to open your gtf samples  


 tex_NFS_Shift2Unleashed_PS3_gtf.zip
(702 Bytes) Downloaded 162 times


supports dxt1 and dxt5
