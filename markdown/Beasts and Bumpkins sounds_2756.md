## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-16T23:45:57+00:00
- Post Title: Beasts and Bumpkins sounds

Could someone help me with these sound files from the game Beasts and Bumpkins?
[B&B sounds.rar](https://xentaxbackup.github.io/file/1321_B&B sounds.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-04T11:30:44+00:00
- Post Title: Beasts and Bumpkins sounds

Found out that this seems to be some sort of [http://wiki.multimedia.cx/index.php?tit ... _Arts_SCxl](http://wiki.multimedia.cx/index.php?title=Electronic_Arts_SCxl)
But the first header is missing.

EDIT: And the compression type is 9, which is unknown.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-18T12:53:23+00:00
- Post Title: Beasts and Bumpkins sounds

Peter Ross suspected it to be MicroTalk 10:1, but I can't convert it with EA SoundXchange.
How can you verify if a certain format is used?
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-11-10T18:08:54+00:00
- Post Title: Beasts and Bumpkins sounds

Guess the only way is to reverse engineer the codec 
But it's really hard to find the place where they are decoded, any suggestions?
(QSound is used, maybe that gives a hint?)
[exe.rar](https://xentaxbackup.github.io/file/2521_exe.rar)
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-05T15:53:14+00:00
- Post Title: Beasts and Bumpkins sounds

Drives me crazy. how to get these sounds?
## Post #6
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-07-27T17:34:01+00:00
- Post Title: Beasts and Bumpkins sounds

After RE'ing the main executable of the Beasts and Bumpkins demo, I got a working decoder!  

I'm not sure if the codec has a name or not, but that's not all too important.

[Dowload the tool](http://www.box.net/shared/qvft8jgy0b)
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-27T18:30:58+00:00
- Post Title: Beasts and Bumpkins sounds

WTF? Dude you made my day, I just say: [http://drop.io/s7lo8bx](http://drop.io/s7lo8bx) 
I had almost given up on this. How did you do the debugging, the 640x480 fullscreen mode was a PITA for me.

Would you give me the source code? The sounds are pretty much the only thing I couldn't figure out so far (apart from the map format)
[http://bitbucket.org/trass3r/openbb/wiki/Home](http://bitbucket.org/trass3r/openbb/wiki/Home)
## Post #8
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-07-27T19:37:56+00:00
- Post Title: Beasts and Bumpkins sounds

> Reply from Rheini
>
> How did you do the debugging, the 640x480 fullscreen mode was a PITA for me.That was one of the problems I had too. So I used a virtual machine. VirtualBox has a neat feature -- when you install the guest additions in the virtualized operating system it will automatically resize the screen to fit VirtualBox's window. You can pretty much see where this is going. You'd just have to resize the window to change the screen res from whatever the game changed it to.

For some reason, when these sounds are decoded in the game, QSound is not used to play them. It uses DirectSound pretty much directly (although from a pointer returned by QSound).

> Reply from Rheini
>
> Would you give me the source code? The sounds are pretty much the only thing I couldn't figure out so far (apart from the map format)Sure, though the good stuff is all in assembly. However I did make a nice little wrapper for it in C++. 
[DecodeM10-src.zip](https://xentaxbackup.github.io/file/3274_DecodeM10-src.zip)
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-27T20:00:29+00:00
- Post Title: Beasts and Bumpkins sounds

> Reply from Zench
>
> For some reason, when these sounds are decoded in the game, QSound is not used to play them. It uses DirectSound pretty much directly (although from a pointer returned by QSound).

Yeah when I tracked QSound usage I got ahold of the environmental sounds, they are played using QSound.
Thanks for the code, will see what I can do with it.
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-29T00:25:11+00:00
- Post Title: Beasts and Bumpkins sounds

Works like a charm 
Converted the initialization routine 

```
{
	inner.CompressedData= inputBuffer+1;
	inner.Bits			= (cast(ubyte*)inputBuffer)[0];
	inner.BitCount		= 8;
	
	inner.FirstBit		= getBits(inner, 1);
	inner.Second4Bits	= 32 - getBits(inner, 4);
	
	inner.FloatTable[0] = (getBits(inner, 4) + 1) * 8.0;

	float ST1 = 1.04 - (getBits(inner, 6) * -0.001);
	
	for (int eax = 0; eax < 63; eax++)
		inner.FloatTable[eax+1] = inner.FloatTable[eax] * ST1;
	
	inner.Table1 = 0;
	inner.Table2 = 0;
	inner.BigTable = 0;
}
```
## Post #11
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-07-29T15:26:32+00:00
- Post Title: Beasts and Bumpkins sounds

Awesome. Now for the rest of it!
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-29T15:32:34+00:00
- Post Title: Beasts and Bumpkins sounds

I started with DecodeBlock but it's a lot of work.

How did you get that struct layout? Are you certain that it's correct?
It seems like at least Table1 is a float table.

Also I haven't found out what getBits does yet.

```
{
	uint res = buffer.Bits & bitmask_lookup_table[count];
	uint a = buffer.BitCount - count;
	uint b = buffer.Bits >> count; // note: count only byte!
    
    buffer.BitCount = a;
    buffer.Bits = b;
    if (a >= 8)
    	return res;
    
    buffer.Bits = ((cast(ubyte*)buffer.CompressedData)[0] << a) | b;
	buffer.CompressedData++;
	buffer.BitCount = a + 8;
	
	return res;
}
```
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-30T01:45:20+00:00
- Post Title: Beasts and Bumpkins sounds

Though some parts are really strange, just look at that -20 stuff:
And CompressedData seems to be floats as well?

```
{
  float *result; // eax@1
  signed int v2; // ebp@1
  int v3; // esi@1
  int v4; // ebx@2
  int v5; // edi@2
  int v6; // edx@2

  result = this->FloatTable;
  v3 = -20 - (_DWORD)this;
  v2 = 54;
  do
  {
    v4 = (int)((char *)result + v3 - 20);
    v5 = (int)((char *)result + v3 - 12);
    v6 = (int)(result - 5);
    result += 2;
    --v2;
    *(float *)v6 = (*(float *)((char *)&this->pCompressedData + v5) + *(result - 4)) * -0.11459156
                 - (*(float *)((char *)&this->pCompressedData + v4) + *(result - 2)) * -0.01803268
                 - (*(float *)(v6 - 4) + *(result - 6)) * -0.59738597;
  }
  while ( v2 );
  return (int)result;
}
```
## Post #14
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-04T18:00:41+00:00
- Post Title: Beasts and Bumpkins sounds

> Reply from Rheini
>
> How did you get that struct layout? Are you certain that it's correct?
It seems like at least Table1 is a float table.Yes, you're right. And the other tables should be floats as well. That structure was pretty tentative until I figured out more of the meanings. Here is what I have now (the names are basically the same though):

```
{
	uint8_t* CompressedData;
	uint32_t CurrentBits;
	uint32_t BitCount;
	uint32_t FirstBit;
	uint32_t Second4Bits;
	float FloatTable[64];
	float Table1[12];
	float Table2[12];
	float BigTable[324];
	float SampleBuffer[432];
};
```


> Reply from Rheini
>
> Also I haven't found out what getBits does yet.In case you didn't figure it out before you got to this, this is what it does: it reads count bits from the input stream (the CompressedData member of S_inner_file_data) and returns them.

> Reply from Rheini
>
> Though some parts are really strange, just look at that -20 stuff:
And CompressedData seems to be floats as well?Hmmm... that function doesn't take a pointer to S_inner_file_data but to an array of floats. All of the functions in the decoder aren't part of the same class, so ecx isn't always a this pointer (think fastcall calling convention). I think the weirdness in that function is because it subtracts pointers from each other. It bugs the crap out of me when I have to decipher these  . When you propagate it out all of the way, one of the pointers will cancel. Here is the function (it's correct, I tested it):

```
{
    float* CurrentPtr = Buffer + 5;

    for (unsigned int i = 0; i < 54 ; i++)
    {
        double a = CurrentPtr[-8] + CurrentPtr[-2];
        double b = CurrentPtr[-10] + CurrentPtr[0];
        double c = CurrentPtr[-6] + CurrentPtr[-4];

        CurrentPtr[-5] = (float)(a * -0.11459156 + b * 0.01803268 + c * 0.59738597);
        CurrentPtr += 2;
    }
    return;
}
```


I presume you're looking to add support for this in OpenBB. Well, I'm interested in contributing. I kinda went all out and recoded the entire decoder in C++ (and debugged out all my mistakes). So the C++ code attached below produces files that are 100% bit identical to assembly version. (I tested all the files from the demo, and I used MSVC++ 2003.) I had a little help from the latest trunk of Boomerang, but it produced incorrect code sometimes so I just hand coded most of it.

I hope you're able to use it, and I hope I didn't spoil the fun you were having in converting the assembly to D 
[decodem10_cppsrc.zip](https://xentaxbackup.github.io/file/3296_decodem10_cppsrc.zip)
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-05T01:45:09+00:00
- Post Title: Beasts and Bumpkins sounds

> Reply from Zench
>
> that function doesn't take a pointer to S_inner_file_data but to an array of floats. All of the functions in the decoder aren't part of the same class, so ecx isn't always a this pointer (think fastcall calling convention). I think the weirdness in that function is because it subtracts pointers from each other. It bugs the crap out of me when I have to decipher these
I didn't even think about that option. And because I only disassembled it and didn't debug it I couldn't recognize it either. I got the following now:

```
{
	buffer[i] = (buffer[i-3] + buffer[i+3]) * -0.11459156
			  + (buffer[i-5] + buffer[i+5]) * 0.01803268
			  + (buffer[i-1] + buffer[i+1]) * 0.59738597;
}
return;
```


> I hope you're able to use it, and I hope I didn't spoil the fun you were having in converting the assembly to DThanks for your hard work 

Still having problems with my BlockDecoder function though. Getting an ArrayOutOfBounds when indexing BigTable at the end, the only major differences are:

```
+	float* CurSampleBufPtr = DecoderStruct.SampleBuffer.ptr;
 
-		if (!DecoderStruct->FirstBit)
+		if (!DecoderStruct.FirstBit)
 		{
-			FunctionThree(DecoderStruct, Flag, TableB + 5, 1);
+			FunctionThree(DecoderStruct, Flag, &TableB[5], 1);
 		}

-			FunctionThree(DecoderStruct, Flag, TableB + 5 + IndexAdjust, 2);
+			FunctionThree(DecoderStruct, Flag, &TableB[5 + IndexAdjust], 2);
 

-				FunctionOne(TableB + 6 - IndexAdjust);
+				FunctionThree(&TableB[6 - IndexAdjust]);
 				SomeOtherFloat *= 0.5;
 			}
 		}
 
-		float* BigTablePtr = DecoderStruct->BigTable + BigTableIndex;
-
-		for (unsigned int i = 0; i < 108; i++)
+		for (uint k = 0; k < 108; k++)
 		{
-			*CurSampleBufPtr = SomeOtherFloat * TableB[i + 5] + SomeFloat * BigTablePtr[i];
+			float tmp = SomeOtherFloat * TableB[k + 5];
+			float tmp2 = SomeFloat * DecoderStruct.BigTable[BigTableIndex + k];
+			*CurSampleBufPtr = tmp + tmp2;
 			CurSampleBufPtr++;
 		}
 	}
```
## Post #16
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-05T17:47:24+00:00
- Post Title: Re: Beasts and Bumpkins sounds

I guess that BigTableIndex, if greater than (or equal to) 324, can index SampleBuffer as well, and that's the correct behavior. Which is somewhat odd. I know that SampleBuffer starts at the right offset. It's possible that it's combined with BigTable. Oh well.
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-05T18:27:13+00:00
- Post Title: Re: Beasts and Bumpkins sounds

Ah well the pitfalls of pointer arithmetics 

Maybe it's just a compiler optimization.
Two loops over BigTable and SampleBuffer get merged to one?

However it's running fine now, thanks. Now it's time to figure out what it does
## Post #18
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-10T20:39:54+00:00
- Post Title: Re: Beasts and Bumpkins sounds

> Reply from Rheini
>
> Two loops over BigTable and SampleBuffer get merged to one?
float BigTable[324];
float SampleBuffer[432];

would be changed to

float BigTableAndSampleBuffer[324 + 432];

and the decoded samples would be accessed at BigTableAndSampleBuffer + 324 is what I meant.
## Post #19
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-10T22:12:06+00:00
- Post Title: Re: Beasts and Bumpkins sounds

I know but where's the sense behind this? That's why I suggested it might be some compiler transformation.

I incorporated the code into my OpenBB hierarchy and created a small tool to unpack the entire SPEECHx.BOX 
[http://trass3r.xentax.com/node/11](http://trass3r.xentax.com/node/11)


EDIT:
What setup did you use for debugging? Have only found this so far describing IDA+VirtualBox: [http://hexblog.com/2010/04/kernel_debug ... pro_1.html](http://hexblog.com/2010/04/kernel_debugging_with_ida_pro_1.html)
## Post #20
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-14T23:13:58+00:00
- Post Title: Re: Beasts and Bumpkins sounds

> Reply from Rheini
>
> I know but where's the sense behind this? That's why I suggested it might be some compiler transformation.Yeah, you're right.

> Reply from Rheini
>
> What setup did you use for debugging? Have only found this so far describing IDA+VirtualBox: http://hexblog.com/2010/04/kernel_debug ... pro_1.htmlI used OllyDbg inside the VM, and IDA Pro Free was outside. Really it wasn't anything fancy. Thanks for sharing that link though, it looks interesting even if it isn't related to my setup.
