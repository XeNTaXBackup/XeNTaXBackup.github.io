## Post #1
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-15T16:40:11+00:00
- Post Title: Where can i learn about quickBMS scripts ?

I dont know aobut memories and all this numbers.
And i dont know about scripting in BMS.
I used once bms with a script that someone did here for a game thats it.

I know to code in c# but i guess you cant crack/hack games just with c#

What i want is to get the text/subtitles from the game Memento Mori 2 to extract the text out and then back in after translation.
So maybe i need to learn how to use BMS ? Im just not sure if learning it will be faster then the game release date in english.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-15T22:26:47+00:00
- Post Title: Where can i learn about quickBMS scripts ?

You can do almost anything with any programming language that is turing complete.

quickBMS would likely make it easier to unpack the archive, but if you're doing translation work then you likely won't be able to use it to re-pack and will end up rolling your own C# re-packer. Unless it has changed.

In any case learning the BMS language is just looking at the readme to see what kinds of commands are available and then picking up some archives with known specs and writing an unpacker based on the specs.

I mean, if you're using a BinaryReader in C# to read binary data and writing unpackers, it's the same idea.
Except you only need to define the structure and don't need to care about the actual parsing.
## Post #3
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-16T00:42:26+00:00
- Post Title: Where can i learn about quickBMS scripts ?

finale00 

I wish i could do it in c#
But im not sure how to use a binary reader and how to search for the current areas in the memory or in the files.

Is there any cample how to do it in c# ? 
I wish i could do it in c# and realy not to parse the text out but do it by define the structure.
Its just i dont have a clue how to do it how to start.

How do i read the files and how can i understand them and see the actual text of the language ?

sorry.
## Post #4
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-16T02:48:07+00:00
- Post Title: Where can i learn about quickBMS scripts ?

Im trying to use this code in c# but im not sure what it will do and im getting errors:

```
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.IO;

namespace WindowsFormsApplication1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();

            R();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        public void R()
        {
            using (var br = new System.IO.BinaryReader(File.Open(@"d:\MEMENTO2_loc_ge.res", FileMode.Open)))
            {
                // 2.
                // Position and length variables.
                int pos = 0;
                // 2A.
                // Use BaseStream.
                int length = (int)br.BaseStream.Length;
                while (pos < length)
                {
                    // 3.
                    // Read integer.
                    int v = br.ReadInt32();
                    textBox1.Text = v.ToString();

                    // 4.
                    // Advance our position variable.
                    pos += sizeof(int);
                }
            }
        }
    }
}

```


The error im getting is on the line: int v = br.ReadInt32();
The error is : Unable to read beyond the end of the stream

And if it will work later on im not sure what to do next and how to do it.


This is the complete exception error:


System.IO.EndOfStreamException was unhandled
  Message=Unable to read beyond the end of the stream.
  Source=mscorlib
  StackTrace:
       at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
       at System.IO.BinaryReader.ReadInt32()
       at WindowsFormsApplication1.Form1.R() in D:\C-Sharp\BinaryReader\WindowsFormsApplication1\WindowsFormsApplication1\Form1.cs:line 41
       at WindowsFormsApplication1.Form1..ctor() in D:\C-Sharp\BinaryReader\WindowsFormsApplication1\WindowsFormsApplication1\Form1.cs:line 19
       at WindowsFormsApplication1.Program.Main() in D:\C-Sharp\BinaryReader\WindowsFormsApplication1\WindowsFormsApplication1\Program.cs:line 18
       at System.AppDomain._nExecuteAssembly(RuntimeAssembly assembly, String[] args)
       at System.AppDomain.ExecuteAssembly(String assemblyFile, Evidence assemblySecurity, String[] args)
       at Microsoft.VisualStudio.HostingProcess.HostProc.RunUsersAssembly()
       at System.Threading.ThreadHelper.ThreadStart_Context(Object state)
       at System.Threading.ExecutionContext.Run(ExecutionContext executionContext, ContextCallback callback, Object state, Boolean ignoreSyncCtx)
       at System.Threading.ExecutionContext.Run(ExecutionContext executionContext, ContextCallback callback, Object state)
       at System.Threading.ThreadHelper.ThreadStart()
  InnerException:
## Post #5
- Username: ChocoladeBen
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 15, 2012 8:42 am
- Post datetime: 2012-08-16T02:53:31+00:00
- Post Title: Where can i learn about quickBMS scripts ?

I changed my code to this one im not getting errors and in the textBox1 the result im getting is: -1325399654 wich does not say anything to me. 
Im not sure what to do next if the result os logical or good ? Im far far far away from unpacking this .res file/s and get the text from there.

```
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.IO;

namespace WindowsFormsApplication1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();

            R();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        public void R()
        {
            using (var br = new System.IO.BinaryReader(File.Open(@"d:\MEMENTO2_loc_ge.res", FileMode.Open)))
            {
                // 2.
                // Position and length variables.
                //int pos = 0;
                // 2A.
                // Use BaseStream.
                int length = (int)br.BaseStream.Length;
                var count = br.BaseStream.Length / sizeof(int);
                for (var i = 0; i < count; i++)
                {
                    int v = br.ReadInt32();
                    textBox1.Text = v.ToString();
                }

            }
        }
    }
}

```
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-16T19:09:45+00:00
- Post Title: Where can i learn about quickBMS scripts ?

You need to first understand the file before you can actually parse it.
