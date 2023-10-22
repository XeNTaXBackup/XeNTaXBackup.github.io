## Post #1
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2014-06-12T05:29:02+00:00
- Post Title: Tales of Vesperia Animation

hi, everyone,

I'm wondering if there're still somebody interested in this game.

I'm trying to rip models from TOV, x360 version. I've done with models and bones, now looking at the animation.

I think I'm really close now, I have figured out the how the animation track is stored and the key frames(or control points I'll mention later), the only thing I haven't got clear is the interpolation thing.For each ajacent key frame pair, there're some data in certain structure following. I think they are interpolation parameters. They may not use linear interpolation, some type of b-spine compression I guess.

Anyone would like to look at this?
I'll upload sample files when I get home later.

Edit:
The animation format is quite typical, but structured in a tedious way. I have written a python script to print out the information neatly. 
I'll explain to you by examples.This is something my script prints out. I'll include the python script as well, so if you are interested, you can take a look.

# a common header
# 00 63 -- the size of this section
# 01 02 -- the type of this transformation, 0x102 means rotation
# 00 2b fe -- bone id
# 44 19 -- This is a kind of flag, let flag = xy zw(each component 4bits), then
#               x -- number of component, they use quaternion for rotation, so x = 4 here.
#               y -- kind of indices type, not related here.
#               z -- use fixed number or not. here z=1, they save a float(-1~1) as a short.
#               w -- key frame type. I don't know how to express this, if w=3|0|2, then all the key frames are just stored as raw values.
#                       if w=8, then only 2 key frames are stored as raw values, if w=9, then serveral extra key frames are added. both w=8|9 means there're 
#                       some data follow which I think is some interpolation parameters.
# 00 79 -- total frame count
00 63 01 02 | 00 2b fe 00 | 44 19 00 79  
	type       = rotation
	sub_type   = 4419
	frames     = 121
	frame_time = 33.333363
	unk_float  = 1.140780
	indices2   = 00 04 00 14 | 00 2b 00 42
# if w = 8, then only 2 key frames, here w = 9, so 3 extra key frames are added(refer to indices2)
	key frames :
		(0.000000, 0.000000, 0.000000, 1.000000)
		(0.000000, 0.987701, 0.000000, -0.156438)
		(0.000000, -0.309030, 0.000000, -0.951048)
		(0.000000, -0.891018, 0.000000, 0.453993)
		(0.000000, 0.000000, 0.000000, 1.000000)
# for n key frames, there're n - 1 blocks of data, each block contains exactly n-component parts.
                # this is what I want to figure out.
               # what I have noticed is that the colored 4 hex, let me call them abcd, the size of data following the first 8bytes is exactly a * 8 + b * 4 + c * 2 +             
               # d * 0, and a+b+c+d is always the same for the different components. 
                # this animation is from the fight with Barboss, there're many gears rotating at constant speed, which is very regular and good for anlyzing.
                interpolate 1
		00 01 00 01 | 01 00 08 12
		ce 22 09 11 | 61 04 40 12 | 7f aa fb f5 | d6 81 f2 b8 | fc d0 01 dd | 0a b8 0e c5 | 99 56 99 66 | 99 67 99 67
		00 01 00 01 | 01 00 08 12
		c2 0e 0b 8d | 4c 04 40 12 | 7f ca ec f5 | 81 98 c8 c6 | e2 db ee e6 | db be e8 cd | 78 66 88 67 | 88 77 89 77

                interpolate 2
		00 01 00 01 | 01 00 08 12
		9f 6a 0d 48 | 42 06 20 12 | 7f d0 e9 f5 | 81 a5 c7 cd | e1 df ed e9 | d1 bf e1 ce | eb d9 f2 e0 | f8 e6 fc ea | 88 77 88 77
		00 01 00 01 | 01 00 08 12
		e9 f5 09 1e | 60 08 00 12 | 81 52 07 0b | 39 7f 16 48 | 08 30 02 23 | fc 48 f7 3a | f4 31 f2 2a | f0 25 ef 21 | ee 1e ed 1b | ec 19 ea 17

                interpolate 3
		00 01 00 01 | 01 00 08 12
		ff ff 09 27 | 60 17 00 12 | 80 01 4e ff | 08 93 0b 34 | 45 7f 1b 48 | 0c 2f 04 22 | 01 47 fb 39 | f7 30 f5 29 | f3 24 f1 20 | f0 1c ee 1a | ed 18 ec 16
		00 01 00 01 | 01 00 08 12
		78 dd 10 0f | 41 04 40 12 | 81 25 1c 0b | 7f 4c 3a 2a | 20 1b 14 13 | 34 35 24 28 | 99 a9 98 99 | 88 98 88 98

                interpolate 4
		00 01 00 01 | 01 01 04 12 | 00 00 00 00
		34 b3 09 d5 | 5f 01 40 12 | 81 36 10 0b | f9 fb b9 ca | 87 ca 87 ba
		00 01 00 01 | 01 01 04 12 | 00 00 00 00
		50 58 0a 4d | 66 01 40 12 | 7f b4 fa f4 | 68 15 88 46 | aa 45 aa 55

I'm sorry if i don't make this clear, I heavily commented the code, you can refer to it.
And here're the sample files.[https://www.mediafire.com/?2tm4rwtl8gb9gvc](https://www.mediafire.com/?2tm4rwtl8gb9gvc)
Any one can help me ?
## Post #2
- Username: delguoqing
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jun 12, 2014 9:55 am
- Post datetime: 2014-08-11T14:16:08+00:00
- Post Title: Tales of Vesperia Animation

Bump.

I'm sorry, but is there anyone who's insterested?

I had been very busy at my work, so I didn't get much time to continue this. But when I came back to this last week, it came to my mind that the animation data in this game might be compressed using some kind of signal processing method.

At first, I thought it was compressed by fourier transform, but it is definitely not, It may be some other transform that I don't know.

    1. Each component of the position/rotation(in quaternion)/scale is compressed as a independent signal.
    2. Each signal is decomposed into several(8 at most) signals of different frequency.
    3. The low frequency is stored in higher precision, and the high frequency is stored in low precision. (4bit ~ 16bit) 
    4. Each basis function can be described by 4 coefficients. As I mentioned in the last post, there're data groups of 8 bytes, 4 bytes and 2 bytes. I used to think each data group contains 2 value, which is wrong. I looked into the data, and find that 0x7FFF, 0x8001 appears very often in 8-bytes-data-group, 0x7F,0x81 appears very often in 4-bytes-group, and 0x7, 0x9 appears very often in 2-bytes-group. I don't think this is a coincidence.

It takes 4 coefficients to describe a signal, so it is definitely not Fourier Transform, also, if it is Fourier Transform, it wouldn't take so many signals to describe a simple rotation.

I tried to visualize these curves with MathVG, but without luck. I then googled a lot and find out that skeletal animations can sometimes be compressed by wavelet compression. So I thought, it may be this case, I should give it a try. But sadly, I knew little about signal processing and I'm not able to find a basis with 4 coefficients to test with it.

Is there anyone who is very good at this and willing to help? Please.
Or am I just guessed wrong ?

Thank you very much.
## Post #3
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2017-05-24T07:51:40+00:00
- Post Title: Tales of Vesperia Animation

TIP:ik
ik_chain write in bone file，maybe. "Tales of" series still use same encryption,model and animetion way untill <<tales of berseria>> 
acm friend，when i see you put “Old soldiers never die, they just fade away” as signature.i was afraid that you would never back .
so happy to see that you relive in nier2
