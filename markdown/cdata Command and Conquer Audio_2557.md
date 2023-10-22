## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-28T03:11:21+00:00
- Post Title: cdata Command and Conquer Audio

After to try to unpack manually   i tried with mplayer a gives me a possible hint:

> [mp3 @ 00B309B4]Could not find codec parameters (Audio: mp3, 8 kb/s)
>
> LAVF_header: av_find_stream_info() failed

After this i found this info here:
[EA_Command_And_Conquer_3_Audio_Codec](http://wiki.multimedia.cx/index.php?title=EA_Command_And_Conquer_3_Audio_Codec)

And a discussion about that:
[EA_Command_And_Conquer_3_Audio_Codec Talk](http://wiki.multimedia.cx/index.php?title=Talk:EA_Command_And_Conquer_3_Audio_Codec)
I attach and example
[example.zip](https://xentaxbackup.github.io/file/1108_example.zip)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2007-05-12T12:41:43+00:00
- Post Title: cdata Command and Conquer Audio

Some info on how to decode was posted by kmx in derelict studios but he left.

Ok, a little update on sound files (those with 16 bytes header)

04 TAG
00/04 channels?
BB80 khz
0000XXXX sample count
0000YYYY data size
0000XXXX sample count
..
data

Here's sample decoding function:

Decode_sample:

eax = sound info block

[eax+34] = current block/sample data ptr
[eax+38] = current block/sample number

[ecx] = sound data ptr
[ecx+4] = sound block/sample count

00886154: push ebx
mov ebx, esp
push ecx
push ecx
(...)
; mov data start ptr to edx
mov edx, esi
movaps xmm7, oword ptr [edi]
movaps xmm6, oword ptr [edi+10h]
; add sample data size (3c)
add edx, 3Ch
mov edi, [ebp+var_18]

sample_decode_loop:; CODE XREF: sub_886154+293j
pxor mm0, mm0
; mov data to mm0
punpcklbw mm0, qword ptr [esi]
(decode...)
; mov decoded data to edi buf, xmm3=left, xmm5=right channel
movlps qword ptr [edi+100h], xmm5
movhps qword ptr [edi+180h], xmm5
movlps qword ptr [edi], xmm3
movhps qword ptr [edi+80h], xmm3
add edi, 8
add esi, 4
; check if done
cmp esi, edx
jnz loc_886345

; sample decoded!
008863ED: emms
(...)
0088659B: retn

The function works like this:

stream = array;

init() {
curr_sample_ptr = sound_data_ptr;
curr_sample_num = sample_count;
}

decode_stream {
init();
while curr_sample_num != 0 {
stream.write(Decode_sample(curr_sample_num, curr_sample_ptr)) //stream actually does not exist in the *real world*, its just played in runtime, so to make proper decryption this must be implemented.
stream.seek(0x200, from_current_pos)
curr_sample_ptr+=0x4C
curr_sample_num-=0x80
}
}

Decode_sample(curr_sample_num, curr_sample_ptr): array {

sample = array[0x200]
sample_ptr = 0
vol_array = CreateVolumeArray(curr_sample_ptr) //reads 0x10 bytes from ptr
curr_sample_ptr += 0x10
sample_end = curr_sample_ptr + 0x3C

While curr_sample_ptr != sample_end {
sample[sample_ptr] = MMX_Extract_sample_qdword(vol_array * curr_sample_ptr[0])

curr_sample_ptr += 4
sample_ptr += 8
}
return sample;
}

Sorry for the crap code, its super pseudo, anyway, in other words:

input data from the file is divided into 0x4C byte blocks, each one of them is decoded into 0x200 byte blocks (2*80h left channel, 2*80h right channel). first 10h of each block is a multiplier which i called "volume", the rest, 0x3c is decoded into sample data. the number in the header which I called "sample count" is divided by 80h, which gives the real sample count (+1 from the mod 80h if !=0)

The function first does the init stuff (fills the table pointed by param1 with curr_sample_ptr and curr_sample_count (param +34h / +38h), second param points to sound_data_ptr and sample_count (param2 +0 / +4).

So its:
-check if the init was alredy done (its run only once per sound stream)
* init
-take 10h and make Volume table
-take 3Ch and go into loop, which uses MMX opcodes in order to produce proper sound sample (80h per channel * 2 = 200h) 

maybe its of use and also not all .cdata are exclusively audio, some of them hold the textures as well.
## Post #3
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2009-10-02T23:30:25+00:00
- Post Title: cdata Command and Conquer Audio

I imagine coming up with a useful tool that can identify each file individually, recognize it as either audio, texture, or whatever else the particular data inside could be, convert it, and save it as the correct universal file format of choice (audio = .wav; texture = .tga) etc...  would be a long-winded process.  Not to mention batch-conversion support to convert an entire library?
## Post #4
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-03T01:26:27+00:00
- Post Title: cdata Command and Conquer Audio

Could someone make a tool to convert the audio from that jumble that kmx supplied?
## Post #5
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2009-10-03T18:14:31+00:00
- Post Title: cdata Command and Conquer Audio

Not necessary, that was for the adpcm data (04 tag) which has been cracked and community tool can decode said adpcm files but the EALayer3 type (05 tag) still doesn't have a proper decoder and all music uses EALAYER3 compression.
## Post #6
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2009-10-03T23:27:09+00:00
- Post Title: cdata Command and Conquer Audio

which tool is that? multi-ex isn't doing it if that's what you're referring to.
## Post #7
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-10-04T07:25:59+00:00
- Post Title: cdata Command and Conquer Audio

Go to [http://www.cncmods.net](http://www.cncmods.net) and you can download tools I wrote that can read audio compressed with the EA XAS ADPCM. I (along with many others) still want someone to figure out the EALayer3 MP3-derived codec.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-04T15:03:33+00:00
- Post Title: cdata Command and Conquer Audio

Can it extract headerless XAS adpcm streams?
## Post #9
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2009-10-07T19:53:46+00:00
- Post Title: cdata Command and Conquer Audio

No, as there aren't such in C&C3/RA3 except EALAYER3 encoded ones.
