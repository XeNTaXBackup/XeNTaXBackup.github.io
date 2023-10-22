## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-11-04T07:25:16+00:00
- Post Title: red alert iphone

I have uploaded the data files from Red Alert iPhone at
[http://www.cncmods.net/files/data.zip](http://www.cncmods.net/files/data.zip)
and
[http://www.cncmods.net/files/CnC_ROW.zip](http://www.cncmods.net/files/CnC_ROW.zip)
data.vfs seems to be the main data file, CnC_ROW.zip seems to be some other data files of unknown purpose.
Anyone know how to get into these? (data.vfs doesn't compress very much which suggests it already compressed)

EDIT: Files didnt upload properly, re-uploading now.
Will edit post again once they work
EDIT: Files uploaded properly now
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-04T17:24:51+00:00
- Post Title: red alert iphone

Simple extractor for VFS, with uncompression support. It does also add the extension to the PNG and the XML files.

```
import std.stream;
import std.string;
import std.system;
import std.path;
import std.algorithm;
import std.file;
import std.zlib;

/// Header of a VFS / FUFS container.
struct VFSHeader
{
    /// Magic = ASCII "FUFS".
    char[4] magic;

    /// Unknown.
    uint unknown;

    /// Number of VFSFile structs.
    uint nFiles;

    /// Read a VFSHeader from a stream.
    void read(Stream s)
    {
        s.readExact(magic.ptr, magic.length);
        s.read(unknown);
        s.read(nFiles);
    }
};

/// File entry of a VFS / FUFS container.
struct VFSFile
{
    /// Absolute offset of the file.
    uint offset;

    /// Unknown. Always greater, is close to 0 in the first entry, and close to 0xFFFFFFFF in the last.
    uint unknown;

    /// File size
    uint size;

    /// Read a VFSFile from a stream.
    void read(Stream s)
    {
        s.read(offset);
        s.read(unknown);
        s.read(size);
    }
}



int main(string[] args)

{
    scope Stream vfs;
    VFSHeader hdr;
    VFSFile[] files;

    // Check args
    if (args.length != 3)
    {
        writeln("Usage: RA_VFSExt input.vfs output_dir");
        return -1;
    }

    // Open & read VFS
    vfs = new EndianStream(new std.stream.File(args[1], FileMode.In), Endian.LittleEndian);

    hdr.read(vfs);
    files = new VFSFile[hdr.nFiles];
    foreach (ref f; files)
        f.read(vfs);

    // Extract VFS
    mkdir(args[2]);

    writeln("Index    Offset   Unknown  Size     Name");
    writeln("-----    ------   -------  ----     ----");
    foreach (idx, f; files)
    {
        string name = format("%d", idx);

        // Read contents
        byte[] data = new byte[f.size];
        vfs.position = f.offset;
        vfs.readExact(data.ptr, data.length);

        // Check compression
        if (data.startsWith("PLZP"))
        {
            uint unCmprSize, cmprSize;

            // Read header (HACK! Not working on big endian...)
            unCmprSize = *(cast(uint *)data + 1);
            cmprSize = *(cast(uint *)data + 2);

            // Uncompress data
            data = cast(byte[])uncompress(data[12 .. 12 + cmprSize], unCmprSize);
            assert(data.length == unCmprSize);

            name ~= "_nozlib";
        }

        // Guess extension
        if (data.startsWith(cast(byte[])"\x89PNG\r\n\x1A\n"))
            name = name.addExt("png");
        else if (data.startsWith("<?xml"))
            name = name.addExt("xml");
        else
            name = name.addExt("unk");

        // Extract
        scope Stream outFile = new std.stream.File(std.path.join(args[2], name), FileMode.OutNew);
        outFile.writeExact(data.ptr, data.length);

        writefln("%.8X %.8X %.8X %.8X %s", idx, f.offset, f.unknown, f.size, name);
    }


    return 0;

}


```
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-11-04T23:32:39+00:00
- Post Title: red alert iphone

Thanks, that works great.
The "unknown" field in the file structures seems to be some kind of hash of the file name.
Its not CRC32, its something else.
Don't know enough ARM assembly to figure it out.
