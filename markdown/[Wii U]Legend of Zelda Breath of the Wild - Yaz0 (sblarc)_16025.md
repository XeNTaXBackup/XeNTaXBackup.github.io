## Post #1
- Username: rumpo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 19, 2015 2:04 am
- Post datetime: 2017-03-18T16:00:43+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

I'm having trouble repacking a Yaz0 file with existing tools (Uwizard seems to be the most up to date, which uses yaz0enc). It's supposed to go Yaz0/SZS > SARC, and while SARC repacking works, Yaz0 unpacking and/or repacking go wrong and make the game crash even if content is left untouched. Can anyone take a look? Here's the header for reference:



A link to the file I'm trying to repack, Common.sblarc, is on the attachment. I can provide the whole file, Bootup.pack (SARC), if needed. Path goes: content/Pack/Bootup.pack/Layout/Common.sblarc
And here are specs of the format from 2005 if they're of any help: [http://www.amnoid.de/gc/yaz0.txt](http://www.amnoid.de/gc/yaz0.txt)

Thanks.
[Common.sblarc.zip](https://xentaxbackup.github.io/file/12653_Common.sblarc.zip)
## Post #2
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2017-03-21T16:26:15+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

Here ya go

```
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

using Syroot.NintenTools.Yaz0;

namespace Yaz0
{
    class Program
    {
        public static byte[] ArrayReverse(byte[] array)
        {
            Array.Reverse(array);
            return array;
        }

        public static Int32 SwapEndianness(Int32 value)
        {
            return BitConverter.ToInt32(ArrayReverse(BitConverter.GetBytes(value)), 0);
        }

        static void Main(string[] args)
        {
            if (args.Count() == 3)
            {
                switch(args[0])
                {
                    case "decode":
                        if (File.Exists(args[1]))
                        {
                            FileInfo fi = new FileInfo(args[1]);
                            Yaz0Compression.Decompress(fi.FullName, args[2]);
                        }
                        else
                        {
                            Console.WriteLine("The specified input file does not exist");
                        }
                        break;
                    case "encode":
                        if (File.Exists(args[1]))
                        {
                            FileInfo fi = new FileInfo(args[1]);
                            byte[] decodedBuffer = File.ReadAllBytes(fi.FullName);
                            Int32 bulkChunksCount = decodedBuffer.Length / 0x08;
                            Int32 extraChunkSize = decodedBuffer.Length % 0x08;
                            byte[] chunkBuffer = new byte[0x08];
                            using (FileStream fs = new FileStream(args[2], FileMode.Create, FileAccess.Write))
                            {
                                fs.Write(Encoding.UTF8.GetBytes("Yaz0"), 0, 4);
                                fs.Write(BitConverter.GetBytes(SwapEndianness((Int32)fi.Length)), 0, 4);
                                fs.Write(BitConverter.GetBytes(SwapEndianness(0x00000000)), 0, 4); //Can be 0x00002000 sometimes, check the original Yaz0 file at offset 0x08
                                fs.Write(BitConverter.GetBytes(SwapEndianness(0x00000000)), 0, 4);

                                for (int i = 0; i < bulkChunksCount; i++)
                                {
                                    fs.Write(BitConverter.GetBytes(0xFF), 0, 1);
                                    Array.Copy(decodedBuffer, (i * 8), chunkBuffer, 0, 8);
                                    fs.Write(chunkBuffer, 0, 8);
                                }

                                if (extraChunkSize != 0)
                                {
                                    Array.Resize(ref chunkBuffer, extraChunkSize);
                                    Array.Copy(decodedBuffer, (0x08 * bulkChunksCount), chunkBuffer, 0, chunkBuffer.Length);

                                    Byte codeByte = 0x00;
                                    switch (extraChunkSize)
                                    {
                                        case 1:
                                            codeByte = 0x80;
                                            break;
                                        case 2:
                                            codeByte = 0xC0;
                                            break;
                                        case 3:
                                            codeByte = 0xE0;
                                            break;
                                        case 4:
                                            codeByte = 0xF0;
                                            break;
                                        case 5:
                                            codeByte = 0xF8;
                                            break;
                                        case 6:
                                            codeByte = 0xFC;
                                            break;
                                        case 7:
                                            codeByte = 0xFE;
                                            break;
                                        default:
                                            break;
                                    }

                                    fs.Write(BitConverter.GetBytes(codeByte), 0, 1);
                                    fs.Write(chunkBuffer, 0, chunkBuffer.Length);
                                }
                            }
                        }
                        else
                        {
                            Console.WriteLine("The specified input file does not exist");
                        }
                        break;
                    default:
                        break;
                }
                Console.WriteLine("Finished!");
                Console.WriteLine("Press any key to exit ...");
                Console.ReadKey();
            }
            else
            {
                //Show help
                Console.WriteLine("Yaz0.exe decode <input_file> <output_file>");
                Console.WriteLine("Yaz0.exe encode <input_file> <output_file>");
                Console.WriteLine("Press any key to exit ...");
                Console.ReadKey();
            }
        }
    }
}


```
## Post #3
- Username: rumpo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 19, 2015 2:04 am
- Post datetime: 2017-03-21T19:15:14+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

> Reply from EcheloCross
>
> Here ya go
Forgive my ignorance but that's C#, right? I see it mentions Syroot.NintenTools.Yaz0, do I need to get it before compiling?
## Post #4
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2017-03-22T04:18:01+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

Yes, its c#, and yes you need to get that Syroot.NintenTools.Yaz0 part for decoding only.  
[https://github.com/Syroot/NintenTools.Yaz0](https://github.com/Syroot/NintenTools.Yaz0)

You can comment out the decoding part and the need for Syroot.Nintentools.Yaz0 if you are already using a different tool to decode them.

The encode method I wrote using the info from the doc you provided.  It uses fake compression (compression level 0), so the file gets larger when encoding.  Even though the files are larger, they are still valid Yaz0.
## Post #5
- Username: rumpo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 19, 2015 2:04 am
- Post datetime: 2017-03-22T21:49:30+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

> Reply from EcheloCross
>
> Yes, its c#, and yes you need to get that Syroot.NintenTools.Yaz0 part for decoding only.  
https://github.com/Syroot/NintenTools.Yaz0

You can comment out the decoding part and the need for Syroot.Nintentools.Yaz0 if you are already using a different tool to decode them.

The encode method I wrote using the info from the doc you provided.  It uses fake compression (compression level 0), so the file gets larger when encoding.  Even though the files are larger, they are still valid Yaz0.
Sorry, I must be doing something wrong. Bear with me as I've never done this before. I downloaded VS2015, made it a Visual C# Console Application, got NuGet, ran the command to get Syroot.Nintentools.Yaz0 and built it, but decode just returns "Finished!" without doing anything while encode refuses to work. Could you please compile it?
## Post #6
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2017-03-23T08:16:26+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

Here ya go

Give it a try like this, and you'll see the files match if you compare the "decoded" and "encoded_decoded" files md5 sums

```

Yaz0.exe encode Common_decoded.sblarc Common_encoded.sblarc

Yaz0.exe decode Common_encoded.sblarc Common_encoded_decoded.sblarc

```

[Yaz0.zip](https://xentaxbackup.github.io/file/12680_Yaz0.zip)
## Post #7
- Username: rumpo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 19, 2015 2:04 am
- Post datetime: 2017-03-23T20:53:36+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

> Reply from EcheloCross
>
> Here ya go

Give it a try like this, and you'll see the files match if you compare the "decoded" and "encoded_decoded" files md5 sums
Code: Select allYaz0.exe decode Common.sblarc Common_decoded.sblarc

Yaz0.exe encode Common_decoded.sblarc Common_encoded.sblarc

Yaz0.exe decode Common_encoded.sblarc Common_encoded_decoded.sblarc
Thanks. It works, but the game seems to require maximum compression, it still crashes. Might be something new for the format. None of the tools I've tried even got close to the original's 3.770KB.
## Post #8
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2017-06-21T16:35:09+00:00
- Post Title: [Wii U]Legend of Zelda: Breath of the Wild - Yaz0 (sblarc)

Hi friend, anyone got anything? Ask, how can you see these files in wiiu? When down the game I only see 00000.app files or other things .app.
