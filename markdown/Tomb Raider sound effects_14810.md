## Post #1
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-06T20:33:14+00:00
- Post Title: Tomb Raider sound effects

I'm trying to play the sound effects for one of the Tomb Raider games (Legend/Anniversary). They look to contain raw riff/wave data. I attempted to add a RIFF header but can't seem to get them to play properly. Can someone with more experience take a look for me?

[https://mega.nz/#!PktCXIaD!XpyuQnWrI7Nx ... KvWY5UCcD8](https://mega.nz/#!PktCXIaD!XpyuQnWrI7NxLRMFNmUhUIX1OMGSUC4pbKvWY5UCcD8)

(Ignore the file extension, they're not FSB files.)

Cheers.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-07T05:29:45+00:00
- Post Title: Tomb Raider sound effects

It looks like Microsoft IMA (RIFF WAVE codec 0x11) starting at 0x24, block size 0x24, I'll try to write a quick converter but that might be enough to figure it out if I don't get to it.
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-07T12:29:48+00:00
- Post Title: Tomb Raider sound effects

Here's a Ruby script that seems to work

```
  File.open(fn, mode='rb') do |f|
    print fn, ': '

    magic, data_size, six, zero1, id, neg1, sample_rate, zero2, zero3 =
      f.read(0x24).unpack('a4 L<4 l< L<3')

    raise 'Missing SECT' unless magic == 'SECT'
    raise 'unknown values differ' unless
      six == 6 and zero1 == 0 and neg1 == -1 and zero2 == 0 and zero3 == 0

    data_size -= 0xc
    print data_size, " bytes, ", sample_rate, "Hz\n"

    out_name = File.basename(fn, File.extname(fn)) + ".wav"
    raise "Output #{out_name} already exists" if File.exists?(out_name)

    File.open(out_name, mode='wb') do |out|
      codec_id = 0x11 # Microsoft IMA ADPCM
      channels = 1
      block_size = 0x24
      samples_per_block = (block_size - 4) * 2 + 1
      byte_rate = sample_rate * block_size / samples_per_block * channels
      sample_size = 4

      fmt = [codec_id, channels, sample_rate, byte_rate, block_size * channels, sample_size, 2, samples_per_block
        ].pack('S< S< L< L< S< S< S< S<')

      wave = ['WAVE', 'fmt ', fmt.size, fmt, 'data', data_size
        ].pack('a4 a4 L< a* a4 L<')

      out.write( ['RIFF', wave.size + data_size].pack('a4L<' ) )
      out.write( wave )
      
      copied = IO.copy_stream(f, out, data_size)
      raise 'data truncated' if copied != data_size

      raise 'extra data' unless f.eof
    end
  end
end
```

And a nice packaged build for windows: [https://hcs64.com/files/lara_01.zip](https://hcs64.com/files/lara_01.zip)
You can run it with all of the files, unlike most of my utilities it accepts multiple files at once.

```
lara *.fsb
```


The example files from your rar seem to clip a lot, but if the histories are to be believed it looks like such extreme values are supposed to be in there. So these might just be very impactful sounds... If you have some voice samples or music that might be a better point of comparison.
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-07T12:59:22+00:00
- Post Title: Tomb Raider sound effects

> Reply from hcs
>
> Here's a Ruby script that seems to work
Code: Select allfor fn in ARGV do
  File.open(fn, mode='rb') do |f|
    print fn, ': '

    magic, data_size, six, zero1, id, neg1, sample_rate, zero2, zero3 =
      f.read(0x24).unpack('a4 L<4 l< L<3')

    raise 'Missing SECT' unless magic == 'SECT'
    raise 'unknown values differ' unless
      six == 6 and zero1 == 0 and neg1 == -1 and zero2 == 0 and zero3 == 0

    data_size -= 0xc
    print data_size, " bytes, ", sample_rate, "Hz\n"

    out_name = File.basename(fn, File.extname(fn)) + ".wav"
    raise "Output #{out_name} already exists" if File.exists?(out_name)

    File.open(out_name, mode='wb') do |out|
      codec_id = 0x11 # Microsoft IMA ADPCM
      channels = 1
      block_size = 0x24
      samples_per_block = (block_size - 4) * 2 + 1
      byte_rate = sample_rate * block_size / samples_per_block * channels
      sample_size = 4

      fmt = [codec_id, channels, sample_rate, byte_rate, block_size * channels, sample_size, 2, samples_per_block
        ].pack('S< S< L< L< S< S< S< S<')

      wave = ['WAVE', 'fmt ', fmt.size, fmt, 'data', data_size
        ].pack('a4 a4 L< a* a4 L<')

      out.write( ['RIFF', wave.size + data_size].pack('a4L<' ) )
      out.write( wave )
      
      copied = IO.copy_stream(f, out, data_size)
      raise 'data truncated' if copied != data_size

      raise 'extra data' unless f.eof
    end
  end
end
And a nice packaged build for windows: https://hcs64.com/files/lara_01.zip
You can run it with all of the files, unlike most of my utilities it accepts multiple files at once.
Code: Select alllara *.fsb

The example files from your rar seem to clip a lot, but if the histories are to be believed it looks like such extreme values are supposed to be in there. So these might just be very impactful sounds... If you have some voice samples or music that might be a better point of comparison.

I can work with this! Thank you for the help
