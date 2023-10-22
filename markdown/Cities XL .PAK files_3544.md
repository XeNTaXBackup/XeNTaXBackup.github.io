## Post #1
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2009-06-20T16:40:44+00:00
- Post Title: Cities XL .PAK files

Hi.
Anybody know how to extract these .PAK files?

Samples: [http://66.7.218.134/~usaportu/pub/Paks.rar](http://66.7.218.134/~usaportu/pub/Paks.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-21T06:42:33+00:00
- Post Title: Cities XL .PAK files

the only problem there is the file table which is obfuscated so it's not possible to retrieve the names of the file, while there is no problem for the content which is simply zipped (job for offzip).
maybe there is a bit of luck if you post also the executable of the game (although I highly doubt because it's a debugging job).
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-21T10:20:49+00:00
- Post Title: Cities XL .PAK files

Yes, the file table is at the end of the files, pointed to by a variable at the beginning. It's encrypted by some process. The resources can simply by unzlibbed, but it's a bit annoying to do, as you don't know the size of the compressed resources.
## Post #4
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2009-06-21T14:24:14+00:00
- Post Title: Cities XL .PAK files

The game is avaible to download here: [https://beta.citiesxl.com/download/](https://beta.citiesxl.com/download/)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-21T21:26:11+00:00
- Post Title: Cities XL .PAK files

Can you upload the exe?
## Post #6
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2009-06-21T21:49:31+00:00
- Post Title: Cities XL .PAK files

I uploaded RAR file with *.EXE and *.DLL of the game.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-24T21:30:31+00:00
- Post Title: Cities XL .PAK files

Well, it looks like the first encrypted part in the header might be decrypted from this piece of asm in core_vr.dll

```
.text:10065990 ; class stlp_std::basic_string<char, class stlp_std::char_traits<char>, class stlp_std::allocator<char>> __cdecl mcPack_namespace::SHA1toStr(unsigned char * const)
.text:10065990 ?SHA1toStr@mcPack_namespace@@YA?AV?$basic_string@DV?$char_traits@D@stlp_std@@V?$allocator@D@2@@stlp_std@@QAE@Z_0 proc near
.text:10065990                                         ; CODE XREF: mcPack_namespace::SHA1toStr(uchar * const)j
.text:10065990
.text:10065990 var_55          = byte ptr -55h
.text:10065990 var_54          = dword ptr -54h
.text:10065990 var_44          = dword ptr -44h
.text:10065990 var_3C          = byte ptr -3Ch
.text:10065990 var_14          = dword ptr -14h
.text:10065990 var_10          = dword ptr -10h
.text:10065990 var_C           = dword ptr -0Ch
.text:10065990 var_4           = dword ptr -4
.text:10065990 arg_0           = dword ptr  4
.text:10065990 arg_4           = dword ptr  8
.text:10065990
.text:10065990                 push    0FFFFFFFFh
.text:10065992                 push    offset loc_100DD5C9
.text:10065997                 mov     eax, large fs:0
.text:1006599D                 push    eax
.text:1006599E                 sub     esp, 4Ch
.text:100659A1                 mov     eax, dword_101271F8
.text:100659A6                 xor     eax, esp
.text:100659A8                 mov     [esp+58h+var_10], eax
.text:100659AC                 push    ebx
.text:100659AD                 push    ebp
.text:100659AE                 push    esi
.text:100659AF                 push    edi
.text:100659B0                 mov     eax, dword_101271F8
.text:100659B5                 xor     eax, esp
.text:100659B7                 push    eax
.text:100659B8                 lea     eax, [esp+6Ch+var_C]
.text:100659BC                 mov     large fs:0, eax
.text:100659C2                 mov     eax, [esp+6Ch+arg_4]
.text:100659C6                 movzx   edx, byte ptr [eax+2]
.text:100659CA                 xor     ecx, ecx
.text:100659CC                 mov     ch, [eax]
.text:100659CE                 movzx   edi, byte ptr [eax+6]
.text:100659D2                 movzx   ebx, byte ptr [eax+0Ah]
.text:100659D6                 mov     cl, [eax+1]
.text:100659D9                 mov     esi, [esp+6Ch+arg_0]
.text:100659DD                 mov     [esp+6Ch+var_54], 0
.text:100659E5                 shl     ecx, 8
.text:100659E8                 or      ecx, edx
.text:100659EA                 movzx   edx, byte ptr [eax+3]
.text:100659EE                 shl     ecx, 8
.text:100659F1                 or      ecx, edx
.text:100659F3                 xor     edx, edx
.text:100659F5                 mov     dh, [eax+4]
.text:100659F8                 mov     dl, [eax+5]
.text:100659FB                 shl     edx, 8
.text:100659FE                 or      edx, edi
.text:10065A00                 movzx   edi, byte ptr [eax+7]
.text:10065A04                 shl     edx, 8
.text:10065A07                 or      edi, edx
.text:10065A09                 xor     edx, edx
.text:10065A0B                 mov     dh, [eax+8]
.text:10065A0E                 mov     dl, [eax+9]
.text:10065A11                 shl     edx, 8
.text:10065A14                 or      edx, ebx
.text:10065A16                 movzx   ebx, byte ptr [eax+0Bh]
.text:10065A1A                 shl     edx, 8
.text:10065A1D                 or      edx, ebx
.text:10065A1F                 movzx   ebx, byte ptr [eax+0Eh]
.text:10065A23                 mov     ebp, edx
.text:10065A25                 xor     edx, edx
.text:10065A27                 mov     dh, [eax+0Ch]
.text:10065A2A                 mov     dl, [eax+0Dh]
.text:10065A2D                 shl     edx, 8
.text:10065A30                 or      edx, ebx
.text:10065A32                 movzx   ebx, byte ptr [eax+0Fh]
.text:10065A36                 shl     edx, 8
.text:10065A39                 or      edx, ebx
.text:10065A3B                 movzx   ebx, byte ptr [eax+12h]
.text:10065A3F                 mov     [esp+6Ch+var_44], edx
.text:10065A43                 xor     edx, edx
.text:10065A45                 mov     dh, [eax+10h]
.text:10065A48                 mov     dl, [eax+11h]
.text:10065A4B                 movzx   eax, byte ptr [eax+13h]
.text:10065A4F                 shl     edx, 8
.text:10065A52                 or      edx, ebx
.text:10065A54                 shl     edx, 8
.text:10065A57                 or      eax, edx
.text:10065A59                 mov     edx, [esp+6Ch+var_44]
.text:10065A5D                 push    eax
.text:10065A5E                 push    edx
.text:10065A5F                 push    ebp
.text:10065A60                 push    edi
.text:10065A61                 push    ecx
.text:10065A62                 lea     eax, [esp+80h+var_3C]
.text:10065A66                 push    offset a08x08x08x08x08 ; "%08X%08X%08X%08X%08X"
.text:10065A6B                 push    eax             ; char *
.text:10065A6C                 call    ds:sprintf
.text:10065A72                 xor     ebx, ebx
.text:10065A74                 add     esp, 1Ch
.text:10065A77                 lea     ecx, [esp+6Ch+var_55]
.text:10065A7B                 mov     byte ptr [esp+6Ch+var_14], bl
.text:10065A7F                 call    ds:??0?$allocator@D@stlp_std@@QAE@XZ ; stlp_std::allocator<char>::allocator<char>(void)
.text:10065A85                 push    eax
.text:10065A86                 lea     ecx, [esp+70h+var_3C]
.text:10065A8A                 push    ecx
.text:10065A8B                 mov     ecx, esi
.text:10065A8D                 mov     [esp+74h+var_4], ebx
.text:10065A91                 call    ds:??0?$basic_string@DV?$char_traits@D@stlp_std@@V?$allocator@D@2@@stlp_std@@QAE@PBDABV?$allocator@D@1@@Z ; stlp_std::basic_string<char,stlp_std::char_traits<char>,stlp_std::allocator<char>>::basic_string<char,stlp_std::char_traits<char>,stlp_std::allocator<char>>(char const *,basic_string<char,stlp_std::char_traits<char>,stlp_std::allocator<char>>::allocator<char> const &)
.text:10065A97                 lea     ecx, [esp+6Ch+var_55]
.text:10065A9B                 call    ds:??1?$allocator@D@stlp_std@@QAE@XZ ; stlp_std::allocator<char>::~allocator<char>(void)
.text:10065AA1                 mov     eax, esi
.text:10065AA3                 mov     ecx, [esp+6Ch+var_C]
.text:10065AA7                 mov     large fs:0, ecx
.text:10065AAE                 pop     ecx
.text:10065AAF                 pop     edi
.text:10065AB0                 pop     esi
.text:10065AB1                 pop     ebp
.text:10065AB2                 pop     ebx
.text:10065AB3                 mov     ecx, [esp+58h+var_10]
.text:10065AB7                 xor     ecx, esp
.text:10065AB9                 call    sub_100D36BC
.text:10065ABE                 add     esp, 58h
.text:10065AC1                 retn
.text:10065AC1 ?SHA1toStr@mcPack_namespace@@YA?AV?$basic_string@DV?$char_traits@D@stlp_std@@V?$allocator@D@2@@stlp_std@@QAE@Z_0 endp
.text:10065AC1
.text:10065AC1 ; ---------------------------------------------------------------------------

```
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-24T22:57:41+00:00
- Post Title: Cities XL .PAK files

I don't know if I rock or I'm simply lucky but I saw that in core.dll was used the CryptDecrypt function of Windows and looking a bit there I found the string "allocator" so I decided to see if I was so lucky to have catched the right decryption and... yes :)
the following is the part of C code for the decryption:

```
    unsigned char key[] = "allocator";
    HCRYPTPROV  hProv;
    HCRYPTHASH  hHash;
    HCRYPTKEY   hKey;
    DWORD       len;

    len = datalen;

    if(!CryptAcquireContext(
        &hProv,
        NULL,
        MS_ENHANCED_PROV,
        PROV_RSA_FULL,
        0)) return(-1);

    if(!CryptCreateHash(
        hProv,
        CALG_MD5,
        0,
        0,
        &hHash)) return(-1);

    if(!CryptHashData(
        hHash,
        key,
        strlen(key),
        0)) return(-1);

    if(!CryptDeriveKey(
        hProv,
        CALG_RC4,
        hHash,
        0x00800000,
        &hKey)) return(-1);

    if(!CryptDecrypt(
        hKey,
        0,
        TRUE,
        0,
        data,
        &len)) return(-1);

    CryptDestroyKey(hKey);
    CryptDestroyHash(hHash);
    CryptReleaseContext(hProv, 0);
    return(0);
}
```
*edit* updated the code so it's just a stand-alone function
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-25T06:52:53+00:00
- Post Title: Cities XL .PAK files

Nice work! I'd seen that one as well, but did not get round to it to take a good look at it.  Seems the game uses a lot - A LOT - of standard Windows functions + a great deal of open source code. The whole game.exe is a collection of declarations to the huge number of dlls the game uses. haha. 

Anyway, do you have a complete working piece of code to decrypt a buffer that way?
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-25T07:05:13+00:00
- Post Title: Cities XL .PAK files

I have the full BMS script for doing it :)

*edit, was updated to version 0.1.1*
[http://aluigi.org/papers/bms/citiesxl.bms](http://aluigi.org/papers/bms/citiesxl.bms)
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-25T08:04:26+00:00
- Post Title: Cities XL .PAK files

Awesome. It's great to see that no job is too difficult here at our forum  . 

I've attached all unpacked files from the .PAK examples in the first post in this thread. 
That will help studying the game engine. 


 paks_unpacked.zip
(1.19 MiB) Downloaded 347 times



The jpgs:



under_construction_large.jpg (20.21 KiB) Viewed 4002 times





skitrack02.jpg (38.23 KiB) Viewed 3987 times





skitrack_green_60.jpg (46.8 KiB) Viewed 3983 times





ascenceur.jpg (25.67 KiB) Viewed 3976 times



test1.mission (XML)

```
- <mission>
  <statetypes>PLAY,</statetypes> 
  <filter>""</filter> 
  <synchronisation>TIME_BASED</synchronisation> 
  <period>1</period> 
  <scene>GAME</scene> 
  <version>7</version> 
- <bloc>
  <type>OBJECTIVE</type> 
  <realisation>AND_R</realisation> 
  <fncheck>localCounter = ( localCounter or 0 ) + 1 LOG_INFO( "localCounter = " .. localCounter ) return ( localCounter == 10 )</fncheck> 
  <fnrealize>LOG_INFO( "[test01] objective has been realized, localCounter = " .. localCounter )</fnrealize> 
  <flags>""</flags> 
  </bloc>
  </mission>

```


cityresourcesconsumption.xml:

```
- <resources>
- <consumption>
- <citizenrange min="0" max="0">
- <resources>
  <RELE_0>600</RELE_0> 
  <RFUE_0>1000</RFUE_0> 
  <RWAT_0>400</RWAT_0> 
  <RWAS_0>800</RWAS_0> 
  <RFRE_0>1000</RFRE_0> 
  <RHOL_1>100</RHOL_1> 
  <RPAS_0>1000</RPAS_0> 
  <ROFF_0>1000</ROFF_0> 
  <RHOT_0>100</RHOT_0> 
  <RIN1_0>1000</RIN1_0> 
  <RIN2_0>1000</RIN2_0> 
  <RIN3_0>1000</RIN3_0> 
  <RAGR_0>1000</RAGR_0> 
  <RRET_1>0</RRET_1> 
  <RLEI_1>300</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="1" max="135">
- <resources>
  <RELE_0>668</RELE_0> 
  <RFUE_0>1068</RFUE_0> 
  <RWAT_0>468</RWAT_0> 
  <RWAS_0>868</RWAS_0> 
  <RFRE_0>1068</RFRE_0> 
  <RHOL_1>168</RHOL_1> 
  <RPAS_0>1068</RPAS_0> 
  <ROFF_0>1945</ROFF_0> 
  <RHOT_0>127</RHOT_0> 
  <RIN1_0>2945</RIN1_0> 
  <RIN2_0>1000</RIN2_0> 
  <RIN3_0>1000</RIN3_0> 
  <RAGR_0>1068</RAGR_0> 
  <RRET_1>270</RRET_1> 
  <RLEI_1>300</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="136" max="243">
- <resources>
  <RELE_0>722</RELE_0> 
  <RFUE_0>1122</RFUE_0> 
  <RWAT_0>522</RWAT_0> 
  <RWAS_0>922</RWAS_0> 
  <RFRE_0>1122</RFRE_0> 
  <RHOL_1>222</RHOL_1> 
  <RPAS_0>1122</RPAS_0> 
  <ROFF_0>2701</ROFF_0> 
  <RHOT_0>149</RHOT_0> 
  <RIN1_0>3701</RIN1_0> 
  <RIN2_0>2701</RIN2_0> 
  <RIN3_0>1000</RIN3_0> 
  <RAGR_0>1122</RAGR_0> 
  <RRET_1>486</RRET_1> 
  <RLEI_1>570</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="244" max="381">
- <resources>
  <RELE_0>791</RELE_0> 
  <RFUE_0>1191</RFUE_0> 
  <RWAT_0>591</RWAT_0> 
  <RWAS_0>991</RWAS_0> 
  <RFRE_0>1191</RFRE_0> 
  <RHOL_1>291</RHOL_1> 
  <RPAS_0>1191</RPAS_0> 
  <ROFF_0>3667</ROFF_0> 
  <RHOT_0>176</RHOT_0> 
  <RIN1_0>3667</RIN1_0> 
  <RIN2_0>3667</RIN2_0> 
  <RIN3_0>3667</RIN3_0> 
  <RAGR_0>1191</RAGR_0> 
  <RRET_1>762</RRET_1> 
  <RLEI_1>786</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="382" max="595">
- <resources>
  <RELE_0>898</RELE_0> 
  <RFUE_0>1298</RFUE_0> 
  <RWAT_0>698</RWAT_0> 
  <RWAS_0>1098</RWAS_0> 
  <RFRE_0>1298</RFRE_0> 
  <RHOL_1>398</RHOL_1> 
  <RPAS_0>1298</RPAS_0> 
  <ROFF_0>5165</ROFF_0> 
  <RHOT_0>219</RHOT_0> 
  <RIN1_0>5165</RIN1_0> 
  <RIN2_0>5165</RIN2_0> 
  <RIN3_0>5165</RIN3_0> 
  <RAGR_0>1298</RAGR_0> 
  <RRET_1>1190</RRET_1> 
  <RLEI_1>1062</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="596" max="1075">
- <resources>
  <RELE_0>1138</RELE_0> 
  <RFUE_0>1538</RFUE_0> 
  <RWAT_0>938</RWAT_0> 
  <RWAS_0>1338</RWAS_0> 
  <RFRE_0>1538</RFRE_0> 
  <RHOL_1>638</RHOL_1> 
  <RPAS_0>1538</RPAS_0> 
  <ROFF_0>8525</ROFF_0> 
  <RHOT_0>315</RHOT_0> 
  <RIN1_0>8525</RIN1_0> 
  <RIN2_0>8525</RIN2_0> 
  <RIN3_0>8525</RIN3_0> 
  <RAGR_0>1538</RAGR_0> 
  <RRET_1>2150</RRET_1> 
  <RLEI_1>1490</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="1076" max="1397">
- <resources>
  <RELE_0>1299</RELE_0> 
  <RFUE_0>1699</RFUE_0> 
  <RWAT_0>1099</RWAT_0> 
  <RWAS_0>1499</RWAS_0> 
  <RFRE_0>1699</RFRE_0> 
  <RHOL_1>799</RHOL_1> 
  <RPAS_0>1699</RPAS_0> 
  <ROFF_0>10779</ROFF_0> 
  <RHOT_0>379</RHOT_0> 
  <RIN1_0>10779</RIN1_0> 
  <RIN2_0>10779</RIN2_0> 
  <RIN3_0>10779</RIN3_0> 
  <RAGR_0>1699</RAGR_0> 
  <RRET_1>2794</RRET_1> 
  <RLEI_1>2450</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="1398" max="1682">
- <resources>
  <RELE_0>1441</RELE_0> 
  <RFUE_0>1841</RFUE_0> 
  <RWAT_0>1241</RWAT_0> 
  <RWAS_0>1641</RWAS_0> 
  <RFRE_0>1841</RFRE_0> 
  <RHOL_1>941</RHOL_1> 
  <RPAS_0>1841</RPAS_0> 
  <ROFF_0>12774</ROFF_0> 
  <RHOT_0>436</RHOT_0> 
  <RIN1_0>12774</RIN1_0> 
  <RIN2_0>12774</RIN2_0> 
  <RIN3_0>12774</RIN3_0> 
  <RAGR_0>1841</RAGR_0> 
  <RRET_1>3364</RRET_1> 
  <RLEI_1>3094</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="1683" max="2185">
- <resources>
  <RELE_0>1693</RELE_0> 
  <RFUE_0>2093</RFUE_0> 
  <RWAT_0>1493</RWAT_0> 
  <RWAS_0>1893</RWAS_0> 
  <RFRE_0>2093</RFRE_0> 
  <RHOL_1>1193</RHOL_1> 
  <RPAS_0>2093</RPAS_0> 
  <ROFF_0>16295</ROFF_0> 
  <RHOT_0>537</RHOT_0> 
  <RIN1_0>16295</RIN1_0> 
  <RIN2_0>16295</RIN2_0> 
  <RIN3_0>16295</RIN3_0> 
  <RAGR_0>2093</RAGR_0> 
  <RRET_1>4370</RRET_1> 
  <RLEI_1>3664</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="2186" max="4751">
- <resources>
  <RELE_0>2976</RELE_0> 
  <RFUE_0>3376</RFUE_0> 
  <RWAT_0>2776</RWAT_0> 
  <RWAS_0>3176</RWAS_0> 
  <RFRE_0>3376</RFRE_0> 
  <RHOL_1>2476</RHOL_1> 
  <RPAS_0>3376</RPAS_0> 
  <ROFF_0>34257</ROFF_0> 
  <RHOT_0>1050</RHOT_0> 
  <RIN1_0>34257</RIN1_0> 
  <RIN2_0>34257</RIN2_0> 
  <RIN3_0>34257</RIN3_0> 
  <RAGR_0>3376</RAGR_0> 
  <RRET_1>9502</RRET_1> 
  <RLEI_1>4670</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="4752" max="6171">
- <resources>
  <RELE_0>3686</RELE_0> 
  <RFUE_0>4086</RFUE_0> 
  <RWAT_0>3486</RWAT_0> 
  <RWAS_0>3886</RWAS_0> 
  <RFRE_0>4086</RFRE_0> 
  <RHOL_1>3186</RHOL_1> 
  <RPAS_0>4086</RPAS_0> 
  <ROFF_0>44197</ROFF_0> 
  <RHOT_0>1334</RHOT_0> 
  <RIN1_0>44197</RIN1_0> 
  <RIN2_0>44197</RIN2_0> 
  <RIN3_0>44197</RIN3_0> 
  <RAGR_0>4086</RAGR_0> 
  <RRET_1>12342</RRET_1> 
  <RLEI_1>9802</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="6172" max="7430">
- <resources>
  <RELE_0>4315</RELE_0> 
  <RFUE_0>4715</RFUE_0> 
  <RWAT_0>4115</RWAT_0> 
  <RWAS_0>4515</RWAS_0> 
  <RFRE_0>4715</RFRE_0> 
  <RHOL_1>3815</RHOL_1> 
  <RPAS_0>4715</RPAS_0> 
  <ROFF_0>53010</ROFF_0> 
  <RHOT_0>1586</RHOT_0> 
  <RIN1_0>53010</RIN1_0> 
  <RIN2_0>53010</RIN2_0> 
  <RIN3_0>53010</RIN3_0> 
  <RAGR_0>4715</RAGR_0> 
  <RRET_1>14860</RRET_1> 
  <RLEI_1>12642</RLEI_1> 
  </resources>
  </citizenrange>
- <citizenrange min="7431" max="11619">
- <resources>
  <RELE_0>6410</RELE_0> 
  <RFUE_0>6810</RFUE_0> 
  <RWAT_0>6210</RWAT_0> 
  <RWAS_0>6610</RWAS_0> 
  <RFRE_0>6810</RFRE_0> 
  <RHOL_1>5910</RHOL_1> 
  <RPAS_0>6810</RPAS_0> 
  <ROFF_0>82333</ROFF_0> 
  <RHOT_0>2424</RHOT_0> 
  <RIN1_0>82333</RIN1_0> 
  <RIN2_0>82333</RIN2_0> 
  <RIN3_0>82333</RIN3_0> 
  <RAGR_0>6810</RAGR_0> 
  <RRET_1>23238</RRET_1> 
  <RLEI_1>15160</RLEI_1> 
  </resources>
  </citizenrange>
  </consumption>
- <pricelevels>
- <verylow>
  <percent>3</percent> 
  </verylow>
- <low>
  <percent>2</percent> 
  </low>
- <medium>
  <percent>1</percent> 
  </medium>
- <high>
  <percent>0.5</percent> 
  </high>
- <veryhigh>
  <percent>0.33</percent> 
  </veryhigh>
  </pricelevels>
  </resources>

```
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-25T08:32:21+00:00
- Post Title: Cities XL .PAK files

[http://www.xentax.com](http://www.xentax.com)  

I've also added you to the team list, btw : [http://www.xentax.com/?page_id=106](http://www.xentax.com/?page_id=106)
## Post #13
- Username: jenx
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 03, 2009 5:26 pm
- Post datetime: 2009-07-28T17:10:02+00:00
- Post Title: Cities XL .PAK files

Bugtest your a bloody legend mate thanks a million for that script...

All textures and sounds successfully extracted  

Still waiting on my damn key for this game though... really want to try it out  

-jenx
## Post #14
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-08-07T13:56:48+00:00
- Post Title: Cities XL .PAK files

Thanks, nice work....

However, it doesn't seem to work on the big 'all_sgbin.pak' file. 

> offset   filesize   filename
>
> ------------------------------
>
>   24c13670 841357     data/gfx/building/b_ressource_t1.sgbin
>
> 
>
> Error: the compressed zlib/deflate input is wrong or incomplete

Any fixes?
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-07T14:29:26+00:00
- Post Title: Cities XL .PAK files

do the following:
- open citiesxl.bms with notepad
- add the following string "before" the clog command at the end like in the following example:

```
    clog NAME OFFSET ZSIZE SIZE
```
- now launch the tool as usual (although would be faster to do it with the -l for listing the files) and then paste here the content of the quickbms output for the last files so I can verify it.
## Post #16
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-08-07T16:25:36+00:00
- Post Title: Re: Cities XL .PAK files

This is the output with the -l option.


> 37fa3763 534518     data/gfx/character/c_ma_cri01.sgbin
>
>   0e9baff3 791830     data/gfx/building/b_ind_hp01_t2.sgbin
>
>   3d975075 100911     data/gfx/objects/f_life[radio].sgbin
>
>   3e11aabc 73802      data/gfx/placeholder/b_aaplaquered_t1.sgbin
>
>   4a7eb324 520788     data/gfx/vehicle/gembeach/v_bo_gembeach03.sgbin
>
>   15d7fa2f 1568537    data/gfx/building/b_ldm_ldnloyd_t3.sgbin
>
>   02a1b0a8 163963     data/gfx/avatar/male/accessories/glass/x_ma_glass02.sgbin
>
>   388ac78a 554198     data/gfx/character/c_ma_low01.sgbin
>
>   3b39ce55 69114      data/gfx/furnitures/f_all_barrier03.sgbin
>
>   4000c84d 42041      data/gfx/road/gembeach/r_rb_pavementbeachboueb_05x40x60.sg
>
> bin
>
>   3ffb5515 40876      data/gfx/road/gembeach/r_pv_pavementbeachboueb_05x40x60.sg
>
> bin
>
>   3d6b53e8 31194      data/gfx/objects/f_anim[badmintonvolant].sgbin
>
>   3cc429a2 107078     data/gfx/furnitures/f_plaza[bac02].sgbin
>
>   39e6a3fb 529454     data/gfx/character/gemski/c_ai_gemski02[sechelico].sgbin
>
>   1ec7cc5a 1322390    data/gfx/building/b_ldm_sanfrantransamericapyramid_c3_t3.s
>
> gbin
>
>   418f818b 416812     data/gfx/road/r_br_bigpile_25x40.sgbin
>
>   000dc486 174688     data/gfx/avatar/female/accessories/glass/x_fa_glass05.sgbi
>
> n
>
>   00a39580 3208767    data/gfx/avatar/female/colorized_accessories/hair/x_fa_hai
>
> r07.sgbin
>
>   1b0cf9ee 2142492    data/gfx/building/b_ldm_parisnotredame_c2_t3.sgbin
>
>   427f8bc5 775930     data/gfx/road/r_br_bigpilegrey03_40x40.sgbin
>
>   3fb08b63 128864     data/gfx/road/gembeach/r_cr_pavementgembeach_02,5x02,5x60.
>
> sgbin
>
>   0ffb4c5b 419963     data/gfx/building/b_ind_np03_t1.sgbin
>
>   2db1bf25 377896     data/gfx/building/gemski/b_gemski[toilets]_t1.sgbin
>
>   3d8235dc 69727      data/gfx/objects/f_life[batte].sgbin
>
>   44c82ab3 422998     data/gfx/road/r_br_start_20x40.sgbin
>
>   3d682ccf 1292       data/gfx/objects/a_ad_gen_procurementhigh02[1-carybox].sgb
>
> in
>
>   3d6831db 9020       data/gfx/objects/a_ob_gen_procurementhigh02[1-carybox].sgb
>
> in
>
>   3d685517 9027       data/gfx/objects/a_test_gen_procurementhigh02[1-carybox].s
>
> gbin
>
>   4273b415 776112     data/gfx/road/r_br_bigpilegrey03_30x40.sgbin
>
>   3d5ee6a4 75783      data/gfx/furntituresstreet/f_trafficsignpost_08.sgbin
>
>   47527e8f 1080361    data/gfx/road/r_na_ribonfound_05x05.sgbin
>
>   44bb4216 422979     data/gfx/road/r_br_start_10x40.sgbin
>
>   46d2d7d5 183330     data/gfx/road/r_na_cross_10x10x40.sgbin
>
>   3b9ec79a 177966     data/gfx/furnitures/f_fri_busstop01.sgbin
>
>   44d512f0 423184     data/gfx/road/r_br_start_40x40.sgbin
>
>   3fc9a358 375861     data/gfx/road/gembeach/r_dk_roadgembeach4.sgbin
>
>   3cdd46d9 56088      data/gfx/furnitures/f_sui_bench02.sgbin
>
>   4ad1b416 472608     data/gfx/vehicle/gembeach/v_mo_gembeach01.sgbin
>
>   0e9541f2 421377     data/gfx/building/b_ind_hp01_t1.sgbin
>
>   42a310ed 775681     data/gfx/road/r_br_bigpilegrey04_40x40.sgbin
>
>   2a43849a 462801     data/gfx/building/gembeach/b_gembeach54[beachresto1].sgbin
>
> 
>
>   28ec6b44 762430     data/gfx/building/gembeach/b_gembeach19[shop3].sgbin
>
>   30d12ad5 1553884    data/gfx/building/h_eli01_t3.sgbin
>
>   486ea97c 1765033    data/gfx/road/r_tn_tunneldeck_20x20.sgbin
>
>   131bf3e2 2770736    data/gfx/building/b_ldm_astroobservatory02_t3.sgbin
>
>   3d0421cc 8730       data/gfx/furnitures/gembeach/f_anim[beachrateau].sgbin
>
>   4a76deb6 513134     data/gfx/vehicle/gembeach/v_bo_gembeach02.sgbin
>
>   4c80addb 207809     data/gfx/vehicle/v_ca_default.sgbin
>
>   029f3032 163958     data/gfx/avatar/male/accessories/glass/x_ma_glass01.sgbin
>
>   3b393acf 37766      data/gfx/furnitures/f_all_barrier02.sgbin
>
>   2b0cd1e7 44996      data/gfx/building/gembeach/b_gembeach[citylink].sgbin
>
>   1862be16 2487479    data/gfx/building/b_ldm_newyorkstpatrickschurch_c1_t3.sgbi
>
> n
>
>   068d9fde 1523993    data/gfx/building/b_ent_eli02_t3.sgbin
>
> 
>
> - 1776 files found

Regarding your extra line:

The second number in the list above equals both the ZSIZE and SIZE. DUMMY is always zero.

Let me know if you need something more...
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-07T17:26:58+00:00
- Post Title: Re: Cities XL .PAK files

ok so dummy must be ignored (because in another archive all the files have it set to 256 so it's not related to the compression of the files).
I have updated the [quickbms script](http://aluigi.org/papers/bms/citiesxl.bms) so that if ZSIZE and SIZE are the same the file is extracted as is.
let me know if the extracted file which gave you the problem is correct (so readable like the others)
## Post #18
- Username: Zipslow
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Aug 07, 2009 7:25 pm
- Post datetime: 2009-08-07T21:20:44+00:00
- Post Title: Re: Cities XL .PAK files

The contents of this post was deleted because of possible forum rules violation.
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-07T23:56:01+00:00
- Post Title: Re: Cities XL .PAK files

I have verified the archive and the format is exactly the same of the PAK files.
that small header of 10 bytes you see at the beginning of each file is just a part of the file (just as it's stored) so it's all correct
## Post #20
- Username: west
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 13, 2009 7:58 pm
- Post datetime: 2009-10-13T15:59:18+00:00
- Post Title: Re: Cities XL .PAK files

Hello,

Now that I see there is a way to extract the .Pak files in Cities XL is there a way to repack the files again.
## Post #21
- Username: Noel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 10, 2009 3:05 pm
- Post datetime: 2009-10-16T11:37:44+00:00
- Post Title: Re: Cities XL .PAK files

> Reply from west
>
> Hello,

Now that I see there is a way to extract the .Pak files in Cities XL is there a way to repack the files again.

How to repack?
Some modified files can be loaded in gamefolder/data/*,some may cause crash
## Post #22
- Username: joeblow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 17, 2009 6:40 am
- Post datetime: 2009-10-17T00:23:41+00:00
- Post Title: Re: Cities XL .PAK files

What specific folders have you had success with other then the ambience sound folder and what was the outcome? Thanks
## Post #23
- Username: Noel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 10, 2009 3:05 pm
- Post datetime: 2009-11-01T02:59:23+00:00
- Post Title: Re: Cities XL .PAK files

The gamesave file is the same format,
so,,,can transform the save from planet to solo ?
## Post #24
- Username: itsthemuffinman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 03, 2009 2:35 am
- Post datetime: 2009-12-03T21:00:51+00:00
- Post Title: Re: Cities XL .PAK files

> Now that I see there is a way to extract the .Pak files in Cities XL is there a way to repack the files again.

West... you got me thinking about this! I think with the most recent patch Monte Cristo have blocked loading files from the data directly, or at least some.

I've had a look through the patch files created by Okeanos and using the QuickBMS script previous I've put together a repacker.

Currently this only works for the single file contents patch file, but this does let you COMPELTELY customise the trade patch effects.

This makes me thinks that as longs as we can get this right we can repack ALL files and hence completely customise the game.  Modding at last!

I'm going to keep working on this and keep everyone posted.  If you guys could point me towards the interesting files I will have a look at repacking them.
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-03T22:40:52+00:00
- Post Title: Re: Cities XL .PAK files

Have a program that the fellows here can work with?
## Post #26
- Username: itsthemuffinman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 03, 2009 2:35 am
- Post datetime: 2009-12-04T08:09:24+00:00
- Post Title: Re: Cities XL .PAK files

Its still very early stages at the moments, will only work for a PAK with a single fileinside .  Over the weekend I will have a look at the file table layout again and try and make it work for more files.

Will keep you posted with progress!
## Post #27
- Username: Noel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 10, 2009 3:05 pm
- Post datetime: 2009-12-12T01:36:05+00:00
- Post Title: Re: Cities XL .PAK files

> Reply from itsthemuffinman
>
> Its still very early stages at the moments, will only work for a PAK with a single fileinside .  Over the weekend I will have a look at the file table layout again and try and make it work for more files.

Will keep you posted with progress!

It's a MMO game , MC's new hotfix may block all of this.
## Post #28
- Username: dakutis
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 13, 2009 11:11 pm
- Post datetime: 2009-12-14T07:20:35+00:00
- Post Title: Re: Cities XL .PAK files

Please, isthemuffinman, share your repacker. It can be very useful also if it can repack only one file!
@Noel: MC can't block repacked mods, or they will have to reprogram the main .exe file and all the .paks
Remember that they use the same tool (a packer/unpacker) to create their patches!"
## Post #29
- Username: Noel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 10, 2009 3:05 pm
- Post datetime: 2009-12-18T14:34:54+00:00
- Post Title: Re: Cities XL .PAK files

> Reply from dakutis
>
> Please, isthemuffinman, share your repacker. It can be very useful also if it can repack only one file!
@Noel: MC can't block repacked mods, or they will have to reprogram the main .exe file and all the .paks
Remember that they use the same tool (a packer/unpacker) to create their patches!"

agree with u
It's very very useful if repack only one file
## Post #30
- Username: evelien de ridder
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 16, 2009 11:31 am
- Post datetime: 2010-02-01T11:58:06+00:00
- Post Title: Re: Cities XL .PAK files

Please, isthemuffinman, share your repacker. It can be very useful also if it can repack only one file!
@Noel: MC can't block repacked mods, or they will have to reprogram the main .exe file and all the .paks
Remember that they use the same tool (a packer/unpacker) to create their patches!"


yes share  but not for online  play only single  love modling  the  game
## Post #31
- Username: evelien de ridder
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 16, 2009 11:31 am
- Post datetime: 2010-02-22T17:42:51+00:00
- Post Title: Re: Cities XL .PAK files

here some  cities xl  pak exploder have fun  

[http://www.file-upload.net/download-228 ... 5.zip.html](http://www.file-upload.net/download-2285688/CitiesXL-PAK-Explorer_V1.3.5.zip.html)
## Post #32
- Username: szab
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 14, 2010 2:53 pm
- Post datetime: 2010-03-14T07:43:36+00:00
- Post Title: Re: Cities XL .PAK files

Hi!

Ich kann nur Deutsch/German. Ihr müsst mit einem Translate übersetzen, was ich schreibe.

Es tut mir sehr Leid, aber ich um Hilfe anderswo nicht bitten kann.
Also... Ich kann nicht .pak Files/Daten auspacken, weil ich nicht viel von diesen Dingen verstehe.
Ich möchte das Spiel vom Deutschen ins Ungarische übersetzen, also brauche ich nur die sprachliche Files/Daten.
Ich versuchte sie schon mit verschiedenen Anwendungsprogramms auspacken, zum Beispiel: Pakexplorer, Pakscape, Total Commander. 

Sie haben meistens aber nicht die .pak's Files/Daten erkannt. Oder sie haben die Files/Daten nicht auspacken gekonnt.  
Könnte jemand mir helfen? Könnte jemand mir die sprachliche Files/Daten auspacken und sie schicken mir weg? (Ich brauche 
nur deutschsprachige Files/Daten.)
Ich wäre sehr froh! 

Ihr könnt mir ruhig auf englisch antworten, ich kann es mit einem Translate übersetzen. 
Ich wäre aber froh, wenn ihr mir auf deutsch antworten könntet. 

Mit freundlichen Grüßen
Szaba
## Post #33
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-14T10:37:29+00:00
- Post Title: Re: Cities XL .PAK files

for the unpacking:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
with the script:
[http://aluigi.org/papers/bms/citiesxl.bms](http://aluigi.org/papers/bms/citiesxl.bms)
## Post #34
- Username: szab
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 14, 2010 2:53 pm
- Post datetime: 2010-03-14T12:47:05+00:00
- Post Title: Re: Cities XL .PAK files

Erfolg!

Sehr, sehr danke! Ich habe die sprachliche Files/Daten auspacken gekonnt!
Wenn ich die Files/Daten überschreibe, also übersetze ich sie, dann... Was soll ich danach machen? 
Wie kann ich sie einpacken, dass sie wieder .pak sein werden?
## Post #35
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-14T15:41:59+00:00
- Post Title: Re: Cities XL .PAK files

I'm not aware of a packer for this game (but I'm not in its community so maybe something exists)
## Post #36
- Username: elmenda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 21, 2010 6:39 am
- Post datetime: 2010-03-21T15:23:51+00:00
- Post Title: Re: Cities XL .PAK files

Hello, I've been following this thread time in order to translate CItiesXL my language, Spanish, and today because of this community I have translated the game almost entirely through the tool Quickbms and citiesxl.bms script (by the way a fantastic job).

The problem I have is that I understand very little about these things and I need some method to repackage the edited files, I think there is some method by which people are already creating mods for this game and are files ending in. Pak.

At this point I have searched all over the net the repackaging method to no avail, since it seems to be a closely guarded secret by those who know him.

My only salvation you are you, who are the ones who know the subject, I would appreciate your help ever since I do not want to throw away so much effort spent on translation of the game with the sole purpose of sharing in the network.

From already thank you very much and sorry for my English because it is low level and have helped me through a translator. Thanks and best regards.
## Post #37
- Username: arcadoli
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 01, 2010 2:09 pm
- Post datetime: 2010-04-01T07:46:00+00:00
- Post Title: Re: Cities XL .PAK files

Hello to all,

I would like to write my own paker/unpaker for cities xl pak files.
I need some more informations please :
I know that pak files are encrypted with RC4 algo, but I supose I have to decrypt between byte 32 to end, am I right?
For the RC4 algo, I need to know wich block-size I have to use, because I've tried to decrypt from byte 32 to end of file, but I don't get anything 'readable'.
What usable informations are exactly in the header (byte 0 to 31) ?

I hope someone here will reply because I'm confused.
Thanks in advance and congratulations to people who are working to 'crack' game file format.

Arcadoli
Note : excuse me for ma bad English please.
## Post #38
- Username: arcadoli
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 01, 2010 2:09 pm
- Post datetime: 2010-04-08T13:22:10+00:00
- Post Title: Re: Cities XL .PAK files

Hi,

Excuses me to disturb you, but I have a question concerning Cities XL.
I've created a tool to unpak / repack.

The file I create with my repaker make the game crash, but I know why :
the header of the file.

I know that the first 4 bytes are MCPK
4 next are version number
4 next are Built number

BUt :

What are the next 20 bytes???

If I copy theses bytes in my file, the game start, so it's really necessary to know what to write in the pak file between offset 0C to 1F.

Can you help me please?I really don't understand what these mean.
Thank you for reading.

Arcadoli
## Post #39
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-08T18:10:13+00:00
- Post Title: Re: Cities XL .PAK files

uhmmm it could be a sha1 hash, I didn't verify it when I performed the reversing because was not necessary for my work
## Post #40
- Username: arcadoli
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Apr 01, 2010 2:09 pm
- Post datetime: 2010-04-08T20:36:16+00:00
- Post Title: Re: Cities XL .PAK files

i don't understand assembler but is this line meaning something to you?


text:10065AC1 ?SHA1toStr@mcPack_namespace@@YA?AV?$basic_string@DV?$char_traits@D@stlp_std@@V?$allocator@D@2@@stlp_std@@QAE@Z_0 endp

(part of a message in the start of this topic)
