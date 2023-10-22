## Post #1
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2019-01-24T09:26:50+00:00
- Post Title: BF2 - BFP4F DFM Menu files

someone asked me about this, so I looked into it, its just a simple XOR encryption:

```
    {
        static byte[] key = { 0x0B, 0xAD, 0xF0, 0x0D };

        static void Main(string[] args)
        {
            if (args.Length != 1 || !File.Exists(args[0]))
            {
                ShowUsage();
                return;
            }
            byte[] input = File.ReadAllBytes(args[0]);
            for (int i = 0; i < input.Length; i++)
                input[i] ^= key[i % 4];
            string name = Path.GetFileNameWithoutExtension(args[0]);
            if (args[0].ToLower().Trim().EndsWith(".dfm"))
                name += ".swf";
            else
                name += ".dfm";
            File.WriteAllBytes(name, input);
        }

        static void ShowUsage()
        {
            Console.WriteLine("DFM Converter Tool by Warranty Voider");
            Console.WriteLine("Usage:");
            Console.WriteLine(" DFMTool filename[.swf|.dfm]");
            Console.WriteLine(" DFMTool input.dfm");
            Console.WriteLine(" DFMTool input.swf");
        }
    }
```


greetz
