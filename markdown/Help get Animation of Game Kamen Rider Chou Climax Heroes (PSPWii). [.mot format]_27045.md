## Post #1
- Username: WhiteVN606
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Nov 08, 2020 8:55 pm
- Post datetime: 2023-08-02T12:52:50+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

Hi, I'm currently trying to get the animation from the game Kamen Rider Chou Climax Heroes. It's in .mot file format, I tried using Lightware 3D to import it but it only got "unknown format" and I tried using GNTools but it outputs a .gnta file (That tool can edit GNTA to get frames and pos but very time consuming to go back and forth). Is there any way to get the animation?

Here is the sample file :
[Aut01.zip](https://xentaxbackup.github.io/file/24151_Aut01.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-02T14:31:20+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

You'll need to give the .mot file a structure. That's also very time consuming.
Without knowing the bone count even more time consuming.

Search for head_00, arm_00. leg_00, etc in .gmo to get the skeleton first.
## Post #3
- Username: WhiteVN606
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Nov 08, 2020 8:55 pm
- Post datetime: 2023-08-02T15:51:51+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

Like there's no import solution in Noesis?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-02T16:06:54+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

Not to my knowledge.
## Post #5
- Username: WhiteVN606
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Nov 08, 2020 8:55 pm
- Post datetime: 2023-08-02T17:13:08+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

sorry about that, thank you for helping me
## Post #6
- Username: WhiteVN606
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Nov 08, 2020 8:55 pm
- Post datetime: 2023-08-28T11:03:39+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

> Reply from shakotay2 ↑Wed Aug 02, 2023 10:31 pm at Wed Aug 02, 2023 10:31 pm
>
> 
You'll need to give the .mot file a structure. That's also very time consuming.
Without knowing the bone count even more time consuming.

Search for head_00, arm_00. leg_00, etc in .gmo to get the skeleton first.

The files already have a skeleton so what now ?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-08-28T21:42:40+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

> Reply from WhiteVN606 ↑Mon Aug 28, 2023 7:03 pm at Mon Aug 28, 2023 7:03 pm
>
> 
The files already have a skeleton so what now ?So can you provide it? (It's around 32 bones in the gmo file, afaics.)
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-14T08:59:35+00:00
- Post Title: Help get Animation of Game "Kamen Rider Chou Climax Heroes" (PSP/Wii). [.mot format]

> Reply from shakotay2 ↑Tue Aug 29, 2023 5:42 am at Tue Aug 29, 2023 5:42 am
>
> 
So can you provide it? (It's around 32 bones in the gmo file, afaics.)
Noesis seems to load the gmo natively.
Anyway, using ASH (with custom variable mode enabled):



0000.gmo.png (64.13 KiB) Viewed 55 times



Layout context:

```
align	address[4]
begin	loop[99]
	word	tag0
	word	tag1
	uint32	size
	test	tag0[>][0x8000]
	begin	scope
		calc	size[-][8]
		calc	nextAddr[=][0]
		tell	address[nextAddr]
		calc	nextAddr[+][size]
		test	tag0[==][0x8041]
		begin	scope
			byte	parentIndex
			byte	skip[3]
		end		scope
		test	tag0[==][0x8048]
			float	Translation[3]
		test	tag0[==][0x804B]
			float	Rotation[4]
		seek	address[nextAddr]
	end		scope
	test	tag0[<][0x8000]
	begin	scope
		byte	skip[8]
		break	loop[99]
	end		scope
end		loop[99]

```
