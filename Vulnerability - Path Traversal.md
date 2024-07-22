Path traversal is a type of security vulnerability that allows attackers to access files and directories that are stored outside the web root folder by manipulating a web application's URL using "dot-dot-slash" sequences to traverse the directory structure of a filesystem to access sensitive information or execute malicious actions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/45d9c1baacda290c1f95858e27f740c9.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/3037513935e3242f74bd0fe97833b5ac.png)

* Usually caused by poor input validation or filtering
* Can be caused when a user's input is passed to a function (Ex: *PHP's file_get_contents*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

| Path Traversal Technique | Description | Example |
| --- | --- | --- |
| dot-dot-slash |  | *http://example.com/index.php?lang=../../../../etc/passwd* |
| null bytes | Disregards whatever comes after the Null Byte | *http://example.com/index.php?lang=../../../../etc/passwd%00* |
