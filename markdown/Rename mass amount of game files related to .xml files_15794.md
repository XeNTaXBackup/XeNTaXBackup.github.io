## Post #1
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-01-27T20:09:00+00:00
- Post Title: Rename mass amount of game files related to .xml files

Hello, I am a foreigner, I am sorry for bad language and/or wrong topic.

I extracted all music files from The Witcher 3 but it seems that all files named as their ID from .xml file, the .xml file also contain filename related to its ID.
I need programmer to write a code, that will rename all files to their true name from .xml file. Could someone please help?
[Untitled.png](https://xentaxbackup.github.io/file/12316_Untitled.png)
## Post #2
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-27T20:56:12+00:00
- Post Title: Rename mass amount of game files related to .xml files

Could you please provide a part of that xml?
Anyway here is some untested code:

```
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Xml;
using System.Xml.Linq;

namespace FileRenamer
{
    class Program
    {
        static void Main(string[] args)
        {
            //var arguments = args;
           var arguments = new string[] { "soundbanksinfo.xml", "ogs"};

            if (arguments.Count() < 2)
            {
                Console.WriteLine("\nUsage: this.exe test.xml \"game\\musicfolder\\\"");
                Console.ReadLine();
                Environment.Exit(0x01);
            }
            var x = XDocument.Load(arguments[0]);
            var fileidpairs = x.Descendants("File")
                .ToArray()
                .Select(y =>new Tuple<int, string>(safeparseint(y.Attribute("Id").Value), y.Descendants("ShortName").First().Value));
            var files = Directory.GetFiles(arguments[1],"*.ogg");
            foreach (var fildescription in fileidpairs)
            {
                if (files.Any(z => Path.GetFileNameWithoutExtension(z) == fildescription.Item1.ToString()))
                {
                    var file = files.First(z => Path.GetFileNameWithoutExtension(z) == fildescription.Item1.ToString());
                    var destname = Path.GetDirectoryName(file) + "\\" +
                                   GetNonFileNameWithoutExtension(fildescription.Item2);
                    if (File.Exists(file))
                    {
                        File.Move(file, destname);
                    }
                }
            }
            
        }
        public static string GetNonFileNameWithoutExtension(string s)
        {
            return !s.Contains('\\') ? s : s.Substring(s.LastIndexOf('\\')+1);
        }

        public static int safeparseint(string i)
        {
            int res;
            if (int.TryParse(i, out res))
            {
                return res;
            }
            else
            {
                return 0;
            }
        }
    }
}

```

Edit: With a test xml this works for me.
## Post #3
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-01-28T06:08:33+00:00
- Post Title: Rename mass amount of game files related to .xml files

Here full .xml file: [http://rgho.st/657sy5qsV](http://rgho.st/657sy5qsV)
I am not a specialist, should I copy your code to the .bat file and run it?
## Post #4
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-28T17:34:56+00:00
- Post Title: Rename mass amount of game files related to .xml files

Its coded in c# you can either compile it yourself in visual studio or use this.
[https://www.dropbox.com/s/jhy9q2vzzi0oa ... r.exe?dl=0](https://www.dropbox.com/s/jhy9q2vzzi0oac5/FileRenamer.exe?dl=0)
## Post #5
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-01-28T18:58:03+00:00
- Post Title: Rename mass amount of game files related to .xml files

I am sorry, I don't want to be annoying, but I have installed Code::Blocks. So I might just compile your code above to .exe file and will it work for the .xml file I've provided?
Thank you for your help in any case!
## Post #6
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-28T19:57:18+00:00
- Post Title: Rename mass amount of game files related to .xml files

> Reply from oux
>
> I am sorry, I don't want to be annoying, but I have installed Code::Blocks. So I might just compile your code above to .exe file and will it work for the .xml file I've provided?
Thank you for your help in any case!
You can't compile c# code in Code::Blocks you need to install either Visual Studio or Monodevelop.
## Post #7
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-01-29T06:37:46+00:00
- Post Title: Rename mass amount of game files related to .xml files

I am doing something incorrect?
I put some .ogg files to "ogs" folder and renamed .xml file to test.xml, then I start FireRenamer.exe programm, but it shows the error:
[Untitled.png](https://xentaxbackup.github.io/file/12329_Untitled.png)
## Post #8
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-29T14:44:33+00:00
- Post Title: Rename mass amount of game files related to .xml files

Fixed some errors It should work now!

New code:

```
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Runtime.InteropServices;
using System.Security.Permissions;
using System.Text;
using System.Threading.Tasks;
using System.Xml;
using System.Xml.Linq;

namespace FileRenamer
{
    public class Filecombo
    {
        public int id;
        public string newname;

        public Filecombo(int i, string s)
        {
            id = i;
            newname = s;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            //var arguments = args;
            var arguments = new string[] { "soundbanksinfo.xml", "ogs"};
            Console.Title = "Witcher 3 Soundbanks renamer by traderain";
            Console.WriteLine("Please give the name of the xml eg.:soundbanks.xml!");
            arguments[0] = Console.ReadLine();
            if (!File.Exists(arguments[0]) || Path.GetExtension(arguments[0]) != ".xml")
            {
                Console.Clear();
                Console.WriteLine("Invalid file!");
                Console.ReadLine();
                Environment.Exit(0x01);
            }
            Console.WriteLine("Please give the name of the folder which contains the .ogg files! eg.: sounds");
            arguments[1] = Console.ReadLine();
            if (!Directory.Exists(arguments[1]))
            {
                Console.Clear();
                Console.WriteLine("Invalid filder!");
                Console.ReadLine();
                Environment.Exit(0x01);
            }
            if (arguments.Count() < 2)
            {
                Console.WriteLine("\nUsage: this.exe test.xml \"game\\musicfolder\\\"");
                Console.ReadLine();
                Environment.Exit(0x01);
            }
            var x = XDocument.Load(arguments[0]);
            var fileidpairs = x.Descendants("File").ToArray();
            var filecombolist = (from fileidpair in fileidpairs let id = safeparseint(fileidpair.Attribute("Id")?.Value) let name = GetNonFileNameWithoutExtension(fileidpair.Element("ShortName")?.Value) select new Filecombo(id, name)).ToList();
            var files = Directory.GetFiles(arguments[1],"*.ogg");
            int count = 0;
            foreach (var fildescription in filecombolist)
            {
                if (files.Any(z => Path.GetFileNameWithoutExtension(z) == fildescription.id.ToString()))
                {
                    var file = files.First(z => Path.GetFileNameWithoutExtension(z) == fildescription.id.ToString());
                    var destname = Path.GetDirectoryName(file) + "\\" +
                                   GetNonFileNameWithoutExtension(fildescription.newname);
                    if (File.Exists(file))
                    {
                        File.Move(file, destname);
                        count++;
                        Console.WriteLine("Renamed file! -> " + "ID: " + fildescription.id + " New name: " + fildescription.newname);
                    }
                }
            }
            Console.WriteLine("Done! Renamed " + count + " file(s).");
            Console.ReadKey();
        }
        public static string GetNonFileNameWithoutExtension(string s)
        {

            s = s ?? "";
            if (s.Contains('\\'))
            {
                s = s.Substring(s.LastIndexOf('\\') + 1,s.Length- (s.LastIndexOf('\\') + 1));
            }
            if (s.Length > 4 && s.Contains(".wav"))
            {
                s = s.Substring(0,s.Length-4);
                s += ".ogg";
            }

            return s;
        }

        public static int safeparseint(string i)
        {
            int res;
            if (int.TryParse(i, out res))
            {
                return res;
            }
            else
            {
                return 0;
            }
        }
    }
}

```
## Post #9
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-01-29T16:42:01+00:00
- Post Title: Rename mass amount of game files related to .xml files

Could you provide compiled .exe file please?
## Post #10
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-29T16:58:23+00:00
- Post Title: Rename mass amount of game files related to .xml files

> Reply from oux
>
> Could you provide compiled .exe file please?
Sure. [https://www.dropbox.com/s/5c4xlaig6as8b ... g.rar?dl=0](https://www.dropbox.com/s/5c4xlaig6as8bdb/Debug.rar?dl=0) (I zipped my whole folder so you can get an idea how my files are setup)
## Post #11
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-01-29T17:22:57+00:00
- Post Title: Rename mass amount of game files related to .xml files

Thank you very much, it works! 

I hope I will learn programming language some day, looking into C++.
## Post #12
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2017-01-29T18:36:20+00:00
- Post Title: Rename mass amount of game files related to .xml files

> Reply from oux
>
> Thank you very much, it works! 

I hope I will learn programming language some day, looking into C++.
Im glad I was able to help!   Have a nice day!
## Post #13
- Username: oux
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jan 28, 2017 3:45 am
- Post datetime: 2017-11-05T12:20:39+00:00
- Post Title: Rename mass amount of game files related to .xml files


## Post #14
- Username: sanderson169
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 04, 2022 1:24 am
- Post datetime: 2022-09-28T22:34:26+00:00
- Post Title: Rename mass amount of game files related to .xml files

Hi! I am super interested on this, idk if anyone can help me.
I have this BMS script, which does something similar to the tool you shared. I would like someone to help me add that if the file is not found in the XML FILE it leaves it WITHOUT A NAME.

```
# script type: parser
# note 1: all *.wem files must be in the same folder as this script and the txt
# note 2: script will maintain the original folder structure
#
# (c) by AlphaTwentyThree of Zenhax
# script for QuickBMS http://quickbms.aluigi.org

get EXT extension
if EXT == "xml"
	callfunction soundbanks 1
else
	print "script only for xml"
endif

startfunction soundbanks
	for i = 1
		FindLoc SEARCH string "<File Id="
		if SEARCH == ""
			cleanexit
		endif
		goto SEARCH
		getDstring DUMMY 10
		getCT DIDX string 0x22
		string DIDX += ".wem"
		getDstring TEST 3 # sometimes the file id tag is empty
		if TEST != " />"
			math SEARCH += 12
			goto SEARCH
			FindLoc SEARCH string "<Path>"
			goto SEARCH
			getDstring DUMMY 6
			getCT FNAME string 0x3c
			string FNAME -= 13
			open FDSE DIDX 1 EXIST
			if EXIST == 1
				get SIZE asize 1
				log MEMORY_FILE 0 0
				log MEMORY_FILE 0 SIZE 1
				string FNAME += ".wem"
				log FNAME 0 SIZE MEMORY_FILE
			endif
		endif
		math SEARCH += 12
		goto SEARCH
	next i
endfunction
```
