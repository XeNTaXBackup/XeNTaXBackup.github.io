## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2015-04-14T06:54:49+00:00
- Post Title: Xbox Coding

Hey Guys i just wanted to know if anyone can help me with this iv been wondering this from a while i seen this for the pc (i want to add audio to the trainer coding) so when i load the trainer i want to be able to hear a song thats added  (this is out there now and has been for a while

"like i said i just want to add audio when its starts up if anyone can help me that would be great"

Trainer coding 

```

bool OneHitKo = false;
bool HooksSet = false;
bool MaxXP = false;
bool Godmode = false;
bool CheatXX = FALSE;
bool CheatXY = FALSE;
bool CheatXB = FALSE;
bool CheatXA = FALSE;
bool CheatYA = FALSE;
bool CheatYB = FALSE;
bool CheatYC = FALSE;
bool CheatYD = FALSE;
bool CheatA1 = FALSE;
bool CheatA2 = FALSE;
bool CheatA3 = FALSE;
bool CheatA4 = FALSE;
bool CheatAC = false;
bool CheatAB = false;
bool CheatAD = false;
bool CheatAE = false;
bool CheatAA = false;
bool CheatA5 = false;
bool CheatA6 = false;
bool CheckGame = FALSE;
bool CheckGame2 = FALSE;
bool GameReady = false;
bool TU = false;

/*
Gold
820FBF44 7D6BF214             add r11,r11,r30 
820FBF50 917F0094             stw r11,94h(r31) 

EXP
820FBFC4 7D6BF214             add r11,r11,r30 
820FBFD0 917F006C             stw r11,6Ch(r31) 

Skills
820F0118 394A0001             addi r10,r10,1 
820F011C 7D4BF92E             stwx r10,r11,r31 

Easy Win
8214A9F8 7D7D5851             subf. r11,r29,r11 
8214AA04 917F0070             stw r11,70h(r31) 


*/

BYTE Gold0[] = { 0x7D, 0x6B, 0xF2, 0x14 };
BYTE Gold1[] = { 0x39, 0x60, 0x27, 0x0F };
BYTE Exp0[] = { 0x7D, 0x6B, 0xF2, 0x14 };
BYTE Exp1[] = { 0x39, 0x6A, 0x27, 0x0F };
BYTE Skill0[] = { 0x39, 0x4A, 0x00, 0x01 };
BYTE Skill1[] = { 0x39, 0x40, 0x0E, 0x0E7 };
BYTE Win0[] = { 0x7D, 0x7D, 0x58, 0x51 };
BYTE Win1[] = { 0x7D, 0x7D, 0x00, 0x00 };






VOID __declspec(naked) CheckHP(VOID)
{
	DWORD Ptr1; 

	__asm
	{
		mr Ptr1,r3
	}

	__asm{

	}

if( Godmode == TRUE && Ptr1 == 0x0000000043802990)
{

	int XValue = 999999;
	__asm
	{

		stfs XValue,250h(r31)

	}

}else{
	if( Godmode == FALSE )
	{

		__asm{

			 stfs fr0,250h(r31) 
		}

	}

}

	__asm{
			
			lis r11,0x820D
			ori r11,r11,0x554C
			mtctr r11
			bctr       
	}
}



VOID SetHooks()
{


	 DWORD Godmode[4];
	 patchInJump( (PDWORD)Godmode, (DWORD)CheckHP, FALSE );
	 
		DoCave(0x820D553C, &Godmode[0], 4);
		DoCave(0x820D5540, &Godmode[1], 4);
		DoCave(0x820D5544, &Godmode[2], 4);
		DoCave(0x820D5548, &Godmode[3], 4);

		HooksSet = true;
}

VOID ShowTrainerMain()
{	
	Prompt = XShowMessageBoxUI(0, L"Viewing Cheat list - Hold in Game", L"Quickly Gain Gold (In Battle) - (LB + A)\r\nMax EXP (In Battle) - (LB + B)\r\nMax Skills - (LB + X)\r\nEasy Win - (LB + Y)", ARRAYSIZE(g_strButtons), g_strButtons, 0, XMB_NOICON, &g_mb_result, &g_xol);

		if( HooksSet == false )
				{
					SetHooks();
				}
}


VOID TrainerLoaded()
{
	PulseController();
	pop(L"Puzzle Quest Executed - LLLCC");
}


VOID ButPress(){

		XINPUT_STATE state; WCHAR r1[512];
		ZeroMemory( &state, sizeof(XINPUT_STATE) );
		while (1){

		if (XInputGetState(0, &state) == ERROR_SUCCESS)
		{
				/* Start Quick Codes */
				
			    /*if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER | XINPUT_GAMEPAD_Y))
				{
					if( Godmode == TRUE ) {
					
					Godmode = FALSE;
					pop(L"GodMode Disabled");
					PulseController();

					} else {

					Godmode = TRUE;
					pop(L"GodMode Enabled");
					PulseController();*/

				
				if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER |  XINPUT_GAMEPAD_A))
				{
					if( CheatAB == TRUE ) {
					
					CheatAB = FALSE;
					DoCheat(0x820FBF44, Gold0, 4);
					pop(L"Quickly Gain Gold (In Battle) - Disabled");
					PulseController();

					} else {

					CheatAB = TRUE;
					DoCheat(0x820FBF44, Gold1, 4);
					pop(L"Quickly Gain Gold (In Battle) - Enabled");
					PulseController();

					}
				}
				
				if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER |  XINPUT_GAMEPAD_B))
				{
					if( CheatAC == TRUE ) {
					
					CheatAC = FALSE;
					DoCheat(0x820FBFC4, Exp0, 4);
					pop(L"Max EXP (In Battle) - Disabled");
					PulseController();

					} else {

					CheatAC = TRUE;
					DoCheat(0x820FBFC4, Exp1, 4);
					pop(L"Max EXP (In Battle) - Enabled");
					PulseController();

					}
				}
				
				if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER |  XINPUT_GAMEPAD_X))
				{
					if( CheatAD == TRUE ) {
					
					CheatAD = FALSE;
					DoCheat(0x820F0118, Skill0, 4);
					pop(L"Max Skills - Disabled");
					PulseController();

					} else {

					CheatAD = TRUE;
					DoCheat(0x820F0118, Skill1, 4);
					pop(L"Max Skills - Enabled");
					PulseController();

					}
				}
				
				if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER |  XINPUT_GAMEPAD_Y))
				{
					if( CheatAE == TRUE ) {
					
					CheatAE = FALSE;
					DoCheat(0x8214A9F8, Win0, 4);
					pop(L"Easy Win - Disabled");
					PulseController();

					} else {

					CheatAE = TRUE;
					DoCheat(0x8214A9F8, Win1, 4);
					pop(L"Easy Win - Enabled");
					PulseController();

					}
				}
				/*if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER | XINPUT_GAMEPAD_RIGHT_SHOULDER | XINPUT_GAMEPAD_DPAD_RIGHT))
				{
					if( CheatRB == TRUE ) {
					
					CheatRB = FALSE;
					DoCheat(0x82C929F0, noreloado, 4);
					pop(L"Achievement Unlocked - 9999G - Fell in love with Mackenzie Pratt!");
					PulseController();

					} else {

					CheatRB = TRUE;
					DoCheat(0x82C929F0, nop, 4);
					pop(L"No Reload Enabled");
					PulseController();

					}
				}

				if(state.Gamepad.wButtons == (XINPUT_GAMEPAD_LEFT_SHOULDER | XINPUT_GAMEPAD_RIGHT_SHOULDER | XINPUT_GAMEPAD_DPAD_LEFT))
				{
					if( CheatRT == TRUE ) {
					
					CheatRT = FALSE;
					DoCheat(0x822DD1B4, moneyo, 4);
					pop(L"Infinite Money Disabled");
					PulseController();

					} else {
						
					CheatRT = TRUE;
					DoCheat(0x822DD1B4, money, 4);
					pop(L"Infinite Money Enabled");
					PulseController();

					}*/
				}
				/* End quick codes */

				/* Static offsets */
				/*if( InfHealth == TRUE ) {
					DoCheat(0x88888888, health, 4);
					DoCheat(0x88888888, health, 4);
				}*/
				/* End static offsets */
		
		}
		Sleep(500);
	 }



VOID ProcessButtonPress( MESSAGEBOX_RESULT g_mb_result )
{

}
```


Main cpp

```
#include "kernel.h"
#include "common.h"
#include "Puzzle Quest.h"


HANDLE hThread; 
DWORD hThreadId;
HANDLE hTh01 = 0; 
DWORD hThId01 = 0;


static void Main01(){
	
	/* Change to 1 to Disable */
	WORD quickcodes = 0;
	/* ----------------------*/

	HRESULT hre = 0; DWORD hr = 0; 
	XINPUT_STATE state; WCHAR r1[512];
	ZeroMemory( &state, sizeof(XINPUT_STATE) );
	while (1){

		if (XInputGetState(0, &state) == ERROR_SUCCESS)
		{
				
			    if ( quickcodes == 0 )
				{ 
					ExCreateThread(&hTh01, 0, &hThId01, (VOID*)XapiThreadStartup , 
					(LPTHREAD_START_ROUTINE)ButPress, NULL, 0x2);
					quickcodes = 1;
				}
				if( (BOOL)state.Gamepad.wButtons & XINPUT_GAMEPAD_BACK  && (BOOL)state.Gamepad.wButtons & XINPUT_GAMEPAD_START )
				{
					ShowTrainerMain();
				}
			
					if( Prompt == 0x000003E5 && g_mb_result.rgwPasscode[0] != 0x00 && g_mb_result.rgwPasscode[1] != 0x00 && g_mb_result.rgwPasscode[2] != 0x00 && g_mb_result.rgwPasscode[3] != 0x00 )
					{
							ProcessButtonPress( g_mb_result );

							memset( &g_mb_result.rgwPasscode[0], 0x00, 0x02 );
							memset( &g_mb_result.rgwPasscode[1], 0x00, 0x02 );
							memset( &g_mb_result.rgwPasscode[2], 0x00, 0x02 );
							memset( &g_mb_result.rgwPasscode[3], 0x00, 0x02 );
							Prompt = 0x9999;
					}
		}else{
			memset( &g_mb_result.rgwPasscode[0], 0x00, 0x02 );
			memset( &g_mb_result.rgwPasscode[1], 0x00, 0x02 );
			memset( &g_mb_result.rgwPasscode[2], 0x00, 0x02 );
			memset( &g_mb_result.rgwPasscode[3], 0x00, 0x02 );
			Prompt = 0x9999;
		}

		Sleep(500);
	}
}

BOOL APIENTRY DllMain(HANDLE hInstDLL, DWORD reason, LPVOID lpReserved){
	if(reason == DLL_PROCESS_ATTACH){
		DmSetMemoryD = (HRESULT (__cdecl *)(LPVOID, DWORD, LPCVOID, LPDWORD)) (ResolveFunct("xbdm.xex", 40));
		if (DmSetMemoryD != 0){
			KrnlType = 1; //  1 = dev kernel ; 0 = retail kernel (default)
			DmGetMemoryD = (HRESULT (__cdecl *)(LPCVOID, DWORD, LPVOID, LPDWORD)) (ResolveFunct("xbdm.xex", 10));
		}
		ExCreateThread(&hThread, 0, &hThreadId, (VOID*)XapiThreadStartup , (LPTHREAD_START_ROUTINE)Main01, NULL, 0x2);
		XSetThreadProcessor(hThread, 4); ResumeThread(hThread); CloseHandle(hThread);
	}

	TrainerLoaded();

	return TRUE;
}
```
## Post #2
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-04-13T08:02:54+00:00
- Post Title: Xbox Coding

Removed.
