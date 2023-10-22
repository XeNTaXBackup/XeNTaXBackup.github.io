## Post #1
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2015-08-24T17:10:38+00:00
- Post Title: any way to export wav from unity

i try this  but somethink's wrong 

public static void ExportWAV(AudioClip audioClip, string wavFilename)
	{
	FileStream output = new FileStream(wavFilename, FileMode.Create);
	BinaryWriter binaryWriter = new BinaryWriter(output);
	binaryWriter.Write(Encoding.ASCII.GetBytes("RIFF"));
	binaryWriter.Write(LittleEndianBinary(36 + audioClip.samples * 2));
	binaryWriter.Write(Encoding.ASCII.GetBytes("WAVE"));
	binaryWriter.Write(Encoding.ASCII.GetBytes("fmt "));
	binaryWriter.Write(LittleEndianBinary(16));
	binaryWriter.Write(LittleEndianBinary(1));
	binaryWriter.Write(LittleEndianBinary(1));
	binaryWriter.Write(LittleEndianBinary(audioClip.frequency ));
	binaryWriter.Write(LittleEndianBinary(audioClip.frequency * 2));
	binaryWriter.Write(LittleEndianBinary(2));
	binaryWriter.Write(LittleEndianBinary(16));
	binaryWriter.Write(Encoding.ASCII.GetBytes("data"));
	binaryWriter.Write(LittleEndianBinary(audioClip.samples * 2));
	float[] array = new float[audioClip.samples];
	audioClip.GetData(array, 0);
	bool flag = false;
	float num = 0f;
	for (int i = 0; i < audioClip.samples; i++)
	{
	float num2 = array * 32767f;
	if (num2 > 32767f)
	{
	flag = true;
	num = Mathf.Max(num, num2 - 32767f);
	num2 = 32767f;
	}
	if (num2 < -32768f)
	{
	flag = true;
	num = Mathf.Max(num, -32768f - num2);
	num2 = -32768f;
	}
	short value = Convert.ToInt16(num2);
	binaryWriter.Write(LittleEndianBinary(value));
	}
	binaryWriter.Close();
	if (flag)
	{
	int num3 = Mathf.Min(Mathf.Abs(-32768), 32767);
	float num4 = num * 100f / ((float)num3 + num);
	Debug.LogWarning(string.Format("Sample overflow while exporting WAV: Reduce volume by about {0}% to avoid data loss!", num4));
	}
	}

	private static byte[] LittleEndianBinary(int value)
	{
	byte[] bytes = BitConverter.GetBytes(value);
	if (!BitConverter.IsLittleEndian)
	{
	Array.Reverse(bytes);
	}
	return bytes;
	}

	private static byte[] LittleEndianBinary(short value)
	{
	byte[] bytes = BitConverter.GetBytes(value);
	if (!BitConverter.IsLittleEndian)
	{
	Array.Reverse(bytes);
	}
	return bytes;
	}
