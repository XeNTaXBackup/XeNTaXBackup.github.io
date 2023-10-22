## Post #1
- Username: iceS
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 04, 2022 8:23 pm
- Post datetime: 2022-11-04T12:58:32+00:00
- Post Title: How to test if Aes encryption key is correct

I get a conset16 bit sKey when I decompile a SO file, I would like to know how to edit the script to test if this key I found can decrypt the file
Because I didn't decompile the method, I want to test whether the regular method can be decrypted  :geek: 

this Key："250d7a1a2a9c7c09"

```

public class AES
{
	private static string sKey = "250d7a1a2a9c7c09";

	public static byte[] Encrypt(byte[] sSrc)
	{
		//Discarded unreachable code: IL_0022, IL_0025, IL_002c, IL_0046, IL_0054, IL_0057, IL_005d, IL_0064, IL_007f, IL_0085, IL_008b, IL_0091, IL_0097
		//IL_0002: Expected I8, but got I4
		//IL_0015: Expected I8, but got I4
		//IL_0021: Expected O, but got I8
		//IL_003b: Expected I8, but got I4
		//IL_0057: Expected I8, but got I4
		//IL_0067: Expected I8, but got I4
		long num = 1L;
		bool flag = WrappersManagerImpl.IsPatched(6360);
		int id = 6360;
		long num2 = 0L;
		return WrappersManagerImpl.GetPatch(id).__Gen_Wrap_192(num2);
	}

	public static byte[] Decrypt(byte[] encrypted)
	{
		//Discarded unreachable code: IL_0022, IL_0025, IL_002c, IL_0046, IL_0054, IL_0057, IL_005e, IL_0072, IL_008d, IL_0093, IL_0099, IL_009f, IL_00a5, IL_00ac, IL_00b5
		//IL_0002: Expected I8, but got I4
		//IL_0015: Expected I8, but got I4
		//IL_0021: Expected O, but got I8
		//IL_003b: Expected I8, but got I4
		//IL_0057: Expected I8, but got I4
		//IL_006b: Expected I8, but got I4
		//IL_0075: Expected I8, but got I4
		//IL_00af: Expected I8, but got I4
		long num = 1L;
		bool flag = WrappersManagerImpl.IsPatched(-1342177280);
		int id = 6338;
		long num2 = 0L;
		return WrappersManagerImpl.GetPatch(id).__Gen_Wrap_192(num2);
	}
}
```


I also found this one

```
using IFix;
using UnityEngine;

public class teset : MonoBehaviour
{
	public static string byteStream = "10, 30, 9, 0, 0, 0, 0, 0, 0, 8, 64, 21, 0, 0, -128, 64";

	public static byte[] ParseBytes()
	{
		throw new Cpp2IlInjected.AnalysisFailedException("CPP2IL failed to recover any usable IL for this method.");
	}

	public static string Byte2Str(byte[] bytes)
	{
		//Discarded unreachable code: IL_0020, IL_004a
		//IL_0013: Expected I8, but got I4
		//IL_001f: Expected O, but got I8
		//IL_0029: Expected I8, but got I4
		//IL_002c: Expected I8, but got I4
		//IL_0034: Expected I4, but got I8
		bool flag = WrappersManagerImpl.IsPatched(9640);
		int id = 9640;
		long num = 0L;
		return WrappersManagerImpl.GetPatch(id).__Gen_Wrap_114(num);
	}

	private void Start()
	{
		//Discarded unreachable code: IL_001c, IL_0023
		bool flag = WrappersManagerImpl.IsPatched(9641);
		WrappersManagerImpl.GetPatch(9641).__Gen_Wrap_2(this);
	}

	private void AES_Encrypt()
	{
		//Discarded unreachable code: IL_001e, IL_0021, IL_003a, IL_0047, IL_0066, IL_0131
		//IL_0002: Expected I8, but got I4
		//IL_004a: Expected I8, but got I4
		//IL_012b: Expected O, but got I4
		long num = 1L;
		bool flag = WrappersManagerImpl.IsPatched(9642);
		WrappersManagerImpl.GetPatch(9642).__Gen_Wrap_2(this);
	}
```



 testfile.zip
(240.44 KiB) Downloaded 13 times
