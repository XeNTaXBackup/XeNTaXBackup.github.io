## Post #1
- Username: GarrodRain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 5:02 pm
- Post datetime: 2018-06-26T11:17:40+00:00
- Post Title: Unity AssetBundleManifest to hash/token.

I'm trying to figure out how to get a file list from a game (Jewel Princess) and i have figured out myself so far how to download the file list and browse through assets on my own, but my knowledge in unity (and programming in general) is a bit lackluster (i only really know lua and a the basics of javascript) and i feel i have hit a wall. I have asked around on other sections on the forum but no one replied so i assume it was either the wrong place to ask.

I download the file list, then extract it with AssetBundleExtractor, into a "Dump", which i decided to look at since the .dat is in hex and i have no idea what sort of program to run that through..
Anyway, from what i can tell there are 2 main arrays, one with names (as string) and the other with another array containing 16 "bytes" each. 

Each entry from what i can tell points to a file, on the server, i'm guessing the file itself is the hash value. When i do find a file (Via wireshark) and look inside them with unity studio, i did notice the containing file within (the CAB) is literally the hex of the string in MD4 with CAB- prefixed to it. However, what i want is the file itself so i can download them.

The file/hash is 32 characters long, which is what a MD4 or MD5 hash generally comes out to be, or the 16bytes array is when converted to hex, i have tried converting the array to hex, or md4'ing the array itself but it does not seem to go anywhere. to give  you an example of the entries

Array1:
[506]
    0 pair data
     0 int first = 506
     1 string second = "illust_cha_001000_1"
Array2:
[506]
    0 pair data
     0 int first = 506
     0 AssetBundleInfo second
      0 Hash128 AssetBundleHash
       0 UInt8 bytes[0] = 14
       0 UInt8 bytes[1] = 188
       0 UInt8 bytes[2] = 197
       0 UInt8 bytes[3] = 148
       0 UInt8 bytes[4] = 132
       0 UInt8 bytes[5] = 255
       0 UInt8 bytes[6] = 85
       0 UInt8 bytes[7] = 123
       0 UInt8 bytes[8] = 155
       0 UInt8 bytes[9] = 81
       0 UInt8 bytes[10] = 29
       0 UInt8 bytes[11] = 226
       0 UInt8 bytes[12] = 83
       0 UInt8 bytes[13] = 237
       0 UInt8 bytes[14] = 212
       0 UInt8 bytes[15] = 153
      0 set AssetBundleDependencies
       0 Array Array (0 items)
        0 int size = 0
which in theory should point to this file:
Filename:69298e14e2128c70979cdc33b450a28b
	contains:CAB-0bd5bdf7d2777b5dfd7153f3e66fd99c
the array, easier to copy : 14, 188, 197, 148, 132, 255, 85, 123, 155, 81, 29, 226, 83, 237, 212, 153

Also, i was given some hints by some guy who speaks another language but i don't particularly understand, something about some call stacks.
Common.InitAssetBundleManager(optional int callCount)
AssetBundleManager.Initialize(int assetBundleVersion)
AssetBundleManager.Initialize(string manifestAssetBundleName)
AssetBundleManager.LoadAssetBundle(string assetBundleName, optional bool isLoadingAssetBundleManifest)
AssetBundleManager.LoadAssetBundleInternal(string assetBundleName, bool isLoadingAssetBundleManifest)
HashAlgorithm.ComputeHash(byte[] buffer)

I was playing around with ComputeHash in C# but i could only get it to work with MD5 and the syntax was completely different, furthermore i have no idea how to run AssetBundleManager from within C# or if i can. 

The file list i am using is here:
rel-res1.sys.jewepri.com/AssetBundles/WebGL/d07fd1cd94690d65df46b9179684b305

Any form of help or pointers would be appreciated, if you could spare the time. Thanks.
