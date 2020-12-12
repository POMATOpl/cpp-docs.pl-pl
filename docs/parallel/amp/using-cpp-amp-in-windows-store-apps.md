---
description: 'Dowiedz się więcej o programie: używanie C++ AMP w aplikacjach platformy UWP'
title: Używanie C++ AMP w aplikacjach platformy UWP
ms.date: 11/04/2016
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
ms.openlocfilehash: 91c7b147ff89a1fe19ebe1b18e465533053542d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314480"
---
# <a name="using-c-amp-in-uwp-apps"></a>Używanie C++ AMP w aplikacjach platformy UWP

C++ AMP (C++ Accelerated Massive Parallelism) można używać w aplikacji platforma uniwersalna systemu Windows (platformy UWP) do wykonywania obliczeń na procesorach GPU (jednostkach przetwarzania grafiki) lub innych akceleratorach obliczeniowych. Jednak C++ AMP nie udostępnia interfejsów API do pracy bezpośrednio z typami środowisko wykonawcze systemu Windows, a środowisko wykonawcze systemu Windows nie zapewnia otoki dla C++ AMP. W przypadku używania środowisko wykonawcze systemu Windows typów w kodzie — w tym tych, które zostały utworzone samodzielnie, należy je przekonwertować na typy zgodne z C++ AMP.

## <a name="performance-considerations"></a>Zagadnienia dotyczące wydajności

Jeśli używasz Visual C++ rozszerzeń składników C++/CX do tworzenia aplikacji platforma uniwersalna systemu Windows (platformy UWP), zalecamy używanie typów ze zwykłymi danymi (POD) wraz z ciągłym magazynem (na przykład `std::vector` lub tablicami w stylu C) dla danych, które będą używane z C++ amp. Może to pomóc w osiągnięciu wyższej wydajności niż użycie typów innych niż POD lub kontenerów systemu Windows RT, ponieważ nie ma potrzeby organizowania.

W jądrze C++ AMP, aby uzyskać dostęp do danych przechowywanych w ten sposób, po prostu zawiń `std::vector` Magazyn tablicy lub tablicę w a, `concurrency::array_view` a następnie użyj widoku tablicy w `concurrency::parallel_for_each` pętli:

```cpp
// simple vector addition example
std::vector<int> data0(1024, 1);
std::vector<int> data1(1024, 2);
std::vector<int> data_out(data0.size(), 0);

concurrency::array_view<int, 1> av0(data0.size(), data0);
concurrency::array_view<int, 1> av1(data1.size(), data1);
concurrency::array_view<int, 1> av2(data_out.size(), data2);

av2.discard_data();

concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)
    {
        av2[idx] = av0[idx] + av1[idx];
    });
```

## <a name="marshaling-windows-runtime-types"></a>Szeregowanie typów środowiska wykonawczego systemu Windows

Podczas pracy z środowisko wykonawcze systemu Windows interfejsów API można używać C++ AMP danych przechowywanych w kontenerze środowisko wykonawcze systemu Windows, takim jak `Platform::Array<T>^` lub w złożonych typach danych, takich jak klasy lub struktury, które są zadeklarowane za pomocą słowa kluczowego **ref** lub słowa kluczowego **Value** . W takich sytuacjach należy wykonać kilka dodatkowych czynności w celu udostępnienia danych C++ AMP.

### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform:: Array \<T> ^, gdzie T jest typem pod

Gdy napotkasz `Platform::Array<T>^` i T jest typem pod, możesz uzyskać dostęp do jego magazynu bazowego tylko przy użyciu `get` funkcji składowej:

```cpp
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```

Jeśli T nie jest typu POD, użyj techniki opisanej w poniższej sekcji, aby użyć danych z C++ AMP.

### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Typy środowiska wykonawczego systemu Windows: klasy odniesienia i klasy wartości

C++ AMP nie obsługuje złożonych typów danych. Obejmuje to typy niebędące POD i wszystkie typy, które są zadeklarowane za pomocą słowa kluczowego **ref** lub słowa kluczowego **Value** . Jeśli w kontekście jest używany nieobsługiwany typ `restrict(amp)` , zostanie wygenerowany błąd czasu kompilacji.

Gdy napotkasz nieobsługiwany typ, możesz skopiować interesujące części danych do `concurrency::array` obiektu. Oprócz udostępniania danych do C++ AMP do użycia, takie podejście ręcznego kopiowania może również zwiększyć wydajność dzięki maksymalizacji lokalizacji danych i zapewnieniu, że dane, które nie będą używane, nie są kopiowane do akceleratora. Dodatkowo można poprawić wydajność przy użyciu *tablicy tymczasowej*, która jest specjalną formą, `concurrency::array` która dostarcza wskazówkę do środowiska uruchomieniowego amp, którą Tablica powinna być zoptymalizowana pod kątem częstego transferu między nim a innymi tablicami w określonym akceleratorze.

```cpp
// pixel_color.h
ref class pixel_color sealed
{
public:
    pixel_color(Platform::String^ color_name, int red, int green, int blue)
    {
        name = color_name;
        r = red;
        g = green;
        b = blue;
    }

    property Platform::String^ name;
    property int r;
    property int g;
    property int b;
};

// Some other file

std::vector<pixel_color^> pixels (256);

for (pixel_color ^pixel : pixels)
{
    pixels.push_back(ref new pixel_color("blue", 0, 0, 255));
}

// Create the accelerators
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);

// Create the staging arrays
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);

// Extract data from the complex array of structs into staging arrays.
concurrency::parallel_for(0, 256, [&](int i)
    {
        red_vec[i] = pixels[i]->r;
        blue_vec[i] = pixels[i]->b;
    });

// Array views are still used to copy data to the accelerator
concurrency::array_view<float, 1> av_red(red_vec);
concurrency::array_view<float, 1> av_blue(blue_vec);

// Change all pixels from blue to red.
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)
    {
        av_red[idx] = 255;
        av_blue[idx] = 0;
    });
```

## <a name="see-also"></a>Zobacz też

[Tworzenie pierwszej aplikacji platformy UWP przy użyciu języka C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)<br/>
[Tworzenie składników środowisko wykonawcze systemu Windows w języku C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
