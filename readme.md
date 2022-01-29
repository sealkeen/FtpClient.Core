## Overview
### FTP client Core
- Saved .Net Framework 4.0 x86 WinApi <-> .Net Core 3.1 WinApiS - cross-windows support (.csproj_vs2010 / .csproj)
### Usage
``` C#
    var _client = new Client("ftp://127.0.0.1", "login", "password");
``` 
- Download 
``` C#
	SaveFileDialog saveFileDialog = new SaveFileDialog();
	bool? ok = saveFileDialog.ShowDialog();
	if (ok.HasValue && ok.Value == true)
	{
		client.DownloadFile(selectedFile.Name, saveFileDialog.FileName);
	}
``` 
- Send 
``` C#			
	Dictionary<string, string> sourceTargetFiles = new Dictionary<string, string>() { { "C:/filename.txt", "filename.txt" } };
	string outputDirectory = "foldername";
	foreach (var pair in sourceTargetFiles) {
		string response = "";
		try { response = _client?.MakeDirectory(outputDirectory); } catch (Exception ex) { } // Console.WriteLine(response);
		response = _client?.UploadFile(pair.Key, Path.Combine(outputDirectory, pair.Value)); // Console.WriteLine(response);
	}

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
