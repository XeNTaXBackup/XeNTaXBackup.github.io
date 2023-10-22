## Post #1
- Username: Nilsen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 26, 2016 7:29 am
- Post datetime: 2016-02-26T00:43:00+00:00
- Post Title: Source demo file parser (.dem) format questions.

Hello, I have been trying to make a parser for [.dem files (Source demo files)](https://developer.valvesoftware.com/wiki/DEM_Format), however I'm getting stuck because of lack of information, and my stupidity.
Without posting all my Java code, I will rather describe some of my questions/problems, and if anyone have any input or answers for one or more of the questions I would be very happy.

1. After reading the header(header->signonlength) should I read the CMD(command) as 1 or 4 bytes? Have seen both used in others code.  Tho. for me only reading 1 byte give an reasonable result.

2. If the read CMD value is 1, which is DEM_SIGNON, I have seen code which ignores the CMD all together, [source code link](https://github.com/mikeemoo/jsgo/blob/master/lib/jsgo.js#L1632), while I have also seen some code seeking(jumping) to the "Sign on length" indexed position: [source code link](http://forum.xentax.com/viewtopic.php?f=36&t=13388). Which is correct?

3. If I'm supposed to seek(jump) when getting the CMD : DEM_SIGNON (1), should I jump to the index given by "Sign on length", or my current position plus the Sign on length(jumping "Sign on length" bytes forward in the stream)? Either way, I always end up getting 0 as the next command.

4. I have seen people use Googles protocol buffer API to read the protocol buffer message, is this needed? Have tried to read some documentation, however having a hard time understanding it. What does it do, and what kind of data is the protocol buffer message?

5. Have seen both Valve's and others code use snappy to decompress potential compressed data in the file, and checking for compression right after reading the tick size of the packet.  [Code source checking if compressed](http://dev.dota2.com/showthread.php?t=32868&p=195353&viewfull=1#post195353) | [Code source not checking for any compression](https://github.com/mikeemoo/jsgo/blob/master/lib/jsgo.js#L1629). How do I know if the data is compressed?

6. Looking at: [this code](https://github.com/mikeemoo/jsgo/blob/master/lib/jsgo.js#L1736) the program checks for a lot of MSG_<TYPE> and read int/float/string accordingly. Where can I find information about the MSG types? Maybe this is something the protocol buffer handles?

Additional Java questions:
1. I first tried to understand replicate [ReadVarInt32() method created by valve](https://github.com/mitsuhiko/dota2-demoinfo2/blob/master/demofile.cpp#L29) as someone said in another thread that DataInputStream.readInt() will not handle the bytes correctly, after some asking and googling I made:

```
	return Integer.reverseBytes(buffer.readInt());
}

```

Does this seem to work? I'm having a hard time checking if my results are correct, while I do think so when looking at the header results.
Also why does every other programming languages Stream.readInt() and Stream.readInt32() work but not java's DataInputStream.readInt()?

2. Is there a quick way to .seek(index)/jump within the Stream/Buffer in java? So far I'm missing methods such as .tell() and .seek() to more easily position myself within my opened stream.

- Hopefully someone have done the same as me in the past and can give me a helping hand.

- Nilsen
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-03-23T12:03:50+00:00
- Post Title: Source demo file parser (.dem) format questions.

The command header is uint8_t for the command, then uint32_t for the tick.

The first link parses the signon data, the second link skips the data (it does a relative seek for signon length bytes).

Dunno about the rest, protobuf wasn't used when I last looked at the demo format.
