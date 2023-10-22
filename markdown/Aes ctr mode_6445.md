## Post #1
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-04-17T15:23:23+00:00
- Post Title: Aes ctr mode

Hello I 'm looking for a program that supports aes_128_ctr mode.

I tried quickbms but I get an "unsupported encryption/hashing type" with it. I also tried cbc and ecb modes, they both work fine with quickbms. Is there a different version of quickbms that supports ctr mode? Or someway to enable it?

Surely there's a program out there that supports ctr mode. Anydody know of any? 

Maybe there is some c/c++ code out there I can modify to fit my needs, Anyone know of any src?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-17T15:53:41+00:00
- Post Title: Aes ctr mode

it's a problem of Openssl that doesn't seem to support the CTR versions of the algorithms:
[http://stackoverflow.com/questions/3783 ... he-evp-api](http://stackoverflow.com/questions/3783311/openssl-is-it-possible-to-use-aes-ctr-mode-encryption-using-the-evp-api)

that's why in quickbms.c and in openssl\evp.h there is that "#if 0" which is used for debugging purpose.
I will investigate a bit this thing to know if there is a possibility of implementing it in any case in the next version.
## Post #3
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-04-17T23:41:13+00:00
- Post Title: Aes ctr mode

yeah I actually saw that page and looked at the src and noticed the  "#if 0" in quickbms.c and evp.h so I was hoping it could be implemented. 

I'm hoping in can because doing encryption/decryption with quickbms is really fast and easy. I'm going to look at ways to use this mode.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-18T09:24:39+00:00
- Post Title: Aes ctr mode

at a first look seems that the EVP mode doesn't support the CTR encryptions for some reasons.
EVP is cool because with some lines of code is possible to implement almost any encryption available in openssl.

so I guess that for the ctr ones I need to implement them one-by-one.
this is probably also the only solution to implement other algorithms that don't seem to exist in EVP like AES_ige_encrypt and AES_bi_ige_encrypt.

yeah it's bad but if it's only the only solution I can't say no :)
## Post #5
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2011-04-21T18:46:30+00:00
- Post Title: Aes ctr mode

sounds promising, but difficult. so were you able to get ctr mode working?

I figured out a workaround til I find a better solution. Ctr mode is like ecb mode but instead of crypting the plaintext it crypts the counter than xors the output block with the plaintext to get the ciphertext for each block.

A creative bms script might be able to do aes-ctr in ecb mode. what do you think?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-22T08:09:25+00:00
- Post Title: Aes ctr mode

I prefer the native implementation in quickbms instead of a bms script work-around.

at the moment I don't have idea how to implement this easily for all the algorithms not supported by the confortable EVP method, anyway it's in my TODO list for the next version.
