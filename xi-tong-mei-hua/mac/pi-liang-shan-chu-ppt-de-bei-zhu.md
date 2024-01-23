# 批量删除PPT的备注

1. 打开PPT的视图，点击宏
2. 随便输入一个名称，点击+号
3. 把下面的输入放到 Sub 和 Sub End 中间

```bash
Dim osld As Slide
For Each osld In ActivePresentation.Slides
With osld.NotesPage.Shapes(2)
If.HasTextFrame Then
.TextFrame.DeleteText
End If
End With
Next osld
```

4. 开始执行
