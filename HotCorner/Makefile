#  https://www.gnu.org/software/make/manual/html_node/Automatic-Variables.html#Automatic-Variables
#  Changed to compile .rc

#CFLAGS=/nologo /O2

#mutch smaller
CFLAGS=/GS /GL /analyze- /W3 /Gy /Zc:wchar_t /Gm- /O2  /Zc:inline /fp:precise /D "WIN32" /D "NDEBUG" /D "_WINDOWS" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX- /Zc:forScope /Gd /Oy- /Oi /MD  /EHsc /nologo 
LFLAGS=/LTCG:incremental /NXCOMPAT /DYNAMICBASE "kernel32.lib" "user32.lib" "gdi32.lib" "winspool.lib" "comdlg32.lib" "advapi32.lib" "shell32.lib" "ole32.lib" "oleaut32.lib" "uuid.lib" "odbc32.lib" "odbccp32.lib" /MACHINE:X86 /OPT:REF /SAFESEH /INCREMENTAL:NO /SUBSYSTEM:WINDOWS /MANIFESTUAC:"level='asInvoker' uiAccess='false'" /OPT:ICF /ERRORREPORT:PROMPT /NOLOGO /TLBID:1 
RFLAGS=/nologo /n

HotCorner.exe: HotCorner.obj HotCorner.res
	$(CC) $(CFLAGS) /Fe:$(@F) $**

HotCorner.res: HotCorner.rc
	$(RC) $(RCFLAGS) $?

clean:
	del *.obj *.res HotCorner.exe

install: HotCorner.exe
	copy HotCorner.exe "%USERPROFILE%\Start Menu\Programs\Startup"

uninstall:
	del "%USERPROFILE%\Start Menu\Programs\Startup\HotCorner.exe"
