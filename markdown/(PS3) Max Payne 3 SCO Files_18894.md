## Post #1
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2018-10-05T20:54:34+00:00
- Post Title: (PS3) Max Payne 3 SCO Files?

Hello,

I need to find the key to open the .SCO files packed for Max Payne 3, PS3 version. Can someone please help me!?
I find the [source code for SCO ToolBox](https://www.gtagarage.com/mods/download.php?f=25035) in GTA Garage, and it works locating the key from GTA 4 and EFLC executables, so I tried to use the key used to open the .RPF files located in hte MP3 eboot.elf, and no luck, it is not the same key.

For your convenience, I packed together the GTA 4 executable, with Max Payne 3 eboot.elf (the decrypted executable for the PS3 version), and a sample .SCO file for the MP3 PS3. [Download here](https://drive.google.com/open?id=1cpkLHOpklf03A89H3ePK6Tbajk6DW6C4).

Here is the code used to open GTA 4 .SCO files:

```
                if ((key = Registry.LocalMachine.OpenSubKey(Key32)) != null ||
                    (key = Registry.LocalMachine.OpenSubKey(Key64)) != null)
                {
                    dir = key.GetValue(ValueName).ToString();
                    exe = "GTAIV.exe";
                }

                if ((key = Registry.LocalMachine.OpenSubKey(Key32E)) != null ||
                    (key = Registry.LocalMachine.OpenSubKey(Key64E)) != null)
                {
                    dir = key.GetValue(ValueName).ToString();
                    exe = "EFLC.exe";
                }
            }

            return FindKey(dir, exe);

            } catch { return null; }
        }

        private static byte[] FindKey(string gtaPath, string gtaExe)
        {
            gtaExe = Path.Combine(gtaPath, gtaExe);

            try {
                uint[] searchOffsets = {
                                       //EFIGS EXEs
                                       0xA94204 /* 1.0 */, 
                                       0xB607C4 /* 1.0.1 */, 
                                       0xB56BC4 /* 1.0.2 */,
                                       0xB75C9C /* 1.0.3 */,
                                       0xB7AEF4 /* 1.0.4 */,
                                        0xBE1370 /* 1.0.4r2 */,
                                        0xBE6540 /* 1.0.6 */,
                                       0xBE7540 /* 1.0.7 */,
                                       //Russian EXEs
                                       0xB5B65C /* 1.0.0.1 */,
                                       0xB569F4 /* 1.0.1.1 */,
                                       0xB76CB4 /* 1.0.2.1 */,
                                       0xB7AEFC /* 1.0.3.1 */,
                                       //Japan EXEs
                                        0xB8813C /* 1.0.1.2 */,
                                        0xB8C38C /* 1.0.2.2 */,
                                     0xBE6510 /* 1.0.5.2 */,
                                     //EFLC
                                       0xBEF028 /* 1.1.2 */,
                                       0xC705E0 /* 1.1.1 */,
                                       0xC6DEEC /* 1.1.0 */,
                                   };
                const string validHash = "DEA375EF1E6EF2223A1221C2C575C47BF17EFA5E";
                byte[] key = null;

                var fs = new FileStream(gtaExe, FileMode.Open, FileAccess.Read);

                foreach (var u in searchOffsets)
                {
                    if (u <= fs.Length - 32)
                    {
                        var tempKey = new byte[32];
                        fs.Seek(u, SeekOrigin.Begin);
                        fs.Read(tempKey, 0, 32);

                        var hash = BitConverter.ToString(SHA1.Create().ComputeHash(tempKey)).Replace("-", "");
                        if (hash == validHash)
                        {
                            key = tempKey;
                            break;
                        }
                    }
                }


```
