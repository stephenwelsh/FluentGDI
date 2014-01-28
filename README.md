FluentGDI
=========

When you still need to use Old School GDI+ no reason you can't make it easier using a bit of Fluent code,

```csharp
FluentGDIProfile _topbarProfile = new FluentGDIProfile() {
  FillBrush = new SolidBrush(Color.Black),
  TextBrush = new SolidBrush(Color.White),
  Alignment = StringAlignment.Near,
  Cell = new RectangleF(0, 0, 100, 10)
};

Bitmap image = new Bitmap(320,240);
FluentGDI gdi = new FluentGDI();
using (FluentGDI gdi = new FluentGDI(Graphics.FromImage(image))) {
  gdi.SetProfile(_profile)
    .SaveCell(ref pos)
    .PenColor(Color.FromArgb(255, 160, 160, 160))
    .FillBrush(new SolidBrush(Color.Grey))
    .RoundedRectangle(6)
    .FillColor(Color.Transparent)
    .PenColor(Color.FromArgb(255, 90, 90, 90))
    .PenWidth(1)
    .RoundedRectangle(6)
    .Move(new RectangleF(12, 0, 88, 55))
    .Text(call.Direction + "Second Line")
    .SetCell(pos)
    .Move(new RectangleF(12, 45, 88, 55))
    .Text("Second Line");
}
image.Save("GDI_Rendered.png", ImageFormat.Png);
```
