# Microsoft

## Visual Studio
- **Turn on Verbose debug:** `Tools -> Project & Solution -> Build & Run Options`

## dotnet Core
...

## MSBuild
...

## WMI Explorer
[Download link here](https://powershell.org/2013/03/wmi-explorer/)

## Powershell

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
