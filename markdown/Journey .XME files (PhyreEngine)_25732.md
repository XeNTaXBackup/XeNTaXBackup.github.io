## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2022-08-24T11:17:20+00:00
- Post Title: Journey .XME files (PhyreEngine)

Journey developed by Thagamecompany

Trying to localize this game but the files have compression. They seem to be a mix of huffman and lz.
Is possible that someone can have a look on them?

Thanks.
[JourneyXME-SAMPLES.7z](https://xentaxbackup.github.io/file/22684_JourneyXME-SAMPLES.7z)
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-25T16:03:27+00:00
- Post Title: Journey .XME files (PhyreEngine)

This uses a form of rolling cipher. The data is first cast to uint32s, then each uint32 is XOR'd by a key that is incremented by the previous encrypted value. This is symmetric so encryption uses the same process as decryption.

```
int rounds = (data.Length + 3) / 4;

uint key = 0x6341F337;

uint temp;
for (int i = 0; i < rounds; i++)
{
    temp = uint_ptr[i]; // store original encrypted value
    uint_ptr[i] ^= key; // decrypt by XOR'ing with key
    key += temp;        // add original encrypted value to key
}

```
## Post #3
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2022-09-07T00:58:01+00:00
- Post Title: Journey .XME files (PhyreEngine)

Thanks for the answer. It was quite helpful and it made it possible to create a tool to decipher and cipher back to work in the game.
Is now possible to translate some games that use this format.

It works on Journey and Flower.

Tool made by Mumm-Ra.
[jf-dec by Mumm-Ra.7z](https://xentaxbackup.github.io/file/22769_jf-dec by Mumm-Ra.7z)
