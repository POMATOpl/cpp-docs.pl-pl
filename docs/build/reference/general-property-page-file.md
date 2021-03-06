---
description: 'Dowiedz się więcej na temat: ogólna Strona właściwości (plik)'
title: Ogólna strona właściwości (plik)
ms.date: 08/30/2019
f1_keywords:
- VC.Project.VCFileConfiguration.ExcludedFromBuild
- VC.Project.VCFileConfiguration.Tool
ms.assetid: 26e3711e-9e7d-4e8d-bc4c-2474538efdad
ms.openlocfilehash: 03b91a028bce5423bcf80fab24153a36eb7435e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200341"
---
# <a name="general-property-page-file"></a>Ogólna strona właściwości (plik)

Ten temat dotyczy projektów systemu Windows. W przypadku projektów z systemem innym niż Windows Zapoznaj się z informacjami na [stronie właściwości systemu Linux C++](../../linux/prop-pages-linux.md).

Po kliknięciu prawym przyciskiem myszy **Eksplorator rozwiązań** węzła pliku zostanie otwarta strona właściwości **Ogólne** pod węzłem **Właściwości konfiguracji** . Zawiera następujące właściwości:

- **Wykluczone z kompilacji**

   Określa, czy plik powinien być w kompilacji dla bieżącej konfiguracji.

   Aby programowo uzyskać dostęp do tej właściwości, zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.ExcludedFromBuild%2A> .

- **Zawartość** (dotyczy tylko aplikacji platformy UWP). Określa, czy plik zawiera zawartość, która ma zostać uwzględniona w pakiecie aplikacji.

- **Typ elementu**

   **Typ elementu** określa narzędzie, które będzie używane do przetwarzania pliku podczas procesu kompilacji. [Pliki, których rozszerzenie jest znane dla programu Visual Studio](/visualstudio/extensibility/visual-cpp-project-extensibility#project-items) , ma wartość domyślną w tej właściwości. Możesz określić niestandardowe narzędzie w tym miejscu, jeśli masz niestandardowy typ pliku lub chcesz przesłonić domyślne narzędzie dla znanego typu plików. Aby uzyskać więcej informacji, zobacz [Określanie niestandardowych narzędzi kompilacji](../specifying-custom-build-tools.md) . Możesz również użyć tej strony właściwości, aby określić, że plik nie jest częścią procesu kompilacji.

   Na poniższej ilustracji przedstawiono stronę właściwości pliku *. cpp* . Domyślny **Typ elementu** dla tego rodzaju pliku to **kompilator C/C++** (*cl.exe*), a strona właściwości udostępnia różne ustawienia kompilatora, które mogą być stosowane tylko do tego pliku.

   ![Ogólna strona właściwości dla elementu projektu](media/file-general-item-type.png "Opcje typu elementu")

    W poniższej tabeli wymieniono domyślne typy elementów:

    |Rozszerzenie pliku|Typ elementu|Narzędzie domyślne|
    |-|-|-|
    |.appx|Definicja aplikacji XAML|[Pakowarka aplikacji](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. HLSL,. CSO|Kompilator HLSL|[fxc.exe](/windows/win32/direct3dtools/fxc)|
    |. h|Nagłówek C/C++|[Preprocesor języka C/C++](../../preprocessor/c-cpp-preprocessor-reference.md)|
    |n/d|Nie uczestniczy w kompilacji|n/d|
    |. XML,. XSLT,. xsl|Xml|[Edytor XML](/visualstudio/xml-tools/xml-editor)|
    |. resw,. resjson|Zasób PRI (platformy UWP Apps)|[MakePri.exe](/windows/uwp/app-resources/compile-resources-manually-with-makepri)|
    ||Nośnik (platformy UWP)|[Pakowarka aplikacji](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. xsd|Narzędzie Generator danych XML|[Narzędzie definicji schematu XML (Xsd.exe)](/dotnet/standard/serialization/xml-schema-definition-tool-xsd-exe) (wymaga obciążenia .NET). Nie dołączono do MSVC.)|
    ||Narzędzie manifestu|[mt.exe](/windows/win32/sbscs/mt-exe)|
    |. RC|Zasób|[Kompilator zasobów systemu Windows (rc.exe)](/windows/win32/menurc/resource-compiler)|
    |. appxmanifest|Manifest pakietu aplikacji|[Pakowarka aplikacji](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.obj|Obiekt|[Konsolidator C/C++ (link.exe)](cl-invokes-the-linker.md)|
    |. ttf|Czcionka|n/d|
    |txt|Tekst|n/d|
    |n/d|Niestandardowe narzędzie kompilacji|Zdefiniowane przez użytkownika|
    |n/d|Kopiuj plik|n/d|
    |. packagelayout|Układ pakietu aplikacji|[Pakowarka aplikacji](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.resx|Zasób zarządzany przez kompilator|[Resgen.exe (Generator plików zasobów)](/dotnet/framework/tools/resgen-exe-resource-file-generator)|
    |. Natvis|Plik wizualizacji debugera języka C++|[Struktura Natvis](/visualstudio/debugger/create-custom-views-of-native-objects)|
    |. jpg,. bmp,. ico itd.|Obraz|Kompilator zasobów oparty na typie aplikacji.|
    |. cpp|Kompilator C/C++|cl.exe|

   Aby programowo uzyskać dostęp do tej właściwości, zobacz <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.Tool%2A> .

Aby uzyskać informacje na temat uzyskiwania dostępu do strony właściwości **ogólnych** w węźle **Właściwości konfiguracji** , zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>Zobacz też

[Odwołanie do strony właściwości projektu C++](property-pages-visual-cpp.md)
