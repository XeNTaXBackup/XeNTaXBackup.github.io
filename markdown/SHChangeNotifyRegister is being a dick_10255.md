## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-03-23T02:21:01+00:00
- Post Title: SHChangeNotifyRegister is being a dick

I added support for Noesis to watch its Python script folder and auto-reload scripts when the files were changed not too long ago. I used SHChangeNotifyRegister to do it. It's been working fine on my machines running Windows 7. But I noticed on another machine (also running Windows 7) it doesn't give me SHCNE_UPDATEITEM events, but it still sends me my WM_USER message for SHCNE_CREATE, SHCNE_DELETE, etc.

This behavior is pretty fucky and doesn't make sense. It would be one thing if it weren't sending the WM_USER message or if it were failing to register the hook, but it's all succeeding and working as expected except that it just doesn't send the update events. Does anyone else have experience using that function or know what could possibly cause it to not drop events on some machines even though they're running the same OS?

Oh, and I found a Microsoft example program using SHChangeNotifyRegister, and it works fine on my machine, but again on that other machine it drops the SHCNE_UPDATEITEM events too no matter what folder I'm watching with it. So that verifies that it isn't actually my code specifically, it's just the shell functionality being broken on that machine. But I can't figure out what could be different on that machine to do it. UAC being on or off makes no difference either.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-23T15:58:41+00:00
- Post Title: SHChangeNotifyRegister is being a dick

yeah the patform sdk docs suck donkey balls when it comes to the shell docs. same behavior if you dont use the shared memory bit flag? you applying the list to a file or a path using recursion flag?
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-23T19:57:42+00:00
- Post Title: SHChangeNotifyRegister is being a dick

my problem is the exact opposite rich, i get the SHCNE_UPDATEITEM but don't get the SHCNE_CREATE and other notifications lololol.

```

#ifndef RC_INVOKED
#include "shlobj.h"
#pragma comment(lib, "shell32.lib")
#endif

#ifndef RC_INVOKED
#include<sstream>
#endif

static const UINT WM_SHELLCHANGENOTIFY = (WM_USER + 0x101);
static HINSTANCE basead = NULL;
static HWND mainhwnd = NULL;

// shell variables
static LPSHELLFOLDER lpShellFolder = NULL;
static LPTSTR lpShellFolderPath = TEXT("c:\\users\\semory\\desktop\\New folder\\");
static LPITEMIDLIST lpShellFolderIDList = NULL;
static IShellItem* lpShellItem = NULL;
static ULONG watchcode = 0;

static LRESULT CALLBACK MainWindowProc(HWND window, UINT message, WPARAM wparam, LPARAM lparam);
static LRESULT EvNCCreate(HWND window, WPARAM wparam, LPARAM lparam);
static LRESULT EvCreate(HWND window, WPARAM wparam, LPARAM lparam);
static LRESULT EvDestroy(HWND window, WPARAM wparam, LPARAM lparam);
static LRESULT EvNCDestroy(HWND window, WPARAM wparam, LPARAM lparam);
static LRESULT EvPaint(HWND window, WPARAM wparam, LPARAM lparam);
static LRESULT EvShellChangeNotify(HWND window, WPARAM wparam, LPARAM lparam);

int run(HINSTANCE handle)
{
 // set base address
 basead = handle;

 // register window
 WNDCLASSEX wcx;
 wcx.cbSize = sizeof(WNDCLASSEX);
 wcx.style = CS_DBLCLKS | CS_HREDRAW | CS_VREDRAW;
 wcx.lpfnWndProc = (WNDPROC)MainWindowProc;
 wcx.cbClsExtra = 0;
 wcx.cbWndExtra = 0;
 wcx.hInstance = basead;
 wcx.hIcon = NULL;
 wcx.hCursor = LoadCursor(NULL, IDC_ARROW);
 wcx.hbrBackground = (HBRUSH)GetStockObject(WHITE_BRUSH);
 wcx.lpszMenuName = NULL;
 wcx.lpszClassName = TEXT("MainWindow");
 wcx.hIconSm = NULL;
 if(RegisterClassEx(&wcx) == FALSE) {
    MessageBox(0, TEXT("Failed to register window class."), TEXT("Error"), MB_ICONSTOP);
    return FALSE;
   }

 // create window
 DWORD styleEx = 0;
 DWORD style = WS_OVERLAPPEDWINDOW | WS_VISIBLE;
 int x = CW_USEDEFAULT; int y = CW_USEDEFAULT;
 int w = CW_USEDEFAULT; int h = CW_USEDEFAULT;
 HWND hwnd = CreateWindowEx(styleEx, TEXT("MainWindow"), TEXT("Hello World!"), style, x, y, w, h, NULL, NULL, basead, NULL);
 if(!hwnd) return -1;

 // create shell item
 HRESULT result = SHGetDesktopFolder(&lpShellFolder);
 if(SUCCEEDED(result)) {
    ULONG eaten = 0;
    result = lpShellFolder->ParseDisplayName(NULL, NULL, lpShellFolderPath, &eaten, &lpShellFolderIDList, NULL);
    if(SUCCEEDED(result)) {
       result = SHCreateItemFromIDList(lpShellFolderIDList, IID_IShellItem, (LPVOID*)&lpShellItem);
       if(SUCCEEDED(result)) SetWindowText(hwnd, lpShellFolderPath);
       else SetWindowText(hwnd, TEXT("SHCreateShellItem failed."));
      }
    else SetWindowText(hwnd, TEXT("ParseDisplayName failed."));
   }
 else
    SetWindowText(hwnd, TEXT("SHGetDesktopFolder failed."));

 // watch shell item
 PIDLIST_ABSOLUTE pidlWatch;
 result = SHGetIDListFromObject(lpShellItem, &pidlWatch);
 if(SUCCEEDED(result)) {
    INT sources = SHCNRF_InterruptLevel | SHCNRF_RecursiveInterrupt | SHCNRF_NewDelivery;
    LONG events = SHCNE_ALLEVENTS;
    SHChangeNotifyEntry entry = { pidlWatch, TRUE };
    watchcode = SHChangeNotifyRegister(hwnd, sources, events, WM_SHELLCHANGENOTIFY, 1, &entry);
    if(watchcode != 0) SetWindowText(hwnd, TEXT("SUCCESSFULLY WATCHING!"));
   }

 // message loop
 MSG msg;
 for(;;) {
     BOOL status = GetMessage(&msg, NULL, 0, 0);
     if(status == -1) return -1;
     else if(status != 0) {
        TranslateMessage(&msg);
        DispatchMessage(&msg);
       }
     else
        break;
    }
 return (int)msg.wParam;
}

int WINAPI WinMain(HINSTANCE handle, HINSTANCE, LPSTR, int)
{
 HRESULT result = CoInitializeEx(NULL, COINIT_APARTMENTTHREADED);
 if(FAILED(result)) return -1;
 int retval = run(handle);
 CoUninitialize();
 return retval;
}

LRESULT CALLBACK MainWindowProc(HWND window, UINT message, WPARAM wparam, LPARAM lparam)
{
 switch(message) {
   case(WM_NCCREATE): return EvNCCreate(window, wparam, lparam);
   case(WM_CREATE): return EvCreate(window, wparam, lparam);
   case(WM_DESTROY): return EvDestroy(window, wparam, lparam);
   case(WM_NCDESTROY): return EvNCDestroy(window, wparam, lparam);
   case(WM_PAINT): return EvPaint(window, wparam, lparam);
   case(WM_SHELLCHANGENOTIFY): return EvShellChangeNotify(window, wparam, lparam);
   default: return DefWindowProc(window, message, wparam, lparam);
  }
 return 0;
}

LRESULT EvNCCreate(HWND window, WPARAM wparam, LPARAM lparam)
{
 mainhwnd = window;
 return DefWindowProc(window, WM_NCCREATE, wparam, lparam);
}

LRESULT EvCreate(HWND window, WPARAM wparam, LPARAM lparam)
{
 LRESULT retval = DefWindowProc(window, WM_CREATE, wparam, lparam);
 if(retval == -1) return -1;
 return retval;
}

LRESULT EvDestroy(HWND window, WPARAM wparam, LPARAM lparam)
{
 // stop watching
 if(watchcode) {
    SHChangeNotifyDeregister(watchcode);
    watchcode = 0;
   }

 // cleanup shell variables
 if(lpShellFolderIDList) {
    CoTaskMemFree((LPVOID)lpShellFolderIDList);
    lpShellFolderIDList = NULL;
   }
 if(lpShellItem) {
    lpShellItem->Release();
    lpShellItem = NULL;
   }
 if(lpShellFolder) {
    lpShellFolder->Release();
    lpShellFolder = NULL;
   }

 // default processing
 return DefWindowProc(window, WM_DESTROY, wparam, lparam);
}

LRESULT EvNCDestroy(HWND window, WPARAM wparam, LPARAM lparam)
{
 LRESULT retval = DefWindowProc(window, WM_NCDESTROY, wparam, lparam);
 mainhwnd = NULL;
 PostQuitMessage(0);
 return retval;
}

LRESULT EvPaint(HWND window, WPARAM wparam, LPARAM lparam)
{
 PAINTSTRUCT ps;
 HDC winDC = BeginPaint(window, &ps);
 EndPaint(window, &ps);
 return 0;
}

LRESULT EvShellChangeNotify(HWND window, WPARAM wparam, LPARAM lparam)
{
 long notification = 0;
 PIDLIST_ABSOLUTE* lppidl = NULL;
 HANDLE lock = SHChangeNotification_Lock((HANDLE)wparam, (DWORD)lparam, &lppidl, &notification);
 if(lock) {
    std::basic_stringstream<TCHAR> ss;
    ss << TEXT("CODE: ");
    if(notification & SHCNE_CREATE) ss << TEXT("SHCNE_CREATE - ");
    else if(notification & SHCNE_DELETE) ss << TEXT("SHCNE_DELETE - ");
    else if(notification & SHCNE_RENAMEITEM) ss << TEXT("SHCNE_RENAMEITEM - ");
    else if(notification & SHCNE_UPDATEITEM) ss << TEXT("SHCNE_UPDATEITEM - ");
    else if(notification & SHCNE_MKDIR) ss << TEXT("SHCNE_MKDIR - ");
    else if(notification & SHCNE_RENAMEFOLDER) ss << TEXT("SHCNE_RENAMEFOLDER - ");
    else if(notification & SHCNE_UPDATEDIR) ss << TEXT("-SHCNE_UPDATEDIR - ");
    else ss << TEXT("Something else happened!");
    SetWindowText(window, ss.str().c_str());
    SHChangeNotification_Unlock(lock);
   }
 return 0;
}

```
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-03-24T00:14:37+00:00
- Post Title: SHChangeNotifyRegister is being a dick

Yeah, I tried every possible combination of sources/events/flags. Same behavior no matter what on that machine, but still working as expected on this one. Same thing with the Microsoft sample code. This behavior would probably be mentioned in the documentation, if it existed.

Here's the MS sample code that doesn't work too just for reference. If they can't use their own API correctly, I don't know who can.
[ChangeNotifyWatcher.zip](https://xentaxbackup.github.io/file/6286_ChangeNotifyWatcher.zip)
