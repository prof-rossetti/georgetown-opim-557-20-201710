# VBA Language Overview

## Datatypes

### Strings

The "string" datatype is used to represent words or text. A string must begin with an opening quotation mark (`"`) and end with a closing quotation mark (`"`) (e.g. `"Hello World"`).

```vb
Dim MyMessage As String
MyMessage = "Hello World"
MsgBox(MyMessage)
```

#### String Operations

##### String Concatenation

The most popular string operation is "concatenation", which assembles multiple strings into a single string. The operator to perform string concatenation is an ampersand (`&`). When concatenating strings with other strings, or even with variables, make sure to include space characters in the proper places or else your strings will run together without a space. For example, **all the following approaches are equivalent**:

```vb
Dim MyMessage As String
MyMessage = "Hello" & " " & "World" ' notice the separate space character
MsgBox(MyMessage)
```

```vb
Dim MyMessage As String
MyMessage = "Hello " & "World" ' notice the trailing space after the word Hello
MsgBox(MyMessage)
```

```vb
Dim MyMessage As String
MyMessage = "Hello" & " World" ' notice the leading space before the word World
MsgBox(MyMessage)
```

```vb
Dim FirstString As String
Dim SecondString As String
MyMessage = FirstString & " " & SecondString ' notice the separate space character in-between the two variables. just because you use variables to represent strings does not change your need to include space characters
MsgBox(MyMessage)
```

##### New Lines

Use the `vbNewLine` keyword to insert a line break in a concatenated string:

```vb
Dim MyMessage As String
MyMessage = "Hello World" & vbNewLine & "Goodbye!"
MsgBox(MyMessage)
```

##### String Case

Use the `UCase()`, `LCase()` and `WorksheetFunction.Proper()` functions to manipulate the case of any string:

```vb
Dim MyMessage As String
MyMessage = "HeLlo WoRlD"
MsgBox(MyMessage & " " & UCase(MyMessage) & " " & LCase(MyMessage) & " " & WorksheetFunction.Proper(MyMessage))
```

##### String Formatting

Convert numbers into strings using a specified template. The template to convert to a USD currency format with a dollar sign and thousands separator and two decimal places is `"$##,##0.00"`:

```vb
Dim Price As Double
Price = 45.12345
MsgBox( Format(Price, "$##,##0.00") )
```

##### String Splitting

Split a string into component parts by using the `Split()` function and passing parameters corresponding to the string to be split, followed by the delimiter:

```vb
Dim MyStr As String
MyStr = "first | second | third"

Dim MyList() As String ' an array of strings
MyList = Split(MyStr, " | ")
```

When a string is split, it results in an [array](/notes/visual-basic/datatypes/arrays.md), which can be accessed in the usual ways:

```vb
Dim ListItem As Variant

For Each ListItem In MyList
    MsgBox(ListItem)
Next ListItem

' --> "first"
' --> "second"
' --> "third"
```
