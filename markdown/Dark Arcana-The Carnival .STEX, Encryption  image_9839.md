## Post #1
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-11-08T08:07:10+00:00
- Post Title: Dark Arcana-The Carnival *.STEX, Encryption  image?

hi body

I use quickbms extract *.stex file from Dark Arcana-The Carnival 
here is my script

##############
filexor 0x96
idstring "cub\0"
get VER string
get FILES long
getdstring DUMMY 0x100
set MAX_OFFSET 0x322AA1C0A

GoTo  0x010C
DO
getdstring NAME 0x100
get OFFSET long
get SIZE long
log NAME OFFSET SIZE

Math OFFSET += SIZE

Math hh = MAX_OFFSET
Math hh  -= OFFSET

GoTo  OFFSET

While hh >= 0x100
##########

the script is work 

but *.stex can not see,lt like a kind of encryption  image.beacuse "ARGB" and "DXT5" in it

can anybody help me to see?

A small sample has been attached. Thanks.
[stex.zip](https://xentaxbackup.github.io/file/5970_stex.zip)
## Post #2
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-11-08T08:09:01+00:00
- Post Title: Dark Arcana-The Carnival *.STEX, Encryption  image?

2.JPG (36 KiB) Viewed 149 times
## Post #3
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-11-08T08:11:02+00:00
- Post Title: Dark Arcana-The Carnival *.STEX, Encryption  image?

1.JPG (21.01 KiB) Viewed 149 times
## Post #4
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-11-15T08:50:56+00:00
- Post Title: Dark Arcana-The Carnival *.STEX, Encryption  image?

here is the desc of stex from atlas_Game.xml

<AtlasPack>
		<AtlasTexture atlas_height="256" atlas_width="256" filename="Game0_common_0.stex">
			<Texture atlas_height="256" atlas_width="256" bottom="49" filename="cursor_close_up.png" flipped="false" left="1" right="49" top="1" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="49" filename="cursor_main.png" flipped="false" left="51" right="99" top="1" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="49" filename="cursor_pick_up.png" flipped="false" left="101" right="149" top="1" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="49" filename="cursor_question_mark.png" flipped="false" left="151" right="199" top="1" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="49" filename="cursor_talk.png" flipped="false" left="201" right="249" top="1" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="99" filename="cursor_use.png" flipped="false" left="1" right="49" top="51" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="99" filename="navigation_cursor_back.png" flipped="false" left="51" right="99" top="51" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="99" filename="navigation_cursor_down.png" flipped="false" left="101" right="149" top="51" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="99" filename="navigation_cursor_down_left.png" flipped="false" left="151" right="199" top="51" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="99" filename="navigation_cursor_down_right.png" flipped="false" left="201" right="249" top="51" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="149" filename="navigation_cursor_forward.png" flipped="false" left="1" right="49" top="101" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="149" filename="navigation_cursor_forward_left.png" flipped="false" left="51" right="99" top="101" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="149" filename="navigation_cursor_forward_right.png" flipped="false" left="101" right="149" top="101" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="149" filename="navigation_cursor_left.png" flipped="false" left="151" right="199" top="101" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="149" filename="navigation_cursor_right.png" flipped="false" left="201" right="249" top="101" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="199" filename="navigation_cursor_up.png" flipped="false" left="1" right="49" top="151" uni_height="48" uni_width="48"/>
			<Texture atlas_height="256" atlas_width="256" bottom="183" filename="32x32_cursor_close_up.png" flipped="false" left="51" right="83" top="151" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="183" filename="32x32_cursor_main.png" flipped="false" left="85" right="117" top="151" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="183" filename="32x32_cursor_navigation_cursor_down_left.png" flipped="false" left="119" right="151" top="151" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="183" filename="32x32_cursor_navigation_cursor_down_right.png" flipped="false" left="153" right="185" top="151" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="183" filename="32x32_cursor_pick_up.png" flipped="false" left="187" right="219" top="151" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="183" filename="32x32_cursor_question_mark.png" flipped="false" left="221" right="253" top="151" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_cursor_talk.png" flipped="false" left="1" right="33" top="201" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_cursor_use.png" flipped="false" left="35" right="67" top="201" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_navigation_cursor_back.png" flipped="false" left="69" right="101" top="201" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_navigation_cursor_down.png" flipped="false" left="103" right="135" top="201" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_navigation_cursor_forward.png" flipped="false" left="137" right="169" top="201" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_navigation_cursor_forward_left.png" flipped="false" left="171" right="203" top="201" uni_height="32" uni_width="32"/>
			<Texture atlas_height="256" atlas_width="256" bottom="233" filename="32x32_navigation_cursor_forward_right.png" flipped="false" left="205" right="237" top="201" uni_height="32" uni_width="32"/>
		</AtlasTexture>
		<AtlasTexture atlas_height="64" atlas_width="128" filename="Game0_common_1.stex">
			<Texture atlas_height="64" atlas_width="128" bottom="33" filename="32x32_navigation_cursor_left.png" flipped="false" left="1" right="33" top="1" uni_height="32" uni_width="32"/>
			<Texture atlas_height="64" atlas_width="128" bottom="33" filename="32x32_navigation_cursor_right.png" flipped="false" left="35" right="67" top="1" uni_height="32" uni_width="32"/>
			<Texture atlas_height="64" atlas_width="128" bottom="33" filename="32x32_navigation_cursor_up.png" flipped="false" left="69" right="101" top="1" uni_height="32" uni_width="32"/>
		</AtlasTexture>
	</AtlasPack>



I think stex is argb array in  memory ？
[atlas_Game.zip](https://xentaxbackup.github.io/file/5995_atlas_Game.zip)
## Post #5
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2012-11-30T08:50:02+00:00
- Post Title: Dark Arcana-The Carnival *.STEX, Encryption  image?

disappointing,no reply....


I think its a dds,compressed and xor

but i don't konw xor key
