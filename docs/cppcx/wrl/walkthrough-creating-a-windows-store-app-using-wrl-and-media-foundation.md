---
title: 'Przewodnik: Tworzenie aplikacji platformy uniwersalnej systemu Windows z użyciem biblioteki WRL i platformy Media Foundation'
ms.date: 04/23/2019
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: fecfc83e674c418a920e3dd73149f4d6294090fa
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404928"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>Przewodnik: Tworzenie aplikacji platformy uniwersalnej systemu Windows z użyciem biblioteki WRL i platformy Media Foundation

> [!NOTE]
> W przypadku nowych aplikacji i składników platformy UWP zaleca się używanie [języka c++/WinRT](/windows/uwp/cpp-and-winrt-apis/), nowego standardowego języka c++ 17 dla środowisko wykonawcze systemu Windows interfejsów API. C++/WinRT jest dostępna w zestawie SDK systemu Windows 10 w wersji 1803. Język C++/WinRT jest implementowany całkowicie w plikach nagłówkowych i został zaprojektowany w celu zapewnienia pierwszej klasy dostępu do nowoczesnego interfejsu API systemu Windows.

W ramach tego samouczka nauczysz się środowisko wykonawcze systemu Windows używać biblioteki szablonów języka C++ (WRL) do tworzenia aplikacji platforma uniwersalna systemu Windows (platformy UWP), która używa [Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk).

W tym przykładzie tworzony jest niestandardowy platforma Media Foundation przekształcania, która stosuje efekt skali odcieni szarości do obrazów przechwytywanych z kamery internetowej. Aplikacja używa języka C++ do definiowania przekształcenia niestandardowego i języka C# do przekształcania przechwyconych obrazów przy użyciu składnika.

> [!NOTE]
> Zamiast języka C#, można również użyć języka JavaScript, Visual Basic lub C++ do użycia składnika transformacji niestandardowej.

W większości przypadków można użyć języka C++/CX do tworzenia środowisko wykonawcze systemu Windows. Jednak czasami trzeba używać WRL. Na przykład podczas tworzenia rozszerzenia multimediów dla Microsoft Media Foundation należy utworzyć składnik implementujący interfejsy COM i środowisko wykonawcze systemu Windows. Ponieważ C++/CX może tworzyć tylko obiekty środowisko wykonawcze systemu Windows, aby utworzyć rozszerzenie multimediów, należy użyć WRL, ponieważ umożliwia implementację zarówno interfejsów COM, jak i środowisko wykonawcze systemu Windows.

> [!NOTE]
> Mimo że ten przykład kodu jest długi, pokazuje minimum, co jest wymagane do utworzenia przydatnego przekształcenia platforma Media Foundation. Można go użyć jako punktu wyjścia dla własnego przekształcenia niestandardowego. Ten przykład został dostosowany z [przykładu rozszerzeń nośników](https://github.com/Microsoft/VCSamples/tree/master/VC2012Samples/Windows%208%20samples/C%2B%2B/Windows%208%20app%20samples), który używa rozszerzeń nośników do zastosowania efektów do wideo, dekodowania wideo i tworzenia programów obsługi schematów, które generują strumienie multimediów.

## <a name="prerequisites"></a>Wymagania wstępne

- W programie Visual Studio 2017 i nowszych platformy UWP jest to opcjonalny składnik. Aby go zainstalować, Otwórz Instalator programu Visual Studio z menu Start systemu Windows i Znajdź swoją wersję programu Visual Studio. Wybierz **Modyfikuj** , a następnie upewnij się, że jest zaznaczony kafelek **programowanie platforma uniwersalna systemu Windows** . W obszarze **Opcjonalne składniki** Sprawdź **Narzędzia C++ Tools for platformy UWP (najnowsze 141)** dla programu Visual Studio 2017 lub **c++ Tools for platformy UWP (V142)** dla programu Visual Studio 2019. Następnie sprawdź wersję Windows SDK, która ma być używana.

- Środowisko pracy z [środowisko wykonawcze systemu Windows](/uwp/api/).

- Środowisko pracy z modelem COM.

- Kamera internetowa.

## <a name="key-points"></a>Kwestie kluczowe

- Aby utworzyć niestandardowy składnik platforma Media Foundation, użyj pliku definicji Microsoft Interface Definition Language (MIDL) w celu zdefiniowania interfejsu, zaimplementuj ten interfejs, a następnie ustaw go jako aktywowalnej z innych składników.

- `namespace`Atrybuty i `runtimeclass` i `NTDDI_WIN8` wartość atrybutu [Version](/windows/win32/Midl/version) są ważnymi częściami definicji MIDL dla składnika Platforma Media Foundation, który korzysta z WRL.

- [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md) jest klasą bazową niestandardowego składnika Platforma Media Foundation. Wartość wyliczenia [Microsoft:: WRL:: RuntimeClassType —:: WinRtClassicComMix](runtimeclasstype-enumeration.md) , która jest dostarczana jako argument szablonu, oznacza klasę do użycia zarówno jako Klasa środowisko wykonawcze systemu Windows, jak i dla klasycznej klasy środowiska uruchomieniowego com.

- Makro [InspectableClass](inspectableclass-macro.md) implementuje podstawowe funkcje com, takie jak zliczanie odwołań i `QueryInterface` Metoda, i ustawia nazwę klasy środowiska uruchomieniowego i poziom zaufania.

- Użyj klasy Microsoft:: WRL::[module](module-class.md) , aby zaimplementować funkcje punktu wejścia biblioteki DLL, takie jak [DllGetActivationFactory](/windows/win32/winrt/functions), [DllCanUnloadNow](/windows/win32/api/combaseapi/nf-combaseapi-dllcanunloadnow)i [DllGetClassObject](/windows/win32/api/combaseapi/nf-combaseapi-dllgetclassobject).

- Połącz bibliotekę DLL ze składnikiem runtimeobject. lib. Należy także określić [/winmd](../../cppcx/compiler-and-linker-options-c-cx.md) w linii konsolidatora, aby wygenerować metadane systemu Windows.

- Użyj odwołań projektu, aby udostępnić składniki WRL dla aplikacji platformy UWP.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>Aby użyć WRL do utworzenia składnika przekształcenia platforma Media Foundation w skali odcieni szarości

1. W programie Visual Studio Utwórz **pusty projekt rozwiązania** . Nazwij projekt, na przykład *MediaCapture*.

1. Dodaj projekt **dll (uniwersalny system Windows)** do rozwiązania. Nazwij projekt, na przykład *GrayscaleTransform*.

1. Dodaj plik **MIDL (. idl)** do projektu. Nazwij plik, na przykład *GrayscaleTransform. idl*.

1. Dodaj ten kod do GrayscaleTransform. idl:

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. Użyj następującego kodu, aby zamienić zawartość `pch.h` :

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. Dodaj nowy plik nagłówkowy do projektu, nadaj mu nazwę `BufferLock.h` , a następnie zastąp zawartość tym kodem:

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h`nie jest używany w tym przykładzie. Jeśli chcesz, możesz usunąć go z projektu.

1. Użyj następującego kodu, aby zamienić zawartość `GrayscaleTransform.cpp` :

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. Dodaj nowy plik definicji modułu do projektu, nadaj mu nazwę `GrayscaleTransform.def` , a następnie Dodaj następujący kod:

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. Użyj następującego kodu, aby zamienić zawartość `dllmain.cpp` :

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. W oknie dialogowym **strony właściwości** projektu ustaw następujące właściwości **konsolidatora** .

   1. W obszarze **dane wejściowe**dla **pliku definicji modułu**Określ `GrayScaleTransform.def` .

   1. Również w obszarze **dane wejściowe**, Dodaj `runtimeobject.lib` , `mfuuid.lib` i `mfplat.lib` do właściwości **dodatkowe zależności** .

   1. W obszarze **metadane systemu Windows**ustaw opcję **Generuj metadane systemu Windows** na **wartość tak (/WinMD)**.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>Aby użyć składnika WRL Custom platforma Media Foundation z poziomu aplikacji C#

1. Dodaj do rozwiązania nowy projekt **aplikacji w języku C# (uniwersalny system Windows)** `MediaCapture` . Nazwij projekt, na przykład *MediaCapture*.

1. W projekcie **MediaCapture** Dodaj odwołanie do `GrayscaleTransform` projektu. Aby dowiedzieć się, jak to zrobić, zobacz [How to: Dodawanie lub usuwanie odwołań za pomocą Menedżera odwołań](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. W programie `Package.appxmanifest` na karcie **możliwości** wybierz pozycję **mikrofon** i **kamera internetowa**. Obie funkcje są wymagane do przechwytywania zdjęć z kamery internetowej.

1. W programie `MainPage.xaml` Dodaj ten kod do głównego elementu [siatki](/uwp/api/windows.ui.xaml.controls.grid) :

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. Użyj następującego kodu, aby zamienić zawartość `MainPage.xaml.cs` :

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

Na poniższej ilustracji przedstawiono `MediaCapture app` .

![Aplikacja MediaCapture przechwytująca zdjęcie](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>Następne kroki

W przykładzie pokazano, jak przechwytywać fotografie z domyślnej kamery internetowej po jednym naraz. [Przykład rozszerzeń multimediów](https://github.com/Microsoft/VCSamples/tree/master/VC2012Samples/Windows%208%20samples/C%2B%2B/Windows%208%20app%20samples) wykonuje więcej. Przedstawiono w nim sposób wyliczania urządzeń z kamerą internetową i pracy z programem obsługi schematów lokalnych oraz zademonstrowanie dodatkowych efektów multimedialnych, które działają zarówno w przypadku poszczególnych zdjęć, jak i strumieni wideo.

## <a name="see-also"></a>Zobacz też

[Biblioteka szablonów języka C++ środowiska wykonawczego systemu Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/win32/medfound/microsoft-media-foundation-sdk)
