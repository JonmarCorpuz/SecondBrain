PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting languagem and a configuration management framework

* Built on top of the .NET framework
* Completely object-oriented, meaning that it handles data as objects rather than as plain text

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PowerShell Elements

## Attributes

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

*
```PowerShell
[string]$VARIABLE=<VALUE>
[char]$VARIABLE=<VALUE>
[byte]$VARIABLE=<VALUE>
[int]$VARIABLE=<VALUE>
[long]$VARIABLE=<VALUE>
[bool]$VARIABLE=<VALUE>
[decimal]$VARIABLE=<VALUE>
[single]$VARIABLE=<VALUE>
[double]$VARIABLE=<VALUE>
[dateTime]$VARIABLE=<VALUE>
[xml]$VARIABLE=<VALUE>
[array]$VARIABLE=<VALUE>
```

*
```PowerShell
$Host="Host information"
$Home="Current user's home folder"
$Pwd="Present working directory"
$Args=" "
```

## Parameters

*
```PowerShell
param(
    [Parameter(Mandatory=$true)][<DATA>]$<PARAMETER_NAME>
)
```

## Conditions

```PowerShell
if (CONDITION) {
  <ACTION>;
} else {
  <ACTION>;
}
```

*
```PowerShell
Switch (<CONDITION>) {
  <VALUE1> {<ACTION>; break}
  <VALUE2> {<ACTION>; breal}
  Default {<DEFAULT ACTION>}
}

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

*
```PowerShell
Function <FUNCTION NAME> {
  [PARAMETERS]
  [VARIABLES]
  [ACTIONS]
}

<FUNCTION NAME> [OPTIONS]
```

## Methods

*
```PowerShell
[...] {$OBJECT.METHOD([PARAMETERS]) [OPTIONS]}
```

*
```PowerShell
[...] {$OBJECT.VALUE [OPTIONS]}
```

## Operators

*
```PowerShell
-eq
-lt
-le
-gt
-ge
-not
-and
-or
-xor
```

*
```PowerShell
+
-
*
%
**
<<
>>
&
|
^
```

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
