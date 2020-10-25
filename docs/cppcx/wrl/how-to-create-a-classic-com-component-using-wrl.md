---
title: 'Porady: tworzenie klasycznego składnika COM za pomocą biblioteki WRL'
description: Za pomocą środowisko wykonawcze systemu Windows biblioteki szablonów C++ (WRL) można tworzyć podstawowe, klasyczne składniki COM do użycia w aplikacjach klasycznych.
ms.date: 10/23/2020
ms.topic: reference
ms.openlocfilehash: 417c2e4635b380717662fa0762062f0228659de4
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497210"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Porady: tworzenie klasycznego składnika COM za pomocą biblioteki WRL

Za pomocą środowisko wykonawcze systemu Windows biblioteki szablonów C++ (WRL) można tworzyć podstawowe, klasyczne składniki COM do użycia w aplikacjach klasycznych, a także używać ich na potrzeby aplikacji platforma uniwersalna systemu Windows (platformy UWP). Do tworzenia składników modelu COM Biblioteka szablonów języka C++ środowisko wykonawcze systemu Windows może wymagać mniej kodu niż ATL. Aby uzyskać informacje na temat podzbioru modelu COM obsługiwanego przez środowisko wykonawcze systemu Windows biblioteki szablonów C++, zobacz [środowisko wykonawcze systemu Windows biblioteki szablonów c++ (WRL)](windows-runtime-cpp-template-library-wrl.md).

W tym dokumencie przedstawiono sposób korzystania z biblioteki szablonów języka C++ środowisko wykonawcze systemu Windows w celu utworzenia podstawowego składnika modelu COM. Mimo że można użyć mechanizmu wdrażania, który najlepiej odpowiada Twoim potrzebom, ten dokument zawiera również podstawowy sposób rejestrowania i używania składnika COM z poziomu aplikacji klasycznej.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Aby użyć środowisko wykonawcze systemu Windows biblioteki szablonów C++ do utworzenia podstawowego klasycznego składnika COM

1. W programie Visual Studio Utwórz **pusty projekt rozwiązania** . Nazwij projekt, na przykład `WRLClassicCOM` .

2. Dodaj **projekt Win32** do rozwiązania. Nazwij projekt, na przykład `CalculatorComponent` . Na karcie **Ustawienia aplikacji** wybierz pozycję **dll**.

3. Dodaj plik **MIDL (. idl)** do projektu. Nazwij plik, na przykład `CalculatorComponent.idl` .

4. Dodaj ten kod do CalculatorComponent. idl:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. W CalculatorComponent. cpp Zdefiniuj `CalculatorComponent` klasę. `CalculatorComponent`Klasa dziedziczy od [firmy Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md). [Microsoft:: WRL:: RuntimeClassFlags \<ClassicCom> ](runtimeclassflags-structure.md) Określa, że klasa dziedziczy z [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) i nie [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable). ( `IInspectable` jest dostępny tylko dla środowisko wykonawcze systemu Windows składników aplikacji). `CoCreatableClass` tworzy fabrykę dla klasy, która może być używana z funkcjami, takimi jak funkcja [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. Użyj poniższego kodu, aby zamienić kod w `dllmain.cpp` . Ten plik definiuje funkcje eksportu biblioteki DLL. Te funkcje używają klasy [Microsoft:: WRL:: module](module-class.md) do zarządzania fabrykami klas dla modułu.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Dodaj plik **definicji modułu (. def)** do projektu. Nazwij plik, na przykład `CalculatorComponent.def` . Ten plik nadaje konsolidatorowi nazwy funkcji, które mają zostać wyeksportowane. Otwórz okno dialogowe **strony właściwości** dla projektu, a następnie w obszarze **Właściwości konfiguracji**  >  **Wejście konsolidatora**  >  **Input**ustaw właściwość **plik definicji modułu** na plik DEF.

8. Dodaj ten kod do CalculatorComponent. def:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Dodaj środowisko runtimeobject. lib do linii konsolidatora. Aby dowiedzieć się, jak to zrobić, zobacz [ `.Lib` pliki jako dane wejściowe konsolidatora](../../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Aby użyć składnika COM z aplikacji klasycznej

1. Zarejestruj składnik COM przy użyciu rejestru systemu Windows. W tym celu Utwórz plik wpisów rejestracyjnych, nadaj mu nazwę `RegScript.reg` i Dodaj następujący tekst. Zamień na *\<dll-path>* ścieżkę do biblioteki dll — na przykład `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll` .

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. Uruchom plik RegScript. reg lub Dodaj go do **zdarzenia po kompilacji**projektu. Aby uzyskać więcej informacji, zobacz [okno dialogowe zdarzenie przed kompilacją/wiersz polecenia zdarzenia po kompilacji](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).

3. Dodaj projekt **aplikacji konsolowej Win32** do rozwiązania. Nazwij projekt, na przykład `Calculator` .

4. Użyj tego kodu, aby zastąpić zawartość `Calculator.cpp` :

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Niezawodne programowanie

Ten dokument korzysta ze standardowych funkcji COM, aby wykazać, że można użyć biblioteki szablonów języka C++ środowisko wykonawcze systemu Windows do utworzenia składnika modelu COM i udostępnienia go dla dowolnej technologii z obsługą modelu COM. Do zarządzania okresem istnienia modelu COM i innych obiektów można również użyć środowisko wykonawcze systemu Windows typów bibliotek szablonów języka C++, takich jak [Microsoft:: WRL:: ComPtr](comptr-class.md) w aplikacji klasycznej. Poniższy kod używa biblioteki szablonów języka C++ środowisko wykonawcze systemu Windows do zarządzania okresem istnienia `ICalculatorComponent` wskaźnika. `CoInitializeWrapper`Klasa jest otoką RAII, która gwarantuje, że biblioteka com jest zwolniona, a także gwarantuje, że okres istnienia biblioteki com na żywo `ComPtr` obiektu wskaźnika inteligentnego.

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Zobacz też

[Biblioteka szablonów języka C++ środowiska wykonawczego systemu Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)
