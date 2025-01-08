# windows-sandbox

This repository contains a Windows Sandbox template that I use for Upwork contracting. It enables me to spin up a safe and isolated environment quickly.

## Programs Installed

The following programs are installed automatically when the sandbox is started:
- Firefox
- Visual Studio Code (VSCode)
- Google Chrome

## Settings in the .wsb File

The `Sandbox-Upwork.wsb` file contains the configuration for the Windows Sandbox environment. Below are the details of the settings:

- **MappedFolders**: Maps a folder from the host to the sandbox.
  - `HostFolder`: `D:\Storage\Github\windows-sandbox`
  - `SandboxFolder`: `C:\Windows-Sandbox`
  - `ReadOnly`: `true` (The folder is read-only in the sandbox)

- **LogonCommand**: Executes a PowerShell script to install the Chocolatey package manager and select programs.
  - `Command`: `powershell.exe -ExecutionPolicy Bypass -Command "start powershell.exe { -File C:\Windows-Sandbox\SandboxTemplates\Install-Choco.ps1 }"`

- **vGPU**: Enables virtual GPU.
- **AudioInput**: Disables audio input. (Microphone passthrough)
- **VideoInput**: Disables video input. (Webcam passthrough)
- **PrinterRedirection**: Disables printer redirection.
- **ClipboardRedirection**: Enables clipboard redirection.
- **MemoryInMB**: Allocates 8192 MB of memory to the sandbox.
- **ProtectedClient**: Enables protected client mode.
