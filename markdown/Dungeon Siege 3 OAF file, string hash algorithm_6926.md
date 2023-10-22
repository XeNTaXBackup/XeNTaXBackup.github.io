## Post #1
- Username: supercolin
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 17, 2011 5:49 pm
- Post datetime: 2011-07-06T16:02:02+00:00
- Post Title: Dungeon Siege 3 OAF file, string hash algorithm

Finally  8) , get the string hash algorithm by decompile and analyze the assembly code of the game.

You may try the attached tool to calculate the hash.

For example, try this:

hash.exe global\strings\gui.std

the results is 4898FEB7, same as the one saved in data_localized_en.oaf.

C code as below. seed is always set to 0x2A in DS3.

DWORD hash(const char * string, unsigned int length, DWORD seed)
{
    char str[MAX_PATH] = {0};
    char *pstr = str;
    strcpy_s(pstr,MAX_PATH,string);

    unsigned int lengtToHandle = length;

    DWORD x = 0;
    DWORD y = 0;
    DWORD z = 0;

    x = length + seed - 0x21524111;
    y = length + seed - 0x21524111;
    z = length + seed - 0x21524111;

    while (*pstr != '\0')
    {
        if (*pstr == '\\')
            *pstr = '/';
        pstr++;
    }
    pstr = str;

    while(lengtToHandle > 0xC)
    {
        x += *pstr << 0x18;
        x += *(pstr + 0x1) << 0x10;
        x += *(pstr + 0x2) << 0x8;
        x += *(pstr + 0x3);

        y += *(pstr + 0x4) << 0x18;
        y += *(pstr + 0x5) << 0x10;
        y += *(pstr + 0x6) << 0x8;
        y += *(pstr + 0x7);

        z += *(pstr + 0x8) << 0x18;
        z += *(pstr + 0x9) << 0x10;
        z += *(pstr + 0xA) << 0x8;
        z += *(pstr + 0xB);

        x -= z;
        x = ((z << 0x4) | (z >> 0x1C)) ^ x;

        z += y;
        y -= x;
        y = ((x << 0x6) | (x >> 0x1A)) ^ y;

        x += z;
        z -= y;
        z = ((y << 0x8) | (y >> 0x18)) ^ z;

        y += x;
        x -= z;
        x = ((z << 0x10) | (z >> 0x10)) ^ x;

        z += y;
        y -= x;
        y = ((x << 0x13) | (x >> 0xD)) ^ y;

        x += z;
        z -= y;
        z = ((y << 0x4) | (y >> 0x1C)) ^ z;

        y += x;

        lengtToHandle -= 0xC;
        pstr += 0xC;
    }
    switch(lengtToHandle)
    {
        case 0xC:
            z += *(pstr + 0xB);
        case 0xB:
            z += *(pstr + 0xA) << 0x8;
        case 0xA:
            z += *(pstr + 0x9) << 0x10;
        case 0x9:
            z += *(pstr + 0x8) << 0x18;
        case 0x8:
            y += *(pstr + 0x7);
        case 0x7:
            y += *(pstr + 0x6) << 0x8;
        case 0x6:
            y += *(pstr + 0x5) << 0x10;
        case 0x5:
            y += *(pstr + 0x4) << 0x18;
        case 0x4:
            x += *(pstr + 0x3);
        case 0x3:
            x += *(pstr + 0x2) << 8;
        case 0x2:
            x += *(pstr + 0x1) << 0x10;
        case 0x1:
            x += *pstr << 0x18;
    }

    z = z ^ y;
    z = z - ((y << 0xE) | (y >> 0x12));

    x = x ^ z;
    x = x - ((z << 0xB) | (z >> 0x15));

    y = y ^ x;
    y = y - ((x << 0x19) | (x >> 0x7));

    z = z ^ y;
    z = z - ((y << 0x10) | (y >> 0x10));

    x = x ^ z;
    x = x - ((z << 0x4) | (z >> 0x1C));

    y = y ^ x;
    y = y - ((x << 0xE) | (x >> 0x12));

    z = z ^ y;
    z = z - ((y << 0x18) | (y >> 0x8));

    return z;
}
[hash.zip](https://xentaxbackup.github.io/file/4441_hash.zip)
