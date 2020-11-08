# Microsoft

## Visual Studio
- **Turn on Verbose debug:** `Tools -> Project & Solution -> Build & Run Options`


## Right click: Open with Neovim
![icon](https://s135.convertio.me/p/ywRSBgj9RAfCq-RIAO2PwA/3321a9b8437526c1d786bee32a723881/nvim-icon.ico)

Replace `hust921` with whatever username
```batch
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\*\shell\Open with Neovim]
"Icon"="C:\\Users\\hust921\\Documents\\nvim.ico"
"Position"="Top"
@="Open with Neovim"

[HKEY_CLASSES_ROOT\*\shell\Open with Neovim\Command]
@="C:\\Users\\hust921\\AppData\\Local\\wsltty\\bin\\mintty.exe --WSL=\"Ubuntu\" --configdir=\"C:\\Users\\hust921\\AppData\\Roaming\\wsltty\" -t '%1' -e bash --login -c \"nvim \\\"$(wslpath '%1')\\\"\""
```

## dotnet Core
...

## MSBuild
...

## WMI Explorer
[Download link here](https://powershell.org/2013/03/wmi-explorer/)

## Powershell

### Aliases
*Reminder: get all using `alias`*
```
Alias           ? -> Where-Object
Alias           % -> ForEach-Object

Alias           select -> Select-Object
Alias           sls -> Select-String

Alias           gc/cat -> Get-Content
Alias           gm     -> Get-Member
```

**Formatting:**
```
Alias           fc -> Format-Custom
Alias           fl -> Format-List
Alias           ft -> Format-Table
Alias           fw -> Format-Wide
Alias           fhx -> Format-Hex             7.0.0.0    Microsoft.PowerShell.Utility
```

### Get-Member
`Get-Member` or `gm` returns a `Microsoft.PowerShell.Commands.MemberDefinition` of any `PSObject` *piped* to it.

```powershell
# ===========================================================================
# == Example 1: Get file (powershell object) -> pipe to Get-Member         ==
# ===========================================================================
Get-ChildItem .\_vsvimrc |gm
#
#    TypeName: System.IO.FileInfo
# Name                      MemberType     Definition
# ----                      ----------     ----------
# AppendText                Method         System.IO.StreamWriter AppendText()
# CopyTo                    Method         System.IO.FileInfo CopyTo(string destFileName), System.IO.FileInfo CopyTo(string destFileName, bool overwrite)
# Create                    Method         System.IO.FileStream Create()
# ...


# ===========================================================================
# == Example 2: Get file property (string) -> pipe to Get-Member           ==
# ===========================================================================
Get-ChildItem .\_vsvimrc -Name |gm
#
#    TypeName: System.String
# Name             MemberType            Definition
# ----             ----------            ----------
# Clone            Method                System.Object Clone(), System.Object ICloneable.Clone()
# CompareTo        Method                int CompareTo(System.Object value), int CompareTo(string strB), int IComparable.CompareTo(System.Object obj), int ICompara…
# Contains         Method                bool Contains(string value), bool Contains(string value, System.StringComparison comparisonType), bool Contains(char value…
# ...
```

### CURL for Powershell
**Basic:**
```Powershell
Invoke-WebRequest http://example.org
# Or
iwr http://example.org
```

**Raw body** (only/scriptable) variations:
```Powershell
(iwr http://example.org).Content
iwr http://example.org | Write-Host -PipelineVariable $_.Content
iwr http://example.org | Select-Object -Expand Content
```

**With header, body, POST:**
```Powershell
iwr http://example.org -Method POST -Headers @{"Content-Type" = "application/json"} -Body '{ "query":{ "query_string":{ "query":"any_string" } } }' | Select-Object -Expand Content
```

**Backtick version** (`\` newline for windows/powershell)
```Powershell
iwr http://example.org `
  -Body '{ "query":{ "query_string":{ "query":"any_string" } } }' `
  -Header @{"Content-Type" = "application/json"} `
  | Select-Object -Expand Content
```

### Managing Windows Services
**NOTE:** When dealing with **WMI**, many commands takes an argument named `<REMOTE HOST>` or `<HOST>`. To use the local computer: use the alias "`.`".


**Get-Service** Examples:
```Powershell
Get-Service "network*"
Get-Service -Name "win*" -Exclude "WinRM"
Get-Service | Where-Object {$_.Status -eq "Running"}
```

**Start-Service** and **Stop-Service** Examples:
```Powershell
Start-Service myservice
Stop-Service myservice

# Start disabled service:
Set-Service myservice -StartupType manual
Start-Service myservice

Get-Service -DisplayName "myservice" | Stop-Service
```

**New-Service** and **Remove-Service** Examples:
```Powershell
New-Service -Name "TestService" -BinaryPathName "C:\Windows\....\some.exe -k arguments /nosplash"

# Another example:
$params = @{
  Name = "TestService"
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params

# Remove Service
Remove-Service -Name "myservice"
```

## Windbg
...
