## Post #1
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2014-06-07T00:27:52+00:00
- Post Title: Dynasty Warriors 8 PC saves, which encryption?

This might be a strange request since i don't actually need help cracking the encryption. I already know HOW to decrypt them in theory by debugging the shit out of the game.
The problem is i have not a single clue about hashes/encryptions (polynomials? ivecs? what???) so i don't know what encryption i'm actually looking at.

The file consists of 2 bytes of hashsum, 2 bytes of an encryption fileseed, 0xB7F44 bytes of encrypted data and 1 more sanity-checksum byte at the end.

Here's some pseudo-code on how to decrypt the data; assume that WriteDword and ReadDword functions do just that at a given position:

```
{
   uint xorValue = fileseed;  // initial 2 byte value from the save game

   for( i = 0; i < (datasize / 4); i++ )  // loop through every integer of data
   {
      for( j = 0; j < 3; j++ )  // loop advances scramble value 3x
      {
         xorValue *= 0x5B1A7851;
         xorValue += 0xCE4E;
      }
      int pos = 4 + ( i * 4 );  // advance reading/writing position
      uint temp = ReadDword( pos );
      WriteDword( pos, temp ^ xorValue );  // xor dword in file with current value
   }
}
```


How often it loops the scrambling seems to be variable, but i've never seen it do anything other than thrice. So yeah, every integer of data gets XORd with a new value, top-to-bottom. The checksum byte at the end of the file is separately decrypted through the same process, but from a fresh start with the fileseed. But that doesn't really matter for this.

After that, you need to decrypt the resulting data AGAIN, but byte for byte this time via this:

```
{
   uint xorValue = 0x13100200;  // fixed initial value

   for( i = 0; i < datasize; i++ )  // loop through every byte of data
   {
      xorValue *= 0x41C64E6D;
      xorValue += 0x3039;
      ubyte xor8 = xorValue >> 0x10;  // get 3rd lowest byte, like 03 in 0x04030201
      pos = 4 + i;  // advance reading/writing position
      ubyte temp = ReadByte( pos );
      WriteByte( pos, temp ^ xor8 );  // xor the byte
   }
}
```


So one layer is XOR'd per integer with a three times "scrambled" value each, and one layer is XOR'd per byte with a value that advances just once, but only takes a specific byte from the integer scrambling value.


As i said, i know jack about encryption, but these seem pretty simple. Are they some common algorithms or totally custom stuff from the devs? What's the significance of the multiplication and addition values (keys, salts, vectors, whatever)?
Also, apologies if my C-like code looks strange or is wrong; I'm not actually a coder at all and don't 'speak' C.
