## SETUP WSL2 (windows only)

Open PowerShell as Andmin and run

```bash
  dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Check requirement for runing WSL2

```bash
    open Run and winver
```

Enable VM feature

```bash
  dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

Set WSL as your default version

```bash
  wsl --set-default-version 2
```

install Ubuntu 20.04 LTS in Microsolf Store

https://docs.microsoft.com/en-us/windows/wsl/install
https://docs.microsoft.com/en-us/windows/wsl/install-manual
