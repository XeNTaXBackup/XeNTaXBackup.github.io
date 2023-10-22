## Post #1
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2011-03-02T04:01:37+00:00
- Post Title: xenoblade unknown text compression?

im trying to exract this file for xenoblade...the best i could do was using falo's script it extracts a bunch of .dat files which are just garbage files(dat = data)....but i believe there is text inside these files..using a hex editor i can clearly see them but cant extract them.its a .pkb file.


the inside looks like this.it has a filename that ends with .txt then it has code then it ends with Tfile...all files are like this but im unsure what compression it uses

vs09270100_prev02.txt ‚©‚ç•ÏŠ·‚³‚ê‚½tfile..
## Post #2
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-04T16:07:41+00:00
- Post Title: xenoblade unknown text compression?

That thing you mention is not a compression, but an encoding (it´s japanese plain text), Im not saying that there could be compressed data in the pkb, but txt´s are not compressed, in fact, if you extract them and change the character set to "shift-jis", you can actually read it:

Before:
[http://img651.imageshack.us/img651/5078/22252256.png](http://img651.imageshack.us/img651/5078/22252256.png)

After:
[http://img233.imageshack.us/img233/3073/28801048.png](http://img233.imageshack.us/img233/3073/28801048.png)

The text "から変換された" Means "Converted from".

Regards:

Sky
## Post #3
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2011-03-05T23:32:50+00:00
- Post Title: xenoblade unknown text compression?

thanks a lot sky...
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-03-13T17:31:22+00:00
- Post Title: xenoblade unknown text compression?

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-14T16:02:13+00:00
- Post Title: xenoblade unknown text compression?

It is not compressed, but rather encrypted with a bitwise simple algorithm (i bet the file is variable-xored), im just way too lazy do code a decrypter
## Post #6
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-03-14T19:48:47+00:00
- Post Title: xenoblade unknown text compression?

Indeed, it's a xor based encryption, but I don't think it's that simple. The key is not fixed and has to be calculated for each byte. I got the algorithm for vs01000000.rev, but if I run it on other files, they're either still garbage (like vs00title0.rev) or only partially decrypted (strings like "<line>" are "<lije?"), maybe I just have to tweak it a bit for the latter problem.
## Post #7
- Username: SkyBladeCloud
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Jun 26, 2010 5:44 am
- Post datetime: 2011-03-14T20:20:51+00:00
- Post Title: xenoblade unknown text compression?

From what I´ve seen, only the header and some other specific file parts are encrypted, I also got the key from one of the files (which is 0x500 bytes long, btw. Basically xores and then decreases, eight times, and then jumps to xor a random value twice, then starts decreasing again...).

About the second one, i cant tell since it´s header is less than 0x500 bytes. Anyway I guess there might be other files implicated and we may not get the encryption using this 2 examples only (actually I´m not interested anyway :P:P:P:P:P). Regards:

Sky
## Post #8
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-03-14T21:00:25+00:00
- Post Title: xenoblade unknown text compression?

> From what I´ve seen, only the header and some other specific file parts are encrypted, I also got the key from one of the files (which is 0x500 bytes long, btw. Basically xores and then decreases, eight times, and then jumps to xor a random value twice, then starts decreasing again...).

Not quite. All of the values follow a certain (quite obnoxious) pattern:
the numerals array can be calculated and doesn't actually need to be stored.
tick is basically a byte counter.
offset is always 4 but changes its sign every 20 bytes
key49Digits are the digits of the key that is returned when tick mod 10 = 4 to 9
Similarly, key0Digits and key1Digits are the digits of the hex numeral when tick mod 10 = 0 or 1,
key2 is what gets returned on 2 and 3.

The initial values are the seeds.

```
		0, 1, 2, 3, 12, 13, 14, 15, 8, 9, 10, 11, 4, 5, 6, 7
	};
	int tick = -1;
	int offset = 4;
	int[] key49Digits = {0, 14};
	int[] key0Digits = {4, 1};
	int[] key1Digits = {4, 5};
	int key2 = 0;

int getNextKey() {
		byte key = 0;
		tick++;
		if (key49Digits[1] == 0) {
			key49Digits[0] = (key49Digits[0] + 1) % 16;
			key0Digits[0] = (key0Digits[0] + 1) % 16;
			key1Digits[0] = (key1Digits[0] + 1) % 16;
			key49Digits[1] = 16;
		}
		key49Digits[1]--;
		
		switch (tick % 10) {
		case 0: 
			key0Digits[1] = (key0Digits[1] + 10) % 16;
			key = (byte) (key0Digits[0] * 16 + key0Digits[1]);
			break;
		case 1:
			key1Digits[1] = (key0Digits[1] + offset) % 16;
			if (tick % 20 == 1) {
				offset = -offset;
			}
			key = (byte) (key1Digits[0] * 16 + key1Digits[1]);
			break;
		case 2:
			key2 = numerals[key49Digits[0]] * 16 + key49Digits[1];
		case 3:
			key = (byte) key2;
			break;
		default:
			key = (byte) (numerals[key49Digits[0]] * 16 + key49Digits[1]);	
		}
		return key;
	}
```


Basically, the value that counts down always does so and in a certain pattern and on certain values of it, the other, seemingly random values, are changed.
As I mentioned this works fine on the encrypted parts of vs01000000.rev, but produces minor mistakes on other files (maybe because there're some corner cases I'm ignoring)
(Alternatively, it's possible that I found a pattern where there is none, hell yeah!)

Also, are you sure that what you've got is actually the key? The algorithm will repeat values eventually, and if the desired value is 0, the file will contain a small part of the correct key, but certainly not all of it. (basically, what's used there is that for every integer a, a xor a equals 0)
Where did you get it anyway?

Here's another rev file as well as what my alg made of its first few KB:
[http://forte.spacequadrat.de/upload/more_rev_stuff.rar](http://forte.spacequadrat.de/upload/more_rev_stuff.rar)

I guess I'll look for more decrypted stuff in the memory sometime.
## Post #9
- Username: iamatmylimit
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jan 30, 2011 3:35 pm
- Post datetime: 2011-03-15T19:56:06+00:00
- Post Title: xenoblade unknown text compression?

congratulations on finding the cut scene text.....i finally saw those lines i was looking for the "long ago" text....

....thanks for finding the cut scene scripts zeforte.....
## Post #10
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-03-16T13:40:32+00:00
- Post Title: xenoblade unknown text compression?

Well damn, the actual algorithm (in Java) is:

```

    public static void decryptREV(byte[] data, byte[] key) {
		byte iterativeKey = ITERATIVE_SEED;
		for (int i = 0; i < data.length; i++) {
			byte dataKey = (byte) ((iterativeKey--) ^ (key[i % key.length]));
			data[i] ^= dataKey;
		}
	}
```


where data is the encrypted data and the "key" bytes are the ASCII codes of the filename(!) without extension.
What's left is to reverse engineer the .rev format and we can extract the strings. I'll get to it when I get the time.
