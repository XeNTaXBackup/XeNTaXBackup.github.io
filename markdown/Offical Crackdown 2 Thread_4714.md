## Post #1
- Username: KIWIDOGGIE
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Jul 28, 2009 1:33 am
- Post datetime: 2010-07-05T14:14:11+00:00
- Post Title: Offical Crackdown 2 Thread

Since Crackdown 2 has so many darn formats, why create 50 threads for each one.

Here is what I have done so far.

PACK Files - They also contain the RIFX format which seems to be nothing but junk if you ask me...

```
        {
            public uint Offset;
            public uint Size;
            public uint Unknown;
        }
        public struct PackHeader
        {
            public string Magic; // PACK
            public byte[] Unknown; // Len16
            public uint numEntires; // Maybe NumberEntries - 1
            public byte[] Unknown2; // Len12
            public List<Entry> Entries;
        }

```


Here is my source code

```
using System.Collections.Generic;
using System.Windows.Forms;
using System.IO;
using EndianIO;
using System.Text;

namespace SoundExtractor
{
    class PackFile
    {
        public struct Entry
        {
            public uint Offset;
            public uint Size;
            public uint Unknown;
        }
        public struct PackHeader
        {
            public string Magic; // PACK
            public byte[] Unknown; // Len16
            public uint numEntires; // Maybe NumberEntries - 1
            public byte[] Unknown2; // Len12
            public List<Entry> Entries;
        }
        PackHeader head;
        EndianReader toc; // TOC file
        BinaryReader br; // PACK file
        public void Load(string _toc, string _br, ListView lst)
        {
            toc = new EndianReader(new FileStream(_toc, FileMode.Open, FileAccess.Read), EndianType.BigEndian);
            br = new BinaryReader(new FileStream(_br, FileMode.Open, FileAccess.Read));
            head = new PackHeader();
            head.Entries = new List<Entry>();
            lst.Items.Clear();
            head.Magic = toc.ReadAsciiString(4);
            if (head.Magic == "PACK")
            {
                head.Unknown = toc.ReadBytes(16);
                head.numEntires = toc.ReadUInt32();
                head.Unknown2 = toc.ReadBytes(12);
                for (uint i = 0; i < head.numEntires - 1; i++)
                {
                    Entry temp = new Entry();
                    temp.Offset = toc.ReadUInt32();
                    temp.Size = toc.ReadUInt32();
                    temp.Unknown = toc.ReadUInt32();
                    ListViewItem lvi = new ListViewItem();
                    lvi.Text = "PACK[" + i + "].raw";
                    lvi.SubItems.Add(temp.Size.ToString());
                    lst.Items.Add(lvi);
                    head.Entries.Add(temp);
                }
            }
            toc.Close();
            MessageBox.Show("Done");
        }

        public void Extract(string FileName, int Index)
        {
            BinaryWriter bw = new BinaryWriter(new FileStream(FileName, FileMode.Create, FileAccess.Write));
            br.BaseStream.Position = head.Entries[Index].Offset;
            bw.Write(br.ReadBytes((int)head.Entries[Index].Size));
            bw.Close();
            MessageBox.Show("Done");
        }
    }
}

```

EDIT: The above code only extracts the SOUND/AUDIO 'PACK' Files. This updated structure will give you extraction for all other pack files.

```
        {
            public string Magic; // PACK
            public byte[] Unknown; // Len8
            public uint numEntries;
            public byte[] Unknown1; // Len16
            public List<Entry> Entries;
        }

        struct Entry
        {
            public uint FileNameLen;
            public uint FileOffset;
            public uint FileLength;
            public int Unknown; // 0xDEDE
        }
```

My Program
[PACKExtractor.zip](https://xentaxbackup.github.io/file/3206_PACKExtractor.zip)
## Post #2
- Username: GXavs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 19, 2010 6:19 pm
- Post datetime: 2010-07-19T16:26:07+00:00
- Post Title: Offical Crackdown 2 Thread

The program seems to work, but what can I do with the files to play/convert them? I would really like to get the audio clips of the voice of the Agency talking.

Also, the program you have up for download doesn't seem to be the updated version that extracts non-audio files.
## Post #3
- Username: KIWIDOGGIE
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Jul 28, 2009 1:33 am
- Post datetime: 2010-07-20T00:21:38+00:00
- Post Title: Offical Crackdown 2 Thread

You need to recompile the source to use the second Pack header I posted. For some reason Crackdown 2 uses a ton of files.
## Post #4
- Username: GXavs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 19, 2010 6:19 pm
- Post datetime: 2010-07-20T04:37:31+00:00
- Post Title: Offical Crackdown 2 Thread

No idea how to play/convert the audio files then?
Everything I tried just gave me static.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-20T10:38:11+00:00
- Post Title: Offical Crackdown 2 Thread

its because its XMA.
## Post #6
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-07-21T22:28:03+00:00
- Post Title: Offical Crackdown 2 Thread

could you include the source files as im getting a few errors compiling this and i dont have the UI, thanks.
## Post #7
- Username: KIWIDOGGIE
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Jul 28, 2009 1:33 am
- Post datetime: 2010-07-22T00:24:36+00:00
- Post Title: Offical Crackdown 2 Thread

Source
[SoundExtractor.rar](https://xentaxbackup.github.io/file/3260_SoundExtractor.rar)
## Post #8
- Username: JORD4N
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 27, 2012 10:24 am
- Post datetime: 2012-04-27T02:32:20+00:00
- Post Title: Offical Crackdown 2 Thread

Any updates on this ? for all the files. so i can edit them
