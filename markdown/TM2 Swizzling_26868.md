## Post #1
- Username: travistrue
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2020 6:14 am
- Post datetime: 2023-06-15T22:46:12+00:00
- Post Title: TM2 Swizzling

I'm loading every TM2 from the PSP version of FF4 into memory, and writing them to PNGs right now. There's over 13k TM2 files, and 145 of those TM2 files fail due to an out-of-bounds error that occurs when trying to swizzle those textures. Thing is, I'm not completely sure those textures need to be swizzled or not. I've rendered some of them to PNG files without swizzling, and they look fine, but I'm waiting on this next job run to figure out if those other files are supposed to be swizzled or not.

Anyway, how does my swizzling function look? Are there any issues with it?

```
	if !header.is_swizzled() {
		return Ok(buffer.to_vec());
	}

	let bpp = header.bpp as usize;
	let original_width = header.width() as usize * bpp / 8; // this could wrong for 4bpp

	/*
	  The Rainbow editor doesn't expand the input array, but this
	  implementation does. Maybe this is the key to the out-of-bounds issues?
	*/

	let mut src_index = 0usize;
	let mut result = vec![T::default(); buffer.len()];

	for y in (0..header.height as usize).step_by(SWIZZLE_HEIGHT) {
		for x in (0..original_width).step_by(SWIZZLE_WIDTH) {
			for tile_y in y..(y + SWIZZLE_HEIGHT) {
				for tile_x in x..(x + SWIZZLE_WIDTH) {
					if tile_x < original_width && tile_y < header.height as usize {
						let dst_index = tile_y * original_width + tile_x;

						let src = buffer
							.get(src_index)
							.ok_or(Error::InvalidSwizzleSrcIndex(
								src_index,
								Box::new(header.clone()),
							))?;

						let dst = result
							.get_mut(dst_index)
							.ok_or(Error::InvalidSwizzleDstIndex(
								dst_index,
								Box::new(header.clone()),
							))?;

						*dst = *src;
					}

					src_index += 1;
				}
			}
		}
	}

	Ok(result)
}

```
