## Post #1
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2015-10-13T09:32:15+00:00
- Post Title: Audition Online 3D model !!!

Hi ! Im new on the forum and i need your help...
Well it will be like days that i want to open audition 3D model but it seems that i can't...
The audition 3D model are ".rgm" files and nowadays we can open them, chinese people can do it thanks to a script that i have ( a script that permit us to load rgm from 3ds max) the problem is that i don't work for me when i try to import an audition .rgm file to 3ds max i have an intense freeze and i have to shutdown my computer lol ! 

If anyone have idea how can i open RGM it would be extremly kind....

Regards,

ps : rgm is both animation and 3d model
## Post #2
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2015-10-13T11:28:29+00:00
- Post Title: Audition Online 3D model !!!

Ok i found an issue tu solve big freeze while importing rgm the problem is that the script need a folder where it can load texture of the model...
but i have another unsolvable error : x-reffed object can't be loaded...
Anyone have an issue for it ?

thanks
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-03-29T03:38:29+00:00
- Post Title: Audition Online 3D model !!!

Someone on the discord was inquiring about writing a new file for this game as they had some plugin source code but some issue. the person wasn't able to share the source code so I ended up reversing the format myself so that I would be able to read and write models to the format.

Anyway here is a incomplete script, it only parses the file but the blocks are not researched so I dont know what anything means.
Hopefully it serves a a baseline for anyone wanting to write a (open source) plugin in the future

```
struct rgm_weight (
	count = 0
	)
struct rgm_mat (
	name = "",
	id = 0
	)
struct rgm_table2 (
	unk1 = 0,
	unk2 = 0,
	unk3 = 0,
	unk4 = 0,
	transform = (matrix3 1)
	)
struct rgm_bones (
	name = "",
	child = 0,
	parent = 0
	)
struct rgm_file (
	filetype = "Delight3D 3D DynamicObjectFile",
	unk1 = 0,
	unk2 = 2,
	unk3 = #(0xDE, 0xDE, 0xDE, 0xFF, 0xFF, 0xFF, 0x1E, 0x1E, 0x1E),
	nodes = #(),
	unk4 = 0,
	unk5 = 0,
	unk6 = #(),
	unk7 = 0,
	unk8 = #(),
	face_count = 0,
	face_array = #(),
	unk9 = 0,
	unk10 = 0,
	unk11 = 0,
	unk12 = 0,
	unk13 = 0,
	mat_array = #(),
	weight_count = 0,
	weight_array = #()
	)
fn ReadFixedString &bstream fixedLen = (
	local str = ""
	for i = 1 to fixedLen do (
		str += bit.intAsChar (ReadByte bstream #unsigned)
		)
	str
	)
fn read_bone &arr &f = (
	local i = 1
	append arr (rgm_bones name:(readstring f) child:(readbyte f #unsigned))
	for i = 1 to arr[arr.count].child do read_bone arr f
	)
fn import file = (
	local rgm = rgm_file()
	local f = undefined, i = 1, b = 0, a = 0, fs = 0
	f = try(fopen file "rbS")catch(undefined)
	if f != undefined then (
		rgm.filetype = ""
		if (readlong f #unsigned) == 0x696C6544 do (
			fseek f 0 #seek_set
			fs = getFileSize file
			if fs >= 30 do (
				rgm.filetype = ReadFixedString f 30
				)
			)
		if rgm.filetype == "Delight3D 3D DynamicObjectFile" then (
			rgm.unk1 = readbyte f #unsigned
			rgm.unk2 = readbyte f #unsigned
			rgm.unk3[1] = readbyte f #unsigned
			rgm.unk3[2] = readbyte f #unsigned
			rgm.unk3[3] = readbyte f #unsigned
			rgm.unk3[4] = readbyte f #unsigned
			rgm.unk3[5] = readbyte f #unsigned
			rgm.unk3[6] = readbyte f #unsigned
			rgm.unk3[7] = readbyte f #unsigned
			rgm.unk3[8] = readbyte f #unsigned
			rgm.unk3[9] = readbyte f #unsigned
			read_bone rgm.nodes f
			-- hmmm, it overran...
			fseek f -4 #seek_cur
			
			rgm.unk4 = readlong f #unsigned
			rgm.unk5 = readlong f #unsigned
			
			do (
				a = readlong f #unsigned
				b = readbyte f #unsigned
				if b == 0x2A then (
					append rgm.unk6 (
						rgm_table2 \
							unk1:(a) \
							unk2:(b) \
							unk3:(readshort f #unsigned) \
							unk4:(readshort f #unsigned) \
							transform:(
								matrix3 \
									[readfloat f, readfloat f, readfloat f] \
									[readfloat f, readfloat f, readfloat f] \
									[readfloat f, readfloat f, readfloat f] \
									[readfloat f, readfloat f, readfloat f]
								)
						)
					) else (fseek f -5 #seek_cur)
				) while b == 0x2A
			rgm.unk6 = readlong f #unsigned -- count
			rgm.unk7 = readbyte f #unsigned -- 0
			if rgm.unk6 > 0 do rgm.unk8[rgm.unk6] = #(0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0)
			for i = 1 to rgm.unk6 do (
				rgm.unk8[1] = readfloat f
				rgm.unk8[2] = readfloat f
				rgm.unk8[3] = readfloat f
				rgm.unk8[4] = readfloat f
				rgm.unk8[5] = readfloat f
				rgm.unk8[6] = readfloat f
				rgm.unk8[7] = readfloat f
				rgm.unk8[8] = readfloat f
				)
			rgm.face_count = readlong f #unsigned
			if rgm.face_count > 0 do rgm.face_array[rgm.face_count] = [1, 2, 3]
			for i = 1 to rgm.face_count do (
				rgm.face_array = [readshort f #unsigned, readshort f #unsigned, readshort f #unsigned] + 1
				)
			rgm.unk9 = readlong f #unsigned
			rgm.unk10 = readlong f #unsigned
			rgm.unk11 = readlong f #unsigned
			rgm.unk12 = readlong f #unsigned
			rgm.unk13 = readlong f #unsigned -- count for materials?
			if rgm.unk13 > 0 do rgm.mat_array[rgm.unk13] = rgm_mat()
			for i = 1 to rgm.unk13 do (
				rgm.mat_array[i] = (rgm_mat name:(ReadFixedString f 40) id:(readbyte f #unsigned))
				)
			
			
			readbyte f #unsigned
			while ftell f < fs do (
				b = readlong f #unsigned
				case b of (
					1: fseek f 16 #seek_cur
					2: fseek f 40 #seek_cur
					default: (
						format "Stop on %\n" i
						format "new id:%\n" b
						exit
						)
					)
				)
			
			
			print (ftell f)
			) else (messagebox "Wrong File Type")
		) else (messagebox "Failed to Open")
	print "Done"
	)
import "C:\\tmp\\AudtionOnline\\fh_c4995.rgm"

```

[rgm.zip](https://xentaxbackup.github.io/file/17829_rgm.zip)
## Post #4
- Username: twigs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 16, 2019 9:03 am
- Post datetime: 2020-05-02T20:49:46+00:00
- Post Title: Audition Online 3D model !!!

> Reply from mariokart64n ↑Sun Mar 29, 2020 11:38 am at Sun Mar 29, 2020 11:38 am
>
> 
Someone on the discord was inquiring about writing a new file for this game as they had some plugin source code but some issue. the person wasn't able to share the source code so I ended up reversing the format myself so that I would be able to read and write models to the format.

Anyway here is a incomplete script, it only parses the file but the blocks are not researched so I dont know what anything means.
Hopefully it serves a a baseline for anyone wanting to write a (open source) plugin in the future
Code: Select allclearlistener()
struct rgm_weight (
	count = 0
	)
struct rgm_mat (
	name = "",
	id = 0
	)
struct rgm_table2 (
	unk1 = 0,
	unk2 = 0,
	unk3 = 0,
	unk4 = 0,
	transform = (matrix3 1)
	)
struct rgm_bones (
	name = "",
	child = 0,
	parent = 0
	)
struct rgm_file (
	filetype = "Delight3D 3D DynamicObjectFile",
	unk1 = 0,
	unk2 = 2,
	unk3 = #(0xDE, 0xDE, 0xDE, 0xFF, 0xFF, 0xFF, 0x1E, 0x1E, 0x1E),
	nodes = #(),
	unk4 = 0,
	unk5 = 0,
	unk6 = #(),
	unk7 = 0,
	unk8 = #(),
	face_count = 0,
	face_array = #(),
	unk9 = 0,
	unk10 = 0,
	unk11 = 0,
	unk12 = 0,
	unk13 = 0,
	mat_array = #(),
	weight_count = 0,
	weight_array = #()
	)
fn ReadFixedString &bstream fixedLen = (
	local str = ""
	for i = 1 to fixedLen do (
		str += bit.intAsChar (ReadByte bstream #unsigned)
		)
	str
	)
fn read_bone &arr &f = (
	local i = 1
	append arr (rgm_bones name:(readstring f) child:(readbyte f #unsigned))
	for i = 1 to arr[arr.count].child do read_bone arr f
	)
fn import file = (
	local rgm = rgm_file()
	local f = undefined, i = 1, b = 0, a = 0, fs = 0
	f = try(fopen file "rbS")catch(undefined)
	if f != undefined then (
		rgm.filetype = ""
		if (readlong f #unsigned) == 0x696C6544 do (
			fseek f 0 #seek_set
			fs = getFileSize file
			if fs >= 30 do (
				rgm.filetype = ReadFixedString f 30
				)
			)
		if rgm.filetype == "Delight3D 3D DynamicObjectFile" then (
			rgm.unk1 = readbyte f #unsigned
			rgm.unk2 = readbyte f #unsigned
			rgm.unk3[1] = readbyte f #unsigned
			rgm.unk3[2] = readbyte f #unsigned
			rgm.unk3[3] = readbyte f #unsigned
			rgm.unk3[4] = readbyte f #unsigned
			rgm.unk3[5] = readbyte f #unsigned
			rgm.unk3[6] = readbyte f #unsigned
			rgm.unk3[7] = readbyte f #unsigned
			rgm.unk3[8] = readbyte f #unsigned
			rgm.unk3[9] = readbyte f #unsigned
			read_bone rgm.nodes f
			-- hmmm, it overran...
			fseek f -4 #seek_cur
			
			rgm.unk4 = readlong f #unsigned
			rgm.unk5 = readlong f #unsigned
			
			do (
				a = readlong f #unsigned
				b = readbyte f #unsigned
				if b == 0x2A then (
					append rgm.unk6 (
						rgm_table2 \
							unk1:(a) \
							unk2:(b) \
							unk3:(readshort f #unsigned) \
							unk4:(readshort f #unsigned) \
							transform:(
								matrix3 \
									[readfloat f, readfloat f, readfloat f] \
									[readfloat f, readfloat f, readfloat f] \
									[readfloat f, readfloat f, readfloat f] \
									[readfloat f, readfloat f, readfloat f]
								)
						)
					) else (fseek f -5 #seek_cur)
				) while b == 0x2A
			rgm.unk6 = readlong f #unsigned -- count
			rgm.unk7 = readbyte f #unsigned -- 0
			if rgm.unk6 > 0 do rgm.unk8[rgm.unk6] = #(0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0)
			for i = 1 to rgm.unk6 do (
				rgm.unk8[1] = readfloat f
				rgm.unk8[2] = readfloat f
				rgm.unk8[3] = readfloat f
				rgm.unk8[4] = readfloat f
				rgm.unk8[5] = readfloat f
				rgm.unk8[6] = readfloat f
				rgm.unk8[7] = readfloat f
				rgm.unk8[8] = readfloat f
				)
			rgm.face_count = readlong f #unsigned
			if rgm.face_count > 0 do rgm.face_array[rgm.face_count] = [1, 2, 3]
			for i = 1 to rgm.face_count do (
				rgm.face_array = [readshort f #unsigned, readshort f #unsigned, readshort f #unsigned] + 1
				)
			rgm.unk9 = readlong f #unsigned
			rgm.unk10 = readlong f #unsigned
			rgm.unk11 = readlong f #unsigned
			rgm.unk12 = readlong f #unsigned
			rgm.unk13 = readlong f #unsigned -- count for materials?
			if rgm.unk13 > 0 do rgm.mat_array[rgm.unk13] = rgm_mat()
			for i = 1 to rgm.unk13 do (
				rgm.mat_array[i] = (rgm_mat name:(ReadFixedString f 40) id:(readbyte f #unsigned))
				)
			
			
			readbyte f #unsigned
			while ftell f < fs do (
				b = readlong f #unsigned
				case b of (
					1: fseek f 16 #seek_cur
					2: fseek f 40 #seek_cur
					default: (
						format "Stop on %\n" i
						format "new id:%\n" b
						exit
						)
					)
				)
			
			
			print (ftell f)
			) else (messagebox "Wrong File Type")
		) else (messagebox "Failed to Open")
	print "Done"
	)
import "C:\\tmp\\AudtionOnline\\fh_c4995.rgm"

Thanks for sharing this! What more info would you need to complete the plugin? The Audition community would be blessed to have the tool to edit such files. I'm happy to provide more info you might need on completing the script..
## Post #5
- Username: sunnydoll
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Nov 09, 2018 7:22 am
- Post datetime: 2020-12-01T17:55:11+00:00
- Post Title: Audition Online 3D model !!!

Hello 
I just wanted to let you guys know that we have our own audition 3D community.
If you are interested to join, just contact me.

mariokart64n helped the audition community so so much and we all want to thank him for all he did for us
