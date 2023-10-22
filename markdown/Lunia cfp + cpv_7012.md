## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T03:28:01+00:00
- Post Title: Lunia cfp + cpv

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-04T15:37:09+00:00
- Post Title: Lunia cfp + cpv

the format is simple but the compression is unknown.
it looks at 99% lzma or lzma2 but it's not, blah
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-15T07:10:37+00:00
- Post Title: Lunia cfp + cpv

Found extractor but only source. Who can compile ? C#

```
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Runtime.InteropServices;
using System.Security.Cryptography;

namespace NewLuniaArchive
{
    class LuniaArchive
    {
        [DllImport("LZMA.dll", CallingConvention = CallingConvention.StdCall)]
        public static extern int LzmaUncompress(byte[] dest, ref int destLen, byte[] src, ref int srcLen, byte[] propData, int propSize);

        public class EntryChecksum
        {
            public String name;
            public String md5;
        }

        public class EntryHeader
        {
            public const UInt16 DirPath = 0x5044;
            public const UInt16 FilePath = 0x5046;

            public Int32 DirCount { get { if (type != DirPath) throw new Exception("A DirCount property is not valid for this object."); return val1; } }
            public Int32 FileCount { get { if (type != DirPath) throw new Exception("A DirCount property is not valid for this object."); return val2; } }

            public Int32 FileOffset { get { if (type != FilePath) throw new Exception("A FileOffset property is not valid for this object."); return val1; } }
            //public Int32 FileSize { get { if (type != FilePath) throw new Exception("A FileSize property is not valid for this object."); return val2; } } // not sure yet

            internal Int16 type;
            Int32 val1;
            Int32 val2;
            public String Name { get; set; }

            public bool IsFile { get { return type == FilePath; } }
            public bool IsDir { get { return type == DirPath; } }

            public EntryHeader parent;

            public EntryChecksum checksum;

            public EntryHeader()
            {
            }

            public EntryHeader(BinaryReader br)
            {
                type = br.ReadInt16();
                val1 = br.ReadInt32();
                val2 = br.ReadInt32();
                Int16 len = br.ReadInt16();
                if (len > 0)
                {
                    Name = Encoding.Unicode.GetString(br.ReadBytes(len * 2));
                }
            }
        }

        void Recurse(EntryHeader parent, BinaryReader br)
        {
            for (int x = 0; x < parent.DirCount; ++x)
            {
                EntryHeader e2 = new EntryHeader(br);
                if (e2.type != EntryHeader.DirPath)
                {
                    throw new Exception("Invalid entry type - DirPath expected.");
                }
                e2.parent = parent;
                entries.Add(e2);
                for (int y = 0; y < e2.DirCount; ++y)
                {
                    EntryHeader e3 = new EntryHeader(br);
                    if (e3.type != EntryHeader.DirPath)
                    {
                        throw new Exception("Invalid entry type - DirPath expected.");
                    }
                    e3.parent = e2;
                    entries.Add(e3);
                    Recurse(e3, br);
                }
                for (int y = 0; y < e2.FileCount; ++y)
                {
                    EntryHeader e5 = new EntryHeader(br);
                    if (e5.type != EntryHeader.FilePath)
                    {
                        throw new Exception("Invalid entry type - FilePath expected.");
                    }
                    e5.parent = e2;
                    entries.Add(e5);
                }
            }
            for (int x = 0; x < parent.FileCount; ++x)
            {
                EntryHeader e4 = new EntryHeader(br);
                if (e4.type != EntryHeader.FilePath)
                {
                    throw new Exception("Invalid entry type - FilePath expected.");
                }
                e4.parent = parent;
                entries.Add(e4);
            }
        }

        EntryHeader root_entry;
        List<EntryHeader> entries = new List<EntryHeader>();
        Dictionary<String, EntryChecksum> checksums = new Dictionary<String, EntryChecksum>();
        String m_basename;

        public byte[] Extract(EntryHeader entry)
        {
            using (FileStream fs = new FileStream(m_basename + ".cfp", FileMode.Open, FileAccess.Read))
            {
                using (BinaryReader br = new BinaryReader(fs))
                {
                    br.BaseStream.Position = entry.FileOffset;
                    Int32 decompressed_size = br.ReadInt32();
                    Int32 compressed_size = br.ReadInt32();
                    byte[] propData = br.ReadBytes(5);
                    byte[] compressed = br.ReadBytes(compressed_size);
                    byte[] decompressed = new byte[decompressed_size];
                    int result = LzmaUncompress(decompressed, ref decompressed_size, compressed, ref compressed_size, propData, 5);
                    if (result != 0)
                    {
                        throw new Exception(String.Format("LzmaUncompress returned error code {0}", result));
                    }
                    return decompressed;
                }
            }
        }

        public EntryHeader GetEntry(String name)
        {
            String[] parts = name.ToLower().Split(new char[] { '\\', '/' });
            EntryHeader p = null;
            EntryHeader e = null;
            int x = 0;
            for (int y = 0; y < parts.Length; ++y )
            {
                String part = parts[y];
                for (; x < entries.Count; ++x)
                {
                    e = entries[x];
                    if (p != null)
                    {
                        if (e.parent != p)
                            continue;
                    }
                    if (e.Name.ToLower() == part)
                    {
                        p = e;
                        break;
                    }
                    e = null;
                }
            }
            if (e != null)
            {
                e.checksum = checksums[name];
            }
            return e;
        }

        public List<String> GetFileNames()
        {
            List<String> names = new List<String>();
            foreach(var kvp in checksums)
            {
                if (kvp.Key.Length > 0 && kvp.Key[0] != '/')
                {
                    names.Add(kvp.Key);
                }
            }
            return names;
        }

        public void Load(String basename)
        {
            m_basename = basename;
            using (FileStream fs = new FileStream(m_basename + ".cfp", FileMode.Open, FileAccess.Read))
            {
                using (BinaryReader br = new BinaryReader(fs))
                {
                    Int16 type = br.ReadInt16();
                    Int64 magic = br.ReadInt64();
                    Int64 header_offset = br.ReadInt64();

                    if (type != 0x4150)
                    {
                        throw new Exception("Invalid archive type - 0x4150 expected.");
                    }

                    br.BaseStream.Position = header_offset;

                    root_entry = new EntryHeader(br);
                    Recurse(root_entry, br);
                }
            }
            using (FileStream fs = new FileStream(m_basename + ".cpv", FileMode.Open, FileAccess.Read))
            {
                using (BinaryReader br = new BinaryReader(fs))
                {
                    Int16 type = br.ReadInt16();
                    Int64 magic = br.ReadInt64();
                    Int32 count = br.ReadInt32();

                    if (type != 0x4649)
                    {
                        throw new Exception("Invalid archive type - 0x4649 expected.");
                    }

                    for (int x = 0; x < count; ++x)
                    {
                        EntryChecksum e = new EntryChecksum();

                        UInt16 len = br.ReadUInt16();
                        e.name = Encoding.Unicode.GetString(br.ReadBytes(len * 2), 0, len * 2);

                        len = br.ReadUInt16();
                        e.md5 = Encoding.ASCII.GetString(br.ReadBytes(len), 0, len);

                        checksums.Add(e.name.ToLower(), e);
                    }

                    long p = br.BaseStream.Length - br.BaseStream.Position;
                    if (p != 0)
                    {
                        throw new Exception(String.Format("There are {0} bytes left to parse.", p));
                    }
                }
            }
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            LuniaArchive archive = new LuniaArchive();

            archive.Load(Directory.GetCurrentDirectory() + "\\" + args[0]);
            String output = Directory.GetCurrentDirectory() + "\\" + args[1] + "\\" + args[0] + "\\";

            List<String> filenames = archive.GetFileNames();
            foreach (String filename in filenames)
            {
                try
                {
                    LuniaArchive.EntryHeader e = archive.GetEntry(filename);
                    if (e == null)
                    {
                        Console.WriteLine("Error: The file {0} could not be found in {1}!", filename, args[0]);
                        continue;
                    }
                    byte[] bytes = archive.Extract(e);
                    if (bytes == null)
                    {
                        Console.WriteLine("Error: The file {0} could not be extracted!", filename);
                        continue;
                    }
                    Directory.CreateDirectory(Path.GetDirectoryName(output + filename));
                    using (FileStream fs = new FileStream(output + filename, FileMode.Create, FileAccess.Write))
                    {
                        using (BinaryWriter bw = new BinaryWriter(fs))
                        {
                            bw.Write(bytes);
                            bw.Flush();
                        }
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine("There was an error processing {0}{1}{2}", filename, Environment.NewLine, ex);
                }
            }
        }
    }
}
```
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T11:16:04+00:00
- Post Title: Lunia cfp + cpv

I have made the script for quickbms based on that code:

```
# script for QuickBMS http://quickbms.aluigi.org

comtype lzma
open FDDE "cfp"
getdstring TYPE 2
get DUMMY longlong
get OFFSET longlong
goto OFFSET
set PATH string ""
set NAME string ""
math VAL1 = 0
math VAL2 = 0
callfunction ENTRY 1
callfunction EXTRACT

startfunction EXTRACT
    string PATH += NAME
    string PATH += /

    math FOLDERS = VAL1
    math FILES = VAL2
    for i = 0 < FOLDERS
        callfunction ENTRY 1
        callfunction EXTRACT
    next i
    for i = 0 < FILES
        callfunction ENTRY 1
        set FNAME string PATH
        string FNAME += NAME
        savepos TMP
        goto VAL1
        get SIZE long
        get ZSIZE long
        savepos OFFSET
        goto TMP
        math ZSIZE += 5
        clog FNAME OFFSET ZSIZE SIZE
    next i
endfunction

startfunction ENTRY
    getdstring TYPE 2
    get VAL1 long
    get VAL2 long
    get NAMESZ short
    math NAMESZ *- 2
    getdstring NAME NAMESZ
    set NAME unicode NAME
endfunction
```
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-15T13:47:09+00:00
- Post Title: Lunia cfp + cpv

Thanks aluigi
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-16T13:14:21+00:00
- Post Title: Lunia cfp + cpv

thanks a lot for support aluigi.
