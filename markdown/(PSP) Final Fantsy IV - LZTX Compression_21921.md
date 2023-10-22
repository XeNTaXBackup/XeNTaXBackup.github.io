## Post #1
- Username: travistrue
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2020 6:14 am
- Post datetime: 2020-03-22T22:41:56+00:00
- Post Title: (PSP) Final Fantsy IV - LZTX Compression

Hey everyone,

I've been learning Rust, and I wanted to try my hand at rebuilding at least part of FF4. To do so, I'd like to be able to scrape at least all of the graphical assets from the PSP ISO version of the game. I have a physical copy of the game, the ISO, and I've been able to extract many of the individual files by following this [thread from 2012](https://forum.xentax.com/viewtopic.php?f=10&t=9582&sid=b13ce12d246db9ec5e9003c0f5ad26b7&start=15).

It looks like all image files are TIM2 (.tm2) files. I was able to write a basic TIM2 image loader in Rust using [this wiki](http://wiki.xentax.com/index.php/TM2_TIM2), and looking through the code in this [C# project on Github](https://github.com/marco-calautti/Rainbow) for specifics on loading a baseline TM2 file. Things have been working out pretty well, and I've been able to extract, load, and render all of the game's tilesets, but I haven't had any luck with loading the .tm2 files for characters, character portraits, menu/shop icons, etc. because they're all compressed using a format called LZTX. I've been reading through that first link I posted quite a few times, and it sounds like the LZTX compression is a form of LZSS compression?

I'm quite new to file compression algorithms, so I'm currently researching LZSS compression. A little bit of research suggested that I learn how LZ77 works first as LZSS is the successor to that algorithm. I'm learning how the data works conceptually right now, but I will still need to know if either the entire file is LZSS-compressed (in which I will need to decode the entire file first), or if just pieces of the file are LZSS buffers/dictionaries that need to be decoded.

I attached one of these LZTX files to this post. Looking at it through a hex editor, it looks like the first 4 bytes is the file's identifier, which is "LZTX", and then there's 5 other bytes of data, then finally, the 4 more bytes that make up "TIM2", which typically makes up the first 4 bytes of a standard .tm2 file. At an initial look, it seems like maybe these aren't actually a .tm2 files. All of these files are just blobs stored in an .lzs archive file, so maybe that entire file blob needs to be decoded?

According to the old thread from 2012 above, it looks like a username named @aspire figured all of this out, and even wrote a C# program that did all of this. The link to that C# project is dead though, unfortunately. If I had that working example in C#, I could learn a lot from that conceptually, and it'd enable me to build a Rust implementation.

Any ideas?

This is my first post on these forums. Is the a user guidelines/code of conduct thread anywhere? I couldn't find one, and I usually try to look that over before I post things on new forums.

EDIT: I see a red Forum Rules bar towards the top of the page. Not sure if I missed that the first time, or what. Reading it now.
[image_panel000.rar](https://xentaxbackup.github.io/file/17782_image_panel000.rar)
## Post #2
- Username: travistrue
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2020 6:14 am
- Post datetime: 2020-03-27T01:58:38+00:00
- Post Title: (PSP) Final Fantsy IV - LZTX Compression

After a few more days, of researching and trying different things, I figured it out! I ended up creating a post over at ROMhacking.net, and got a helpful response that helped confirm a few things that I wasn't too sure of. Here's the [link](http://www.romhacking.net/forum/index.php?topic=30338.0) to that post along with pasted code, and a link to the open source project that all my code is a part of.

For convenience, I posted my Rust code below. The details are explained in detail in that link to ROMhacking.net.

```
	let mut pos = 0;
	let mut dec_pos = 0;
	let mut control = 0;
	let mut result = Vec::new();

	while pos < buffer.len() - 1 {
		control = buffer[pos];
		pos += 1;

		for i in 0..8 {
			if ((control >> i) & 0x1) == 0 {
				let byte1 = buffer[pos] as usize;
				let byte2 = buffer[pos+1] as usize;
				let length = (byte2 & 0x0F) as i32 + 3;
				let offset = (((byte2 & 0xF0) << 4) | byte1) as i32;
				let mut r = dec_pos - ((dec_pos + 0xFEE - offset) & 0xFFF);
				pos += 2;

				for _ in 0..length {
					if r >= 0 {
						result.push(result[r as usize]);
					} else {
						result.push(0);
					}

					dec_pos += 1;
					r += 1;
				}
			} else {
				result.push(buffer[pos]);
				dec_pos += 1;
				pos += 1;
			}

			if pos >= buffer.len() {
				break;
			}
		}
	}

	result
}

```
