PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting languagem and a configuration management framework

* Built on top of the .NET framework
* Completely object-oriented, meaning that it handles data as objects rather than as plain text

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PowerShell Elements

## Attributes

A

* d (Directory), which indicates a folder
* a (Archive), which indicates an archived item
* r (ReadOnly), which indicates an item that's in read only
* h (Hidden), which indicates a hidden item
* s (System), which indicates an item that belongs to the operating system
* -, which indicates the absence of an attribute

## Variables

```PowerShell
# Implicit variable declaration
$VARIABLE = DATA

# Explicit variable declaration
[DATA TYPE]$VARIABLE = DATA
```

## Parameters

## Conditions

```PowerShell
if (CONDITION)
{
}
else
{
}
```

## Loops

* While loop
```PowerShell
while (CONDITION)
{
  COMMANDS;
}
```

* Do while loops
```PowerShell
do
{
  COMMANDS;
}
while (CONDITION)
```

* For loops
```PowerShell
for (VARIABLE INITIALIZATION; CONDITION; INCREMENT)
{
  COMMANDS;
}
```

* For each loop
```PowerShell
foreach ($ITEM in $COLLECTION)
{
  COMMANDS;
}
```

## Functions

## Operators

* -eq
* -lt
* -le
* gt
* ge

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PowerShell Cmdlets

## Text Manipulation

*
```PowerShell
Out-File <FILE NAME> [OPTIONS]
```

## Item Manipulation

*
```PowerShell
Get-Location [OPTIONS]
```

*
```PowerShell
Set-Location [OPTIONS] <DESTINATION>
```

*
```PowerShell
Get-ChildItem <FOLDER>
```

*
```PowerShell
New-Item [OPTIONS] <ITEM NAME>
```

*
```PowerShell
Remove-Item [OPTIONS] <ITEM NAME>
```

*
```PowerShell
Copy-Item [OPTIONS] <ITEM SOURCE> <DESTINATION>
```

*
```PowerShell
Move-Item <OLD PATH> <NEW PATH>
```

*
```PowerShell
Rename-Item <OLD NAME> <NEW NAME>
```

*
```PowerShell
Get-Content <FILE> [OPTIONS]
```

## Object Manipulation

## Process Manipulation

*
```PowerShell
Get-Process [OPTIONS]
```

*
```PowerShell
Start-Process <PROCESS NAME|ID>
```

*
```PowerShell
Stop-Process [OPTIONS]
```

## Output Manipulation

## Command History

*
```PowerShell
Get-History [OPTIONS]
```

*
```PowerShell
Clear-History
```

## Command Help

*
```PowerShell
Get-Help [OPTIONS]
```

*
```PowerShell
Get-Command [OPTIONS]
```
