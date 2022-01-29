## Overview
### FTP client Core
- Saved .Net Framework 4.0 x86 WinApi <-> .Net Core 3.1 WinApiS - cross-windows support (.csproj_vs2010 / .csproj)
- usage:
``` C#
    var _client = new Client("ftp://127.0.0.1", "login", "password");
        public void Send(Dictionary<string, string> sourceTargetFiles, string outputDirectory = "")
        {
            try
            {
                foreach (var pair in sourceTargetFiles)
                {
                    _log?.Invoke("Выполняется попытка отправить файлы на FTP сервер.");
                    _log?.Invoke("Sending file to FTP server...");
                    _log?.Invoke($"Creating output directory <{outputDirectory}>... ");
                    string response = "";

                    try { 
                        response = _client?.MakeDirectory(outputDirectory);
                        _log?.Invoke($"Server Respose : {response}");
                    } catch (Exception ex) { } // Ignore create directory error

                    response = _client?.UploadFile(pair.Key, Path.Combine(outputDirectory, pair.Value));
                    _log?.Invoke($"Server Respose : {response}");
                }
            }
            catch (Exception ex)
            {
                _log?.Invoke($"Error occured : {ex.Message}");
            }
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
