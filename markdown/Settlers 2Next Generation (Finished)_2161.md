## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2006-10-18T21:10:39+00:00
- Post Title: Settlers 2:Next Generation (Finished)

I could need some help with the files of The Settlers 2:Next Generation. It doesn't seem to be archives, so I don't know if this is the right forum.
The devs seem to use compression/encryption on each file.
I've attached 2 of them. One must be a normal texture, the other one the credits text. The files always start with this ...rc00 header, but the rest is different.
Can somebody help me? Is this any known compression/encryption algorithm or is it own code?
A german demo is available here:
[http://www.giga.de/tv/gigagamespc/00132 ... er_2_demo/](http://www.giga.de/tv/gigagamespc/00132922_siedler_2_demo/)

EDIT: Get some decryption code below.
[files.zip](https://xentaxbackup.github.io/file/935_files.zip)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2006-10-19T09:32:36+00:00
- Post Title: Settlers 2:Next Generation (Finished)

The international version of this game seems to be called Settlers 2: 10th Anniversary.
A demo can be found here: [http://www.3dgamers.com/games/settlers2ng/downloads/](http://www.3dgamers.com/games/settlers2ng/downloads/)
## Post #3
- Username: takysoft
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 18, 2006 8:02 am
- Post datetime: 2006-12-18T00:04:13+00:00
- Post Title: Settlers 2:Next Generation (Finished)

I have the same problem. Same game.
Tried to localize the game to hungarian(translate), but the files are encrypted.

If anyone has a decrypter, please email me.
## Post #4
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2007-01-18T20:09:06+00:00
- Post Title: Settlers 2:Next Generation (Finished)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-18T20:55:30+00:00
- Post Title: Settlers 2:Next Generation (Finished)

Where did you get that from?
## Post #6
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2007-01-19T10:28:48+00:00
- Post Title: Settlers 2:Next Generation (Finished)

2Rheini: Found it half month ago on some community board.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-19T11:42:58+00:00
- Post Title: Settlers 2:Next Generation (Finished)

cool. do you still know which board this was?
I managed to write a working decryptor on my own in the meantime but if there already is an encryptor that's of course even better.
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-20T02:11:12+00:00
- Post Title: Settlers 2:Next Generation (Finished)

You did finally break the last byte? Good work!

Care to explain to the rest of the world how the system works?
## Post #9
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-02-01T21:54:47+00:00
- Post Title: Settlers 2:Next Generation (Finished)

@Rheini:

I'd also be interested in how the encryption works. I toyed around with the two command line tools but when I read you had a working decryptor I stopped.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-11T00:23:51+00:00
- Post Title: Settlers 2:Next Generation (Finished)

Here is a code snippet with the most important parts of my quick n dirty tool written in D. Please PM me if you make any optimizations.
Comments and variable names are in German (Learn it or die tryin' )

The entry point for code analysis is the Entpacken function at the end.

```
	private ubyte[16] basis; /// der 16-Byte Basiswert für pwcrc

	/// Die Kopfstruktur einer Siedler2-Datei
	struct Kopf {
		uint uk; /// seems to belong to the header 
		uint fcc; /// header 
		uint datacrc; /// crc32 checksum of decompressed data 
		uint pwcrc; /// tricky checksum
		uint datasize; /// decompressed data size
	}

	/**
	 * Ver- oder Entschlüsseln
	 * Params:
	 * 		puffer = Ein- und Ausgabepuffer
	 */
	void Schlüsseln(ubyte[] puffer)
	{
		uint x = kopf.pwcrc; // Startwert
		BerechneStartwert(x);
		Verschlüsselungsfunktion(x); // einmal initial durchlaufen

		uint xorgröße = (x & 0x7F) + 0x80; // das ist die Größe des XOR-Schlüssels

		byte[256] xorpuffer;

		for(int i=0; i<xorgröße; i++)
		{
			Verschlüsselungsfunktion(x);
			xorpuffer[i] = x & 0xFF;
		}

 		for(int i=0; i<puffer.length; i++)
 		{
 			puffer[i] = puffer[i] ^ xorpuffer[i%xorgröße];
 		}

// -----hier beginnt zweite Stufe----
		Verschlüsselungsfunktion(x);
		xorgröße = ((x & 0x1F) | 0x10) + 1;

		for(uint i=0; i<xorgröße; i++)
		{
			Verschlüsselungsfunktion(x);
			xorpuffer[i] = x & 0xFF;
		}
		Verschlüsselungsfunktion(x);
		uint offset = x % puffer.length; // Offset des falschen Bytes im Datenpuffer
		Verschlüsselungsfunktion(x);

		uint abstand = (x & 0x3FFF) | 0x2000;
		for(uint i=offset; i<puffer.length; i+=abstand)
		{
			puffer[i] ^= xorpuffer[(basis[i % 16] ^ i) % xorgröße];
		}
	}

	/// den 16er Basiswert intialisieren
	void InitialisiereBasiswert()
	{
		this.basis[] = cast(ubyte[]) [0xC9, 0x59, 0x46, 0xCA, 0xD9, 0xF0, 0x4F, 0x0A, 0xA1, 0x00, 0xAA, 0xB8, 0xCB, 0xE8, 0xDB, 0x6B];
	}

	/**
	 * berechnet den pwcrc-Wert
	 *
	 * muss vor Schlüsseln() aufgerufen werden
	 * übergeben wird der Dateiname
	 */
	uint BerechnePwCRC(string dateiname)
	{
		uint x = crc32(cast(ubyte[])dateiname); // Startwert für die x-Variable
		BerechneStartwert(x);

		for (uint i=0; i<16; i++)
		{
			Verschlüsselungsfunktion(x);
			 basis[i] ^= x & 0xFF;
		}

		return crc32(basis);
	}

	/// Berechnet den Startwert der x-Variable
	void BerechneStartwert(inout uint x)
	{
		uint[32] puffer = [12u, 0x17, 0x0A, 0x19, 0x08, 0x1B, 0x06, 0x1D, 0x04, 0x1E, 0x01, 0x16, 0x09, 0x0D, 0x15, 0x00,
						0x11, 0x1A, 0x05, 0x0F, 0x12, 0x1C, 0x0B, 0x02, 0x0E, 0x03, 0x18, 0x07, 0x13, 0x10, 0x14, 0x1F];

		uint ecx=0;
		uint edi=0;
		uint edx;

		x &= 0x7FFFFFFF;
		do 
		{
			edx = 1;
			edx <<= ecx & 0xFF;
			if (x & edx) // != 0
				edi++;
			ecx++;
		} while(ecx < 0x1F);

		if (edi < 8)
		{
			uint esi = 8;
			esi -= edi;
			edx =0;
			if (esi != 0)
			{
				uint ebp; // ebp ist nur lokal hier, ist richtig so
				do 
				{
					ecx = puffer[edx];
					ebp = 1 << (ecx & 0xFF);
					x |= ebp;
					edx++;
				} while(edx < esi);
			}
		}
		if (edi > 24)
		{
			uint esi = 32;
			esi -= edi;
			edx = 0;
			if (esi != 0)
			{
				do 
				{
					ecx = puffer[edx];
					edi = 1 << (ecx & 0xFF);
					edi ^= 0xFFFFFFFF;
					x &= edi;
					edx++;


				} while(edx < esi);
			}
		}
		if (x == 0)
			x = 1;
		else
			x &= 0x7FFFFFFF;
	}

	/// Hilfsfunktion zu Schlüsseln()
	void Verschlüsselungsfunktion(inout uint x)
	{
		uint oben  = (x >> 16) * 0x41A7; // 41A7=16807
		uint unten = (x & 0x0FFFF) * 0x41A7;
		x = ((oben & 0x7FFF) << 16) + unten;
		if (x > 0x7FFFFFFF)
			x = (x & 0x7FFFFFFF) + 1;
		x += oben >> 15;
		if (x > 0x7FFFFFFF)
			x = (x & 0x7FFFFFFF) + 1;
	}

	///
	int Entpacken(string dateiname)
	{
			if (Lesen(dateiname))
				return 1;

			// Dateinamen herausfiltern
			uint index = std.string.rfind(dateiname, cast(dchar) '\\');
			if (index != -1)
			{
				dateiname = dateiname[index+1 .. dateiname.length];
			}

			InitialisiereBasiswert();

			if (dateiname[dateiname.length-3 .. dateiname.length] != "s2m")
			{
				dateiname = std.string.tolower(dateiname);
				if (BerechnePwCRC(dateiname) != kopf.pwcrc)
				{
					writef("Prüfsumme stimmt nicht überein!\n");
					return 2;
				}
			}

			Schlüsseln(puffer); //decrypt
			ubyte[] AusPuf;
			AusPuf.length = kopf.datasize;
			Dekomprimieren(puffer, AusPuf); // LZSS

			if (crc32(AusPuf) != kopf.datacrc)
			{
				writef("crc fehlgeschlagen!\n");
			}
			// Entpackte Daten in Datei schreiben
			std.file.write(dateiname, AusPuf);

		return 0;
	}
```
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-28T02:00:44+00:00
- Post Title: Settlers 2:Next Generation (Finished)

Attached the S2Tools posted above.
[S2Tools.rar](https://xentaxbackup.github.io/file/1498_S2Tools.rar)
