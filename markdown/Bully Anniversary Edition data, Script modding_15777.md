## Post #1
- Username: AIC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 09, 2016 10:05 pm
- Post datetime: 2017-01-23T09:23:32+00:00
- Post Title: Bully Anniversary Edition data, Script modding

This topic is about modding Bully Anniversary Edition.   

"main.11.com.rockstargames.bully.obb"
If you change the file's extension to zip, you can unzip them.

If you move modified file or script to "Android/data/com.rockstargames.bully" then the changes will be applied.

This is the C language source that decompiles xml file.

```
#include<stdlib.h>
#include<string.h>
#pragma warning(disable:4996)
unsigned char stringDecode[0x100];
char *stringCode = "6Ev2GlK1sWoCa5MfQ0pj43DH8Rzi9UnX";
const unsigned long magichash = 0x0ceb538d;

void initStringDecode();
void decode(char *str, char *decodestr, int *num);
void decode2(char *buffer, char *decodestr, int size);

void initStringDecode()
{
   int idx = 0;
   memset(stringDecode, 0, sizeof(stringDecode));
   do
   {
      *(stringDecode + stringCode[idx]) = idx;
      ++idx;
   } while (idx != 32);
}

void decode(char *str, char *decodestr, int *num)
{
   int s = 0;
   unsigned char v1;
   unsigned char dectable;
   int idx = 0;
   int cnt = 0;
   int l = strlen(str) - 2;
   int buf = l;
   int len = (5 * l >> 3);
   *num = len;
   memset(decodestr, 0, len);
   do
   {
      if (l <= cnt)
         buf = 0;
      else
         buf = str[cnt + 2];
      dectable = stringDecode[buf];
      //printf("%x\n", buf);
      switch (s)
      {
      case 3:
         v1 = 0;
         break;
      case 2:
         v1 = 0;
         dectable = 2 * dectable;
         break;
      case 1:
         v1 = 0;
         dectable = 4 * dectable;
         break;
      case 0:
         v1 = 0;
         dectable = 8 * dectable;
         break;
      case 7:
         v1 = 16 * dectable;
         dectable >>= 4;
         break;
      case 6:
         v1 = 32 * dectable;
         dectable >>= 3;
         break;
      case 5:
         v1 = dectable << 6;
         dectable >>= 2;
         break;
      case 4:
         v1 = dectable << 7;
         dectable >>= 1;
         break;
      default:
         v1 = 0;
         dectable = 0;
         break;
      }
      
      decodestr[idx] |= dectable;
      //printf("%x\n", dectable);
      if (l - 1 != idx)
         decodestr[idx + 1] |= v1;
      if ((unsigned int)(s + 5) <= 7)
         s += 5;
      else
      {
         idx++;
         s -= 3;
         if (idx == l)
            return;
      }
      
      cnt++;
   } while (l > cnt);

   decode2(decodestr, decodestr, *num);
}
void decode2(char *buffer,char *decodestr,int size)
{
   int i;
   char b;
   unsigned long m = magichash;
   unsigned int num = 0x12;
   for (i = 0; i < size; i++)
   {
      b = buffer[i];
      m = 0xab * (m % 0xb1) - 2 * (m / 0xb1);
      decodestr[i]=(b^num) + m;
      num += 6;
   }
}
int main(void)
{
   FILE *fp = fopen("C:\\Users\\Moon\\Desktop\\input.xml", "wb");
   FILE *fp1 = fopen("C:\\Users\\Moon\\Desktop\\output.txt", "rb");
   char *buff = (char *)malloc(0x1000000);
   char *arr = (char *)malloc(0x1000000);
   int sz;
   initStringDecode();
   memset(arr, 0, 0x1000000);
   fread(arr,0x1000000, 1, fp1);
   decode(arr, buff, &sz);
   fwrite(buff, sz, 1, fp);
}

```


This is an example of xml, msh, tex files.
Download : [http://www.mediafire.com/file/rkkerd4cp ... xample.zip](http://www.mediafire.com/file/rkkerd4cp6lk2l9/Example.zip)

Who made a xml compiler, please...
## Post #2
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2020-11-10T09:25:51+00:00
- Post Title: Bully Anniversary Edition data, Script modding

> Reply from AIC ↑Mon Jan 23, 2017 5:23 pm at Mon Jan 23, 2017 5:23 pm
>
> 
This topic is about modding Bully Anniversary Edition.   

"main.11.com.rockstargames.bully.obb"
If you change the file's extension to zip, you can unzip them.

If you move modified file or script to "Android/data/com.rockstargames.bully" then the changes will be applied.

This is the C language source that decompiles xml file.
Code: Select all#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#pragma warning(disable:4996)
unsigned char stringDecode[0x100];
char *stringCode = "6Ev2GlK1sWoCa5MfQ0pj43DH8Rzi9UnX";
const unsigned long magichash = 0x0ceb538d;

void initStringDecode();
void decode(char *str, char *decodestr, int *num);
void decode2(char *buffer, char *decodestr, int size);

void initStringDecode()
{
   int idx = 0;
   memset(stringDecode, 0, sizeof(stringDecode));
   do
   {
      *(stringDecode + stringCode[idx]) = idx;
      ++idx;
   } while (idx != 32);
}

void decode(char *str, char *decodestr, int *num)
{
   int s = 0;
   unsigned char v1;
   unsigned char dectable;
   int idx = 0;
   int cnt = 0;
   int l = strlen(str) - 2;
   int buf = l;
   int len = (5 * l >> 3);
   *num = len;
   memset(decodestr, 0, len);
   do
   {
      if (l <= cnt)
         buf = 0;
      else
         buf = str[cnt + 2];
      dectable = stringDecode[buf];
      //printf("%x\n", buf);
      switch (s)
      {
      case 3:
         v1 = 0;
         break;
      case 2:
         v1 = 0;
         dectable = 2 * dectable;
         break;
      case 1:
         v1 = 0;
         dectable = 4 * dectable;
         break;
      case 0:
         v1 = 0;
         dectable = 8 * dectable;
         break;
      case 7:
         v1 = 16 * dectable;
         dectable >>= 4;
         break;
      case 6:
         v1 = 32 * dectable;
         dectable >>= 3;
         break;
      case 5:
         v1 = dectable << 6;
         dectable >>= 2;
         break;
      case 4:
         v1 = dectable << 7;
         dectable >>= 1;
         break;
      default:
         v1 = 0;
         dectable = 0;
         break;
      }
      
      decodestr[idx] |= dectable;
      //printf("%x\n", dectable);
      if (l - 1 != idx)
         decodestr[idx + 1] |= v1;
      if ((unsigned int)(s + 5) <= 7)
         s += 5;
      else
      {
         idx++;
         s -= 3;
         if (idx == l)
            return;
      }
      
      cnt++;
   } while (l > cnt);

   decode2(decodestr, decodestr, *num);
}
void decode2(char *buffer,char *decodestr,int size)
{
   int i;
   char b;
   unsigned long m = magichash;
   unsigned int num = 0x12;
   for (i = 0; i < size; i++)
   {
      b = buffer[i];
      m = 0xab * (m % 0xb1) - 2 * (m / 0xb1);
      decodestr[i]=(b^num) + m;
      num += 6;
   }
}
int main(void)
{
   FILE *fp = fopen("C:\\Users\\Moon\\Desktop\\input.xml", "wb");
   FILE *fp1 = fopen("C:\\Users\\Moon\\Desktop\\output.txt", "rb");
   char *buff = (char *)malloc(0x1000000);
   char *arr = (char *)malloc(0x1000000);
   int sz;
   initStringDecode();
   memset(arr, 0, 0x1000000);
   fread(arr,0x1000000, 1, fp1);
   decode(arr, buff, &sz);
   fwrite(buff, sz, 1, fp);
}


This is an example of xml, msh, tex files.
Download : http://www.mediafire.com/file/rkkerd4cp ... xample.zip

Who made a xml compiler, please...

Did you find compiler? And where did you find that decompiler? ^^
