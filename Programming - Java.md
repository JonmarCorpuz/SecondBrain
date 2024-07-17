# Variables

| Keyword | Purpose |
| --- | --- |
| byte | 8-bit signed integer (Ranges from -128 tO 127) | 
| short | 16-bit signed integer (Ranges from -32 768 to 32 767) | 
| int | 32-bit signed integer (Ranges from -2^31 to 2^31 - 1) |
| long | 64-bit signed integer (Ranges from -2^63 to 2^63 - 1) | 
| float | 32-bit IEEE 754 floating point | 
| double | 64-bit IEEE 757 floating point | 
| boolean | True or false values |
| char | 16-bit unicode character (Ranges from '\u0000' to '\uffff') |

**Variable declaration and initialization**
```Java
{byte|short|int|float|long|double|boolean|char|string|object} <variable_name> = <value>;
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Conditional Statements

**If statement**
```Java
if (<condition>) {
  <code_to_be_executed>;
}
```

**If-else statement**
```Java
if (<condition>) {
  <code_to_be_executed>;
} else
  <code_to_be_executed>;
}
```

**If-else if-else statments**
```Java
if (<condition>) {
  <code_to_be_executed>;
} else if (<conditions>) {
  <code_to_be_executed>;
}else
  <code_to_be_executed>;
}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Switch Statements

```Java
switch (<expression>) {
  case <value>:
    <code_to_execute>;
    break;
  [case <value>:
    <code_to_execute>;
    break;]
  // If no match is found
  default:
    <code_to_execute>;
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Loops

| Loop Control Statement | Purpose |
| --- | --- |
| break | Terminates the loop  |
| break outerLoop | Terminates the nested loop |
| continue | skips the current iteration of the loop and continues to the next iteration |
| return | Immediately exits the loop and returns a value |

## While Loops

**While loop**
```Java
while (<conditions>) {
  <code_to_be_executed>;
}
```

**Do While loop**
```Java
do {
  <code_to_be_executed>;
} while (<conditions>)
```

## For Loops

**For loop**
```Java
for (<initialization>; <conditions>; <update>) {
  <code_to_be_executed>;
}
```

**For each loop**
```Java
for (<data_type> <element> : <array>) {
  <code_to_be_executed>;
}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Functions

```Java

```
