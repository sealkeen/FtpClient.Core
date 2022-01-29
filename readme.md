## Overview
### FTP client Core
- Saved .Net Framework 4.0 x86 WinApi <-> .Net Core 3.1 WinApiS - cross-windows support (.csproj_vs2010 / .csproj)
- usage:
``` C#
    var client = new Client("ftp://127.0.0.1", "login", "password");
```
### Functional
- Connect to an FTP server;
- Download / Upload files;
- List FTP directories.
	
### Current versions support :
- WPF .Net 4.0 builds for Windows;
- WPF .Net Core 3.1 build for Windows;
- .Net Standard 2.0 Library
- .Net Standard 2.1 Library 
