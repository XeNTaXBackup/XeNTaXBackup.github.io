## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-19T22:12:39+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

Ok, I hope someone can figure this out. I have attached the headers + resource info from three Flat Out 2 BFS files. 

I can extract the resources, but I do not know the filename encryption method. 

```
uint32   unknown
uint32   Offset of resource data (size of header + info)
uint32   Number of resources
uint32   Unknown1, but in the executable this is left shifted 3 times (*2*2*2) This value is the distance from the end of the current variable to what I believe is the filename encryption part. 
byte{Unknown1*8}    Unknown block
byte {n}    Filename encryption???
byte{Number of resources*18h)    Table with resource info

The table with resource info is like this:

uint32    Uncompressed? "false" = 5 bytes, "true" is 4 bytes. If compressed then Zlib!
uint32   Offset
uint32   Uncompressed size 
uint32    Compressed size (or uncompressed if no compression)
byte{8}    Unknown variables

```


Dear compression/encryption experts, I hope you can find out what the heck happens. There's a Flat Our 2 BFSUnpacker on the Internet, but no documentation.
[bfs_file_headers.zip](https://xentaxbackup.github.io/file/1276_bfs_file_headers.zip)
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-19T23:23:13+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

First off, this is less an encryption than a dictionary-based character-wise compression method.

So, the short answer: It's basically Huffman. 

The long answer (I haven't located the resource offsets now, but these are the necessary steps):

- Build the dictionary, starting with index 1 (probably from the block following the Unknown1 value, I'd assume): read a uint16, separate it into its high and low byte. If the low byte is 0x80, then the high byte is a plain character, addressed via the index value (a code word, to use Huffman terminology). Otherwise, continue recursively by building the dictionary for index * 2 first, and then index * 2 + 1, thus traversing a pure binary tree. The resulting tree will have characters in its leaf nodes, addressed by the appropriate index values (level-wise numbered nodes). You won't need to store the tree of course, just gather those code words and the matching characters.

- Uncompress the file name: There must be a compressed and an uncompressed size given somewhere and a buffer containing the compressed file name data. To uncompress the filename, you need to reconstruct the index values for the dictionary by reading the compressed buffer bit-wise (starting from the LSB at each byte). Start with a 1 as the initial value and append bits until you have reached a value that is contained in the dictionary. Emit the matching character, reset your code word to 1, repeat until you reach the end of the buffer.

None of the above has been tested, it might actually be completely wrong. Furthermore, I'm not a decompression genius either. I assume that you were talking about the unpacker found [here](http://forum.v5g.de/showthread.php?t=5284), which is fortunately written in Java and thus fodder for decompilers such as [JODE](http://jode.sourceforge.net/). 

So ... if you want to do a clean-room reimplementation, you'd better not follow the above links, but let me give a technical description instead (if the above is not enough to get you started).

Have fun!
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-20T05:42:54+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

Thanks for the link, I had another win32 unpacker, but this Java Code can help me a lot further I guess. I'm gonna take a good look !
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-20T06:46:37+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

Here's the decompiled Java Code for anyone who's interested- code from three classes. 

```
 * Visit http://jode.sourceforge.net/
 */
import java.io.DataInputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Hashtable;
import java.util.zip.DataFormatException;
import java.util.zip.Inflater;

import com.jcraft.jzlib.ZStream;

public class BfsUnpacker
{
    public static final char file = 'a';
    public static final String FILE = "c:/games/flatout2/fo2a.bfs";
    public static final String UNFILE = "fo2a";
    Hashtable dict;
    String filename;
    DataInputStream is;
    byte[] intBuf = new byte[4];
    int noOfFiles;
    int[] index;
    int[] values;
    FileEntry[] files;
    String[] filenames;
    int filePos;
    
    public BfsUnpacker(String filename) {
	((BfsUnpacker) this).filename = filename;
	open();
    }
    
    public static final int swabInt(int v) {
	return v >>> 24 | v << 24 | v << 8 & 0xff0000 | v >> 8 & 0xff00;
    }
    
    protected byte readByte() {
	byte i;
	try {
	    ((BfsUnpacker) this).filePos++;
	    i = ((BfsUnpacker) this).is.readByte();
	} catch (IOException e) {
	    e.printStackTrace();
	    return (byte) 0;
	}
	return i;
    }
    
    protected int readShort() {
	int i;
	try {
	    ((BfsUnpacker) this).filePos += 2;
	    int b1 = ((BfsUnpacker) this).is.readByte() & 0xff;
	    int b2 = ((BfsUnpacker) this).is.readByte() & 0xff;
	    i = b1 + b2 * 256;
	} catch (IOException e) {
	    e.printStackTrace();
	    return 0;
	}
	return i;
    }
    
    protected int readInt() {
	if (((BfsUnpacker) this).is == null)
	    return 0;
	int i;
	try {
	    ((BfsUnpacker) this).filePos += 4;
	    i = swabInt(((BfsUnpacker) this).is.readInt());
	} catch (IOException e) {
	    e.printStackTrace();
	    return 0;
	}
	return i;
    }
    
    int findIndex(int pos) {
	int min = 2147483647;
	int minid = 0;
	for (int i = 0; i < ((BfsUnpacker) this).index.length; i++) {
	    int p = ((BfsUnpacker) this).index[i];
	    if (p >= pos && p < min) {
		min = p;
		minid = i;
	    }
	}
	return minid;
    }
    
    int findFile(int pos) {
	int min = 2147483647;
	int minid = 0;
	for (int i = 0; i < ((BfsUnpacker) this).files.length; i++) {
	    FileEntry fe = ((BfsUnpacker) this).files[i];
	    if (fe.getOffset() >= pos && fe.getOffset() < min) {
		min = fe.getOffset();
		minid = i;
	    }
	}
	return minid;
    }
    
    String decrypt(byte[] buf, int off, int len) {
	Inflater inf = new Inflater();
	inf.setInput(buf);
	byte[] dec = new byte[buf.length];
	try {
	    inf.inflate(dec, off, len);
	} catch (DataFormatException e) {
	    System.out.println(e);
	    return null;
	}
	return new String(dec);
    }
    
    public void open() {
	ioexception = ioexception_3_;
	break while_1_;
    }
    
    private void readStrings() {
	int sp = ((BfsUnpacker) this).filePos;
	int length = readInt();
	int offset0 = readInt();
	int offset1 = readInt();
	int offset2 = readInt();
	int offset3 = readInt();
	int no1 = (offset1 - offset0) / 4;
	int[] positions = new int[no1 + 1];
	for (int i = 0; i < no1; i++) {
	    int j = readInt();
	    positions[i] = j;
	}
	positions[no1] = length - offset3;
	int no2 = (offset2 - offset1) / 2;
	int[] sizes = new int[no2];
	for (int i = 0; i < no2; i++) {
	    int size = readShort();
	    sizes[i] = size;
	}
	int no3 = offset3 - offset2;
	try {
	    ((BfsUnpacker) this).filenames = new String[no1];
	    ((BfsUnpacker) this).dict = new Hashtable();
	    buildDict(no3, 1);
	} catch (IOException ioexception) {
	    /* empty */
	}
	byte[] buf = new byte[255];
	try {
	    for (int i = 1; i < no1 + 1; i++) {
		int packsize = positions[i] - positions[i - 1];
		int unpacksize = sizes[i - 1];
		((BfsUnpacker) this).is.read(buf, 0, packsize);
		((BfsUnpacker) this).filePos += packsize;
		String fn = parseFilename(buf, packsize, unpacksize);
		((BfsUnpacker) this).filenames[i - 1] = fn;
	    }
	} catch (IOException e) {
	    e.printStackTrace();
	}
    }
    
    private void buildDict(int bytes, int key) throws IOException {
	int x = ((BfsUnpacker) this).is.readShort();
	((BfsUnpacker) this).filePos += 2;
	bytes -= 2;
	int v = x / 256;
	int t = x % 256;
	if (t == 128)
	    ((BfsUnpacker) this).dict.put(Integer.valueOf(key),
					  Character.valueOf((char) v));
	else {
	    buildDict(bytes, (key << 1) + 1);
	    buildDict(bytes, key << 1);
	}
    }
    
    private String parseFilename(byte[] buf, int packsize, int unpacksize) {
	String res = "";
	int pattern = 1;
	char lastFound = '\0';
	for (int i = 0; i < packsize; i++) {
	    int b = buf[i];
	    for (int j = 0; j < 8; j++) {
		int bit = (b & 0x1) == 1 ? 1 : 0;
		pattern <<= 1;
		pattern += bit;
		b >>= 1;
		if (pattern > 1
		    && ((BfsUnpacker) this).dict
			   .containsKey(Integer.valueOf(pattern))) {
		    res = new StringBuilder().append(res).append
			      ((Character) ((BfsUnpacker) this).dict
					       .get(Integer.valueOf(pattern)))
			      .toString();
		    pattern = 1;
		    lastFound = '\0';
		}
	    }
	}
	return res.substring(0, unpacksize);
    }
    
    public void close() {
	if (((BfsUnpacker) this).is != null) {
	    try {
		((BfsUnpacker) this).is.close();
	    } catch (IOException e) {
		e.printStackTrace();
	    }
	}
	((BfsUnpacker) this).is = null;
    }
    
    public void unpack(String dir) {
	int written = 0;
	long start = System.currentTimeMillis();
	File f = new File(dir);
	if (!f.exists())
	    f.mkdir();
	try {
	    for (int i = 0; i < ((BfsUnpacker) this).noOfFiles; i++) {
		int id = findFile(((BfsUnpacker) this).filePos);
		FileEntry fe = ((BfsUnpacker) this).files[id];
		String pathname
		    = new StringBuilder().append(dir).append("/").append
			  (((BfsUnpacker) this).filenames[fe.getDir()])
			  .toString();
		File path = new File(pathname);
		if (!path.exists())
		    path.mkdirs();
		String currFilename
		    = new StringBuilder().append(pathname).append("/").append
			  (((BfsUnpacker) this).filenames[fe.getFile()])
			  .toString();
		File fi = new File(currFilename);
		FileOutputStream fos = new FileOutputStream(fi);
		int toSkip = fe.getOffset() - ((BfsUnpacker) this).filePos;
		((BfsUnpacker) this).is.skipBytes(toSkip);
		((BfsUnpacker) this).filePos += toSkip;
		String type = "";
		if (fe.getType() == 5) {
		    int percent
			= (int) (100.0F
				 - ((float) fe.getPackedSize()
				    / (float) fe.getUnpackedSize() * 100.0F));
		    type = new StringBuilder().append("inflating ").append
			       (percent).append
			       ("%").toString();
		} else
		    type = "copying";
		System.out.print(new StringBuilder().append(currFilename)
				     .append
				     (" ").append
				     (type).append
				     (" ").toString());
		Inflater inf = new Inflater();
		int BUFSIZE = 4096;
		byte[] buf = new byte[BUFSIZE];
		byte[] dec = new byte[BUFSIZE];
		int bytesToRead = fe.getPackedSize();
		int steps = bytesToRead / BUFSIZE / 10;
		int step = steps;
		while (bytesToRead > 0) {
		    if (step == 0) {
			System.out.print(".");
			step = steps;
		    }
		    step--;
		    int currBytes = 0;
		    if (bytesToRead > BUFSIZE) {
			((BfsUnpacker) this).is.read(buf);
			((BfsUnpacker) this).filePos += buf.length;
			currBytes = buf.length;
			bytesToRead -= buf.length;
		    } else {
			((BfsUnpacker) this).is.read(buf, 0, bytesToRead);
			((BfsUnpacker) this).filePos += bytesToRead;
			currBytes = bytesToRead;
			bytesToRead = 0;
		    }
		    if (fe.getType() == 5) {
			inf.setInput(buf, 0, currBytes);
			int bytes = 10;
			try {
			    while (!inf.needsInput() && bytes > 0) {
				bytes = inf.inflate(dec);
				fos.write(dec, 0, bytes);
				written += bytes;
			    }
			} catch (DataFormatException e) {
			    System.out.print("crc error");
			} catch (IOException ioexception) {
			    /* empty */
			}
		    } else {
			fos.write(buf, 0, currBytes);
			written += currBytes;
		    }
		}
		System.out.println("ok");
		fos.close();
	    }
	} catch (FileNotFoundException e) {
	    e.printStackTrace();
	} catch (IOException e) {
	    e.printStackTrace();
	}
	long end = System.currentTimeMillis();
	float sec = (float) ((end - start) / 1000L);
	float kbps = (float) (written / 1024) / sec;
	System.out.println(new StringBuilder().append("...done! Read ").append
			       (((BfsUnpacker) this).filePos).append
			       (", wrote ").append
			       (written).append
			       (" bytes in ").append
			       ((int) sec).append
			       (" seconds (").append
			       (kbps).append
			       (" KB/sec)").toString());
    }
    
    public void list() {
	int pos = 0;
	for (int i = 0; i < ((BfsUnpacker) this).files.length; i++) {
	    FileEntry file = ((BfsUnpacker) this).files[i];
	    pos = file.getOffset() + 1;
	    System.out.println
		(new StringBuilder().append
		     (((BfsUnpacker) this).filenames[file.getDir()]).append
		     ("/").append
		     (((BfsUnpacker) this).filenames[file.getFile()]).append
		     (" ").append
		     (file.toString()).toString());
	}
    }
    
    static void CHECK_ERR(ZStream z, int err, String msg) {
	if (err != 0) {
	    if (z.msg != null)
		System.out.print(new StringBuilder().append(z.msg).append
				     (" ").toString());
	    System.out.println(new StringBuilder().append(msg).append
				   (" error: ").append
				   (err).toString());
	}
    }
    
    public static void main(String[] args) {
	System.out.println("Karoks bfsunpacker for flatout2, alpha1");
	if (args.length != 1) {
	    System.out.println("Usage: bfsunpacker2.bat <FILE.bfs>");
	    System.exit(1);
	}
	String file = args[0];
	File f = new File(file);
	if (!f.exists()) {
	    System.out.println(new StringBuilder().append("File ").append
				   (file).append
				   (" not found!").toString());
	    System.exit(2);
	}
	BfsUnpacker fo2Unpack2 = new BfsUnpacker(file);
	fo2Unpack2.unpack(".");
	fo2Unpack2.close();
    }
}


----


/* BitField - Decompiled by JODE
 * Visit http://jode.sourceforge.net/
 */

public class BitField
{
    public static final String TOP = "1";
    public static final String DOWN = "0";
    int value;
    int size;
    boolean[] bits;
    
    public BitField(int value) {
	this(value, 8);
    }
    
    public BitField(int value, int size) {
	((BitField) this).value = value;
	((BitField) this).size = size;
	((BitField) this).bits = new boolean[size];
	parse();
    }
    
    public void parse() {
	int v = ((BitField) this).value;
	for (int i = 0; i < ((BitField) this).size; i++) {
	    boolean set = false;
	    if ((v & 0x1) == 1)
		set = true;
	    ((BitField) this).bits[((BitField) this).size - i - 1] = set;
	    v >>= 1;
	}
    }
    
    public String toString() {
	String bit = "";
	for (int i = 0; i < ((BitField) this).size; i++) {
	    if (((BitField) this).bits[i])
		bit = new StringBuilder().append(bit).append("1").toString();
	    else
		bit = new StringBuilder().append(bit).append("0").toString();
	}
	return bit;
    }
    
    public int getValue() {
	return ((BitField) this).value;
    }
}

----
/* FileEntry - Decompiled by JODE
 * Visit http://jode.sourceforge.net/
 */

public class FileEntry
{
    int type;
    int offset;
    int unpackedSize;
    int packedSize;
    int dir;
    int file;
    int id;
    
    public String toString() {
	return new StringBuilder().append("type=").append
		   (((FileEntry) this).type).append
		   (" off=").append
		   (((FileEntry) this).offset).append
		   (" pack=").append
		   (((FileEntry) this).packedSize).append
		   (" unpack=").append
		   (((FileEntry) this).unpackedSize).append
		   (" u1=").append
		   (((FileEntry) this).dir).append
		   (" u2=").append
		   (((FileEntry) this).file).toString();
    }
    
    public int getId() {
	return ((FileEntry) this).id;
    }
    
    public void setId(int id) {
	((FileEntry) this).id = id;
    }
    
    public int getFile() {
	return ((FileEntry) this).file;
    }
    
    public void setFile(int file) {
	((FileEntry) this).file = file;
    }
    
    public int getType() {
	return ((FileEntry) this).type;
    }
    
    public void setType(int type) {
	((FileEntry) this).type = type;
    }
    
    public int getOffset() {
	return ((FileEntry) this).offset;
    }
    
    public void setOffset(int offset) {
	((FileEntry) this).offset = offset;
    }
    
    public int getUnpackedSize() {
	return ((FileEntry) this).unpackedSize;
    }
    
    public void setUnpackedSize(int unpackedSize) {
	((FileEntry) this).unpackedSize = unpackedSize;
    }
    
    public int getPackedSize() {
	return ((FileEntry) this).packedSize;
    }
    
    public void setPackedSize(int packedSize) {
	((FileEntry) this).packedSize = packedSize;
    }
    
    public int getDir() {
	return ((FileEntry) this).dir;
    }
    
    public void setDir(int dir) {
	((FileEntry) this).dir = dir;
    }
}

/* Test - Decompiled by JODE
 * Visit http://jode.sourceforge.net/
 */
import java.util.zip.DataFormatException;
import java.util.zip.Deflater;
import java.util.zip.Inflater;

public class Test
{
    public static void main(String[] args) {
	Deflater def = new Deflater();
	char[] chars = "dddxvon.ini".toCharArray();
	byte[] buf = new byte[chars.length];
	for (int i = 0; i < chars.length; i++) {
	    buf[i] = (byte) chars[i];
	    System.out.println(buf[i]);
	}
	def.setInput(buf);
	def.finish();
	byte[] buf2 = new byte[20];
	int packsize = def.deflate(buf2, 0, buf2.length);
	System.out.println(packsize);
	System.out.println(new String(buf2));
	Inflater inf = new Inflater();
	inf.setInput(buf2, 0, packsize);
	byte[] buf3 = new byte[20];
	try {
	    inf.inflate(buf3);
	    System.out.println(new String(buf3));
	} catch (DataFormatException e) {
	    e.printStackTrace();
	}
    }
}

```
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-20T13:36:24+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

I'm always amazed at the general quality of decompiled Java code. In this particular case, even local variable names were preserved during compilation, which of course makes the result even better.

Anyway, good luck!
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-20T14:49:37+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

> Reply from Deniz Oezmen
>
> I'm always amazed at the general quality of decompiled Java code.
I'm shocked.
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-07-20T14:56:38+00:00
- Post Title: Flat Out 2 - Filename Encryption/Compression

> Reply from Rheini
>
> I'm shocked.
Intriguing. Care to elaborate?
