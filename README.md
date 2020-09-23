<div align="center">

## How Enable/Disable Back & Forward in webbrowser


</div>

### Description

it show how to enable / disable

back & forward in a webbrowser control
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Sebastien Levesque](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/sebastien-levesque.md)
**Level**          |Beginner
**User Rating**    |3.7 (11 globes from 3 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Internet/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-html__1-34.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/sebastien-levesque-how-enable-disable-back-forward-in-webbrowser__1-10132/archive/master.zip)





### Source Code

```
Private Sub WebBrowser1_CommandStateChange(ByVal Command As Long, ByVal Enable As Boolean)
On Error Resume Next
Select Case Command
  Case CSC_NAVIGATEFORWARD
    If Enable = True Then
      'Forward dispo
      ForwardEnable = True
      RaiseEvent ForwardUpdate(True)
    Else
      'Forward non dispo
      ForwardEnable = False
      RaiseEvent ForwardUpdate(False)
    End If
    'Pas de forward
  Case CSC_NAVIGATEBACK
    If Enable = True Then
      BackEnable = True
      RaiseEvent BackUpdate(True)
      'Back dispo
    Else
      BackEnable = False
      RaiseEvent BackUpdate(False)
      'Back non dispo
    End If
End Select
 If Command = -1 Then Exit Sub
'End If
End Sub
```

