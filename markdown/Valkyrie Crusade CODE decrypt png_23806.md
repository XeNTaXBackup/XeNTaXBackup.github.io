## Post #1
- Username: UuPhan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-04-28T17:52:25+00:00
- Post Title: Valkyrie Crusade CODE decrypt png

Quickbms Script for Valkyrie Crusade decryption.
ID com.nubee.valkyriecrusade

```
typedef unsigned char   u8;
typedef unsigned int    u32;
 
static u32 secretKey = 0x45AF6E5D;
 
void Decrypt(u8* data, int data_size, int seed)
{
   u32* buffer = (u32*)(data);
   u32 xored_size = data_size / 4;
 
   if (xored_size > 0)
   {
      for (int i = 0; i < xored_size; i++)
      {
         buffer[i] = (buffer[i] ^ secretKey) - seed;
      }
   }
}
"
 
idstring "\x43\x4F\x44\x45\x00\x01\x55\x77"
get CRC32 long
get SEED long
get SIZE asize
math SIZE - 16
 
get NAME basename
string NAME + .png
log MEMORY_FILE 16 SIZE
calldll MEMORY_FILE10 "Decrypt" "tcc" RET MEMORY_FILE SIZE SEED
log NAME 0 SIZE MEMORY_FILE

```
