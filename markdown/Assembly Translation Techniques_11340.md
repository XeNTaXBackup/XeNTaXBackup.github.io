## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-21T07:23:02+00:00
- Post Title: Assembly Translation Techniques

Guys... if you have disassembled code and you know exactly where the subroutine you want to analyze is, what's the best way to translate that into code? I've been piddling with trying to figure out the morphs in Saints Row IV, and I know where the code is that parses the loaded morph data, but even after just analyzing the header part of it I already want to pick my eyes out with an icepick. Is there a better way than going line-by-line like this?

```
# LOCAL VARIABLES
#
var_120         = byte ptr -120h
var_20          = dword ptr -20h
var_1C          = dword ptr -1Ch
var_18          = dword ptr -18h
var_14          = dword ptr -14h
var_10          = dword ptr -10h
var_C           = dword ptr -0Ch
var_8           = dword ptr -8
var_1           = byte ptr -1

#
# FUNCTION ARGUMENTS
#
arg_0           = dword ptr  8
arg_4           = dword ptr  0Ch
arg_8           = dword ptr  10h
arg_C           = dword ptr  14h

#
# BRANCH 000
#

loc_FC51E6:
xor     eax, eax ; set eax (return value) to 0 and exit subroutine
pop     ebx
mov     esp, ebp
pop     ebp
retn

eax = 0;
return eax;

#
# BRANCH 001
#

loc_FC51B4:
mov     eax, 8
sub     eax, edx

eax = 8
eax = eax - edx

#
# MAIN CODE
#

-- section 1
push    ebp
mov     ebp, esp
sub     esp, 120h           ; don't overwrite stack variables
push    ebx
mov     ebx, [ebp+arg_0]
mov     [ebp+var_1], 0
test    bl, 7
jnz     short loc_FC51E6
-- section 2
mov     ecx, [ebp+arg_8]
mov     edx, [ecx]
and     edx, 7
jnz     short loc_FC51B4
xor     eax, eax
jmp     short loc_FC51BB
-- section 3
loc_FC51BB:
add     eax, [ecx]
add     ebx, eax
add     eax, 18h
mov     [ecx], eax
mov     edx, [ebx+4]
mov     [ebp+var_C], ebx
cmp     edx, 3
jz      short loc_FC51ED
push    3
push    edx
lea     eax, [ebp+var_120]
push    offset aMorphVersionIs ; "Morph version is (%d).  Expecting curre"...
push    eax             ; char *
call    _sprintf
add     esp, 10h
loc_FC51ED:
cmp     dword ptr [ebx], 0BADBEEFh  // if(ebx != 0x0BADBEEF)
jnz     short loc_FC51E6            //    jmp short loc_FC51E6
                                    // else
push    esi                         //     nop
mov     esi, [ebx+8]                //     esi = [ebx+8]
test    esi, esi                    //     ZF = (esi & esi == 0 ? 1 : 0);
jz      short loc_FC5202            //     if(ZF == 1) jmp loc_FC5202

-- section 1
ebx = arg_0;  // (dword ptr)
var_1 = 0; // (byte ptr)
if(!ebx) return 0;
-- section 2
ecx = arg_8
edx = *ecx
if(edx == 0)
   eax = 0
else
   eax = 8
   eax = eax - edx
-- section 3
eax = eax + *ecx
ebx = ebx + eax
eax = eax + 0x18 (position of end of CCMORPH_PC header)
*ecx = eax
edx = *(ebx + 4)
*var_C = ebx
if(edx != 3)
  {
   error("Morph version is (%d).");
   eax = 0;
   return eax;
  }
else
  {
   FUCKING KILL ME ALREADY
  }
  
esi = [ebx+8]
if(esi == 0)
  {
  }


```
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-22T20:46:42+00:00
- Post Title: Assembly Translation Techniques

Wahahahaha figured it out  . Having some fun now. Now I know what chrrox meant when he said one guy just rips code straight out the game.

Though I do have one remaining problem: Steam games. Every time I try to debug and set breakpoints in OllyDbg, all Steam games crash. Is there a way around this without say getting banned from Steam, etc.?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-03-29T22:39:29+00:00
- Post Title: Assembly Translation Techniques

> Reply from howfie
>
> Wahahahaha figured it out  . Having some fun now. Now I know what chrrox meant when he said one guy just rips code straight out the game.

Can you elaborate on this?
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-04-01T05:56:15+00:00
- Post Title: Assembly Translation Techniques

there's a few programs out there than can take assembly and generate C code; it's still not pretty, but it's functional and a heck of a lot easier on the eyes than looking at assembly.
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-05-07T14:53:39+00:00
- Post Title: Assembly Translation Techniques

IDA Pro with Hex-Rays Decompiler will do that. Even better if you can provide the necessary structs so instead of the code dereferencing pointers it will actually tell you which members they're accessing. BTW, if you want to translate assembly back to code, the best way is to step through in OllyDbg and looking at what changes. A lot of calls are library calls, usually, so you can ignore some functions if they have well defined behaviours.
