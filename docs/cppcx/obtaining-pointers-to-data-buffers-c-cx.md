---
description: 'Dowiedz się więcej o: uzyskiwanie wskaźników do buforów danych (C++/CX)'
title: Uzyskiwanie wskaźników do buforów danych (C++/CX)
ms.date: 11/19/2018
ms.assetid: db4f9370-dd95-4896-b5b8-4b202284f579
ms.openlocfilehash: d4fc883d7a7d0bae5d72c6aabd42446c74162c42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328941"
---
# <a name="obtaining-pointers-to-data-buffers-ccx"></a>Uzyskiwanie wskaźników do buforów danych (C++/CX)

W środowisko wykonawcze systemu Windows interfejs [Windows:: Storage:: Streams:: IBuffer](/uwp/api/windows.storage.streams.ibuffer) udostępnia niezależny od języka sposób, aby uzyskać dostęp do buforów danych. W języku C++ można uzyskać surowy wskaźnik do tablicy bazowego bajtowego przy użyciu interfejsu IBufferByteAccess biblioteki środowisko wykonawcze systemu Windows, który jest zdefiniowany w robuffer. h. Korzystając z tej metody, można zmodyfikować w miejscu tablicę bajtową bez wprowadzania żadnych niepotrzebnych kopii danych.

Na poniższym diagramie przedstawiono element obrazu XAML, którego źródłem jest obiekt [Windows:: UI:: XAML:: Media:: Imaging WriteableBitmap](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap). Aplikacja kliencka, która jest zapisywana w dowolnym języku, może przekazać odwołanie do `WriteableBitmap` kodu języka c++, a następnie w języku c++ można użyć odwołania, aby uzyskać dostęp do źródłowego buforu. W aplikacji platforma uniwersalna systemu Windows, która jest zapisywana w języku C++, można użyć funkcji w poniższym przykładzie bezpośrednio w kodzie źródłowym bez pakowania go w składniku środowisko wykonawcze systemu Windows.

![Kod języka C&#43;&#43; , który uzyskuje dostęp do danych pikseli bezpośrednio](../cppcx/media/ibufferbyteaccessdiagram.png "Kod języka C&#43;&#43; , który uzyskuje dostęp do danych pikseli bezpośrednio")

## <a name="getpointertopixeldata"></a>GetPointerToPixelData

Poniższa metoda akceptuje obiekt [Windows:: Storage:: Streams:: IBuffer](/uwp/api/windows.storage.streams.ibuffer) i zwraca surowy wskaźnik do bazowej tablicy bajtów. Aby wywołać funkcję, należy przekazać Właściwość [WriteableBitmap::P ixelbuffer](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap.pixelbuffer) .

```cpp
#include <wrl.h>
#include <robuffer.h>
using namespace Windows::Storage::Streams;
using namespace Microsoft::WRL;
typedef uint8 byte;
// Retrieves the raw pixel data from the provided IBuffer object.
// Warning: The lifetime of the returned buffer is controlled by
// the lifetime of the buffer object that's passed to this method.
// When the buffer has been released, the pointer becomes invalid
// and must not be used.
byte* Class1::GetPointerToPixelData(IBuffer^ pixelBuffer, unsigned int *length)
{
    if (length != nullptr)
    {
        *length = pixelBuffer ->Length;
    }
    // Query the IBufferByteAccess interface.
    ComPtr<IBufferByteAccess> bufferByteAccess;
    reinterpret_cast<IInspectable*>( pixelBuffer)->QueryInterface(IID_PPV_ARGS(&bufferByteAccess));

    // Retrieve the buffer data.
    byte* pixels = nullptr;
    bufferByteAccess->Buffer(&pixels);
    return pixels;
}
```

## <a name="complete-example"></a>Kompletny przykład

W poniższych krokach pokazano, jak utworzyć aplikację w języku C# platforma uniwersalna systemu Windows, która przekazuje `WriteableBitmap` do biblioteki DLL składnika Środowisko wykonawcze systemu Windows języka C++. Kod C++ uzyskuje wskaźnik do buforu pikseli i wykonuje prostą modyfikację obrazu w miejscu. Alternatywnie możesz utworzyć aplikację kliencką w Visual Basic, JavaScript lub C++ zamiast języka C#. Jeśli używasz języka C++, nie potrzebujesz biblioteki DLL składnika. można po prostu dodać te metody bezpośrednio do klasy MainPage lub innej zdefiniowanej klasy.

#### <a name="create-the-client"></a>Tworzenie klienta

1. Użyj szablonu projektu pustej aplikacji, aby utworzyć aplikację platforma uniwersalna systemu Windows w języku C#.

1. W MainPage. XAML

   - Użyj tego kodu XAML, aby zamienić `Grid` element:

        ```xml
        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <StackPanel HorizontalAlignment="Left" Margin="176,110,0,0" VerticalAlignment="Top" Width="932">
                <Image x:Name="Pic"/>
                <Button Content="Process Image" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Height="47" Click="Button_Click_1"/>
            </StackPanel>
        </Grid>
        ```

1. W MainPage.xaml.cs

   1. Dodaj następujące deklaracje przestrzeni nazw:

        ```csharp
        using Windows.Storage;
        using Windows.Storage.FileProperties;
        using Windows.UI.Xaml.Media.Imaging;
        using Windows.Storage.Streams;
        using Windows.Storage.Pickers;
        ```

   1. Dodaj `WriteableBitmap` zmienną członkowską do `MainPage` klasy i nadaj jej nazwę `m_bm` .

        ```csharp
        private WriteableBitmap m_bm;
        ```

   1. Użyj poniższego kodu, aby zastąpić `OnNavigatedTo` metodę zastępczą metody. Spowoduje to otwarcie selektora plików podczas uruchamiania aplikacji. (Należy zauważyć, że `async` słowo kluczowe jest dodawane do sygnatury funkcji).

        ```csharp
        async protected override void OnNavigatedTo(NavigationEventArgs e)
        {
            FileOpenPicker openPicker = new FileOpenPicker();
            openPicker.ViewMode = PickerViewMode.Thumbnail;
            openPicker.SuggestedStartLocation = PickerLocationId.PicturesLibrary;
            openPicker.FileTypeFilter.Add(".jpg");
            openPicker.FileTypeFilter.Add(".jpeg");
            openPicker.FileTypeFilter.Add(".png");

            StorageFile file = await openPicker.PickSingleFileAsync();
            if (file != null)
            {
                // Get the size of the image for the WriteableBitmap constructor.
                ImageProperties props = await file.Properties.GetImagePropertiesAsync();
                m_bm = new WriteableBitmap((int)props.Height, (int)props.Width);
                m_bm.SetSource(await file.OpenReadAsync());
                Pic.Source = m_bm;
            }
            else
            {
                //  Handle error...
            }
        }
        ```

   1. Dodaj procedurę obsługi zdarzeń dla przycisku. (Ponieważ `ImageManipCPP` odwołanie do przestrzeni nazw nie zostało jeszcze utworzone, może mieć podkreślenie faliste w oknie edytora).

        ```csharp
        async private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            ImageManipCPP.Class1 obj = new ImageManipCPP.Class1();
            await obj.Negativize(m_bm);
            Pic.Source = m_bm;
        }
        ```

#### <a name="create-the-c-component"></a>Tworzenie składnika C++

1. Dodaj nowy składnik C++ środowisko wykonawcze systemu Windows do istniejącego rozwiązania i nadaj mu nazwę `ImageManipCPP` . Dodaj odwołanie do niego w projekcie C#, klikając prawym przyciskiem myszy projekt w **Eksplorator rozwiązań** i wybierając polecenie **Dodaj**, **odwołanie**.

1. W Class1. h

   1. Dodaj ją **`typedef`** w drugim wierszu po `#pragma once` :

        ```cpp
        typedef uint8 byte;
        ```

   1. Dodaj `WebHostHidden` atrybut tuż powyżej początku `Class1` deklaracji.

        ```cpp
        [Windows::Foundation::Metadata::WebHostHidden]
        ```

   1. Dodaj ten podpis metody publicznej do `Class1` :

        ```cpp
        Windows::Foundation::IAsyncAction^ Negativize(Windows::UI::Xaml::Media::Imaging::WriteableBitmap^ bm);
        ```

   1. Dodaj podpis z `GetPointerToPixelData` metody, która jest wyświetlana we wcześniejszym fragmencie kodu. Upewnij się, że ta metoda jest prywatna.

1. W Class1. cpp

   1. Dodaj te `#include` dyrektywy i deklaracje przestrzeni nazw:

        ```cpp
        #include <ppltasks.h>
        #include <wrl.h>
        #include <robuffer.h>

        using namespace Windows::Storage;
        using namespace Windows::UI::Xaml::Media::Imaging;
        using namespace Windows::Storage::Streams;
        using namespace Microsoft::WRL;
        ```

   1. Dodaj implementację `GetPointerToPixelData` z wcześniejszego fragmentu kodu.

   1. Dodaj implementację programu `Negativize` . Ta metoda tworzy efekt, który przypomina folię ujemną przez odwrócenie wartości każdej wartości RGB w pikselu. Tworzymy metodę asynchroniczną, ponieważ w większych obrazach może upłynąć dużo czasu.

        ```cpp
        IAsyncAction^ Class1::Negativize(WriteableBitmap^ bm)
        {
            unsigned int length;
            byte* sourcePixels = GetPointerToPixelData(bm->PixelBuffer, &length);
            const unsigned int width = bm->PixelWidth;
            const unsigned int height = bm->PixelHeight;

            return create_async([this, width, height, sourcePixels]
            {
                byte* temp = sourcePixels;
                for(unsigned int k = 0; k < height; k++)
                {
                    for (unsigned int i = 0; i < (width * 4); i += 4)
                    {
                        int pos = k * (width * 4) + (i);
                        temp[pos] = ~temp[pos];
                        temp[pos + 1] = ~temp[pos + 1] / 3;
                        temp[pos + 2] = ~temp[pos + 2] / 2;
                        temp[pos + 3] = ~temp[pos + 3];
                    }
                }
            });

        }
        ```

      > [!NOTE]
      > Ta metoda może działać szybciej, jeśli do zrównoleglanie operacji użyto biblioteki AMP lub równoległych wzorców.

1. Upewnij się, że masz co najmniej jeden obraz w folderze Obrazy, a następnie naciśnij klawisz F5, aby skompilować i uruchomić program.
