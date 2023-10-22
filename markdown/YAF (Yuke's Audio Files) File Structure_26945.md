## Post #1
- Username: WCG847
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 23, 2021 8:48 pm
- Post datetime: 2023-07-05T19:09:50+00:00
- Post Title: YAF (Yuke's Audio Files) File Structure

Hello!

Today, we are diving deep into the file structure of YAF (Yuke's audio files). The YAF file structure is intriguing, and it's essential to understand how it works. In this post, I will break down the file structure's components and explain how they function.

Offset 0X00 to 0X03 is the magic number, which is always SFAY. 0X04 to 0X07 is always 00 00 00 10. The purpose of this component is unknown, but it appears in every YAF file. From 0X08 to 0X17, the file name is stored. The file name is followed by 0X18 to 0X19, which represents the number of audio files in a YAF file.

0X1A to 0X2B serves an unknown purpose, and it remains constant for every YAF file. 0X2C to 0X2F might be a checksum or encoding-related component. The first byte increases by 8 is indicative of a progressive order. Moving on, 0X30 to 0X32 is the offset of the first audio file, which is always 20000 in hex.

The ID for YAF files is stored in 0X33 to 0X35. It is important to flip the bytes and convert them to decimals, where the last two bytes hold critical information. While 00 represents normal crowd, 10 represents face (cheer), and 20 represents heel (boo). Furthermore, the first two bytes for SVR 09+ represent the character ID, and one byte of SVR 08 represents the character ID as well. 

Finally, from 0X36 to 0X3A, we have the component that is most challenging to calculate - the size of the audio file. Here, you must flip the bytes and convert the byte sequence to an integer by adding each byte multiplied by 256 raised to the power of its position in the sequence. This action yields an integer, which represents the value represented by the little endian byte sequence. The converted byte sequence can now be represented in its proper unit.

To conclude, a thorough understanding of the YAF file structure is crucial for anyone looking to tinker with or modify audio files in SVR 08-10 games. The various components and their purposes within the file structure define how the audio files are structured and read by the games. This knowledge allows modders to extract, edit, and inject audio files to enhance and personalize their gameplay experience further. However it is important to note that while some YAF files in SVR 10 may have a similar file structure to their counterparts in SVR 08-09, others like those containing audio commentary do have a slightly different structure, making them more challenging to modify. In part 2, we will explore these differences in greater detail and provide specific techniques for handling and modifying YAF files containing audio commentary in SVR 10 games.

Thank you for reading, and I hope this post helps you understand the YAF file structure better, especially when it comes to audio file modding in SVR 08-10 games.
