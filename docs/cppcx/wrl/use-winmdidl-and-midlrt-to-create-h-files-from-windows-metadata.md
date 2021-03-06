---
description: 'Dowiedz się więcej na temat: jak używać winmdidl.exe i midlrt.exe do tworzenia plików. h z metadanych systemu Windows'
title: 'Instrukcje: Użycie winmdidl.exe i midlrt.exe w celu utworzenia plików .h z metadanych systemu Windows'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
ms.openlocfilehash: be76f0cb898017c575356f90fcd043f987a0dbad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209259"
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Instrukcje: Użycie winmdidl.exe i midlrt.exe w celu utworzenia plików .h z metadanych systemu Windows

Winmdidl.exe i midlrt.exe Włącz interakcje na poziomie COM między natywnym kodem C++ i składnikami środowisko wykonawcze systemu Windows. Winmdidl.exe przyjmuje jako wejściowy plik WinMD zawierający metadane dla składnika środowisko wykonawcze systemu Windows i wyprowadza plik IDL. Midlrt.exe konwertuje ten plik IDL na pliki nagłówkowe, które mogą być używane przez kod języka C++. Oba narzędzia działają w wierszu polecenia.

Te narzędzia są używane w dwóch głównych scenariuszach:

- Tworzenie niestandardowych plików IDL i nagłówków w taki sposób, aby aplikacja C++ zapisywana przy użyciu biblioteki szablonów środowisko wykonawcze systemu Windows (WRL) mogła korzystać z niestandardowego składnika środowisko wykonawcze systemu Windows.

- Generowanie plików proxy i szczątków dla typów zdarzeń zdefiniowanych przez użytkownika w składniku środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [zdarzenia niestandardowe i metody dostępu do zdarzeń w składnikach środowisko wykonawcze systemu Windows](/windows/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components).

Te narzędzia są wymagane tylko do analizowania niestandardowych plików WinMD. Pliki. idl i. h dla składników systemu operacyjnego Windows zostały już wygenerowane. Domyślnie w Windows 8.1 znajdują się one w folderze \Program Files (x86) \Windows Kits\8.1\Include\winrt \\ .

## <a name="location-of-the-tools"></a>Lokalizacja narzędzi

Domyślnie w [Windows 8.1, winmdidl.exe i midlrt.exe znajdują się w folderze C:\Program Files (x86) \Windows Kits\8.1 \\ . Wersje narzędzi są również dostępne w folderach \bin\x86\ i \bin\x64\.

## <a name="winmdidl-command-line-arguments"></a>Winmdidl argumenty wiersza polecenia

```
Winmdidl.exe [/nologo] [/suppressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile
```

**/nologo**<br/>
Zapobiega wyświetlaniu przez konsolę komunikatu o prawach autorskich winmdidl i numer wersji.

**/suppressversioncheck**<br/>
Nie używany.

**/Time**<br/>
Wyświetla łączny czas wykonywania w danych wyjściowych konsoli.

**/OutDir:**<em>dir</em><br/>
Określa katalog wyjściowy. Jeśli ścieżka zawiera spacje, użyj cudzysłowów. Domyślny katalog wyjściowy to *\<drive>* : \Users \\ *\<username>* \AppData\Local\VirtualStore\Program Files (x86) \microsoft Visual Studio 12,0 \\ .

**/banner:**<em>plik</em><br/>
Określa plik, który zawiera niestandardowy tekst do dołączania do domyślnego komunikatu o prawach autorskich i numer wersji winmdidl w górnej części wygenerowanego pliku IDL. Jeśli ścieżka zawiera spacje, użyj cudzysłowów.

**/utf8**<br/>
Powoduje, że plik jest sformatowany jako UTF-8.

*Winmd*<br/>
Nazwa pliku winmd do przeanalizowania. Jeśli ścieżka zawiera spacje, użyj cudzysłowów.

## <a name="midlrt-command-line-arguments"></a>Midlrt argumenty wiersza polecenia

Zobacz [midlrt i składniki Środowisko wykonawcze systemu Windows](/windows/win32/Midl/midlrt-and-windows-runtime-components).

## <a name="examples"></a>Przykłady

Poniższy przykład przedstawia polecenie winmdidl w wierszu polecenia programu Visual Studio x86. Określa katalog wyjściowy, a plik zawierający specjalny tekst transparentu do dodania do wygenerowanego pliku IDL.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0>winmdidl /nologo /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt "C:\Users\giraffe\Documents\Visual Studio 2013\Projects\Test_for_winmdidl\Debug\Test_for_winmdidl\test_for_winmdidl.winmd"`

W następnym przykładzie przedstawiono wyświetlanie konsoli z winmdidl, która wskazuje, że operacja zakończyła się pomyślnie.

**Generowanie c:\users\giraffe\documents \\ \ Test_for_winmdidl. idl**

Następnie midlrt jest uruchamiany w wygenerowanym pliku IDL. Zwróć uwagę, że argument **metadata_dir** jest określony po nazwie pliku IDL. Ścieżka \WinMetadata\ jest wymagana — jest to lokalizacja dla systemu Windows. winmd.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0> midlrt "c:\users\username\documents\test_for_winmdidl.idl" /metadata_dir "C:\Windows\System32\WinMetadata"`

## <a name="remarks"></a>Uwagi

Plik wyjściowy z operacji winmdidl ma taką samą nazwę jak plik wejściowy, ale ma rozszerzenie nazwy pliku IDL.

Jeśli tworzysz składnik środowisko wykonawcze systemu Windows, do którego będzie uzyskiwany dostęp z WRL, możesz określić winmdidl.exe i midlrt.exe do uruchamiania jako kroki po kompilacji, aby pliki. idl i. h były generowane dla każdej kompilacji. Aby zapoznać się z przykładem, zobacz Wywoływanie [zdarzeń w składnikach środowisko wykonawcze systemu Windows](/windows/uwp/winrt-components/raising-events-in-windows-runtime-components).
