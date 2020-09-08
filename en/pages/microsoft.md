# Microsoft

## Visual Studio
- **Turn on Verbose debug:** `Tools -> Project & Solution -> Build & Run Options`

## dotnet Core
...

## MSBuild
...

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

## Windbg
...
