## Post #1
- Username: QQyL
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 28, 2018 8:27 am
- Post datetime: 2018-11-28T00:50:10+00:00
- Post Title: Can I break my own format?

Hi guys, I am new on this community. I didn't write clearly open my question. I couldn't find where to write. This place seems to be appropriate.

I am developing a binary file format for my game. With the same method, even files such as pictures, music, zip can be added but yet I have not developed until that part. I want to try myself.

I will share the sample file with three messages. Messages are as follows

Thank you solve this
How to solve this bro?
I've just wondering

Let me talk a bit about the file format;

#Header
4bytes Signature
1byte Pad Byte
2bytes Version
4bytes Max Line Number (message count is 3)
1byte Header end

# Body (The following is for a message.)
4bytes part1 length
4bytes part2 length
1byte part1 start
(4bytes)*part1_length
1byte part1 end
1byte part2 start
(4bytes)*part2_length
1byte part2 end
2bytes new line

Trick: Part1 and Part2 data can be mixed to find and decode the encrypted data.

Download file: [https://uploadfiles.io/elojf](https://uploadfiles.io/elojf)

Thank you for interest.
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-10-15T10:32:38+00:00
- Post Title: Can I break my own format?

Here is a simple and very fast format. 
It's written in C++, it uses a full structure serialization (a memory imprint) with pointer fixups. This technique is used by many formats.
It's a super simple barebone format, where you can add many more features, boundaries are limitless.

```
    Some sample code made by Lukas Cone.
    I hereby place this code under the Public Domain.
    TL,DR: Use this however you want
*/
#include <fstream>
#include <vector>
#include <cstring>

struct Header
{
    int signature = 0x12345678;
    short version = 1;
    short numSentences = 0;
    char **sentences = nullptr;
};

Header *LoadFormat(const char *filePath)
{
    std::ifstream str(filePath, std::ios_base::binary | std::ios_base::in | std::ios_base::ate);

    if (str.fail())
        return nullptr;

    const size_t fileSize = str.tellg();
    char *buffer = static_cast<char*>(malloc(fileSize));

    str.seekg(0);
    //add testing for a signature
    str.read(buffer, fileSize);
    str.close();

    Header *hdr = reinterpret_cast<Header *>(buffer);

    hdr->sentences = reinterpret_cast<char**>(buffer + reinterpret_cast<intptr_t>(hdr->sentences));

    for (int s = 0; s < hdr->numSentences; s++)
        hdr->sentences[s] = buffer + reinterpret_cast<intptr_t>(hdr->sentences[s]);

    return hdr;
}

void SaveFormat(const char *filePath, const Header &hdr)
{
    std::ofstream str(filePath, std::ios_base::out | std::ios_base::binary);
    Header outHdr = hdr;

    outHdr.sentences = reinterpret_cast<char**>(sizeof(Header));
    str.write(reinterpret_cast<const char*>(&outHdr), sizeof(Header));

    const size_t savepos = str.tellp();
    std::vector<size_t> strLens;
    strLens.reserve(hdr.numSentences);

    str.seekp(sizeof(void*) * hdr.numSentences, std::ios_base::cur);

    for (int s = 0; s < hdr.numSentences; s++)
    {
        const size_t cStrSize = strlen(hdr.sentences[s]) + 1;
        str.write(hdr.sentences[s], cStrSize);
        strLens.push_back(cStrSize);
    }

    str.seekp(savepos);
    size_t lastOffset = savepos + sizeof(void*) * hdr.numSentences;

    for (auto &a : strLens)
    {
        str.write(reinterpret_cast<const char*>(&lastOffset), sizeof(void*));
        lastOffset += a;
    }

    str.close();
}

static char s1[] = "Thank you solve this";
static char s2[] = "How to solve this bro?";
static char s3[] = "I'm just wondering";
static char *sentences[] = {s1, s2, s3};

int main()
{
    Header test;

    test.numSentences = 3;
    test.sentences = sentences;

    SaveFormat("testing.f", test);

    Header *testInput = LoadFormat("testing.f");

    if (test.numSentences != testInput->numSentences)
        return 1;

    for (int s = 0; s < 3; s++)
        if (strcmp(test.sentences[s], testInput->sentences[s]))
            return 2;

    return 0;
}

```
