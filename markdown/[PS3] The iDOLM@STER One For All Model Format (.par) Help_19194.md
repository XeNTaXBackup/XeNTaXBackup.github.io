## Post #1
- Username: TheTanStar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 13, 2018 9:46 am
- Post datetime: 2018-12-15T20:42:23+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

I've dumped a decrypted DLC character model archive from RAM (the game resources outside of videos and audio are encrypted and compressed) and extracted it with this script:
[http://aluigi.org/bms/naruto_paa_bin_arc.bms](http://aluigi.org/bms/naruto_paa_bin_arc.bms)

Archive: [http://www.mediafire.com/file/fft5p0t080tlgl6](http://www.mediafire.com/file/fft5p0t080tlgl6)
Expanded Archive: [http://www.mediafire.com/file/d6hpxqtfy78ykmh](http://www.mediafire.com/file/d6hpxqtfy78ykmh)
Expanded Archive contents:


I managed to extract the .pta file with the same script (it's just a renamed archive with texture files in .gtf format), but I can't make sense of the rest of the files. I assume that the .pmd file contains the model data (it's definitely not a mmd model), but I can't otherwise make sense of the file formatting.

Finally, I have a feeling that the .plt file isn't the correct size due to how I dumped the original archive from RAM.

Any help would be greatly appreciated to help import the archive or its expanded files into a program like noesis to convert it into an usable format.
## Post #2
- Username: TheTanStar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 13, 2018 9:46 am
- Post datetime: 2018-12-18T16:14:59+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

Added original .par archive to first post
## Post #3
- Username: TheTanStar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 13, 2018 9:46 am
- Post datetime: 2019-01-18T06:22:34+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

Updated first post with some clarifications and a preview of the expanded archive.
## Post #4
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-29T12:16:36+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

triangle strip damage is strong on this one ugh
[1.PNG](https://xentaxbackup.github.io/file/16823_1.PNG)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-29T14:45:27+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

> Reply from MarieRose1301 ↑Sun Sep 29, 2019 8:16 pm at Sun Sep 29, 2019 8:16 pm
>
> 
triangle strip damage is strong on this one ughcould be a matter of how the meshes are devided up into submeshes, i.e. where the triangle strips (re-) start.
example from chr_body_rank_104_a_slender.pmd.
.



uvs_test.png (60.02 KiB) Viewed 380 times
## Post #6
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-09-29T15:43:29+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

> Reply from shakotay2 ↑Sun Sep 29, 2019 10:45 pm at Sun Sep 29, 2019 10:45 pm
>
> 
MarieRose1301 wrote: ↑Sun Sep 29, 2019 8:16 pm
triangle strip damage is strong on this one ugh
could be a matter of how the meshes are devided up into submeshes, i.e. where the triangle strips (re-) start.
example from chr_body_rank_104_a_slender.pmd.
.
uvs_test.png

Yeah, I've noticed that, this particular model has many unconnected faces which my guess is are still triangle strips with just one triangle in them, right?
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-29T23:59:23+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

A member on the xentax discord named Theos had created a Noesis script and was having troubles importing these meshes with the proper weight ids. I attempted to provide support but came to the conclusion Theo's Noesis script and format specification were incomplete. I spent about 3 days reversing the format and wrote a new Noesis script from scratch. 

I found this topic and noticed that you guys probably made the same mistake Theo did, by not reading the mesh table and just reading the buffers straight through. For each submesh there is a header, and an address that goes beyond the buffers to a subheader containing the mesh details for buffer offsets, material ids, and the bone palette. 

here is a noesis script I wrote;


I tried to obtain more samples, but I was unable to unpack any usable files from the game or the DLC, so if anyone has more samples please contact me. Due to the lack of samples I had, I'm sure there may be some issues parsing other files beyond the files I had so if you encounter any issues please inform me.

```
# 
# Author: mariokart64n
# URL: https://forum.xentax.com/viewtopic.php?t=19194
# Date: April 26 2020
#
# Credits
#    Chrrox, i modified his strip reading function from an old maxscript
#    Theo, for providing samples and overview for file structure
#

showConsole = False    # shows console, leave off by default
NOEPY_HEADER = 0x504D4401   # PMD Magic

from inc_noesis import *
import math    # needed for sqrt function, used to normalize vertex normals


class pmdblock:
	pos = 0
	endpos = 0
	datapos = 0
	type = 0
	unk001 = 0
	unk002 = 0
	addr = 0
	size = 0
	count = 0
	unk003 = 0
	unk004 = 0
	unk005 = 0
	addrs = []
	sizes = []

	def read_block(self, f=NoeBitStream()):
		self.pos = f.tell()
		self.type = f.readUInt()
		self.unk001 = f.readUShort()
		self.unk002 = f.readUShort()
		self.addr = f.readUInt()
		self.size = f.readUInt()
		self.endpos = self.pos + self.addr
		if self.size > 0 and self.addr == 0x20:
			self.count = f.readUInt()
			self.unk003 = f.readUInt()
			self.unk004 = f.readUInt()
			self.unk005 = f.readUInt()
			if self.count > 0:
				self.addrs = [int] * self.count
				self.sizes = [int] * self.count
			f.seek(self.endpos, NOESEEK_ABS)
			i = 0
			for i in range(0, self.count):
				self.addrs[i] = f.readUInt()
			for i in range(0, self.count):
				self.sizes[i] = f.readUInt()
			self.datapos = self.endpos + (self.count * 8)
			self.endpos = self.datapos + self.size

class pmdPTR_entry:
	pos = 0
	index = 0
	size = 0
	unk006 = 0
	name = ""
	parent_id = 0  # parent
	child_id = 0  # child (bone connection)
	unk009 = 0
	unk010 = 0
	unk011 = []
	matrix = []
	unk012 = 0
	unk013 = 0
	unk014 = 0
	unk015 = 0
	unk016 = 0

	def __init__(self):
		self.unk011 = [float] * 9
		self.matrix = [float] * 16

	def read_ptr_entry(self, f=NoeBitStream()):
		self.pos = f.tell()
		self.index = f.readUInt()
		self.size = f.readUInt()
		self.unk006 = f.readUInt()
		self.name = f.readBytes(32).decode("UTF-8").rstrip("\0")
		self.parent_id = f.readInt()
		self.child_id = f.readInt()
		self.unk009 = f.readUInt()
		self.unk010 = f.readUInt()
		self.unk011 = [
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()
		]
		self.matrix = [
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat(),
			f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()
		]
		self.unk012 = f.readUInt()
		self.unk013 = f.readUInt()
		self.unk014 = f.readUInt()
		self.unk015 = f.readUInt()
		f.seek(self.pos + self.size, NOESEEK_ABS)

class pmdPME_matInfo:
	index = 0
	face_pos = 0
	face_count = 0
	unk080 = 0
	vert_pos = 0
	vert_count = 0

	def read_pmdPME_matInfo(self, f=NoeBitStream()):
		self.index = f.readUInt()
		self.face_pos = f.readUInt()
		self.face_count = f.readUInt()
		self.unk080 = f.readUInt()
		self.vert_pos = f.readUInt()
		self.vert_count = f.readUInt()

class pmdPME_entry:
	pos = 0
	data_pos = 0
	index = 0
	size = 0
	unk006 = 0
	name = ""
	unk020 = 0  # 0
	unk021 = 0  # parent bone
	unk022 = 0  # 0
	unk023 = 0  # -1
	unk024 = 0  # 0
	unk025 = 0  # ?? addr
	vert_count = 0
	unk026 = 0  # always 0?
	vert_buffer_size = 0
	face_count = 0
	face_max_vert_index = 0
	face_buffer_size = 0
	matid_count = 0  # num of materials
	matid = []
	matid_addr = 0
	matid_size = 0
	boneid = []
	boneid_count = 0
	boneid_addr = 0
	boneid_size = 0
	unk037 = 0
	unk038 = 0
	unk039 = 0
	unk040 = 0
	unk041 = 0
	unk042 = 0
	unk043 = 0
	bmin = []
	bmax = []
	unk046 = 0  # 1
	parent_id_addr = 0
	parent_id = 0
	unk048 = 0  # 4
	unk049 = 0  # 0
	unk050 = 0  # 1
	unk051 = 0  # 2
	unk052 = 0  # 1
	end_addr = 0
	unk054 = 0  # 0?
	unk055 = 0  # 0?
	unk056 = 0  # 0?
	unk057 = 0  # float?
	unk058 = 0  # float?
	unk059 = 0  # float?
	unk060 = 0  # float?
	unk061 = 0  # float?
	unk062 = 0  # float?
	unk063 = 0
	unk064 = 0
	unk065 = 0
	unk066 = 0
	unk067 = 0
	unk068 = 0
	unk069 = 0
	unk070 = 0
	unk071 = 0
	unk072 = 0
	unk073 = 0
	unk074 = 0
	unk075 = 0
	unk076 = 0
	unk077 = 0
	unk078 = 0
	unk079 = 0
	unk080 = 0

	def __init__(self):
		self.bmin = [float] * 4
		self.bmax = [float] * 4

	def read_pme_entry(self, f=NoeBitStream()):
		i = 1
		self.pos = f.tell()
		self.index = f.readUInt()
		self.size = f.readUInt()
		self.unk006 = f.readUInt()
		self.name = f.readBytes(32).decode("UTF-8").rstrip("\0")
		self.unk020 = f.readUInt()
		self.unk021 = f.readUInt()
		self.unk022 = f.readUInt()
		self.unk023 = f.readUInt()
		self.unk024 = f.readUInt()
		self.unk025 = f.readUInt()
		self.vert_count = f.readUInt()
		self.unk026 = f.readUInt()
		self.vert_buffer_size = f.readUInt()
		self.face_count = f.readUInt()
		self.face_max_vert_index = f.readUInt()
		self.face_buffer_size = f.readUInt()
		self.matid_count = f.readUInt()
		self.matid_addr = f.readUInt()
		self.matid_size = f.readUInt()
		self.boneid_count = f.readUInt()
		self.boneid_addr = f.readUInt()
		self.boneid_size = f.readUInt()
		self.unk037 = f.readUInt()
		self.unk038 = f.readUInt()
		self.unk039 = f.readUInt()
		self.unk040 = f.readUInt()
		self.unk041 = f.readUInt()
		self.unk042 = f.readUInt()
		self.unk043 = f.readUInt()
		self.bmin = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.bmax = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.unk046 = f.readUInt()
		self.parent_id_addr = f.readUInt()
		self.unk048 = f.readUInt()
		self.unk049 = f.readUInt()
		self.unk050 = f.readUInt()
		self.unk051 = f.readUInt()
		self.unk052 = f.readUInt()
		self.end_addr = f.readUInt()
		self.unk054 = f.readUInt()
		self.unk055 = f.readUInt()
		self.unk056 = f.readUInt()
		self.unk057 = f.readUInt()
		self.unk058 = f.readUInt()
		self.unk059 = f.readUInt()
		self.unk060 = f.readUInt()
		self.unk061 = f.readUInt()
		self.unk062 = f.readUInt()
		self.unk063 = f.readUInt()
		self.unk064 = f.readUInt()
		self.unk065 = f.readUInt()
		self.unk066 = f.readUInt()
		self.unk067 = f.readUInt()
		self.unk068 = f.readUInt()
		self.unk069 = f.readUInt()
		self.unk070 = f.readUInt()
		self.unk071 = f.readUInt()
		self.unk072 = f.readUInt()
		self.unk073 = f.readUInt()
		self.unk074 = f.readUInt()
		self.unk075 = f.readUInt()
		self.unk076 = f.readUInt()
		self.unk077 = f.readUInt()
		self.unk078 = f.readUInt()
		self.unk079 = f.readUInt()
		self.unk080 = f.readUInt()
		self.data_pos = f.tell()
		if self.matid_count > 0:
			f.seek(self.data_pos + self.matid_addr, NOESEEK_ABS)
			self.matid = [pmdPME_matInfo] * self.matid_count
			for i in range(0, self.matid_count):
				self.matid[i] = pmdPME_matInfo()
				self.matid[i].read_pmdPME_matInfo(f)
		if self.boneid_count > 0:
			f.seek(self.data_pos + self.boneid_addr, NOESEEK_ABS)
			self.boneid = [int] * self.boneid_count
			for i in range(0, self.boneid_count):
				self.boneid[i] = f.readUInt()
		f.seek(self.data_pos + self.parent_id_addr, NOESEEK_ABS)
		self.parent_id = f.readUInt()
		f.seek(self.pos + self.size, NOESEEK_ABS)

class pmdPMA_entry:
	pos = 0
	unk198 = 0
	unk199 = 0
	unk200 = 0
	name = ""
	unk201 = 0
	unk202 = 0
	unk203 = 0
	unk204 = 0
	unk205 = 0
	unk206 = 0
	unk207 = 0
	unk208 = 0
	unk209 = 0
	unk210 = 0
	unk211 = 0
	unk212 = 0
	unk213 = 0
	unk214 = 0
	unk215 = 0
	unk216 = 0
	unk217 = 0
	unk218 = 0
	unk219 = [0, 0, 0, 0]
	unk220 = [0, 0, 0, 0]
	unk221 = [0, 0, 0, 0]
	unk222 = [0, 0, 0, 0]
	unk223 = 0.0
	unk224 = 0.0
	diffuseMap_index = 0
	unk226 = 0  # FFs
	unk227 = 0
	normalMap_index = 0
	unk229 = 0
	unk230 = 0.0
	unk231 = 0  # FF
	unk232 = 0
	shadowMap_index = 0
	unk234 = 0
	unk235 = 0
	unk236 = 0
	unk237 = 0
	unk238 = 0
	unk239 = 0
	unk240 = 0
	unk241 = 0
	reflectionMaskMap_index = 0
	unk243 = 0
	unk244 = 0
	unk245 = 0
	unk246 = [0, 0, 0, 0]
	unk247 = [0, 0, 0, 0]
	def read_pma_entry(self, f=NoeBitStream()):
		self.pos = f.tell()
		self.unk198 = f.readUInt()
		self.unk199 = f.readUInt()
		self.unk200 = f.readUInt()
		self.name = f.readBytes(32).decode("UTF-8").rstrip("\0")
		self.unk201 = f.readUInt()
		self.unk202 = f.readUInt()
		self.unk203 = f.readUInt()
		self.unk204 = f.readUInt()
		self.unk205 = f.readUInt()
		self.unk206 = f.readUInt()
		self.unk207 = f.readUInt()
		self.unk208 = f.readUInt()
		self.unk209 = f.readUInt()
		self.unk210 = f.readUInt()
		self.unk211 = f.readUInt()
		self.unk212 = f.readUInt()
		self.unk213 = f.readUInt()
		self.unk214 = f.readUInt()
		self.unk215 = f.readUInt()
		self.unk216 = f.readUInt()
		self.unk217 = f.readUInt()
		self.unk218 = f.readUInt()
		self.unk219 = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.unk220 = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.unk221 = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.unk222 = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.unk223 = f.readFloat()
		self.unk224 = f.readFloat()
		self.diffuseMap_index = f.readUInt()
		self.unk226 = f.readUInt()
		self.unk227 = f.readUInt()
		self.normalMap_index = f.readUInt()
		self.unk229 = f.readUInt()
		self.unk230 = f.readFloat()
		self.unk231 = f.readUInt()
		self.unk232 = f.readUInt()
		self.shadowMap_index = f.readUInt()
		self.unk234 = f.readUInt()
		self.unk235 = f.readUInt()
		self.unk236 = f.readUInt()
		self.unk237 = f.readUInt()
		self.unk238 = f.readUInt()
		self.unk239 = f.readUInt()
		self.unk240 = f.readUInt()
		self.unk241 = f.readUInt()
		self.reflectionMaskMap_index = f.readUInt()
		self.unk243 = f.readUInt()
		self.unk244 = f.readUInt()
		self.unk245 = f.readUInt()
		self.unk246 = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
		self.unk247 = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]

class pmdPAR_entry:
	pos = 0
	name = ""
	version = 0
	image_size = 0
	image_count = 0
	unk103 = 0
	image_addr = 0
	image_size2 = 0
	format = 0
	unk107 = 0
	unk108 = 0
	unk109 = 0
	unk110 = 0
	width = 0
	height = 0
	depth = 0
	unk114 = 0
	unk115 = 0
	unk116 = 0
	unk117 = 0
	unk118 = 0
	unk119 = 0
	unk120 = 0
	unk121 = 0
	unk122 = 0
	unk123 = 0
	unk124 = 0
	unk125 = 0
	unk126 = 0
	unk127 = 0
	unk128 = 0
	unk129 = 0
	unk130 = 0
	unk131 = 0
	unk132 = 0
	unk133 = 0
	unk134 = 0
	unk135 = 0
	unk136 = 0
	def read_par_entry(self, f = NoeBitStream()):
		self.pos = f.tell()
		self.version = f.readUInt()
		self.image_size = f.readUInt()
		self.image_count = f.readUInt()
		self.unk103 = f.readUInt()
		self.image_addr = f.readUInt()
		self.image_size2 = f.readUInt()
		self.format = f.readUByte()
		self.unk107 = f.readUByte()
		self.unk108 = f.readUByte()
		self.unk109 = f.readUByte()
		self.unk110 = f.readUInt()
		self.width = f.readUShort()
		self.height = f.readUShort()
		self.depth = f.readUShort()
		self.unk114 = f.readUShort()
		self.unk115 = f.readUInt()
		self.unk116 = f.readUInt()
		self.unk117 = f.readUInt()
		self.unk118 = f.readUInt()
		self.unk119 = f.readUInt()
		self.unk120 = f.readUInt()
		self.unk121 = f.readUInt()
		self.unk122 = f.readUInt()
		self.unk123 = f.readUInt()
		self.unk124 = f.readUInt()
		self.unk125 = f.readUInt()
		self.unk126 = f.readUInt()
		self.unk127 = f.readUInt()
		self.unk128 = f.readUInt()
		self.unk129 = f.readUInt()
		self.unk130 = f.readUInt()
		self.unk131 = f.readUInt()
		self.unk132 = f.readUInt()
		self.unk133 = f.readUInt()
		self.unk134 = f.readUInt()
		self.unk135 = f.readUInt()
		self.unk136 = f.readUInt()

class ptafile:
	par = []
	def create_image_list(self, f = NoeBitStream()):
		texList = []
		imgData = []
		i = 0
		pos = f.tell()
		filetype = f.readUInt()
		version = f.readUInt()
		count = f.readUInt()
		unk299 = f.readUInt()
		self.par = [pmdPAR_entry] * count
		i = 0
		for i in range(0, count):
			f.seek(pos + 0x10 + (i * 4), NOESEEK_ABS)
			self.par[i] = pmdPAR_entry()
			f.seek(pos + f.readUInt(), NOESEEK_ABS)
			self.par[i].read_par_entry(f)
			f.seek(pos + 0x10 + (count * 4) + (i * 0x80), NOESEEK_ABS)
			self.par[i].name = f.readBytes(128).decode("UTF-8").rstrip("\0")
		if count > 0:
			texList = [NoeTexture] * count
		for i in range(0, count):
			#print(str(i) + " " + self.par[i].name)
			f.seek(self.par[i].pos + self.par[i].image_addr, NOESEEK_ABS)
			imgData = f.readBytes(self.par[i].image_size)
			if self.par[i].format == 0x85:
				texList[i] = NoeTexture(self.par[i].name, self.par[i].width, self.par[i].height, imgData, noesis.NOESISTEX_RGBA32)
			elif self.par[i].format == 0x86:
				texList[i] = NoeTexture(self.par[i].name, self.par[i].width, self.par[i].height, imgData, noesis.NOESISTEX_DXT1)
			elif self.par[i].format == 0x87:
				texList[i] = NoeTexture(self.par[i].name, self.par[i].width, self.par[i].height, imgData, noesis.NOESISTEX_DXT3)
			elif self.par[i].format == 0x88:
				texList[i] = NoeTexture(self.par[i].name, self.par[i].width, self.par[i].height, imgData, noesis.NOESISTEX_DXT5)
			else:
				print(self.par[i].format)
				texList[i] = NoeTexture(self.par[i].name, self.par[i].width, self.par[i].height, imgData, noesis.NOESISTEX_UNKNOWN)
		return texList

class pmdfile:
	ptr = []
	pme = []
	pma = []
	def read_pmd(self, f=NoeBitStream(), fileSize=0):
		f.seek(0, NOESEEK_ABS)
		chunk = pmdblock()
		while f.tell() < fileSize:
			chunk.read_block(f)
			if chunk.type == 0x50545201 and chunk.count > 0:  # PTR (Skeleton)
				self.ptr = [pmdPTR_entry] * chunk.count
				i = 0
				for i in range(0, chunk.count):
					f.seek(chunk.datapos + chunk.addrs[i], NOESEEK_ABS)
					self.ptr[i] = pmdPTR_entry()
					self.ptr[i].read_ptr_entry(f)
				# print(self.ptr[i].matrix[3])
			elif chunk.type == 0x504D4501 and chunk.count > 0:  # PME
				self.pme = [pmdPME_entry] * chunk.count
				i = 0
				for i in range(0, chunk.count):
					f.seek(chunk.datapos + chunk.addrs[i], NOESEEK_ABS)
					self.pme[i] = pmdPME_entry()
					self.pme[i].read_pme_entry(f)
			elif chunk.type == 0x504D4101 and chunk.count > 0:  # PMA
				self.pma = [pmdPMA_entry] * chunk.count
				i = 0
				for i in range(0, chunk.count):
					f.seek(chunk.datapos + chunk.addrs[i], NOESEEK_ABS)
					self.pma[i] = pmdPMA_entry()
					self.pma[i].read_pma_entry(f)
			f.seek(chunk.endpos, NOESEEK_ABS)

	def create_bone_list(self):
		BoneList = []
		BoneMatrix43 = NoeMat43()
		BoneMatrix44 = NoeMat44()
		BoneName = ""
		ParentName = ""
		i = 0
		NumBones = len(self.ptr)
		if NumBones > 0:
			BoneList = [NoeBone] * NumBones
			for i in range(0, NumBones):
				BoneMatrix44 = NoeMat44((
					NoeVec4(
						(self.ptr[i].matrix[0], self.ptr[i].matrix[1], self.ptr[i].matrix[2], self.ptr[i].matrix[3])),
					NoeVec4(
						(self.ptr[i].matrix[4], self.ptr[i].matrix[5], self.ptr[i].matrix[6], self.ptr[i].matrix[7])),
					NoeVec4(
						(self.ptr[i].matrix[8], self.ptr[i].matrix[9], self.ptr[i].matrix[10], self.ptr[i].matrix[11])),
					NoeVec4((self.ptr[i].matrix[12], self.ptr[i].matrix[13], self.ptr[i].matrix[14],
							 self.ptr[i].matrix[15]))
				))

				BoneMatrix43 = BoneMatrix44.toMat43()
				BoneMatrix43 = BoneMatrix43.inverse()

				BoneName = "bone%03i" % i
				ParentName = "bone%03i" % self.ptr[i].parent_id
				if self.ptr[i].name != "":
					BoneName = self.ptr[i].name
				if self.ptr[i].parent_id > -1 and self.ptr[i].parent_id < NumBones:
					if self.ptr[self.ptr[i].parent_id].name != "":
						ParentName = self.ptr[self.ptr[i].parent_id].name
					BoneList[i] = (NoeBone(i, BoneName, BoneMatrix43, ParentName, self.ptr[i].parent_id))
				else:
					BoneList[i] = (NoeBone(i, self.ptr[i].name, BoneMatrix43, None, -1))
		return BoneList

	def create_mesh_list(self, f = NoeBitStream(), texList = []):
		mshList = []
		matList = []
		posList = []
		nrmList = []
		bWeList = []
		colList = []
		uv0List = []
		uv1List = []
		idxList = []
		vert = [0.0, 0.0, 0.0, 0.0]
		norm = [0.0, 0.0, 0.0, 0.0]
		colr = [1.0, 0.0, 0.0, 0.0]
		boWe = [1.0, 0.0, 0.0, 0.0]
		boId = [0, 0, 0, 0]
		uvw0 = [0.0, 0.0]
		uvw1 = [0.0, 0.0]
		mesh = 0
		element = 0
		mesh_count = 0
		mesh_index = 0
		material_count = 0
		material_name = ""
		texture_name = ""
		texture_count = 0
		vstride = 0
		fstride = 0
		vcount = 0
		vertAdd = 0
		StartDirection = 1
		FaceDirection = 1
		f1 = 1
		f2 = 2
		f3 = 3
		face_term = 0xFFFFFFFF
		mat_index = 0
		v = 0
		x = 0
		div = 0.0


		mesh_count = 0
		for mesh in range(0, len(self.pme)):
			mesh_count = mesh_count + self.pme[mesh].matid_count

		if mesh_count > 0:
			mshList = [NoeMesh] * mesh_count
			matList = [NoeMaterial] * mesh_count

		mesh_index = 0
		material_count = len(self.pma)
		texture_count = len(texList)

		for mesh in range(0, len(self.pme)):
			vstride = int(self.pme[mesh].vert_buffer_size / self.pme[mesh].vert_count)
			fstride = int(self.pme[mesh].face_buffer_size / self.pme[mesh].face_count)
			vcount = 0
			vertAdd = 0
			for element in range(0, self.pme[mesh].matid_count):
				material_name = "mat%03i" % mesh_index
				texture_name = ""
				if self.pme[mesh].matid[element].index < material_count:
					material_name = self.pma[self.pme[mesh].matid[element].index].name
					if self.pma[self.pme[mesh].matid[element].index - self.pma[self.pme[mesh].matid[element].index].unk243].diffuseMap_index < texture_count:
						texture_name = texList[self.pma[self.pme[mesh].matid[element].index - self.pma[self.pme[mesh].matid[element].index].unk243].diffuseMap_index].name
				#print("MaterialName " + str(material_name))
				#print("TextureName " + str(texture_name))
				matList[mesh_index] = NoeMaterial(material_name, texture_name)
				matList[mesh_index].setDefaultBlend(False)
				if texture_name != "":
					if self.pma[self.pme[mesh].matid[element].index].normalMap_index > -1 and self.pma[self.pme[mesh].matid[element].index].normalMap_index < texture_count:
						matList[mesh_index].setNormalTexture(textList[self.pma[self.pme[mesh].matid[element].index].normalMap_index].name)
					if self.pma[self.pme[mesh].matid[element].index].shadowMap_index > -1 and self.pma[self.pme[mesh].matid[element].index].shadowMap_index < texture_count:
						matList[mesh_index].setOcclTexture(textList[self.pma[self.pme[mesh].matid[element].index].shadowMap_index].name)


				vstride = int(self.pme[mesh].vert_buffer_size / self.pme[mesh].vert_count)
				fstride = int(self.pme[mesh].face_buffer_size / self.pme[mesh].face_count)
				if (element + 1) == self.pme[mesh].matid_count:
					vcount = self.pme[mesh].vert_count - self.pme[mesh].matid[element].vert_pos
				else:
					vcount = self.pme[mesh].matid[element + 1].vert_pos - self.pme[mesh].matid[element].vert_pos
				colList = []
				posList = []
				nrmList = []
				bWeList = []
				uv0List = []
				uv1List = []
				idxList = []
				if vcount > 0:
					colList = [NoeVec4] * vcount
					posList = [NoeVec3] * vcount
					nrmList = [NoeVec3] * vcount
					bWeList = [NoeVertWeight] * vcount
					uv0List = [NoeVec3] * vcount
					uv1List = [NoeVec3] * vcount
				for v in range(0, vcount):
					f.seek(self.pme[mesh].data_pos + (vertAdd * vstride) + (v * vstride), NOESEEK_ABS)
					vert = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
					norm = [float(f.readShort() / 32767.0), float(f.readShort() / 32767.0),
							float(f.readShort() / 32767.0), float(f.readShort() / 32767.0)]
					div = math.sqrt((norm[0] * norm[0]) + (norm[1] * norm[1]) + (norm[2] * norm[2]))
					norm = [norm[0] / div, norm[1] / div, norm[2] / div, norm[3]]
					uvw0 = [f.readHalfFloat(), f.readHalfFloat()]
					uvw1 = [0.0, 0.0]
					if vstride > 72:
						uvw1 = [f.readHalfFloat(), f.readHalfFloat()]
					colr = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
					boWe = [1.0, 0.0, 0.0, 0.0]
					boId = [0, 0, 0, 0]
					if vstride > 52:
						boWe = [f.readFloat(), f.readFloat(), f.readFloat(), f.readFloat()]
						boId = [f.readUByte(), f.readUByte(), f.readUByte(), f.readUByte()]
					f.seek(8, NOESEEK_REL)  # Tangents?
					posList[v] = NoeVec3((vert[0] * vert[3], vert[1] * vert[3], vert[2] * vert[3]))
					nrmList[v] = NoeVec3((norm[0], norm[1], norm[2]))
					uv0List[v] = NoeVec3((uvw0[0], uvw0[1], 0.0))
					uv1List[v] = NoeVec3((uvw1[0], uvw1[1], 0.0))
					bWeList[v] = NoeVertWeight(boId, boWe)
					colList[v] = NoeVec4((colr[0], colr[1], colr[2], 1.0))

				f.seek(self.pme[mesh].data_pos + self.pme[mesh].vert_buffer_size + (self.pme[mesh].matid[element].face_pos * fstride), NOESEEK_ABS)
				#  This Algo for reading the face strip was taken from
				#  one of chrrox's old maxscripts and adapted here

				StartDirection = -1
				FaceDirection = 1
				x = 0
				f1 = 1
				f2 = 2
				f3 = 3
				face_term = 0xFFFFFFFF
				StartDirection = -1
				if fstride == 1:
					f1 = f.readUByte()
					f2 = f.readUByte()
					face_term = 0xFF
				elif fstride == 2:
					f1 = f.readUShort()
					f2 = f.readUShort()
					face_term = 0xFFFF
				FaceDirection = StartDirection
				while True:
					if f.tell() >= (self.pme[mesh].data_pos + self.pme[mesh].vert_buffer_size + ((self.pme[mesh].matid[element].face_pos + self.pme[mesh].matid[element].face_count) * fstride)):
						break
					if fstride == 1:
						f3 = f.readUByte()
					elif fstride == 2:
						f3 = f.readUShort()
					if f3 == face_term:
						if fstride == 1:
							f1 = f.readUByte()
							f2 = f.readUByte()
						elif fstride == 2:
							f1 = f.readUShort()
							f2 = f.readUShort()
						FaceDirection = StartDirection
					else:
						FaceDirection *= -1
						if f1 != f2 and f2 != f3 and f3 != f1:
							if FaceDirection > 0:
								idxList.append(f1 - vertAdd)
								idxList.append(f3 - vertAdd)
								idxList.append(f2 - vertAdd)
							else:
								idxList.append(f1 - vertAdd)
								idxList.append(f2 - vertAdd)
								idxList.append(f3 - vertAdd)
						f1 = f2
						f2 = f3
				vertAdd += vcount
				mshList[mesh_index] = NoeMesh(idxList, posList, "mesh%03i" % mesh_index)
				if self.pme[mesh].name != "":
					mshList[mesh_index].setMaterial(self.pme[mesh].name)
				mshList[mesh_index].setMaterial(material_name)
				mshList[mesh_index].setIndices(idxList)
				mshList[mesh_index].setPositions(posList)
				mshList[mesh_index].setNormals(nrmList)
				mshList[mesh_index].setUVs(uv0List, 0)
				mshList[mesh_index].setUVs(uv1List, 1)
				#mshList[mesh_index].setColors(colList)
				mshList[mesh_index].setWeights(bWeList)
				if self.pme[mesh].boneid_count > 0:
					mshList[mesh_index].setBoneMap(self.pme[mesh].boneid)
				else:
					mshList[mesh_index].setBoneMap([self.pme[mesh].parent_id])
				mesh_index = mesh_index + 1
		return mshList, matList

def noepyLoadModel(data, mdlList):
	f = NoeBitStream(data, NOE_BIGENDIAN)
	if f.readUInt() != NOEPY_HEADER:
		return 0

	pmd = pmdfile()
	pta = ptafile()
	TexList = []
	MatList = []

	#  Check if there is a texture library
	filename = rapi.getInputName()
	filename = filename[:-3] + {'PMD': 'PTA'}[filename[-3:].upper()]
	if rapi.checkFileExists(filename):
		t = NoeBitStream(rapi.loadIntoByteArray(filename), NOE_BIGENDIAN)
		TexList = pta.create_image_list(t)
	pmd.read_pmd(f, len(data))
	BoneList = pmd.create_bone_list()
	MeshList, MatList = pmd.create_mesh_list(f, TexList)
	mdl = NoeModel()
	if showConsole: print("NumBones: " + str(len(BoneList)))
	mdl.setBones(BoneList)
	mdl.setMeshes(MeshList)
	mdl.setModelMaterials(NoeModelMaterials(TexList, MatList))
	mdlList.append(mdl)
	return 1

def noepyCheckType(data):
	if len(data) < 8:
		return 0
	f = NoeBitStream(data, NOE_BIGENDIAN)
	if f.readUInt() != NOEPY_HEADER:
		return 0
	return 1

def registerNoesisTypes():
	if showConsole == True:
		noesis.logPopup()
		for i in range(0, 30): print("\n")
	handle = noesis.register("The Idolm@aster: One For All (PS3)", ".pmd")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	return 1


```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-30T07:13:51+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

> Reply from mariokart64n ↑Thu Apr 30, 2020 7:59 am at Thu Apr 30, 2020 7:59 am
>
> I attempted to provide support but came to the conclusion Theo's Noesis script and format specification were incomplete.[...]

I found this topic and noticed that you guys probably made the same mistake Theo did, by not reading the mesh table and just reading the buffers straight through.There is a big difference between "making a mistake" and just being "uncomplete". 

(There's a whole bunch of "unknowns" in your script. Me, I wouldn't say this is a mistake, would I?  )

But if you think a "lack of knowledge" is a mistake, generally, I'd agree.
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-04-30T15:38:17+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

I don't understand your criticism of having variables named unknown? All the block structures are completely mapped to each respective class making  inspecting each variable possible. The fact is; you guys should have been more diligent and read the mesh table properly, your incompetence was not your lack of knowledge but rather your laziness.
## Post #10
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2020-05-10T13:37:16+00:00
- Post Title: [PS3] The iDOLM@STER One For All Model Format (.par) Help

Apparently the _SDW ambient occlusion maps sometimes may include object space normal maps in them, for outfits like both Leon's costumes and probably Miki's Nostalgia one.
[](https://ibb.co/8dFgrC0)
