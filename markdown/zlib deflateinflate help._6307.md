## Post #1
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-27T07:13:14+00:00
- Post Title: zlib deflate/inflate help.

I wanna know how I can use zlib.dll to inflate a small stream. I feel like a complete noob, but for some reason I can't figure out how to call inflate...

I would also like to know how to call deflate and what properties I can edit (specifically what compression is used by the files with a 68 XX header).
## Post #2
- Username: BuC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 18, 2010 4:35 am
- Post datetime: 2011-03-31T04:38:44+00:00
- Post Title: zlib deflate/inflate help.

here is an example that i use in my app im developing, using Ionic.Zlib
this is splitting a file, compress each split, and rewriting the zlib header.
in my case the header is the length of the file -2 bytes.

```
        {
            Directory.CreateDirectory("temp");
            var save = new Reader(zoneLocation, Endian.Little, 0);
            save.Position = 0;
            int count = s1 / 65536; //s1 = zoneFile.Length Converted to Int32

            for (int i = 1; i <= count; i++)
            {
                byte[] cut = save.ReadBytes(65536);
                var write = new Writer("temp\\" + i + ".dat", FileMode.OpenOrCreate);
                write.Write(ZlibStream.CompressBuffer(cut));
                write.Close();
                var writeheader = new DJsIO("temp\\" + i + ".dat", DJFileMode.Open,
                                            EndianType.BigEndian);
                long head = writeheader.Length - 2;
                string hexValue = head.ToString("X");
                writeheader.Position = 0;
                writeheader.WriteHexString(hexValue);
                writeheader.Close();
                save.Position = 65536 * i;
            }

            save.Close();

            for (int s = 1; s <= count; s++)
            {
                File.Move("temp\\" + s + ".dat", "temp\\000" + s + ".dat");
            }

            string[] tmpFiles = Directory.GetFiles("temp\\", "*.dat");
            var outputFile = new FileStream("temp\\temp.dat", FileMode.OpenOrCreate, FileAccess.Write);
            string prevFileName = "temp.dat";

            foreach (string tempFile in tmpFiles)
            {
                string fileName = Path.GetFileNameWithoutExtension(tempFile);
                string baseFileName = fileName;
                int bytesRead = 0;
                var buffer = new byte[1024];
                var inputTempFile = new FileStream(tempFile, FileMode.OpenOrCreate, FileAccess.Read);

                while ((bytesRead = inputTempFile.Read(buffer, 0, 1024)) > 0)
                    outputFile.Write(buffer, 0, bytesRead);

                inputTempFile.Close();
            }

            outputFile.Close();

            File.Copy("temp\\temp.dat", "temp.dat", true);
            Directory.Delete("temp", true);
        }

```
## Post #3
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-02T00:56:28+00:00
- Post Title: zlib deflate/inflate help.

Where exactly is deflate being called? I can't see it.

EDIT: Thanks man I see it now, this is just what I needed.
