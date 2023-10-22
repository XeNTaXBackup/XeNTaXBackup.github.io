## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2013-11-14T05:37:38+00:00
- Post Title: Ys Online .bms request .Ysf file format

I found finally this game in a ftp link, and btw i found the next .cs for this file format but i want to ask if its posible made a .bms to extract this content.

.ysf file Sample Files
[http://www.mediafire.com/?glxc8xbx13783xv](http://www.mediafire.com/?glxc8xbx13783xv)

ysf.cs

```
using System.Collections.Generic;
using System.Text;
using System.IO;
using UnpackShell.Interfaces;
using System.ComponentModel.Composition;

namespace UnpackShell.Unpackers
{
    [Export(typeof(IUnpacker))]
    public class YSFUnpacker : IUnpacker
    {
        const string ID = "This is a YS-Online data file by 'YSO File System v0.1'\0";

        struct ArcEntry
        {
            public string Filename;
            public int Offset;
            public int Length;
        }

        public string GetName()
        {
            return "ys.ysf";
        }

        public string GetDescription()
        {
            return "Y's Online YSF file";
        }

        public string GetVersion()
        {
            return "1.0";
        }

        public UnpackerFlags GetFlags()
        {
            return UnpackerFlags.Experimental | UnpackerFlags.SupportsSubdirectories;
        }

        ArcEntry[] GetDirectory(Stream strm, bool CheckOnly)
        {
            byte[] buf = new byte[56];
            int numFiles;
            int DirOffset;
            BinaryReader rd;
            string id, name;
            ArcEntry[] result;

            rd = new BinaryReader(strm);

            rd.Read(buf, 0, 56);
            id = Encoding.ASCII.GetString(buf);
            if (id != ID)
                return null;

            DirOffset = rd.ReadInt32();
            if ((strm.Length - DirOffset) % 64 != 0)
                return null;

            numFiles = (int)(strm.Length - DirOffset) / 64;

            result = new ArcEntry[numFiles];
            if (CheckOnly)
                return result; // only need to return non-null here

            strm.Seek(DirOffset, SeekOrigin.Begin);
            for (int i = 0; i < numFiles; i++)
            {
                byte[] nameBuf = new byte[56];

                rd.Read(nameBuf, 0, 56);
                name = Encoding.ASCII.GetString(nameBuf);
                name = name.Substring(0, name.IndexOf('\0'));

                result[i].Filename = name;
                result[i].Offset = rd.ReadInt32();
                result[i].Length = rd.ReadInt32();
            }

            return result;
        }

        public bool IsSupported(Stream strm, Callbacks callbacks)
        {
            return GetDirectory(strm, true) != null;
        }

        public IEnumerable<FileEntry> ListFiles(Stream strm, Callbacks callbacks)
        {
            List<FileEntry> results = new List<FileEntry>();

            foreach (ArcEntry ae in GetDirectory(strm, false))
            {
                FileEntry fe = new FileEntry();
                fe.Filename = ae.Filename;
                fe.UncompressedSize = ae.Length;
                results.Add(fe);
            }

            return results;
        }

        public void UnpackFiles(Stream strm, Callbacks callbacks)
        {
            foreach (ArcEntry ae in GetDirectory(strm, false))
            {
                byte[] buf = new byte[ae.Length];
                strm.Seek(ae.Offset, SeekOrigin.Begin);
                strm.Read(buf, 0, ae.Length);
                callbacks.WriteData(ae.Filename, buf);
            }
        }

        public void PackFiles(Stream strm, List<PackFileEntry> filesToPack, Callbacks callbacks)
        {
            throw new NotImplementedException();
        }
    }
}

```
## Post #2
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-11-18T20:51:13+00:00
- Post Title: Ys Online .bms request .Ysf file format

Yeah, I wrote that code. I don't do BMS scripts though (simply because I have a very hard time understanding the confusing syntax... I mean "LOG" to write data a file? seriously?  ) so you have to either find someone else to convert it for you, or simply use the program from where you grabbed that code from to unpack the files for you (that's what it's there for)
## Post #3
- Username: jubadub
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 21, 2014 11:19 am
- Post datetime: 2014-10-21T04:19:44+00:00
- Post Title: Ys Online .bms request .Ysf file format

> Reply from Rimbros
>
> I found finally this game in a ftp link, and btw i found the next .cs for this file format but i want to ask if its posible made a .bms to extract this content.
Sorry I'm quite late, but could this be what you were looking for?

```
# Package: YSF
# by Fatduck Mar 2013
# script for QuickBMS http://quickbms.aluigi.org

idstring "This is a YS-Online data file by 'YSO File System v0.1'\0"
get OFSTBL long
get SIZETBL long
math ENDTBL = OFSTBL
math ENDTBL += SIZETBL
goto OFSTBL
do 
getdstring RESNAME 0x38
get OFSRES long
get SIZERES long
savepos OFSTBL
log RESNAME OFSRES SIZERES
while OFSTBL != ENDTBL
```


Obs.: lol, Call of "Sodium". XD

I found this code in a Chinese forum post, which you can view if you'd like (registering there is required to view it, though. It's feasible with Google Translate). Link to the post: [http://gameresearch.haotui.com/viewthread.php?tid=339](http://gameresearch.haotui.com/viewthread.php?tid=339)
As already written in the code, the code was done by "Fatduck", so all credit goes to him. I'm just pointing out his code.

Though, I personally just used Darkstar's code, compiled it with MS Visual Studio and ran it! (Thanks, Darkstar!)
Now the only issue I have is with the "data5.ysf" file and the many derived "data4.ysf" files, because it seems that those files aren't REAL .ysf files, but are actually RENAMED .zip files, which also are password-protected! (I think the chinese guy's post also says that, though. I didn't learn that from him, though, but from using both Darkstar's program and confirming it through "ZIP Password Unlocker", which admitted there being a password in the file, and its RAR counterpart, called "RAR Password Unlocker", not being able to find a password that was "expected of a RAR file's", so to speak.)

Because of the unknown password(s?), I couldn't extract those files. =| I tried brute-forcing with ZIP Password Unlocker, but I got up to 6 characters (as in, it's guaranteed to have a password of 6 characters or more) and still it wasn't enough, and my computer isn't good enough to go beyond that. I also tried brute-forcing with a mask, where I used just non-capital "a-z" characters and "0-9" (numbers). Got up to 7 characters, and that also didn't work.
It's also not the same password used to extract the .FSB files of the game (which contain the music AND sound files of the game), which was "tkdnsem000" (you may use FSB Extractor for this, I managed to discover the password through the help of a friend and especially through the help of a French person who had made another FSB-extracting program).

I tried reading some ZIP hacking guide I had found here, which had input from aluigi even, but I'm still too much of a rookie at this to manage something of that scale, at least as of today. =( The screenshots that served as the tutorial of that same guide are also all missing/were removed by ImageShack, as well, to my misfortune.

Anyone got any input that could serve as guidance? Regardlessly, thank you very much for reading all of this. :)


P.S.: Rimbros, would it be okay if you shared that FTP link with me, even if through only a PM? I guess that doesn't break the rules, since Ys Online is/was a game freely available and downloadable to all the public in the past, right?
I do have the game as I played it originally on 3 different servers out of existing 5 (Europe, Japan and Taiwan, although I missed China and Korea), but I'm always in search of different versions I may not have. And of course, if YOU would like, I'm more than interested in sharing those with you or anyone interested for that matter, as long as, again, it is alright with this forum. :) Else I'll just shut my trap on this subject. :X
## Post #4
- Username: hardeep15
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 11, 2020 2:26 pm
- Post datetime: 2020-01-11T06:40:23+00:00
- Post Title: Ys Online .bms request .Ysf file format

Norton offers support to install the software on the computer same way we, here at superb support offers [www.norton.com/setup](http://enter-norton.com) premium services to support the user to install Norton and other antivirus programs and other computer related issues.
