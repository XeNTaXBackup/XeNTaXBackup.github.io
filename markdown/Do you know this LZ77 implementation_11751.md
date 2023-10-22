## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-08-05T01:12:54+00:00
- Post Title: Do you know this LZ77 implementation?

I ported an LZ77 decompression routine to C# from an annoying ebook application. Could anyone identify if this is a specific public implementation? Note original assembly processed data in 4-byte chunks where possible, and there was branching everywhere. The C# version was tidied up a bit to reduce the amount of redundant code. An explanation I wrote about the encoding format is near the top.

```
{
	int inputPos = 0, outputPos = 0;

	try
	{
		while (true)
		{
			// The most significant '1' bit defines the range of the code word and operation performed by the decoder.
			// When the MSB is in the low nibble (or not present at all, as in a zero code byte), a literal is encoded.
			// When the MSB is in the high nibble, a length-distance pair is encoded. For MSB that is at 0x1 or 0x2 in
			// the high nibble, whatever bits lower than the MSB encode the length, and a short encodes the lookback
			// distance. For MSB that is at 0x4 or 0x8 in the high nibble, the lookback distance is encoded in the code
			// byte at positions 3-5 (from LSB, 1-based index), and the copy length at positions 6-8, with additional
			// lookback distance in the following byte. For all length-distance encodings, the lower 2 bits from the
			// value that encodes the lookback distance is used to encode the number of literal bytes to copy immediately
			// after.
			//
			// Copy length encoding: if the length is part of the code byte and is 0, add the value that has each bit in
			// the size of the encoding flipped to 1 (so 0x7 for 3 bits, 0xf for 4 bits, 0x1f for 5 bits), otherwise the
			// copy length is the number encoded in those bits. If those bits were 0, for each subsequent byte with value
			// of 0, add 0xff. Add the value of the next non-0 byte.
			//
			// Code byte with MSB at 0x4 or 0x8 in the upper nibble is a two byte encoding, with lookback range up to
			// 2048 bytes and copy length up to 8 bytes. The second byte's value times 8 is added to the lookback distance
			// from the code byte.
			// Code byte with MSB at 0x2 in the upper nibble has lookback range up to 16384 bytes and infinite (+2) copy
			// range. Up to 33 copy length can be stored within the code byte.
			// Code byte with MSB at 0x1 in the upper nibble has lookback range from 16385 to 49151 bytes (but not 32767
			// bytes) and infinite (+2) copy range. Up to 9 copy length can be stored within the code byte. Special encoding
			// of 0 for lookback length from loopback code means end of compressed stream. Up to 7 copy length can be
			// stored within the code byte.

			bool isLookback = true;
			bool skipParseCopyLength = false;
			int lookbackLength = 1;
			int copyLength = 1;
			byte copyLengthMask = 0;

			byte code = input[inputPos++];
			if (code < 0x10)
			{
				isLookback = false;
				copyLength += 2;
				copyLengthMask = 0x0f;
			}
			else if (code < 0x20)
			{
				copyLength += 1;
				copyLengthMask = 0x07;
				lookbackLength |= (code & 0x08) << 11;
				lookbackLength += 0x3fff;
			}
			else if (code < 0x40)
			{
				copyLength += 1;
				copyLengthMask = 0x1f;
			}
			else
			{
				skipParseCopyLength = true;
				copyLength += code >> 5;
				lookbackLength += (code >> 2) & 0x07;
				lookbackLength += input[inputPos++] * 8;
			}

			if (!isLookback || !skipParseCopyLength)
			{
				if ((code & copyLengthMask) == 0)
				{
					byte nextCode;
					for (nextCode = input[inputPos++]; nextCode == 0; nextCode = input[inputPos++])
					{
						copyLength += 0xff;
					}
					copyLength += nextCode + copyLengthMask;
				}
				else
				{
					copyLength += code & copyLengthMask;
				}

				if (isLookback)
				{
					int lookbackCode = input[inputPos++];
					lookbackCode |= input[inputPos++] << 8;
					if (code < 0x20 && (lookbackCode >> 2) == 0) break;
					lookbackLength += lookbackCode >> 2;
					code = (byte)lookbackCode;
				}
			}

			if (isLookback)
			{
				int lookbackPos = outputPos - lookbackLength;
				for (int i = 0; i < copyLength; ++i)
				{
					output[outputPos++] = output[lookbackPos++];
				}
				copyLength = code & 0x03;
			}

			for (int i = 0; i < copyLength; ++i)
			{
				output[outputPos++] = input[inputPos++];
			}
		}
	}
	catch
	{ }

	decompressedLength = outputPos;
	if (inputPos == input.Length) return 0;
	else return inputPos < input.Length ? -8 : -4;
}
```
