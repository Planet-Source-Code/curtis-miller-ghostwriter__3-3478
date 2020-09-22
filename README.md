<div align="center">

## GhostWriter


</div>

### Description

Opens Notepad and mysteriously(By not creating a window) Types a message in notepads text.
 
### More Info
 
No inputs

This program Shows how to gain acess to a main window and a child window and send text to it.

May freak people out if they double click this app.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Curtis Miller](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/curtis-miller.md)
**Level**          |Intermediate
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/curtis-miller-ghostwriter__3-3478/archive/master.zip)

### API Declarations

Windows.h


### Source Code

```
/*******************
****Ghost Writer****
*******************/
#include <windows.h>
int WinMain(HINSTANCE hInstance,HINSTANCE hPrevInstance,LPSTR lpCmdLine,int nShowCmd)
{
	ShellExecute(NULL,"open","C:\\Windows\\NOTEPAD.EXE",NULL,NULL,SW_SHOWNORMAL); //Opens Notepad
	Sleep(1000); //Stops the program for 1000 millaseconds
	HWND Notepad;	//Defines handle notepad
	HWND text;		//Defines handle to text
	Notepad = FindWindow("Notepad",NULL); //Initializes Notepad handle
	text = FindWindowEx(Notepad,0,"Edit",0); //Initializes text to the child window Edit
	SendMessage(text,WM_SETTEXT,0,(LPARAM)(LPCTSTR)"This Code was written in C++"); //Sends the Text to the CHild window text
	return 0;
}
```

