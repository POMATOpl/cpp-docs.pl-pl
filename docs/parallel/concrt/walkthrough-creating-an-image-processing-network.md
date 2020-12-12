---
description: 'Dowiedz się więcej na temat: Przewodnik: tworzenie sieci Image-Processing'
title: 'Wskazówki: tworzenie sieci przetwarzania obrazów'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 1cdd94d6cad6ee76c02b7eb2cf8b4ca38a53fa96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169310"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>Wskazówki: tworzenie sieci przetwarzania obrazów

W tym dokumencie przedstawiono sposób tworzenia sieci asynchronicznych bloków komunikatów, które wykonują przetwarzanie obrazu.

Sieć określa, które operacje wykonać na obrazie na podstawie jego właściwości. W tym przykładzie zastosowano model *przepływu danych* do przesyłania obrazów za pośrednictwem sieci. W modelu przepływu danych niezależne składniki programu komunikują się ze sobą przez wysyłanie komunikatów. Gdy składnik odbiera komunikat, może wykonać pewne działania, a następnie przekazać wynik tej akcji do innego składnika. Porównaj ten element z modelem *przepływu sterowania* , w którym aplikacja używa struktur kontroli, na przykład instrukcji warunkowych, pętli i tak dalej, aby kontrolować kolejność operacji w programie.

Sieć oparta na przepływu danych tworzy *potok* zadań. Każdy etap potoku jednocześnie wykonuje część ogólnego zadania. Analogicznie do tego jest linia montażowa dla produkcji samochodów. Gdy każdy pojazd przechodzi przez linię zestawu, jedna stacja składa się z ramki, drugi instaluje aparat i tak dalej. Dzięki umożliwieniu jednoczesnego montażu wielu pojazdów, linia zestawu zapewnia lepszą przepływność niż Montaż kompletnych pojazdów pojedynczo.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem tego instruktażu zapoznaj się z następującymi dokumentami:

- [Bloki komunikatów asynchronicznych](../../parallel/concrt/asynchronous-message-blocks.md)

- [Instrukcje: korzystanie z filtru bloku komunikatów](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [Przewodnik: tworzenie agenta przepływu danych](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Zalecamy także zapoznanie się z podstawą interfejsu GDI+ przed rozpoczęciem tego instruktażu.

## <a name="sections"></a><a name="top"></a> Poszczególne

Ten Instruktaż zawiera następujące sekcje:

- [Definiowanie funkcji przetwarzania obrazów](#functionality)

- [Tworzenie sieci przetwarzania obrazów](#network)

- [Kompletny przykład](#complete)

## <a name="defining-image-processing-functionality"></a><a name="functionality"></a> Definiowanie funkcji przetwarzania obrazów

W tej sekcji przedstawiono funkcje obsługi, które są używane przez sieć przetwarzania obrazu do pracy z obrazami odczytywanymi z dysku.

Poniższe funkcje `GetRGB` oraz `MakeColor` wyodrębnią i łączą poszczególne składniki danego koloru.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Poniższa funkcja, `ProcessImage` wywołuje dany obiekt [std:: Function](../../standard-library/function-class.md) , aby przekształcić wartość koloru każdego piksela w obiekcie [mapy bitowej](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) GDI+. `ProcessImage`Funkcja używa algorytmu [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) , aby przetwarzać każdy wiersz mapy bitowej równolegle.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

Poniższe funkcje, `Grayscale` ,, `Sepiatone` `ColorMask` i `Darken` , wywołują `ProcessImage` funkcję w celu przekształcenia wartości koloru każdego piksela w `Bitmap` obiekcie. Każda z tych funkcji używa wyrażenia lambda do definiowania przekształcenia koloru jednego piksela.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Poniższa funkcja, `GetColorDominance` , również wywołuje `ProcessImage` funkcję. Jednak zamiast zmieniać wartości każdego koloru, ta funkcja używa obiektów [concurrency::Binding](../../parallel/concrt/reference/combinable-class.md) do obliczenia, czy składnik koloru czerwony, zielony lub niebieski jest zdominowany.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Poniższa funkcja, `GetEncoderClsid` Pobiera identyfikator klasy dla danego typu MIME kodera. Aplikacja używa tej funkcji do pobierania kodera dla mapy bitowej.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[Top](#top)]

## <a name="creating-the-image-processing-network"></a><a name="network"></a> Tworzenie sieci przetwarzania obrazów

W tej sekcji opisano sposób tworzenia sieci asynchronicznych bloków komunikatów, które wykonują przetwarzanie obrazu na każdym obrazie JPEG (. jpg) w danym katalogu. Sieć wykonuje następujące operacje związane z przetwarzaniem obrazów:

1. Dla każdego obrazu, który jest tworzony przez Tomasz, Konwertuj na skalę szarości.

1. Dla każdego obrazu, który ma kolor czerwony, należy usunąć składniki zielone i niebieskie, a następnie przyciemnić je.

1. W przypadku innych obrazów Zastosuj Sepia Toning.

Sieć stosuje tylko pierwsze operacje przetwarzania obrazu, które pasują do jednego z tych warunków. Na przykład, jeśli obraz jest tworzony przez Tomasz i ma kolor czerwony w kolorze dominującym, obraz jest konwertowany tylko na skalę szarości.

Gdy sieć wykonuje każdą operację przetwarzania obrazu, zapisuje obraz na dysku jako plik mapy bitowej (. bmp).

Poniższe kroki pokazują, jak utworzyć funkcję implementującą tę sieć przetwarzania obrazów i zastosować tę sieć do każdego obrazu JPEG w danym katalogu.

#### <a name="to-create-the-image-processing-network"></a>Aby utworzyć sieć przetwarzania obrazów

1. Utwórz funkcję, `ProcessImages` która pobiera nazwę katalogu na dysku.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. W `ProcessImages` funkcji Utwórz `countdown_event` zmienną. `countdown_event`Klasa jest pokazana w dalszej części tego przewodnika.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Utwórz obiekt [std:: map](../../standard-library/map-class.md) , który kojarzy `Bitmap` obiekt z jego pierwotną nazwą pliku.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Dodaj następujący kod w celu zdefiniowania elementów członkowskich sieci przetwarzania obrazów.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Dodaj następujący kod, aby połączyć sieć.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Dodaj następujący kod, aby wysłać do szefa sieci pełna ścieżka każdego pliku JPEG w katalogu.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. Poczekaj, aż `countdown_event` zmienna osiągnie wartość zero.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

W poniższej tabeli opisano elementy członkowskie sieci.

|Członek|Opis|
|------------|-----------------|
|`load_bitmap`|Obiekt [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) ładujący `Bitmap` obiekt z dysku i dodaje wpis do `map` obiektu w celu skojarzenia obrazu z jego pierwotną nazwą pliku.|
|`loaded_bitmaps`|Obiekt [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) , który wysyła załadowane obrazy do filtrów przetwarzania obrazu.|
|`grayscale`|`transformer`Obiekt, który konwertuje obrazy, które są tworzone przez Tomasz do skali szarości. Używa metadanych obrazu w celu określenia jego autora.|
|`colormask`|`transformer`Obiekt, który usuwa zieloną i niebieską składową koloru z obrazów, które mają kolor czerwony.|
|`darken`|`transformer`Obiekt, który ciemnieje obrazy, które są czerwone jako kolor dominujący.|
|`sepiatone`|`transformer`Obiekt, który stosuje Sepia Toning do obrazów, które nie są tworzone przez Tomasz i nie są w przeważającej stopniu czerwone.|
|`save_bitmap`|`transformer`Obiekt, który zapisuje przetworzoną `image` na dysk jako mapę bitową. `save_bitmap` Pobiera oryginalną nazwę pliku z `map` obiektu i zmienia rozszerzenie nazwy pliku na BMP.|
|`delete_bitmap`|`transformer`Obiekt, który zwalnia pamięć dla obrazów.|
|`decrement`|Obiekt [concurrency:: Call](../../parallel/concrt/reference/call-class.md) , który działa jako węzeł terminalu w sieci. Zmniejsza on obiekt, `countdown_event` Aby sygnalizować główną aplikację, że obraz został przetworzony.|

`loaded_bitmaps`Bufor komunikatów jest ważny, ponieważ, jako `unbounded_buffer` obiekt, oferuje `Bitmap` obiekty dla wielu odbiorników. Gdy blok docelowy akceptuje `Bitmap` obiekt, `unbounded_buffer` obiekt nie oferuje tego `Bitmap` obiektu innym obiektom docelowym. W związku z tym kolejność obiektów połączonych z `unbounded_buffer` obiektem jest ważna. `grayscale`, `colormask` , I `sepiatone` blokują każdy używa filtru, aby akceptować tylko niektóre `Bitmap` obiekty. `decrement`Bufor komunikatów jest ważnym elementem docelowym `loaded_bitmaps` buforu komunikatów, ponieważ akceptuje wszystkie `Bitmap` obiekty odrzucone przez pozostałe bufory komunikatów. `unbounded_buffer`Obiekt jest wymagany do propagowania komunikatów w określonej kolejności. W związku z tym `unbounded_buffer` obiekt jest blokowany do momentu, gdy nowy blok docelowy zostanie połączony z nim i akceptuje komunikat, jeśli żaden blok docelowy nie akceptuje tego komunikatu.

Jeśli aplikacja wymaga, aby wiele bloków komunikatów przetworzył komunikat, a nie tylko jeden blok komunikatów, który najpierw akceptuje komunikat, można użyć innego typu bloku komunikatów, takiego jak `overwrite_buffer` . `overwrite_buffer`Klasa przechowuje jeden komunikat w danym momencie, ale propaguje ten komunikat do każdego z jego obiektów docelowych.

Na poniższej ilustracji przedstawiono sieć przetwarzania obrazów:

![Sieć przetwarzania obrazów](../../parallel/concrt/media/concrt_imageproc.png "Sieć przetwarzania obrazów")

`countdown_event`Obiekt w tym przykładzie umożliwia sieci przetwarzania obrazu informowanie głównej aplikacji o przetworzeniu wszystkich obrazów. `countdown_event`Klasa używa obiektu [concurrency:: Event](../../parallel/concrt/reference/event-class.md) do sygnalizowania, gdy wartość licznika osiągnie zero. Główna aplikacja zwiększa licznik za każdym razem, gdy wysyła nazwę pliku do sieci. Węzeł terminalu sieci zmniejsza licznik po przetworzeniu każdego obrazu. Gdy aplikacja główna przejdzie do określonego katalogu, czeka na `countdown_event` obiekt, aby sygnalizować, że jego licznik osiągnął wartość zerową.

W poniższym przykładzie pokazano `countdown_event` klasę:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[Top](#top)]

## <a name="the-complete-example"></a><a name="complete"></a> Kompletny przykład

Poniższy kod przedstawia kompletny przykład. `wmain`Funkcja zarządza biblioteką GDI+ i wywołuje funkcję, `ProcessImages` Aby przetwarzać pliki JPEG w `Sample Pictures` katalogu.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

Na poniższej ilustracji przedstawiono przykładowe dane wyjściowe. Każdy obraz źródłowy znajduje się powyżej odpowiadającego mu zmodyfikowanego obrazu.

![Przykładowe dane wyjściowe dla przykładu](../../parallel/concrt/media/concrt_imageout.png "Przykładowe dane wyjściowe dla przykładu")

`Lighthouse` jest tworzony przez Tomasz Alphin i w związku z tym jest konwertowany na skalę szarości. `Chrysanthemum`, `Desert` , `Koala` , i `Tulips` mają kolor czerwony w kolorze dominującym i dlatego mają usunięte składniki Blue i Green koloru i są przyciemnione. `Hydrangeas`, `Jellyfish` i `Penguins` są zgodne z kryteriami domyślnymi i dlatego są Sepia toned.

[[Top](#top)]

### <a name="compiling-the-code"></a>Kompilowanie kodu

Skopiuj przykładowy kod i wklej go w projekcie programu Visual Studio lub wklej go w pliku o nazwie, `image-processing-network.cpp` a następnie uruchom następujące polecenie w oknie wiersza polecenia programu Visual Studio.

**cl.exe/DUNICODE/EHsc Image-Processing-Network. cpp/link Gdiplus. lib**

## <a name="see-also"></a>Zobacz też

[Instruktaże środowisko uruchomieniowe współbieżności](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
