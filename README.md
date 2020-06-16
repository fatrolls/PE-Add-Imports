Add Imports to any EXE.. function calls and new dll to load.<br>
Add Custom Section to any EXE or DLL.

Usage
```
#include "PEFile.h"

int main(int argc, char* argv[]) {
	// Open the input file
	PEFile pe("1.exe");

	// Add "MessageBoxA" & "ShowWindow" functions to the import table
	char* functions[] = { "MessageBoxA", "ShowWindow" };
	pe.addImport("user32.dll", functions, 2);
	
	// Add a new section named ".at4re" with size "0x1000" byte
	pe.addSection(".at4re", 0x1000, false);
	
	// Save the modified file
	pe.saveToFile("1+.exe");
}
```
