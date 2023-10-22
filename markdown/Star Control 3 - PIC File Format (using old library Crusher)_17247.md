## Post #1
- Username: 0xdeadbeef
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 01, 2016 7:34 am
- Post datetime: 2017-11-05T03:01:01+00:00
- Post Title: Star Control 3 - PIC File Format (using old library Crusher)

Hi all

I am going to share the file format for all the PIC files in the old game Star Control 3.  These files are archives compressed using the old library Crusher! by David Cecil.

Here is a download link to crushers.dll:

[http://s000.tinyupload.com/?file_id=082 ... 7420998422](http://s000.tinyupload.com/?file_id=08211060657420998422)

SHA-256: F0E44B9F9FE5E4AF6A8B11A5F0AF65A11D696F0291721C4B2923ED84495A26D5

Here is some quick Python code showing how to use the DLL. This is a 32-bit DLL, so you will need a 32-bit Python installation. Unfortunately there isn't an easy way around this.

```

Interface to the long-defunct Crusher! compression library by David Cecil.

Initialize with the path to crushers.dll:

    crusher.init(dllpath)
    
Expand from a bytes object to another bytes object of specified size:

    result = crusher.expand(compressed_data, output_size)
    
Errors from crushers.dll will generally raise crusher.error.  However,
incorrect parameters to crusher.expand may cause access violations.

"""

import atexit
import ctypes

ERROR_FORMAT = '{}{} failed with error code {}'

class error(Exception):
    def __init__(self, msg):
        self.msg = msg
        
def _cxTry(func, *args):
    rc = func(*args)
    if rc != 0:
        raise error(ERROR_FORMAT.format(func.__name__, args, rc))
    
def expand(data, outputsize):
    _cxTry(_crusherdll.cxBuf2BufInit)
    outbuf = ctypes.create_string_buffer(outputsize)
    try:
        _cxTry(_expander, data, outbuf, outputsize, len(data))
    except:
        raise
    finally:
        _cxTry(_crusherdll.cxBuf2BufClose)
    return outbuf.raw
        
_crusherdll = None
_expander = None

def init(dllpath):
    global _crusherdll
    global _expander
    _crusherdll = ctypes.WinDLL(dllpath)
    _cxTry(_crusherdll.cxInit)
    _expander = _crusherdll.cxBuf2BufExpand
    _expander.argtypes = (
        ctypes.c_char_p, ctypes.c_char_p,
        ctypes.c_ulong, ctypes.c_ulong
    )
    atexit.register(_close)

def _close():
    _cxTry(_crusherdll.cxCleanup)

```


Here is pseudocode showing the format of the PIC files:

```
    int32_t offset;
    int32_t compressed_size;
    // Flags: 0 - normal file, 4 - cursor file, 0xffff - has palette patch, see below
    int16_t flags;
    // Drawing offsets:
    int16_t x, y;
    // Uncompressed size is w * h
    int16_t w, h;
    int16_t alwayszero;
};

// Header:
int16_t filecount;
fileinfo_t directory[filecount];

// The rest of the archive is the packed file data.

// Files with a palette patch have this format:
int16_t first_color;
int16_t palette_patch_size;
char palette_patch[palette_patch_size];
char compressed_data[fileinfo.compressed_size - 4 - palette_patch_size];

```


Hopefully this post is useful to anyone who wants to play around with this old game, or has something else compressed with Crusher.
## Post #2
- Username: Zardas81
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 27, 2017 4:57 am
- Post datetime: 2019-04-16T16:25:04+00:00
- Post Title: Star Control 3 - PIC File Format (using old library Crusher)

Played around with this a bit, and made a QuickBMS script. This takes .PIC files and outputs all images found in them as separate PPM files. Still needs some work (paletted files work fine, the rest not so much), but since the things I was looking for (full size pictures of the alien species) don't seem to be in these files, I'm not really interested in developing this further. But perhaps it'll be useful to someone.

Requires [crushers.dll](http://www.download-dll.com/dll-crushers.dll.html) to be in the same folder.

```
# script for QuickBMS http://quickbms.aluigi.org

# MEMORY_FILE: compressed data buffer
# MEMORY_FILE2: decompressed data buffer
# MEMORY_FILE3: image palette data
# MEMORY_FILE10: output 24-bit truecolor image

get FILES short

for i = 0 < FILES
	get OFFSET long
	get ZSIZE long
	get FLAGS short
	get X short
	get Y short
	get WIDTH short
	get HEIGHT short
	xmath SIZE "WIDTH * HEIGHT"
	get UNKNOWN short

	print "Offset: %OFFSET% Zsize: %ZSIZE% Size: %SIZE% Flags: %FLAGS|2h% X:%X% Y:%Y% W:%WIDTH% H:%HEIGHT%"

	# some files are 0x0, deleted file?
	if SIZE == 0
		continue
	endif
	
	# 0 - normal file, 4 - cursor file, 0xFF00 - has palette
	# TODO handle 0 and 4
	if FLAGS == 0xFF00
		# read palette data
		savepos POS
		goto OFFSET
		get FIRST_COLOR short # TODO does this do anything?
		get PALETTE_SIZE short
		savepos PALETTE_OFFSET
		log MEMORY_FILE3 PALETTE_OFFSET PALETTE_SIZE
		print "Palette size: %PALETTE_SIZE% First color: %FIRST_COLOR|h%"
		goto POS
		
		# the image data offset is now at the end of the palette data
		xmath OFFSET "OFFSET + 4 + PALETTE_SIZE"
	endif

	if ZSIZE == SIZE
		# image is stored
		log MEMORY_FILE2 OFFSET SIZE
	else
		# read compressed image data
		log MEMORY_FILE OFFSET ZSIZE

		# init decompression buffer
		log MEMORY_FILE2 0 0
		putvarchr MEMORY_FILE2 SIZE 0
		calldll "crushers.dll" "cxBuf2BufInit" cdecl RET
		
		# perform decompression
		calldll "crushers.dll" "cxBuf2BufExpand" cdecl RET MEMORY_FILE MEMORY_FILE2 SIZE ZSIZE

		# clean up
		calldll "crushers.dll" "cxBuf2BufClose" cdecl RET
	endif
	
	# init output PPM in memory
	get FN filename
	string FN P "%FN%_%i%_%WIDTH%x%HEIGHT%_%X%,%Y%.ppm"
	log MEMORY_FILE10 0 0
	
	# PPM header
	putct "P6" string -1 MEMORY_FILE10
	put 0x0A byte MEMORY_FILE10
	putct WIDTH string -1 MEMORY_FILE10
	put 0x20 byte MEMORY_FILE10
	putct HEIGHT string -1 MEMORY_FILE10
	put 0x0A byte MEMORY_FILE10
	# palettes are 6 bit per channel
	if FLAGS == 0xFF00
		putct 64 string -1 MEMORY_FILE10
	else
		putct 256 string -1 MEMORY_FILE10
	endif
	put 0x0A byte MEMORY_FILE10

	# convert image data to RGB
	goto 0 MEMORY_FILE2
	for j = 0 < SIZE
		get PIXEL byte MEMORY_FILE2
		
		if FLAGS == 0xFF00
			math PIXEL * 3
			goto PIXEL MEMORY_FILE3
			get PIXEL_R byte MEMORY_FILE3
			get PIXEL_G byte MEMORY_FILE3
			get PIXEL_B byte MEMORY_FILE3
					
			put PIXEL_R byte MEMORY_FILE10
			put PIXEL_G byte MEMORY_FILE10
			put PIXEL_B byte MEMORY_FILE10
		else
			# TODO figure out actual palette, using grayscale atm
			put PIXEL byte MEMORY_FILE10
			put PIXEL byte MEMORY_FILE10
			put PIXEL byte MEMORY_FILE10
		endif
	next j

	# write PPM to file
	savepos PPMSIZE MEMORY_FILE10
	log FN 0 PPMSIZE MEMORY_FILE10
next i

```
