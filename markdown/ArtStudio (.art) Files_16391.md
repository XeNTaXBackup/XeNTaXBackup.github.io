## Post #1
- Username: willwill
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2017 10:11 am
- Post datetime: 2017-06-11T03:00:56+00:00
- Post Title: ArtStudio (.art) Files

Hello, this is my first time ever in this website.


I use this drawing application for iPhone and I would like to create a utility that would ease inter-operation between ArtStudio and Photoshop. 


Currently the workaround I do is like this:
1) Export PSD from ArtStudio
2) Open PSD in Photoshop, edit and export layers as PNGs
3) Send PNGs to camera roll
4) Open original ArtStudio file and import each PNG layer one by one
(These noted red are very tedious tasks)


However this would be much better:
1) Copy .art file to PC
2) Use the utility to parse and convert layers to PNGs, edit in Photoshop, export as PNGs
3) Send the edited PNGs to the utility to merge a .art file
Note: My ideal solution would be to use a PSD library but I will look at it later on, now the most easy approach is with PNGs.


My first task is to create the file parser, how to figure out the file format structure is beyond my current experience and your help will be much appreciated.  
[ArtStudio Files.zip](https://xentaxbackup.github.io/file/12986_ArtStudio Files.zip)
## Post #2
- Username: willwill
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2017 10:11 am
- Post datetime: 2017-06-11T03:54:11+00:00
- Post Title: ArtStudio (.art) Files

Based on my current experiments a typical structure might look like this (see the .zip).

Currently I have this code going on, I don't know if it's of any help.

```
using System.IO;
using Debug = System.Diagnostics.Debug;

namespace ArtstudioFileParser
{
	class MainClass
	{
		static void DumpFile(string file)
		{
			using (var stream = new FileStream(file, FileMode.Open, FileAccess.Read))
			{
				while (stream.Position < stream.Length)
				{
					var readByte = stream.ReadByte();

					var readChar = Convert.ToChar(readByte);
					readChar = (readChar >= 32) ? readChar : ' ';

					Debug.WriteLine(
						"Pos: {0} | Byte: {1} | Char: {2}",
						stream.Position,
						readByte,
						readChar
					);
				}
			}
		}

		static void ParseFile(string file)
		{
			using (var reader = new BinaryReader(File.Open(file, FileMode.Open)))
			{
				// skip 0 - 8
				while (reader.BaseStream.Position < 9)
					reader.ReadByte();

				// what is it on header 4?
				//Debug.WriteLine("Size: " + reader.ReadInt16());

				//new FileStream(file, FileMode.Open, FileAccess.Read))
				

				//Debug.WriteLine(stream.read

				//while (stream.Position < stream.Length)
				//{
				//	var readByte = stream.ReadByte();

				//	var readChar = Convert.ToChar(readByte);
				//	readChar = (readChar >= 32) ? readChar : ' ';

				//	Debug.WriteLine(
				//		"Pos: {0} | Byte: {1} | Char: {2}",
				//		stream.Position,
				//		readByte,
				//		readChar
				//	);
				//}
			}
		}

		public static void Main(string[] args)
		{
			//var inputFile = "D:\\Programming\\ArtStudio File Format\\artstudio_1x1_2layers_100and50_transparent.art";
			DumpFile(inputFile);
		}

	}
}

```


Let's say for example I want to examine this file: artstudio_2x2_rgba.txt

```
Pos: 2 | Byte: 0 | Char:  
Pos: 3 | Byte: 0 | Char:  
Pos: 4 | Byte: 64 | Char: @
Pos: 5 | Byte: 1 | Char:  
Pos: 6 | Byte: 0 | Char:  
Pos: 7 | Byte: 0 | Char:  
Pos: 8 | Byte: 0 | Char:  


Pos: 9 | Byte: 9 | Char:  
Pos: 10 | Byte: 28 | Char:  
Pos: 11 | Byte: 0 | Char:  
Pos: 12 | Byte: 0 | Char:  


Pos: 13 | Byte: 60 | Char: <
... the xml structure here ...
Pos: 7188 | Byte: 62 | Char: >

Pos: 7189 | Byte: 10 | Char:  
Pos: 7190 | Byte: 3 | Char:  
Pos: 7191 | Byte: 0 | Char:  
Pos: 7192 | Byte: 0 | Char:  
Pos: 7193 | Byte: 0 | Char:  
Pos: 7194 | Byte: 16 | Char:  
Pos: 7195 | Byte: 0 | Char:  
Pos: 7196 | Byte: 0 | Char:  
Pos: 7197 | Byte: 0 | Char:  

Pos: 7198 | Byte: 255 | Char: ÿ
Pos: 7199 | Byte: 0   | Char:
Pos: 7200 | Byte: 0   | Char:
Pos: 7201 | Byte: 255 | Char: ÿ
Pos: 7202 | Byte: 0   | Char:
Pos: 7203 | Byte: 255 | Char: ÿ
Pos: 7204 | Byte: 0   | Char:
Pos: 7205 | Byte: 255 | Char: ÿ
Pos: 7206 | Byte: 0   | Char:
Pos: 7207 | Byte: 0   | Char:
Pos: 7208 | Byte: 255 | Char: ÿ
Pos: 7209 | Byte: 255 | Char: ÿ
Pos: 7210 | Byte: 0   | Char:
Pos: 7211 | Byte: 0   | Char:
Pos: 7212 | Byte: 0   | Char:
Pos: 7213 | Byte: 0   | Char:

```


1. From position 1 to 8 this block is quite common, perhaps is the header of the file (8 bytes).

2. From position 9 to 12, what is this?

3. In position 13 up to far down the end some xml structure occurs, which is easy to understand. Mostly it contains rubbish information, such as tool presets, color swatches, and environment settings. From here I would strategically read only the essential, such as layer names, image size, etc... I have removed the lines to make the post lightweight (total text file is 7224 lines long). 

4. In this file at position 7188 the xml structure stops,
from what I understand there are 9 positions of data that mean something.

5. Later on at position 7198 there are the pixels of the image. This was a little easy to guess since the I placed these colors on the image, red-green-blue-transparent.


More or less same would go for the file artstudio_1x1_white.txt

```
Pos: 2    | Byte: 0   | Char:
Pos: 3    | Byte: 0   | Char:
Pos: 4    | Byte: 64  | Char: @

Pos: 5    | Byte: 1   | Char:
Pos: 6    | Byte: 0   | Char:
Pos: 7    | Byte: 0   | Char:
Pos: 8    | Byte: 0   | Char:


Pos: 9    | Byte: 89  | Char: Y
Pos: 10   | Byte: 28  | Char:
Pos: 11   | Byte: 0   | Char:
Pos: 12   | Byte: 0   | Char:


Pos: 13   | Byte: 60  | Char: <
...
Pos: 7268 | Byte: 62  | Char: >



Pos: 7269 | Byte: 10  | Char:
Pos: 7270 | Byte: 3   | Char:
Pos: 7271 | Byte: 0   | Char:
Pos: 7272 | Byte: 0   | Char:
Pos: 7273 | Byte: 0   | Char:
Pos: 7274 | Byte: 4   | Char:
Pos: 7275 | Byte: 0   | Char:
Pos: 7276 | Byte: 0   | Char:
Pos: 7277 | Byte: 0   | Char:


Pos: 7278 | Byte: 255 | Char: ÿ
Pos: 7279 | Byte: 255 | Char: ÿ
Pos: 7280 | Byte: 255 | Char: ÿ
Pos: 7281 | Byte: 255 | Char: ÿ

```




Questions...

The most tricky part so far is to locate the byte offsets.

1. Normally the XML block starts at byte 13, but where it ends? How can you determine the size of it, meaning that when you will know where to stop reading it? There would be some length in the beginning to define the offset? Or there would be some escape byte?

2. When the XML block ends at X byte, after that there is some preparation for reading the pixels. How would you know how many pixels are there? My estimation on this would be this (I am not sure though if it is OK):

For example in artstudio_2x2_rgba you get this Pos: 7194 | Byte: 16 | Char:   which might mean that you get a size of 16 bytes which is for the 4 pixels (4 * RGBA).

Another example at artstudio_1x1_white is that you get Pos: 7274 | Byte: 4   | Char: which might mean the one pixel.

Currently this looks like it works for one layer. Later on I will prepare a file containing 2 layers for more testing...

I hope my studies would give you clues, if you are more experienced than me you might be able to tell right away how things go.  
[ArtStudio Files Text Dump.zip](https://xentaxbackup.github.io/file/12987_ArtStudio Files Text Dump.zip)
## Post #3
- Username: willwill
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jun 11, 2017 10:11 am
- Post datetime: 2017-06-11T18:26:42+00:00
- Post Title: ArtStudio (.art) Files

According to further tests, I have might found it...


```
	Pos: 1    | Byte: 0   | Char:
	Pos: 2    | Byte: 0   | Char:
	Pos: 3    | Byte: 0   | Char:
	Pos: 4    | Byte: 64  | Char: @
	Pos: 5    | Byte: 1   | Char:
	Pos: 6    | Byte: 0   | Char:
	Pos: 7    | Byte: 0   | Char:
	Pos: 8    | Byte: 0   | Char:

SIZE OF XML BLOCK (integer - 2 additional bytes must be added)
	Pos: 9    | Byte: 43  | Char: +
	Pos: 10   | Byte: 41  | Char: )
	Pos: 11   | Byte: 0   | Char:
	Pos: 12   | Byte: 0   | Char:

XML BLOCK
	Pos: 13   | Byte: 60  | Char: <
	...
	Pos: 10550 | Byte: 62  | Char: >

END XML BLOCK - START READING PIXELS
	Pos: 10551 | Byte: 10  | Char:

FLAG TO PROCEED TO LAYER READING
	Pos: 10552 | Byte: 3   | Char:
	Pos: 10553 | Byte: 0   | Char:
	Pos: 10554 | Byte: 0   | Char:
	Pos: 10555 | Byte: 0   | Char:

LAYER INFORMATION (an integer)
(4_bytes * 4_pixel_elements = total_bytes_to_read)
	Pos: 10556 | Byte: 20  | Char:
	Pos: 10557 | Byte: 0   | Char:
	Pos: 10558 | Byte: 0   | Char:
	Pos: 10559 | Byte: 0   | Char:

LAYER PIXEL DATA
(as mentioned in total_bytes_to_read)
	Pos: 10560 | Byte: 1   | Char:
	Pos: 10561 | Byte: 0   | Char:
	Pos: 10562 | Byte: 60  | Char: <
	Pos: 10563 | Byte: 255 | Char: ÿ
	Pos: 10564 | Byte: 1   | Char:
	Pos: 10565 | Byte: 0   | Char:
	Pos: 10566 | Byte: 60  | Char: <
	Pos: 10567 | Byte: 255 | Char: ÿ
	Pos: 10568 | Byte: 1   | Char:
	Pos: 10569 | Byte: 0   | Char:
	Pos: 10570 | Byte: 60  | Char: <
	Pos: 10571 | Byte: 255 | Char: ÿ
	Pos: 10572 | Byte: 1   | Char:
	Pos: 10573 | Byte: 0   | Char:
	Pos: 10574 | Byte: 60  | Char: <
	Pos: 10575 | Byte: 255 | Char: ÿ
	Pos: 10576 | Byte: 1   | Char:
	Pos: 10577 | Byte: 0   | Char:
	Pos: 10578 | Byte: 60  | Char: <
	Pos: 10579 | Byte: 255 | Char: ÿ


>> REPEAT AGAIN <<
	FLAG TO PROCEED TO LAYER READING
	LAYER INFORMATION
	LAYER PIXEL DATA

	e.g.

	Pos: 10580 | Byte: 3   | Char:
	Pos: 10581 | Byte: 0   | Char:
	Pos: 10582 | Byte: 0   | Char:
	Pos: 10583 | Byte: 0   | Char:
		Pos: 10584 | Byte: 20  | Char:
		Pos: 10585 | Byte: 0   | Char:
		Pos: 10586 | Byte: 0   | Char:
		Pos: 10587 | Byte: 0   | Char:
			Pos: 10588 | Byte: 255 | Char: ÿ
			Pos: 10589 | Byte: 255 | Char: ÿ
			Pos: 10590 | Byte: 0   | Char:
			Pos: 10591 | Byte: 255 | Char: ÿ
			Pos: 10592 | Byte: 255 | Char: ÿ
			Pos: 10593 | Byte: 255 | Char: ÿ
			Pos: 10594 | Byte: 0   | Char:
			Pos: 10595 | Byte: 255 | Char: ÿ
			Pos: 10596 | Byte: 255 | Char: ÿ
			Pos: 10597 | Byte: 255 | Char: ÿ
			Pos: 10598 | Byte: 0   | Char:
			Pos: 10599 | Byte: 255 | Char: ÿ
			Pos: 10600 | Byte: 255 | Char: ÿ
			Pos: 10601 | Byte: 255 | Char: ÿ
			Pos: 10602 | Byte: 0   | Char:
			Pos: 10603 | Byte: 255 | Char: ÿ
			Pos: 10604 | Byte: 255 | Char: ÿ
			Pos: 10605 | Byte: 255 | Char: ÿ
			Pos: 10606 | Byte: 0   | Char:
			Pos: 10607 | Byte: 255 | Char: ÿ

	Pos: 10608 | Byte: 3   | Char:
	Pos: 10609 | Byte: 0   | Char:
	Pos: 10610 | Byte: 0   | Char:
	Pos: 10611 | Byte: 0   | Char:
		Pos: 10612 | Byte: 20  | Char:
		Pos: 10613 | Byte: 0   | Char:
		Pos: 10614 | Byte: 0   | Char:
		Pos: 10615 | Byte: 0   | Char:
			Pos: 10616 | Byte: 225 | Char: á
			Pos: 10617 | Byte: 10  | Char:
			Pos: 10618 | Byte: 10  | Char:
			Pos: 10619 | Byte: 255 | Char: ÿ
			Pos: 10620 | Byte: 225 | Char: á
			Pos: 10621 | Byte: 10  | Char:
			Pos: 10622 | Byte: 10  | Char:
			Pos: 10623 | Byte: 255 | Char: ÿ
			Pos: 10624 | Byte: 225 | Char: á
			Pos: 10625 | Byte: 10  | Char:
			Pos: 10626 | Byte: 10  | Char:
			Pos: 10627 | Byte: 255 | Char: ÿ
			Pos: 10628 | Byte: 225 | Char: á
			Pos: 10629 | Byte: 10  | Char:
			Pos: 10630 | Byte: 10  | Char:
			Pos: 10631 | Byte: 255 | Char: ÿ
			Pos: 10632 | Byte: 225 | Char: á
			Pos: 10633 | Byte: 10  | Char:
			Pos: 10634 | Byte: 10  | Char:
			Pos: 10635 | Byte: 255 | Char: ÿ

```


Now I will proceed to code the parser, I think it will be OK.
