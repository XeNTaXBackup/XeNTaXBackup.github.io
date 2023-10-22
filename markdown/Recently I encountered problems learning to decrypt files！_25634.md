## Post #1
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-07-22T22:38:53+00:00
- Post Title: Recently I encountered problems learning to decrypt files！

Today I'm unpacking a discontinued mobile game called: Ultra Kaiju Battle Breeder，All unpacked files are textAssets files！
I got the source code of cs by decompiling so, dat

```
{
	public class LoadedAssetBundle
	{
		public AssetBundle m_AssetBundle;

		public int m_ReferencedCount;

		public AssetBundle m_DecryptedAssetBundle;

		public LoadedAssetBundle(AssetBundle assetBundle)
		{
			//IL_0008: Expected I8, but got I4
			//IL_000f: Expected I4, but got I8
			long num = 1L;
			m_ReferencedCount = (int)num;
			m_AssetBundle = assetBundle;
			bool flag = Decrypt();
		}

		private bool Decrypt()
		{
			//Discarded unreachable code: IL_0053, IL_0057, IL_005d, IL_0074, IL_007b, IL_007e, IL_0082, IL_0086, IL_0089, IL_00b9, IL_00bf, IL_00e0
			//IL_0002: Expected I8, but got I4
			//IL_0007: Expected I8, but got I4
			//IL_0018: Expected O, but got I4
			//IL_0069: Expected I8, but got I4
			//IL_006c: Expected I8, but got I4
			//IL_007e: Expected I8, but got I4
			//IL_0089: Expected I8, but got I4
			//IL_0099: Expected O, but got I4
			//IL_00ab: Expected O, but got I4
			//IL_00c2: Expected I8, but got I4
			//IL_00cb: Expected I4, but got I8
			//IL_00db: Expected O, but got I4
			long num = 1L;
			if (num == 0L)
			{
			}
			long num2 = 0L;
			AssetBundle assetBundle = m_AssetBundle;
			if (num == 0L)
			{
			}
			bool flag = (UnityEngine.Object)0 != assetBundle;
			AssetBundle assetBundle2 = m_AssetBundle;
			if ((object)assetBundle2 == null)
			{
				throw new NullReferenceException();
			}
			TextAsset[] array = assetBundle2.LoadAllAssets<TextAsset>();
			if (array != null)
			{
				int ivcode = 25242;
				RijndaelManaged rijndael = AesCryptor.getRijndael(0, ivcode);
				throw new IndexOutOfRangeException();
			}
			AssetBundle decryptedAssetBundle = m_DecryptedAssetBundle;
			return (UnityEngine.Object)0 != decryptedAssetBundle;
		}
	}
}
```


guess using des encryption，I think the IV obtained by decompiling must be wrong

AesCryptor method from their custom method

```
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;
using System.Text;
using Cpp2IlInjected;
using UnityEngine;

namespace Network
{
	public class AesCryptor
	{
		public class Phrase
		{
			private StringBuilder builder;

			private string data;

			public static byte[] fqifiv
			{
				get
				{
					//IL_0002: Expected I8, but got I4
					//IL_0011: Expected I8, but got I4
					Encoding uTF;
					string text = default(string);
					do
					{
						long num = 0L;
						if (Singleton<T>.I() == null)
						{
							throw new NullReferenceException();
						}
						long num2 = 0L;
						uTF = Encoding.UTF8;
						if (text == null)
						{
							throw new NullReferenceException();
						}
						int length = text.Length;
					}
					while (uTF != null);
					throw new NullReferenceException();
				}
			}

			public static byte[] fqifkey
			{
				get
				{
					//IL_0002: Expected I8, but got I4
					//IL_000a: Expected I8, but got I4
					Encoding uTF;
					do
					{
						long num = 0L;
						uTF = Encoding.UTF8;
						long num2 = 0L;
						if (Singleton<T>.I() == null)
						{
							throw new NullReferenceException();
						}
					}
					while (uTF != null);
					throw new NullReferenceException();
				}
			}

			public Phrase()
			{
				//IL_0006: Expected I8, but got I4
				//IL_0019: Expected I8, but got I4
				//IL_0022: Expected I8, but got I4
				//IL_002e: Expected O, but got I8
				long num = 256L;
				builder = (StringBuilder)typeof(StringBuilder).TypeHandle;
				base._002Ector();
				long num2 = 0L;
				long num3 = default(long);
				if (Singleton<T>.I() == null)
				{
					num3 = 0L;
					throw new NullReferenceException();
				}
				string text = (data = ((UmbGetString)num3).getString_1_3());
			}

			private static int RotateBit(int value, short n)
			{
				throw new Cpp2IlInjected.AnalysisFailedException("CPP2IL failed to recover any usable IL for this method.");
			}

			public byte[] GetRandomCode16(int keycode)
			{
				//IL_0002: Expected I8, but got I4
				//IL_0004: Expected I8, but got I4
				//IL_000d: Expected I8, but got I4
				//IL_0015: Expected I4, but got I8
				//IL_0015: Expected I4, but got I8
				Encoding aSCII;
				do
				{
					long num = 0L;
					long num2 = 0L;
					aSCII = Encoding.ASCII;
					long num3 = 16L;
					string codeXXStr_ = GetCodeXXStr_((int)num2, (int)num3);
				}
				while (aSCII != null);
				throw new NullReferenceException();
			}

			public byte[] GetRandomCode32(int keycode)
			{
				//IL_0002: Expected I8, but got I4
				//IL_000b: Expected I8, but got I4
				//IL_0013: Expected I4, but got I8
				Encoding aSCII;
				do
				{
					long num = 0L;
					aSCII = Encoding.ASCII;
					long num2 = 32L;
					string codeXXStr_ = GetCodeXXStr_(keycode, (int)num2);
				}
				while (aSCII != null);
				throw new NullReferenceException();
			}

			public void GetRandomCode(int keycode, out byte[] _32, out byte[] _16)
			{
				//IL_0002: Expected I8, but got I4
				//IL_000b: Expected I8, but got I4
				//IL_0013: Expected I4, but got I8
				//IL_0024: Expected I4, but got O
				//IL_0027: Expected I8, but got I4
				//IL_0032: Expected I8, but got I4
				//IL_003b: Expected I4, but got I8
				//IL_004f: Expected I4, but got O
				long num = 0L;
				Encoding aSCII = Encoding.ASCII;
				long num2 = 32L;
				string codeXXStr_ = GetCodeXXStr_(keycode, (int)num2);
				if (aSCII == null)
				{
					throw new NullReferenceException();
				}
				System.Runtime.CompilerServices.Unsafe.As<byte[], byte>(ref _32).m_value = (byte)(int)aSCII;
				long num3 = 0L;
				Encoding aSCII2 = Encoding.ASCII;
				long num4 = 16L;
				string codeXXStr_2 = GetCodeXXStr_(keycode, (int)num4);
				if (aSCII2 == null)
				{
					throw new NullReferenceException();
				}
				System.Runtime.CompilerServices.Unsafe.As<byte[], byte>(ref _16).m_value = (byte)(int)aSCII2;
			}

			private string GetCodeXXStr_(int keycode, int x)
			{
				//IL_0012: Expected I8, but got I4
				//IL_0019: Expected I4, but got I8
				//IL_0037: Expected I4, but got I8
				//IL_003f: Expected I8, but got I4
				//IL_004e: Expected O, but got I8
				long num2 = default(long);
				StringBuilder stringBuilder4;
				do
				{
					StringBuilder stringBuilder = builder;
					if (stringBuilder == null)
					{
						throw new NullReferenceException();
					}
					long num = 0L;
					stringBuilder.Length = (int)num;
					StringBuilder stringBuilder2 = builder;
					string text = data;
					if (text == null)
					{
						throw new NullReferenceException();
					}
					char c = text.get_Chars((int)num);
					if (stringBuilder2 == null)
					{
						num2 = 0L;
						throw new NullReferenceException();
					}
					StringBuilder stringBuilder3 = ((StringBuilder)num2).Append(c);
					if (stringBuilder2 == null)
					{
						throw new NullReferenceException();
					}
					char c2 = ((string)(object)stringBuilder2).get_Chars((int)c);
					stringBuilder4 = builder;
					while (x != 0)
					{
					}
				}
				while (stringBuilder4 != null);
				throw new NullReferenceException();
			}
		}

		public static RijndaelManaged getRijndael()
		{
			byte[] fqifkey = Phrase.fqifkey;
			return getRijndael(Phrase.fqifiv, fqifkey);
		}

		public static RijndaelManaged getRijndael(int keycode, int ivcode)
		{
			//Discarded unreachable code: IL_0006, IL_000c
			throw new NullReferenceException();
		}

		public static RijndaelManaged getRijndael(byte[] key, byte[] iv)
		{
			//Discarded unreachable code: IL_0013, IL_0019, IL_001f, IL_0025, IL_002b, IL_0031, IL_0038, IL_003e
			if ((object)typeof(RijndaelManaged).TypeHandle == null)
			{
				throw new NullReferenceException();
			}
			return (RijndaelManaged)typeof(RijndaelManaged).TypeHandle;
		}

		public static byte[] EncryptBytes(SymmetricAlgorithm alg, byte[] message)
		{
			//Discarded unreachable code: IL_001e, IL_002a, IL_0031, IL_0033, IL_0045, IL_0048, IL_004b, IL_004e, IL_0055, IL_0058, IL_005c, IL_005f, IL_006f, IL_0072
			//IL_0002: Expected I8, but got I4
			//IL_0020: Expected I8, but got I4
			//IL_0033: Expected I8, but got I4
			//IL_004b: Expected I8, but got I4
			//IL_0058: Expected I8, but got I4
			//IL_005f: Expected I8, but got I4
			//IL_0062: Expected I8, but got I4
			//IL_0072: Expected I8, but got I4
			//IL_0075: Expected I8, but got I4
			while (true)
			{
				long num = 1L;
				if (message != null)
				{
					if (num == 0L)
					{
						break;
					}
					if (alg != null)
					{
						if ((object)typeof(CryptoStream).TypeHandle == null)
						{
							throw new NullReferenceException();
						}
						throw new NullReferenceException();
					}
					continue;
				}
				return (byte[])typeof(CryptoStream).TypeHandle;
			}
			return (byte[])typeof(CryptoStream).TypeHandle;
		}

		public static byte[] DecryptBytes(SymmetricAlgorithm alg, byte[] message)
		{
			//Discarded unreachable code: IL_0044, IL_00af, IL_00b8
			//IL_0028: Expected I8, but got I4
			//IL_003e: Expected I8, but got I4
			//IL_004f: Expected I8, but got I4
			//IL_005c: Expected I8, but got I4
			//IL_0062: Expected I8, but got I4
			//IL_0073: Expected I8, but got I4
			//IL_008e: Expected O, but got I4
			//IL_009d: Expected O, but got I4
			//IL_00a0: Expected I8, but got I4
			//IL_00a3: Expected I8, but got I4
			//IL_00a6: Expected I8, but got I4
			//IL_00a9: Expected I8, but got I4
			//IL_00b2: Expected I8, but got I4
			//IL_00c3: Expected I8, but got O
			if (message != null)
			{
				if (alg == null)
				{
					goto IL_00a6;
				}
				if ((object)typeof(CryptoStream).TypeHandle == null)
				{
					throw new NullReferenceException();
				}
				if ((object)typeof(MemoryStream).TypeHandle == null)
				{
					throw new NullReferenceException();
				}
				long num = 0L;
				int num2 = 154;
				if ((object)typeof(CryptoStream).TypeHandle != null)
				{
					if ((object)typeof(IDisposable).TypeHandle != null)
					{
						long num3 = 0L;
					}
					return (byte[])typeof(CryptoStream).TypeHandle;
				}
				long num4 = default(long);
				if (num != 0L)
				{
					num4 = 0L;
				}
				if (alg != null && (object)typeof(IDisposable).TypeHandle != null)
				{
					long num5 = 0L;
				}
				long num6 = default(long);
				if (num4 != 0L)
				{
					num6 = 0L;
				}
				if ((object)typeof(MemoryStream).TypeHandle != null)
				{
					if ((object)typeof(IDisposable).TypeHandle != null)
					{
						long num7 = 0L;
					}
					return (byte[])typeof(MemoryStream).TypeHandle;
				}
				if (num6 != 0L)
				{
					return (byte[])typeof(MemoryStream).TypeHandle;
				}
				string text = 0 + "Failed to decrypt:";
				if ((object)typeof(IDisposable).TypeHandle == null)
				{
				}
				Debug.LogWarning(0);
			}
			long num8 = 0L;
			long num9 = 1L;
			long num10 = 1L;
			goto IL_00a6;
			IL_00a6:
			long num11 = 0L;
			return (byte[])typeof(ArgumentNullException).TypeHandle;
		}
	}
}

```


Load Assetbundle into memory to get TextAssets, decrypt using Des, I am stuck on the decryption method now, I can only understand the code obtained by decompilation here...  

I'm just starting to look into decompiling and writing bms scripts，

I will upload so , dat and some resource files，Hope to help me, give me ideas！

[https://drive.google.com/file/d/1Qmsh8U ... sp=sharing](https://drive.google.com/file/d/1Qmsh8U49QshvElJD5VzfrPYcY9B5zoCt/view?usp=sharing)

Thanks again
