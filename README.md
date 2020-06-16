Add Imports to any EXE.. function calls and new dll to load.
Add Custom Section to any EXE or DLL.

Usage
```
    PEFile pe("1.exe"); 
    pe.addSection(".at4re", 0x1000, false);
    char* functions[] = { "MessageBoxA", "ShowWindow" }; 
    pe.addImport("user32.dll", functions, 2); 
    pe.saveToFile("1+.exe");
```
