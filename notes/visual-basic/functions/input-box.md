# VBA Language Overview

## The `InputBox` Function

Use VBA's built-in [`InputBox` function](https://msdn.microsoft.com/en-us/vba/excel-vba/articles/application-inputbox-method-excel) to capture a user input. Pass a textual message as the function's primary parameter. Store the resulting value in a variable to make further use of it:

```vb
Dim MyName As String
MyName = InputBox("Please input your name: ")
MsgBox(MyName)
```
