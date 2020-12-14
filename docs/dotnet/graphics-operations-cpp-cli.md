---
description: 'Dowiedz się więcej o: operacjach graficznych (C++/CLI)'
title: Operacje graficzne (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: 84dbc75aa306219b8733848ece5c594ca40a0489
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223545"
---
# <a name="graphics-operations-ccli"></a>Operacje graficzne (C++/CLI)

Ilustruje manipulowanie obrazami przy użyciu Windows SDK.

W poniższych tematach przedstawiono <xref:System.Drawing.Image?displayProperty=fullName> sposób użycia klasy do przeprowadzenia manipulowania obrazem.

## <a name="display-images-with-the-net-framework"></a><a name="display"></a> Wyświetlanie obrazów z .NET Framework

Poniższy przykład kodu modyfikuje obsługę zdarzeń OnPaint, aby pobrać wskaźnik do <xref:System.Drawing.Graphics> obiektu w formularzu głównym. <xref:System.Windows.Forms.Form.OnPaint%2A>Funkcja jest przeznaczona dla aplikacji Windows Forms, która prawdopodobnie została utworzona za pomocą Kreatora aplikacji Visual Studio.

Obraz jest reprezentowany przez <xref:System.Drawing.Image> klasę. Dane obrazu są ładowane z pliku jpg przy użyciu <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> metody. Przed narysowaniem obrazu w formularzu zmieniany jest rozmiar formularza w celu dopasowania go do obrazu. Rysowanie obrazu odbywa się przy użyciu <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> metody.

<xref:System.Drawing.Graphics>Klasy i <xref:System.Drawing.Image> są zarówno w <xref:System.Drawing?displayProperty=fullName> przestrzeni nazw.

### <a name="example"></a>Przykład

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override
{
    Graphics^ g = pe->Graphics;
    Image^ image = Image::FromFile("SampleImage.jpg");
    Form::ClientSize = image->Size;
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );
}
```

## <a name="draw-shapes-with-the-net-framework"></a><a name="draw"></a> Rysowanie kształtów za pomocą .NET Framework

Poniższy przykład kodu używa klasy, <xref:System.Drawing.Graphics> Aby zmodyfikować <xref:System.Windows.Forms.Form.OnPaint%2A> procedurę obsługi zdarzeń w celu pobrania wskaźnika do <xref:System.Drawing.Graphics> obiektu w formularzu głównym. Ten wskaźnik służy następnie do ustawiania koloru tła formularza i rysowania linii i łuku przy użyciu <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> <xref:System.Drawing.Graphics.DrawArc%2A> metod i.

### <a name="example"></a>Przykład

```cpp
#using <system.drawing.dll>
using namespace System;
using namespace System::Drawing;
// ...
protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override
{
   Graphics^ g = pe->Graphics;
   g->Clear(Color::AntiqueWhite);

   Rectangle rect = Form::ClientRectangle;
   Rectangle smallRect;
   smallRect.X = rect.X + rect.Width / 4;
   smallRect.Y = rect.Y + rect.Height / 4;
   smallRect.Width = rect.Width / 2;
   smallRect.Height = rect.Height / 2;

   Pen^ redPen = gcnew Pen(Color::Red);
   redPen->Width = 4;
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);

   Pen^ bluePen = gcnew Pen(Color::Blue);
   bluePen->Width = 10;
   g->DrawArc( bluePen, smallRect, 90, 270 );
}
```

## <a name="rotate-images-with-the-net-framework"></a><a name="rotate"></a> Obróć obrazy za pomocą .NET Framework

Poniższy przykład kodu demonstruje użycie <xref:System.Drawing.Image?displayProperty=fullName> klasy do załadowania obrazu z dysku, obrócenie go o 90 stopni i zapisanie go jako nowego pliku jpg.

### <a name="example"></a>Przykład

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );
   image->Save("SampleImage_rotated.jpg");
   return 0;
}
```

## <a name="convert-image-file-formats-with-the-net-framework"></a><a name="convert"></a> Konwertowanie formatów plików obrazów za pomocą .NET Framework

Poniższy przykład kodu demonstruje <xref:System.Drawing.Image?displayProperty=fullName> klasę i <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> Wyliczenie używane do konwertowania i zapisywania plików obrazów. Poniższy kod ładuje obraz z pliku JPG, a następnie zapisuje go w formatach plików GIF i BMP.

### <a name="example"></a>Przykład

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->Save("SampleImage.png", ImageFormat::Png);
   image->Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}
```

## <a name="related-sections"></a>Sekcje pokrewne

[Wprowadzenie do programowania grafiki](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[Informacje o kodzie zarządzanym GDI+](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>Zobacz też

[Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
