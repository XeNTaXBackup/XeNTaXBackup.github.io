## Post #1
- Username: iceS
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 04, 2022 8:23 pm
- Post datetime: 2022-12-16T10:12:03+00:00
- Post Title: Lord of Eternal Night (Unity) - decrypting assets

Game:Lord of Eternal Night
Download:[https://android.byfen.com/app/64079](https://android.byfen.com/app/64079)
The game is encrypted using AssetBundleEncryptStream
Curious what their decryption law is, how to get the key and offset？


Code:
AssetBundleEncryptStream:

```
	{
		private int _headLen;

		private byte[] _keys;

		private int _encryptLength;

		private byte[] _unityCodes;

		private int _keyLen;

		private int _count;

		private int _kindex;

		public AssetBundleEncryptStream(int headLen, byte[] keys, int encryptLength, string path, FileMode mode, FileAccess access, FileShare share, int bufferSize, bool useAsync)
		{

			RuntimeHelpers.InitializeArray(new byte[5], (RuntimeFieldHandle)/*OpCode not supported: LdMemberToken*/);
			if ((object)typeof(FileStream).TypeHandle == null)
			{
			}
			base._002Ector(path, mode, access, share, (int)mode, (byte)access != 0);
			_keys = keys;
			_headLen = headLen;
			_encryptLength = (int)typeof(FileStream).TypeHandle;
			_keyLen = (int)typeof(FileStream).TypeHandle;
		}

		public override int Read(byte[] array, int offset, int count)
		{

			int result = base.Read(array, offset, count);
			int count2 = _count;
			return result;
		}
	}
```


Encrypt：

```
	{
		private byte[] encryptResName;

		private int minLength;

		private int keylength;

		private int enlength;

		private int startEnd;

		private int enkeyPos;

		private int encryptLength;

		private int headLen;

		private byte[] _unityCodes;

		public void SetEncryptResKey(string name)
		{
			//Discarded unreachable code: IL_001b
			ByteArray byteArray = new ByteArray();
			byteArray.init();
			byteArray.writeStringNoLenth(name);
			MemoryStream stream = byteArray.stream;
		}

		public byte[] EncryptRes(byte[] data)
		{

			bool flag = CheckNeedEncryptRes(data);
			ByteArray byteArray = new ByteArray();
			byteArray.init();
			long num = 0L;
			byteArray.loadBytes(data, (int)num);
			int num2 = startEnd;
			BinaryReader reader = byteArray.reader;
			int num3 = keylength;
			enkeyPos = num3;
			int num4 = startEnd;
			BinaryReader reader2 = byteArray.reader;
			int num5 = enlength;
			byte[] array = encryptResName;
			encryptLength = num5;
			int num6 = startEnd;
			int num7 = encryptLength;
			int num8 = keylength;
			byte[] array2 = new byte[(object)data];
			byte[] array3 = encryptResName;
			long num9 = 0L;
			array3.CopyTo(array2, (int)num9);
			int num10 = keylength;
			long num11 = 0L;
			long num12 = 0L;
			int num13 = encryptLength;
			long num14 = 0L;
			int num15 = headLen;
			byte[] unityCodes = _unityCodes;
			throw new IndexOutOfRangeException();
		}

		public bool CheckNeedEncryptRes(byte[] data)
		{
			int num = headLen;
			long num2 = 1L;
			long num3 = 0L;
			throw new NullReferenceException();
		}

		public FileStream EncryptResByPath(string path)
		{
			
			long num = 0L;
			FileStream fileStream = File.OpenRead(path);
			byte[] data = new byte[0];
			bool flag = ((Encrypt)(object)fileStream).CheckNeedEncryptRes(data);
			byte[] array = new byte[1];
			byte[] array2 = new byte[1];
			long num2 = 0L;
			byte[] array3 = new byte[0];
			long num3 = 0L;
			array3.CopyTo(array3, (int)num3);
			long num4 = 0L;
			long num5 = 0L;
			if (fileStream == null)
			{
				return fileStream;
			}
			if (num5 != 0L)
			{
				long num6 = 0L;
			}
			return fileStream;
		}

		public Encrypt()
		{
			RuntimeHelpers.InitializeArray(new byte[5], (RuntimeFieldHandle)/*OpCode not supported: LdMemberToken*/);
		}
	}
```

GameLib_encrypt_EncryptWrap：

```
	{

		if ((object)typeof(ToLua).TypeHandle == null)
		{
		}
		long num = 2L;
		ToLua.CheckArgsCount((IntPtr)typeof(ToLua).TypeHandle, (int)num);
		long num2 = 1L;
		object obj = ToLua.CheckObject<T>((IntPtr)typeof(ToLua).TypeHandle, (int)num2);
		long num3 = 2L;
		string encryptResKey = ToLua.CheckString((IntPtr)obj, (int)num3);
		((Encrypt)obj).SetEncryptResKey(encryptResKey);
		long num4 = 0L;
		throw new NullReferenceException();
	}

	private static int EncryptRes(IntPtr L)
	{

		if ((object)typeof(ToLua).TypeHandle == null)
		{
		}
		long num = 2L;
		ToLua.CheckArgsCount((IntPtr)typeof(ToLua).TypeHandle, (int)num);
		object obj = ToLua.CheckObject<T>((IntPtr)typeof(ToLua).TypeHandle, (int)num);
		long num2 = 2L;
		byte[] data = ToLua.CheckByteBuffer((IntPtr)obj, (int)num2);
		byte[] array = ((Encrypt)obj).EncryptRes(data);
		ToLua.Push((IntPtr)array, array);
		long num3 = 1L;
		throw new NullReferenceException();
	}

	private static int CheckNeedEncryptRes(IntPtr L)
	{

		if ((object)typeof(ToLua).TypeHandle == null)
		{
		}
		long num = 2L;
		ToLua.CheckArgsCount((IntPtr)typeof(ToLua).TypeHandle, (int)num);
		long num2 = 1L;
		object obj = ToLua.CheckObject<T>((IntPtr)typeof(ToLua).TypeHandle, (int)num2);
		long num3 = 2L;
		byte[] array = ToLua.CheckByteBuffer((IntPtr)obj, (int)num3);
		bool flag = ((Encrypt)obj).CheckNeedEncryptRes(array);
		if ((object)typeof(LuaDLL).TypeHandle == null)
		{
		}
		LuaDLL.lua_pushboolean((IntPtr)typeof(LuaDLL).TypeHandle, (byte)(int)array != 0);
		long num4 = 1L;
		throw new NullReferenceException();
	}

	private static int EncryptResByPath(IntPtr L)
	{
		if ((object)typeof(ToLua).TypeHandle == null)
		{
		}
		long num = 2L;
		ToLua.CheckArgsCount((IntPtr)typeof(ToLua).TypeHandle, (int)num);
		long num2 = 1L;
		object obj = ToLua.CheckObject<T>((IntPtr)typeof(ToLua).TypeHandle, (int)num2);
		long num3 = 2L;
		string path = ToLua.CheckString((IntPtr)obj, (int)num3);
		FileStream fileStream = ((Encrypt)obj).EncryptResByPath(path);
		ToLua.PushObject((IntPtr)fileStream, fileStream);
		long num4 = 1L;
		throw new NullReferenceException();
	}
```


Tolua ：
[https://github.com/topameng/tolua](https://github.com/topameng/tolua)

game sample：
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/17Y5nUaQP8osWnFkNi-IvoTfeIZezsyd9?usp=share_link)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-16T12:26:58+00:00
- Post Title: Lord of Eternal Night (Unity) - decrypting assets

I don't know how it works, but I could guess how to decrypt it. It is an XOR of length 0x0D, except for the header, which is repeated. The header is definitely UnityFS~4.24f1, then the size information, so XOR with that first.

The data from 0x0A to 0x16 is a repeating xor key. The length varies from file to file, so you will have to adjust it yourself, but you should probably be able to decrypt with this. Every file I have tested has been successful.

*Edit
Example : role$101$models$101_equip_01.fbx.u
1E 5D 50 45 49 31 35 38 32 37 04 B0 0E 08 44 C3 08 10 31 35 38 32 37 04 B0 0E 08 44 C3 08 10 31 35 38 32 37 04 B0 0E 08 44 C3 08 10 31 35 38 32 37 04 B0 0E 08 44 C3 08 10 31 35 38 32 37 04 B0 0E 08 44 C3 08 10 31 35 38 32 37 04 B0 0E 08
The repeat key is 04 B0 0E 08 44 C3 08 10 31 35 38 32 37.
## Post #3
- Username: iceS
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 04, 2022 8:23 pm
- Post datetime: 2022-12-16T12:38:51+00:00
- Post Title: Lord of Eternal Night (Unity) - decrypting assets

There are tens of thousands of files, can you write a script for batch processing，thanks
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-16T12:59:51+00:00
- Post Title: Lord of Eternal Night (Unity) - decrypting assets

The important is perseverance. I have manually decrypted over 60,000 assets that I really needed. By the way, I don't know how you made il2cpp so readable code, is it cpp2il?

Incidentally, the total number of assets in this game is 13181, but not all of them seem to be encrypted, so the number of files that need to be decrypted is much smaller.
## Post #5
- Username: iceS
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 04, 2022 8:23 pm
- Post datetime: 2022-12-16T13:03:53+00:00
- Post Title: Lord of Eternal Night (Unity) - decrypting assets

Can you publish your decrypted assets，
I decompiled it using cpp2il，Decompilation to this degree is rare！
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-12-16T13:06:52+00:00
- Post Title: Lord of Eternal Night (Unity) - decrypting assets

For me, the assets of this game are not what I need, so I am not going to do the stones. If I knew the length of the key for each file, it would be easy. Good luck!
