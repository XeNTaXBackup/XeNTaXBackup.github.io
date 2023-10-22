## Post #1
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-13T14:16:25+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

Hello there! i try search models from this game in unpacked data with idtool, what i found in Model Researcher:

I newbie on hex founding meshes and etc, but have some success but i don't understand where and how to find UV, if someone have a time help me out please, sample files will be below.

P.S. i think skeletal data in same file as mesh (i've research 00d.dat), i don't know now what file is .dbr maybe texture. 
UPDATE: I don't understand how to find UV in hex table, right, or where i can start, i know for UV need use UV tab, if you possible found UV let me know how and where it start in hex or just do a sample screen from model researcher.


[https://dropmefiles.com/1oa1x](https://dropmefiles.com/1oa1x)
## Post #2
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2021-02-13T23:17:36+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

After finding the vertices, you can start looking for the normals, because they can be visualized. Texture coordinates can also be rendered in the Texture tab.



00d.dat_Sun_Feb_14_06-10-28_2021.png (83.31 KiB) Viewed 258 times
## Post #3
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-14T22:45:28+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

Thanks Lazov i will use that information!
## Post #4
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-15T01:29:57+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

Here my result, ive rotate uv by blender to match with textures, try to find how to find bones, weights and anim if it possible.
## Post #5
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-16T20:53:06+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

I'll remane topic for better name becouse it is not about UV only now.
And with new question, for who made exporters models, How i can better know when model info start?

I want do export script for noesis or console app (c#) for find mesh (vertex\normal\UV) then export it by OBJ or SMD, becouse look game files one by one is hard and kill lots of time.

And what ive try search match by hex like 

```
08 00 00 00 08 00 00 00 2D 2D 2D 2D 2D 2D 2D 2D
```

and next bytes are verteces but not all it is 2D 2D 2D 2D 2D 2D 2D 2D sometime its just start, and i want to know where i need start to know where vertex a begun, or get position of start or count of vertex\normal\UV and etc. or maybe have tools who hust find vertex of file and try to generate model or some code, becouse if i can't know start of model i think i've can't do batch export of model.

I've appreciate help with c# code, noesis or blender scripts, or just tip how to parse model then next or check by nothing meshes found.

Here a bunch of samples [https://dropmefiles.com/soqWc](https://dropmefiles.com/soqWc)

P.S. If some have tutorial for that link me, please maybe it help me.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-18T12:06:17+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

Counts should not be a big deal if you're a coder:
.



counts.png (12.87 KiB) Viewed 212 times



Search for 000001000200 to find start of face indices block(s).
End of block 2D2D [2D...?]
Counts to follow, see picture.

To get start of vertices (0x6f80 for "hand" here) do a backward search for 080000002D2D2D2D2D2D2D2D
(so backwards 2D2D2D2D2D2D2D2D00000008) starting from FI's start address (0x8f10 for "hand" in this sample).

That's how I'd do it.

Don't know whether this applies for all sub meshes/all samples - just found this on a quick glance!

And please: it spells "because", not "becouse".
## Post #7
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-18T12:49:14+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

Very thanks shakotay2, excuse me for mistake in english, i try search how to convert hex faces into tri-stripes, when i read just short (2 byte int16) it looks like quads:

```
f  3 3 3 4
f  5 6 7 8
f  9 10 11 12
f  13 14 15 16
f  16 10 10 8
f  17 17 18 18
```


but i need tri strips like that, how it looks in model researcher:

```
f  3 4 5
f  6 5 4
f  5 6 7
f  8 7 6
f  7 8 9
f  10 9 8
f  9 10 11
f  12 11 10
f  11 12 13
f  14 13 12
f  13 14 15
f  16 15 14
f  10 8 17
f  20 19 18
```


for example, this is may noob question but i didn't understand and can't see simple tutorial how to convert quad to tri-stripts, but i see many peoples do that in exporters, if some one can teach me with sample or code i will be appreciate it.

P.S. This is what i want in the end:

```
f  4/4/4 5/5/5 6/6/6
f  7/7/7 6/6/6 5/5/5
f  6/6/6 7/7/7 8/8/8
f  9/9/9 8/8/8 7/7/7
f  8/8/8 9/9/9 10/10/10
f  11/11/11 10/10/10 9/9/9
f  10/10/10 11/11/11 12/12/12
f  13/13/13 12/12/12 11/11/11
f  12/12/12 13/13/13 14/14/14
f  15/15/15 14/14/14 13/13/13
f  14/14/14 15/15/15 16/16/16
f  17/17/17 16/16/16 15/15/15
f  11/11/11 9/9/9 18/18/18
```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-18T14:22:34+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

For the hand (no quads afaics) the tri strips look like so (using hex2obj):
f 1 2 3
f 4 6 5
f 5 6 7
f 6 8 7
f 7 8 2
f 8 9 2
f 2 9 3
f 9 10 3
...

and the algo used (usually?) is to be found here:

> Reply from shakotay2 ↑Sat Feb 27, 2016 7:12 am at Sat Feb 27, 2016 7:12 am
>
> 

But there's different ways/algos so may not apply to every mesh.

edit: the link I gave above was for auto creating triangle strips, so not correct here!
see remark here: 
> Reply from shakotay2 ↑Fri Feb 19, 2021 5:08 pm at Fri Feb 19, 2021 5:08 pm
>
>
## Post #9
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-18T17:36:46+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

@shakotay2 i try find vertex and faces count by 2D 2D 2D 2D pattern and 6 of 8 will be successful, but sometime it without  2D 2D 2D 2D at the end, just store after faces end like on image, this is eyeball, one of it, second, first eye ball will have 2D 2D 2D 2D at the end.
[without pattern.png](https://xentaxbackup.github.io/file/19554_without pattern.png)
## Post #10
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-18T19:12:41+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

I've try search pair (vert. face count) and found only two possitions, after face ind. and  before vertex data of model i think.

```
1             6300       CA 00 00 00 55 02 00 00 
2             8EA0       CA 00 00 00 62 02 00 00
3             BA60       21 00 00 00 6E 00 00 00
4             C7D0       21 00 00 00 68 00 00 00
5             D530       46 03 00 00 F9 08 00 00
6             17190      23 02 00 00 A3 06 00 00
7             1D5D0      65 01 00 00 EB 02 00 00
8             214F0      28 00 00 00 40 00 00 00

```

try to search more maybe  i found postions or better pattern to stop using 2D 2D 2D 2D.
## Post #11
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-18T23:42:07+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

@shakotay2 I've looking at your [code](https://forum.xentax.com/viewtopic.php?f=16&t=12804&start=15#p116369) and test it on c#, i im right it generate faces from vertex count?
Ive get this from build_tristrips:

```
f  2 4 3
f  3 4 5
f  4 6 5
f  5 6 7
f  6 8 7
f  7 8 9
f  8 10 9
f  9 10 11

```

It looks like okay firts time, but in model research faces tab sometime faces looks like that:

```
f  191 204 192
f  199 192 204
f  192 199 193
f  15 16 26
f  250 26 16
f  26 250 32
f  105 32 250
f  32 105 41
f  95 41 105

```

And i don't see simiral from my output, its gonna be like:

```
f  249 250 251
f  250 252 251
f  251 252 253
f  252 254 253
f  253 254 255
f  254 256 255
f  255 256 257
f  256 258 257
...
f  475 476 477
f  476 478 477
f  477 478 479
f  478 480 479
...

```

and etc.

Picture below how it look in blender.
[compate.jpg](https://xentaxbackup.github.io/file/19556_compate.jpg)
## Post #12
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-19T01:01:26+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

@shakotay2 Ive made it work! A big thanks for the code!   
Ive just give f1 f2 f3 my faces and input facecount from faces list and hooray miracle it look fine!

P.S. i may post c# code if you want a look a it, i just little edit your C code sample.
[success.jpg](https://xentaxbackup.github.io/file/19557_success.jpg)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-19T09:08:48+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from JakeMiles ↑Fri Feb 19, 2021 7:42 am at Fri Feb 19, 2021 7:42 am
>
> 
@shakotay2 I've looking at your code and test it on c#, i im right it generate faces from vertex count?Upps, well, sorry! My fault, what I linked was the code for auto generated triangle strips. But f1, f2 should not be preset for existing face indices.  So f1= GetFaceIndex(...); f2= GetFaceIndex(...); (That's what you've changed probably.)

> P.S. i may post c# code if you want a look a it, i just little edit your C code sample.Feel free to post it here - might help others, too.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-02-19T12:25:18+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from JakeMiles ↑Fri Feb 19, 2021 1:36 am at Fri Feb 19, 2021 1:36 am
>
> 
but sometime it without  2D 2D 2D 2D at the end, just store after faces end like on image
The byte 0x2D (the char '-') is merely a character for padding when the data block is not aligned to 0x10 bytes. The count fields of the vertices/indices are usually stored before corresponding data blocks, if there's no further info (size fields, offsets etc.) stored ahead that can help determining how to read the data correctly. There seems to always be a 0x130-byte header before the vertices block, with the fixed signature 70 01 95 00. So if you must do it by searching for a signature, this should be a good choice.



00d_hdrs.png (13.74 KiB) Viewed 156 times
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-02-19T12:44:47+00:00
- Post Title: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

[](https://ibb.co/6NCgXwW)

Only thing i've been able to find are heads, I'm guessing there is a different block type that holds weighted geometry...

I usually would write a program to import directly into blender or 3dsmax, but I gave C# a go and wrote this exporter.

```
	C# Programs, dumps geometry from data file to obj from Fahrenheit (Indigo Prophecy) 2005
	Author:		mariokart64n
	Date:		February 19, 2021

	more info:
				https://forum.xentax.com/viewtopic.php?f=16&t=23441

	*/

using System;
using System.IO;
using System.Text;

namespace PackExtract {
	class Program {
		static Encoding enc8 = Encoding.UTF8;	// Required for ReadString Function
		static int readShort(ref Byte[] buffer, ref int ptr) {
			// Converts Unsigned 16bit Integer from the buffer
			int word = 0;
			word += buffer[ptr + 1] * 0x00000100;
			word += buffer[ptr + 0] * 0x00000001;
			ptr += 2;
			return word;
			}
		static int readLong(ref Byte[] buffer, ref int ptr) {
			// Converts Unsigned 32bit Integer from the buffer
			int dword = 0;
			dword += buffer[ptr + 3] * 0x01000000;
			dword += buffer[ptr + 2] * 0x00010000;
			dword += buffer[ptr + 1] * 0x00000100;
			dword += buffer[ptr + 0] * 0x00000001;
			ptr += 4;
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
		static string ReadString(ref Byte[] buffer, ref int pos, int length) {
			// Reads a string from the buffer
			string output = String.Empty;
			Decoder decoder8 = enc8.GetDecoder();
			int nChars = decoder8.GetCharCount(buffer, pos, length);
			char[] chars = new char[nChars];
			nChars = decoder8.GetChars(buffer, pos, length, chars, 0);
			output += new String(chars, 0, nChars);
			pos += length;
			return output.Replace("\0", string.Empty);
			}
		static void Main(string[] args) {
			Console.WriteLine("===========================================================\n");
			Console.WriteLine("OBJ Dumper for Fahrenheit (Indigo Prophecy) 2005\n");
			Console.WriteLine("Written By:\tmariokart64n");
			Console.WriteLine("Released:\tFebruary 19, 2021\n");
			Console.WriteLine("    https://forum.xentax.com/viewtopic.php?f=16&t=23441\n");
			Console.WriteLine("===========================================================\n\n");
			
			// Check that an argument was supplied
			if (args.Length > 0) {
				
				// Set Filepath
				string file = args[0];
				Console.WriteLine("File:\t{0}\n", file);
				
				// Open File into a FileStream
				
				var fs = new FileStream(file, FileMode.Open);
				// Read File into byte[] Array
				var fsize = (int)fs.Length;
				var buffer = new byte[fsize];
				
				fs.Read(buffer, 0, fsize);
				fs.Close();
				
				// Read file id
				int ptr = 0;
				int i = 0;
				int fileID1 = 0;
				int fileID2 = 0;
				if (fsize > 8) {
					fileID1 = readLong(ref buffer, ref ptr);
					fileID2 = readLong(ref buffer, ref ptr);
					}
				if (fileID1 == 0x41544144 && fileID2 == 0x4B4E4142) {
					int unk01 = readLong(ref buffer, ref ptr);	// always 1?
					int filesize = readLong(ref buffer, ref ptr);
					int count = readShort(ref buffer, ref ptr);
					int unk03 = readLong(ref buffer, ref ptr);	// count?
					int unk04 = readLong(ref buffer, ref ptr);	// 0
					int unk05 = readLong(ref buffer, ref ptr);	// addr?
					int unk06 = readLong(ref buffer, ref ptr);	// count?
					int unk10 = 0;
					int unk11 = 0;
					int unk12 = 0;
					int addr = 0;
					int hash1 = 0;
					int hash2 = 0;
					int meshCount = 0;
					int vertCount = 0;
					int faceCount = 0;
					string objfile = "";
					bool faceCW = true;
					int f1 = 0;
					int f2 = 0;
					int f3 = 0;
					int faceOffset = 0;
					double x = 0.0F;
					double y = 0.0F;
					double z = 0.0F;
					double w = 0.0F;
					
					if (count > 0) {
						for (int b = 0; b < count; b++) {
							ptr = 0x20 + (b * 0x10);
							unk10 = readLong(ref buffer, ref ptr); // ?
							unk11 = readLong(ref buffer, ref ptr); // ?
							unk12 = readLong(ref buffer, ref ptr); // always 0
							addr = readLong(ref buffer, ref ptr);
							ptr = addr;
							hash1 = readLong(ref buffer, ref ptr);
							hash2 = readLong(ref buffer, ref ptr);
							if (hash1 == 0x00931B68 && hash2 == 0x00ADA1F8) {
								
								
								Console.WriteLine("MESHDATA{0}: [{1}{2}]\t@ {3}\n", b, hash1, hash2, addr);
								
								ptr += 0x14;
								meshCount = readLong(ref buffer, ref ptr);
								Console.WriteLine("MESHCOUNT\t{0}\n-------------------------------------\n", meshCount);
								
								ptr += 0x03E0;
								faceOffset = 1;
								for (int m = 0; m < meshCount; m++) {
									Console.WriteLine("  SUBMESH\t{0}\n", m);
									
									ptr += 0x60;
									vertCount = readLong(ref buffer, ref ptr);
									faceCount = readLong(ref buffer, ref ptr);
									Console.WriteLine("    VERTCOUNT\t{0}\n", vertCount);
									Console.WriteLine("    FACECOUNT\t{0}\n", faceCount);
									
									ptr += 0x0108;
									
									Console.WriteLine("    POSITIONS\t@ {0}\n", ptr);
									
									for (i = 0; i < vertCount; i++) {
										objfile += "v " + (readFloat(ref buffer, ref ptr)).ToString("0.000000");
										objfile += " " + (readFloat(ref buffer, ref ptr)).ToString("0.000000");
										objfile += " " + (readFloat(ref buffer, ref ptr)).ToString("0.000000") + "\n";
										ptr += 4;
										}
									objfile += "\n";
									
									Console.WriteLine("    NORMALS\t@ {0}\n", ptr);
									for (i = 0; i < vertCount; i++) {
										x = readFloat(ref buffer, ref ptr);
										y = readFloat(ref buffer, ref ptr);
										z = readFloat(ref buffer, ref ptr);
										w = readFloat(ref buffer, ref ptr);
										//x *= w; y *= w; z *= w;
										w = Math.Sqrt(Math.Pow(x, 2) + Math.Pow(y, 2) + Math.Pow(z, 2));
										x /= w; y /= w; z /= w;
										objfile += "vn " + (x).ToString("0.000000");
										objfile += " " + (y).ToString("0.000000");
										objfile += " " + (z).ToString("0.000000") + "\n";
										}
									objfile += "\n";
									
									Console.WriteLine("    TEXCOORD\t@ {0}\n", ptr);
									
									for (i = 0; i < vertCount; i++) {
										objfile += "vt " + (readFloat(ref buffer, ref ptr)).ToString("0.000000");
										objfile += " " + (-readFloat(ref buffer, ref ptr)).ToString("0.000000") + " 0.000000\n";
										}
									ptr += (16-(ptr % 16)) % 16;
									objfile += "\n";
									
									Console.WriteLine("    PRIMITIVES\t@ {0}\n", ptr);
									objfile += "o mesh_" + m.ToString("0") + "\n";
									objfile += "g mesh_" + m.ToString("0") + "\n";
									i = 0;
									while (i < faceCount) {
										faceCW = true;
										f1 = readShort(ref buffer, ref ptr);
										f2 = readShort(ref buffer, ref ptr);
										i+=2;
										while (i < faceCount) {
											f3 = readShort(ref buffer, ref ptr);
											if (f3 == 0xFFFF || f3 == -1) {break;}
											if (f1 != f2 && f2 != f3 && f3 != f1) {
												if (faceCW) {
													objfile += "f " + (f1 + faceOffset).ToString("0");
													objfile += "/" + (f1 + faceOffset).ToString("0");
													objfile += "/" + (f1 + faceOffset).ToString("0");
													objfile += " " + (f2 + faceOffset).ToString("0");
													objfile += "/" + (f2 + faceOffset).ToString("0");
													objfile += "/" + (f2 + faceOffset).ToString("0");
													objfile += " " + (f3 + faceOffset).ToString("0");
													objfile += "/" + (f3 + faceOffset).ToString("0");
													objfile += "/" + (f3 + faceOffset).ToString("0") + "\n";
													}
												else {
													objfile += "f " + (f1 + faceOffset).ToString("0");
													objfile += "/" + (f1 + faceOffset).ToString("0");
													objfile += "/" + (f1 + faceOffset).ToString("0");
													objfile += " " + (f3 + faceOffset).ToString("0");
													objfile += "/" + (f3 + faceOffset).ToString("0");
													objfile += "/" + (f3 + faceOffset).ToString("0");
													objfile += " " + (f2 + faceOffset).ToString("0");
													objfile += "/" + (f2 + faceOffset).ToString("0");
													objfile += "/" + (f2 + faceOffset).ToString("0") + "\n";
													}
												}
											faceCW = !faceCW;
											f1 = f2; f2 = f3;
											i += 1;
											}
										
										}
									ptr += (16-(ptr % 16)) % 16;
									objfile += "\n";
									faceOffset += vertCount;
									Console.WriteLine("  END BLOCK\t@ {0}\n-------------------------------------\n", ptr);
									}
								}
							else {
								//Console.WriteLine("Unknown Block [{0}{1}]\t@ {2}\n", hash1, hash2, addr);
								}
							}
						}
					
					if (objfile != "") {
						using (StreamWriter outputFile = new StreamWriter(Path.Combine(Path.GetDirectoryName(file), Path.GetFileNameWithoutExtension(file) + ".obj"), false)) {
							outputFile.WriteLine(objfile);
							}
						
						
						}
					
					}
				else {
					// Warning User that File Is Invalid
					Console.WriteLine("Invalid File");
					}
				}
			else {Console.WriteLine("Usage:\n\tdat_obj_dumper.exe <dat_file>");}
			
			Console.WriteLine("\n\n\tPress Any Key to Continue....");
			Console.WriteLine("===========================================================");
			Console.Read();
			}
		}
	}

```
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-19T15:22:18+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

If you want it "perfect" (complete format analysis) you'd probably use the approach of mariokart64n.

But using the method of Bigchillghost I got a bunch of 10 H2O files very quickly which resulted in:
.



00d_9of10_meshes.png (87.9 KiB) Viewed 175 times



> Reply from Bigchillghost ↑Fri Feb 19, 2021 8:25 pm at Fri Feb 19, 2021 8:25 pm
>
> There seems to always be a 0x130-byte header before the vertices block, with the fixed signature 70 01 95 00. So if you must do it by searching for a signature, this should be a good choice.Yeah, thanks! Best choice - for me at least!  

Took me 15 minutes of expanding my (obsolete) Make_H2O code (and 10 minutes of debugging  ):
(uvs and normals not handled; (.._8.H2O discarded, see code) )

```
{                                                                         //
   char * pFBuf, szNo[4], * pTmp ;
   BYTE cnt, cntMax ;
   int nValue[16] ;
   DWORD FIcnt, dwFaceIndCnt[100], vCnt, dwVertsCnt[100] ;
   DWORD addrFI, addrUV, addrV, j=0, offs2 ;  //
   DWORD addr[100] ;        // 
   char lines[6][20]= {"","Vb1","16 99","","021000",""} ;
   bool bStop= false ;

   pFBuf = (char *) lpFBuf ; pTmp= pFBuf ;
   if ((*pFBuf&255)!=0x44) {                             // 
        chMB("This doesn't seem to be a 'Fahrenheit' file!") ; return ;
   }
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating H2O files:") ;
   cnt= 0 ;
   do {    //
        nValue[0]= 0x70; nValue[1]= 1; nValue[2]= 0x95; nValue[3]= 0;    // assumed signature of magic table
        offs2 = FindBytes(lpFBuf, j, dwFileSize-j, nValue, 4) ;
        if (offs2!=0) {
            pFBuf += offs2 ; j += offs2 ;
            addr[cnt]= j +32 ;  // vertex count und face index count
            fprintf(stream, "70019500...: %x\n", j) ;
            pFBuf += 4 ; j += 4 ;                               // skip signature bytes
        }
        else bStop= true ;
        cnt++ ;                                                 // next submesh
   } while (!bStop&&(j<dwFileSize)) ;
   //fprintf(stream, "\n assumed magic tables: %d\n", cnt-1) ;    //
   cntMax= cnt-1 ; addrUV= 0 ; cnt= 0 ;
        do {
            pFBuf= pTmp ; pFBuf += addr[cnt] ; j = addr[cnt] ;  // vor auf DW vCnt
            GetDW(pFBuf, j, vCnt, false) ;  dwVertsCnt[cnt]= vCnt ;
            addrV= addr[cnt] + 17*16;           // 0x130 bytes header, 32+17*16
            GetDW(pFBuf, j, FIcnt, false) ; dwFaceIndCnt[cnt]= FIcnt ;
            addrFI = addrV + 40* vCnt ;		// always 40? 48 required for .._8.H2O
            pFBuf= pTmp ; pFBuf += addrFI ;
            while (*pFBuf==0x2D) { pFBuf++ ; addrFI++;}     // risky!! skipping the padding
            fprintf(stream, "FI: %d, v: %d\n", FIcnt, dwVertsCnt[cnt]) ;
            //fprintf(stream, "g SM_%d\n#  at 0x%x (FIs at 0x%x)\n", cnt, addrV, addrFI) ;
            _itoa(cnt, szNo, 10) ;
            if (create_H2O(szPathname, cnt, lines, addrFI, dwFaceIndCnt[cnt], addrUV, 255, addrV, dwVertsCnt[cnt], 2) )
                SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) szNo) ;
            else SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " failed") ;
            cnt++ ;
        } while (cnt<cntMax) ;
        //fprintf(stream, "\n vertex blocks: %d, vMax: %d\n", cnt, vMax) ;
   if (strlen(szErrMess)>17) MessageBox(NULL, szErrMess, "error", MB_ICONINFORMATION);
}
```
## Post #17
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-02-19T17:23:41+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

@shakotay2 Here a my code, it may look not right but - "it just works" and faces on obj looks okay.
listFaces i've temporary store face data look like:

```
 listFaces[1]: 2
 listFaces[2]: 3
... etc

```

before add it to listFaces i've just increase by +1 when read face data wich look like 0,1,2.
Then i just do this, with you edited code:

```
        private void MakeTriStipesFromListFormated(int FacesCount)
        {
            int FaceDir;
            int startDir = -1;
            int cnt = 0, f1, f2, f3;
            int fl = 0;
            
            FaceDir = startDir;
            do
            {
                cnt++;
                f1 = listFaces[fl];
                f2 = listFaces[fl + 1];
                f3 = listFaces[fl + 2];
                FaceDir *= -1;
                if ((f1 != f2) && (f2 != f3) && (f3 != f1))
                {
                    
                    
                        if (FaceDir > 0) log.AppendText(string.Format("f  {0}/{0}/{0} {1}/{1}/{1} {2}/{2}/{2}\n", f1, f2, f3));
                        else log.AppendText(string.Format("f  {0}/{0}/{0} {1}/{1}/{1} {2}/{2}/{2}\n", f1, f3, f2));
                    

                }
                f1 = f2;
                f2 = f3;
                fl++;

                
            } while (cnt < FacesCount);
            
        }

```


And get faces for obj, f 1/1/1 2/2/2 3/3/3 etc.
I understand maybe i do someting wrong because i don't understand how code works fully, but result is fine.

@Bigchillghost Thanks for that, ive look at it.

@mariokart64n Good sample, it export face without eyeballs it is OKAY? And i look at your code and find tip for me how to rotate UV,   

@shakotay2 wow, H2O this is Hex 2 Obj your application? i think i need look at it(your SM_of_Fahrenheit_loop() code) for better understand where and how get possition, thanks for helping guys!
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-19T19:11:19+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from JakeMiles ↑Sat Feb 20, 2021 1:23 am at Sat Feb 20, 2021 1:23 am
>
> before add it to listFaces i've just increase by +1 when read face data wich look like 0,1,2.yeah, the '+1' is required for wavefront obj format

> @shakotay2 wow, H2O this is Hex 2 Obj your application? i think i need look at it(your SM_of_Fahrenheit_loop() code) for better understand where and how get possition, thanks for helping guys!Yes, but SM_of_Fahrenheit_loop() is for my obsolete Make_H2O project (now replaced by: Make_obj) which I revived to get the quick results from my previous post.

Here's the output for 0d1.dat (no uvs so far), contains 3 lods, afaics:
.



0d1-dat.png (156.49 KiB) Viewed 157 times



uv's address is easy to calculate: vert_addr + 32 * vertex_count for v16 block, n16 block, t8 block
(For v16, n16, uva8, uvb8 you might try 40* vertex_count, didn't check this neither sure about uva, uvb.)
To not confuse: it's always all vertices of a sub mesh then all normals etc.

'C' source to be found here:

> Reply from shakotay2 ↑Sat Feb 20, 2021 4:27 am at Sat Feb 20, 2021 4:27 am
>
> 

(The handling of the created H2O files is a little bit unhandy   - the idea was to do quick checks with the .dat files.)

contents of log file:

```
 assumed magic tables: 30
FI: 90, v: 28
g SM_0
#  at 0x12af20 (FIs at 0x12b380)
FI: 88, v: 28
g SM_1
#  at 0x12bba0 (FIs at 0x12c000)
FI: 2314, v: 917
g SM_2
#  at 0x12c810 (FIs at 0x135760)
FI: 132, v: 88
g SM_3
#  at 0x136af0 (FIs at 0x1378b0)
FI: 597, v: 204
g SM_4
#  at 0x138120 (FIs at 0x13a100)
FI: 585, v: 201
g SM_5
#  at 0x13ad10 (FIs at 0x13cc80)
FI: 1900, v: 682
g SM_6
#  at 0x13d890 (FIs at 0x144320)
FI: 90, v: 28
g SM_7
#  at 0x156660 (FIs at 0x156ac0)
FI: 88, v: 28
g SM_8
#  at 0x1572e0 (FIs at 0x157740)
FI: 2504, v: 1005
g SM_9
#  at 0x157f50 (FIs at 0x161c60)
FI: 593, v: 204
g SM_10
#  at 0x163750 (FIs at 0x165730)
FI: 577, v: 201
g SM_11
#  at 0x166340 (FIs at 0x1682b0)
FI: 1878, v: 687
g SM_12
#  at 0x168ea0 (FIs at 0x16fa00)
FI: 567, v: 280
g SM_13
#  at 0x17b920 (FIs at 0x17e4e0)
FI: 1174, v: 489
g SM_14
#  at 0x1c6cb0 (FIs at 0x1cc880)
FI: 19, v: 12
g SM_15
#  at 0x1cd320 (FIs at 0x1cd560)
FI: 175, v: 85
g SM_16
#  at 0x1d1570 (FIs at 0x1d2580)
FI: 165, v: 85
g SM_17
#  at 0x1d3500 (FIs at 0x1d4510)
FI: 335, v: 170
g SM_18
#  at 0x1d5480 (FIs at 0x1d7470)
FI: 5, v: 4
g SM_19
#  at 0x1d8c40 (FIs at 0x1d8d00)
FI: 167, v: 89
g SM_20
#  at 0x1dbae0 (FIs at 0x1dcbb0)
FI: 167, v: 89
g SM_21
#  at 0x1ddac0 (FIs at 0x1deb90)
FI: 337, v: 178
g SM_22
#  at 0x1dfa80 (FIs at 0x1e1bf0)
FI: 917, v: 392
g SM_23
#  at 0x1e32d0 (FIs at 0x1e7c50)
FI: 5, v: 4
g SM_24
#  at 0x1e84f0 (FIs at 0x1e85b0)
FI: 169, v: 89
g SM_25
#  at 0x1ec670 (FIs at 0x1ed740)
FI: 167, v: 89
g SM_26
#  at 0x1ee660 (FIs at 0x1ef730)
FI: 335, v: 178
g SM_27
#  at 0x1f0620 (FIs at 0x1f2790)
FI: 1029, v: 431
g SM_28
#  at 0x1f3e60 (FIs at 0x1f8f40)
FI: 5, v: 4
g SM_29
#  at 0x1fe1d0 (FIs at 0x1fe290)
```
## Post #19
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-05T11:05:51+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

I think ive found bones, in sample file, 02f2.databank somewhere here hex 2C18, wich start a way up, maybe here 25C0, i don't know how to detect bones, it 80 3F  by next 80 3F diagonal? somewhere need to be a weight paint, bones a 4 byte float? where to start i need to check, wich are bones and wich weight paint? i try watch some tutorials and it hard for me currently, link me a help, if know good knowbledge about how find/read bones, for start if i can solve it, then next matrix and transforms after.

here a sample. if need more i attach more.
[https://dropmefiles.com/4Ceqf](https://dropmefiles.com/4Ceqf)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-05T12:34:29+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

There's dozens of different skeleton formats - you'll confuse yourself just jumping into your example.
Do you know what a matrix is and how it's organized? columns, rows?

And NEVER start with an unknown example as a beginner. Better try to understand a "working example" first.

I'd strongly recommend to get some basic knowledge on skeletons as can be found here:
[viewtopic.php?f=29&t=19429](https://forum.xentax.com/viewtopic.php?f=29&t=19429)

Bigchillghost linked to the basic here:
[viewtopic.php?f=29&t=19428](https://forum.xentax.com/viewtopic.php?f=29&t=19428)
for good reasons. 

btw: the list of (possibly) bones in your example is not very promising, too (you'll end up with wild guessing  ):

F_CVA_EXT1_MAING
F_CVA_EXT1_KF_waist
F_CVA_EXT1_EX_eye_D
F_CVA_EXT1_KF_wrist_D
F_CVA_EXT1_EX_majeur_2_D
F_CVA_EXT1_EX_index_1_G
F_CVA_EXT1_EX_EL_roll_G
F_CVA_EXT1_KF_hip_G
F_CVA_EXT1_MAING_s_Shape
F_CVA_EXT1_KF_sternum

(broken?)
F_CVA_EX    oulder_D

T1_EX_index_2_D
F_CVA_EX

F_CVA_EXT1_KF_collar_G
F_CVA_EXT1_EX_pouce_1_G
F_CVA_EXT1_KF_hip_D

F_CVA_EXT1_KF_ankle_G
F_CVA_EXT1_F_CVA_E1_TIF_
## Post #21
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-05T16:23:37+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from shakotay2 ↑Fri Mar 05, 2021 8:34 pm at Fri Mar 05, 2021 8:34 pm
>
> 
There's dozens of different skeleton formats - you'll confuse yourself just jumping into your example.
Do you know what a matrix is and how it's organized? columns, rows?

And NEVER start with an unknown example as a beginner. Better try to understand a "working example" first.

I'd strongly recommend to get some basic knowledge on skeletons as can be found here:
viewtopic.php?f=29&t=19429

Bigchillghost linked to the basic here:
viewtopic.php?f=29&t=19428
for good reasons. 

btw: the list of (possibly) bones in your example is not very promising, too (you'll end up with wild guessing  ):

Thanks a tip, i try samples and Noesis can't load skel, maybe i do something wrong, i just paste scripts code in .py drop it to .plugins\python
try load model from script sample and noesis just don't show anything, no errors.

That right bones not all present names, but ive found table? after 44 41 54 41 42 41 4E 4B (Databank header) just take a bit lower and take 2 byte from 484 offset(hex) it is F4 0B if search it give 3 positions two in begin and end table, and one in middle, give another example, offset 134 give two bytes 6F 84, if search it, again 3 pos, in start\end table, and one before bone name. But maybe im newbie and this is just a coincidence. I don't know what 4 or 2 bytes before 6F 84 (in start table) maybe marker for something, and what is first 2 bytes in the last 4 bytes from this line, about table in the end offset example 3B220, first 2 bytes match EE 0B with start table, somewhere else (403C), before bone(?) name (424C).

P.S. I don't know for what i write it, but maybe it have a little right position, to do, i wish    But something in my mind say me, this is wrong way  
Maybe this is not good file example, ive attach more bigger file.

[https://dropmefiles.com/MFmSW ](https://dropmefiles.com/MFmSW)
[https://dropmefiles.com/roquP](https://dropmefiles.com/roquP)
[bytes.png](https://xentaxbackup.github.io/file/19649_bytes.png)
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-05T17:51:57+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from JakeMiles ↑Sat Mar 06, 2021 12:23 am at Sat Mar 06, 2021 12:23 am
>
> Thanks a tip, i try samples and Noesis can't load skel, maybe i do something wrong, i just paste scripts code in .py drop it to .plugins\python
try load model from script sample and noesis just don't show anything, no errors.Which sample, which script exactly?
## Post #23
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-05T18:45:29+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

Found vertex shape for morph face.

[shapekeys.jpg](https://xentaxbackup.github.io/file/19650_shapekeys.jpg)
## Post #24
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-05T18:50:51+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from shakotay2 ↑Sat Mar 06, 2021 1:51 am at Sat Mar 06, 2021 1:51 am
>
> 
Which sample, which script exactly?
This:
[viewtopic.php?p=148524#p148524](https://forum.xentax.com/viewtopic.php?p=148524#p148524)
Rath.zip and Noesis script below.

Noesis give error, "File could not be previewed"
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-05T19:23:34+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from JakeMiles ↑Sat Mar 06, 2021 2:50 am at Sat Mar 06, 2021 2:50 am
>
> 
Noesis give error, "File could not be previewed"You need to add the "startup code" before the Noesis code snippet (#load the model...), then it works:

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("bonestest-skel", ".rn")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    return 1
    
    #load the model
    #...

```

.



Raz_skel.png (7.87 KiB) Viewed 97 times
## Post #26
- Username: JakeMiles
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Aug 13, 2015 6:59 am
- Post datetime: 2021-03-05T19:26:39+00:00
- Post Title: Re: Fahrenheit (Indigo Prophecy) 2005 EU PC - Research

> Reply from shakotay2 ↑Sat Mar 06, 2021 3:23 am at Sat Mar 06, 2021 3:23 am
>
> 

Didn't know about it, thanks!
