# PowerShell FUDATS 🕒

**FUDATS** (File Update Timestamps and Date) is a lightweight PowerShell script designed to quickly and easily modify the metadata timestamps of any file. 

## About PowerShell FUDATS

When testing systems, organizing archives, or managing digital forensics, you often need to alter a file's timestamp. This script allows you to simultaneously update a file's **Creation Time**, **Last Write Time**, and **Last Access Time** to a specific target date and time without requiring third-party software.

## Features

* **All-in-One Update:** Modifies creation, modification, and access times in a single execution.
* **Error Handling:** Built-in validation checks if the file exists before attempting to modify it, preventing unexpected console errors.
* **Native PowerShell:** No external dependencies, modules, or installations required.

## The Script

following code as a `powershellfudats.ps1` file

```powershell
$filePath = "File_Path"
$newDate = Get-Date "_date_ 12:00:00"

if (Test-Path $filePath) {
    $file = Get-Item$filePath
    
    $file.CreationTime =$newDate
    $file.LastWriteTime =$newDate
    $file.LastAccessTime =$newDate
    
    Write-Host "Success! File dates updated to $newDate" -ForegroundColor Green
} else {
    Write-Host "Error: File not found at $filePath" -ForegroundColor Red
}
