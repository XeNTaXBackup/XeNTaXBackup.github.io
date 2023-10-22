## Post #1
- Username: TheFifthHorseman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 23, 2020 12:24 am
- Post datetime: 2020-11-24T15:18:43+00:00
- Post Title: Bloodrayne .TEX (Xbox type 13)

I'm looking to decode the textures used in console versions of Bloodrayne to a more readable / editable format. It seems, though, that each of the console versions had its' own (and possibly more than one) variation on the format.
Currently looking at the Xbox format and while I've got the header, palette and image data positions, the texture seems to be encoded in some way that requires translating the pixel coordinates. I have no idea what the algorithm for that should be, any ideas?

What I expect:


What I get:
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-11-24T16:10:10+00:00
- Post Title: Bloodrayne .TEX (Xbox type 13)

likely morton order swizzled, post some samples.
## Post #3
- Username: TheFifthHorseman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 23, 2020 12:24 am
- Post datetime: 2020-11-24T16:47:33+00:00
- Post Title: Bloodrayne .TEX (Xbox type 13)

The raw texture for the above picture: [https://drive.google.com/file/d/1Nv6LDl ... sp=sharing](https://drive.google.com/file/d/1Nv6LDlxEAaCnK1gS7pxqOwedhrNSIDeK/view?usp=sharing)
The current conversion script (adding to a Type 1 / Type 2 converter script that goes some 15 years back):

```

use open IO=> ':raw';

$opaque= pack "C", 255;
sub addalpha {
	return pack '(a4)*', map {$_.$opaque} unpack '(a3)*', shift;
}
while (<>) {
	unless (($base= $ARGV) =~s/\.TEX$//i) {
		warn "$ARGV has an unrecognized file extension\n";
		next;
	}

	($version, $texType, $W, $H, $x, $mipLevels, $x, $x)= unpack "I*", substr $_, 0, 32;

	if (3 != $version) {
		if (2 != $version) {
			if (6 != $version) {
				if (13 != $version) {
					warn "$ARGV is not a TEX file\n";
					next;
				}
			}
		}
	}
	#$W=$W+$W;
	#$H=$H/2;
	warn "version $version\n";
	warn "texType $texType\n";
	warn "$W x $H\n";
	warn "mip levels $mipLevels\n";
	$suffix= "";
	@shift= 0 .. $mipLevels;
	@W= map {$W >> $_} (@shift,@shift);	# doubled for offsets into texType 2 with miplevels
	@H= map {$H >> $_} (@shift,@shift);
	$pixW= $texType == 3 ?4 :1;
	@off= ($sum= 0);
	for (0..$#W) {
		push @off, $sum+= $W[$_]*$pixW*$H[$_];
	}

	for $mip (0 .. 0) {	
#	for $mip (0 .. $mipLevels) { # We're only interested in the largest version of the texture
		$W= $W[$mip];
		$H= $H[$mip];
		if ($mip) {
			$suffix= -$mip;
		}
		$out= "$base$suffix.bmp";

		# likely BMP values
		$offset= 54;
		$size= $offset + $W*$H*4;
		$ID2= 40;
		$planes= 1;
		$bpp= 32;
		$compression= 0;
		$SizeImage= $W*$H;
		$XPPM= 2834;
		$YPPM= 2834;
		$ColorsUsed= 0;
		$ColorsImportant= 0;

		$colormap= "";
		# override some of these on a per-tex-type basis
		if (1 == $texType || 2 == $texType) {

			@color= @col= unpack "C*", substr $_, 32, 256*3;
			if (2 == $version) {
				@color= @col= unpack "C*", substr $_, 24, 256*3;
			}
			for $n (0..255) {
				# bmp colors are BGR instead of RGB
				for $m (0..2) {
					$color[($n*3)+$m]= $col[($n*3)+2-$m];
				}
			}
			if (1 == $texType) {
				$offset= 54 + 256*4;    # 256 color palette
				$size= $offset+$W*$H;
				$bpp= 8;
				$ColorsUsed= 256;
				$ColorsImportant= 256;
				$colormap= addalpha pack 'C*', @color;
				$texture= pack "(a$W)*", reverse unpack "(a$W)*", substr $_, 800+$off[$mip], $W*$H;
			} else {
				$wh= $W*$H;
				my @image= unpack "C*", pack "(a$W)*", reverse unpack "(a$W)*", substr $_, 800+$off[$mip], $wh;
				my @opacity= unpack "(a1)*", pack "(a$W)*", reverse unpack "(a$W)*", substr $_, 800+$off[$mip+1+$mipLevels], $wh;
				my @rgb= unpack "(a3)*", pack "C*", @color;
				$texture= pack "(a4)*", map {"$rgb[$image[$_]]$opacity[$_]"} 0..($wh-1);
			}
		} elsif (3 == $texType) {
			$W4= $W*4;	# width of scanline
			$texture= pack "(a$W4)*", reverse unpack "(a$W4)*", substr $_, 32+$off[$mip], $W4*$H;
		} elsif (6 == $texType) {
			#PS2 texture format
			@color= @col= unpack "C*", substr $_, 0x38, 256*4;
			
			$CurrOfs = 1;
			for $i (1 .. 255){
				$SwitchI = ($i / 8)%4;
				if    ( 1 == $SwitchI ) { $vSum = 8;  }
				elsif ( 2 == $SwitchI ) { $vSum = -8; }
				else  				 	{ $vSum = 0; }
				$storeAddr = $i + $vSum ;
				$color[($storeAddr*4)+0] = $col[($CurrOfs*4)+0];
				$color[($storeAddr*4)+1] =  $col[($CurrOfs*4)+1];
				$color[($storeAddr*4)+2] =  $col[($CurrOfs*4)+2];
				$color[($storeAddr*4)+3] =  $col[($CurrOfs*4)+3];
				$CurrOfs += 1;
			}
			for $n (0..256*4-1) {
				$col[$n]=$color[$n];
			}
			for $n (0..255) {
				# bmp colors are BGR instead of RGB
				$color[($n*4)+0]= $col[($n*4)+2];
				$color[($n*4)+1]= $col[($n*4)+1];
				$color[($n*4)+2]= $col[($n*4)+0];
				$color[($n*4)+3]= 255;
			}
			
			$offset= 54 + 256*4;    # 256 color palette
			$size= $offset+$W*$H;
			$bpp= 8;
			$ColorsUsed= 256;
			$ColorsImportant= 256;
			$colormap= pack 'C*', @color;
			@texout = @rawtex = unpack "C*", substr $_, (0x38 + 31 + 0x100*4)+$off[$mip], $W*$H;

			$block_location = 0;
			$byte_num = 0;
			$swap_selector = 0;
			$posY = 0;
			$column_location = 0;
			for $y (0..$H-1) {
				for $x (0..$W-1) {
					$block_location = ($y & -16) * $W + ($x & -16) * 2;
					$swap_selector = (( ($y + 2) >> 2) & 0x1) * 4;
					$posY = ((($y  & -4) >> 1) + ($y & 1)) & 0x7;
					$column_location = $posY * $W * 2 + (($x + $swap_selector) & 0x7) * 4;
					$byte_num = (( $y >> 1) & 1) + ( ( $x >> 2) & 2);
					$texout[($y * $W) + $x] = $rawtex[$block_location + $column_location + $byte_num + 1];
				}
			}

			@texrows = @rawtexrows=  unpack "(a$W)*", pack 'C*', @texout;
			$texture= pack "(a$W)*", reverse @texrows;
		} elsif (13 == $texType) {
			#Xbox (original) texture format
			@color= @col= unpack "C*", substr $_, 0x18, 256*4;
			#The palette is BMP-correct as-is
			$offset= 0x18 + 256*4;    # 256 color palette
			$size= $offset+$W*$H;
			$bpp= 8;
			$ColorsUsed= 256;
			$ColorsImportant= 256;
			$colormap= pack 'C*', @color;
			@texout = @rawtex = unpack "C*", substr $_, (0x18 + 0x100*4)+$off[$mip], $W*$H;

			@texrows = @rawtexrows=  unpack "(a$W)*", pack 'C*', @texout;
			$texture= pack "(a$W)*", reverse @texrows;
		}
		else {
			warn "$ARGV: unsupported tex file type: $texType\n";
			next;
		}

		$header= "BM".pack "IssIIIIssIIIIII", $size, 0, 0, $offset, $ID2, $W, $H, $planes, $bpp, $compression, $SizeImage, $XPPM, $YPPM, $ColorsUsed, $ColorsImportant;

		open OUT, "> $out" or die "can't write to $out";

		print OUT $header;
		print OUT $colormap;
		print OUT $texture;

		close OUT;
	}
}

```

The type 6 support was based on code described in another thread here ( [viewtopic.php?p=161964#p162244](https://forum.xentax.com/viewtopic.php?p=161964#p162244) ) and works for that, but the unswizzling algorithm isn't applicable for Type 13. When tried, this is the result I get:
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-11-24T17:37:43+00:00
- Post Title: Bloodrayne .TEX (Xbox type 13)

Have you tried using Turfster's BloodRayne Toolset?  It works perfectly with your example:
## Post #5
- Username: TheFifthHorseman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 23, 2020 12:24 am
- Post datetime: 2020-11-24T17:57:01+00:00
- Post Title: Bloodrayne .TEX (Xbox type 13)

Which version are you using? I've got v3.5BETA5 build 051205-0240, and that one doesn't handle the Xbox textures.

EDIT: Found 3.7 build 190106-1258, that one SOLVED the problem. Thanks!
