## Post #1
- Username: Pakolmo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 25, 2017 10:35 am
- Post datetime: 2019-04-26T02:25:04+00:00
- Post Title: Help with dialogs encripted from Chewy: Esc from F5

Hi!

Can you help me to decode the texts from the Chewy: Esc from F5 game? 
It is a Blue Byte game (settlers).

I have the English and German file: [https://www.dropbox.com/s/msjbf0t90jc9ieu/chewy.7z?dl=0](https://www.dropbox.com/s/msjbf0t90jc9ieu/chewy.7z?dl=0)

Thanks!
## Post #2
- Username: Pakolmo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 25, 2017 10:35 am
- Post datetime: 2019-04-29T12:56:08+00:00
- Post Title: Help with dialogs encripted from Chewy: Esc from F5

I think it is the C++ code to decrypt the texts form Chewy: Esc from F5.

[https://codesearch.isocpp.org/actcd19/m ... nes/chewy/](https://codesearch.isocpp.org/actcd19/main/s/scummvm/scummvm_2.0.0+dfsg-2/engines/chewy/)

decrypt(data, chunk->size);

void Resource::decrypt(byte *data, uint32 size) {
	byte *c = data;

	for (uint i = 0; i < size; i++) {
		*c = -(*c);
		++c;
	}
}

[https://codesearch.isocpp.org/actcd19/m ... source.cpp](https://codesearch.isocpp.org/actcd19/main/s/scummvm/scummvm_2.0.0+dfsg-2/engines/chewy/resource.cpp)

Can somebody do a decrypt and encrypt tool, please?

Thanks!
