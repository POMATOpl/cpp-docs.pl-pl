---
description: 'Dowiedz się więcej o: opcje kompilatora i konsolidatora (C++/CX)'
title: Opcje kompilatora i konsolidatora (C++/CX)
ms.date: 01/22/2017
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
ms.openlocfilehash: 66f3cf5a08d7ca0a07b5708495f76902c2286436
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340427"
---
# <a name="compiler-and-linker-options-ccx"></a>Opcje kompilatora i konsolidatora (C++/CX)

Zmienna środowiskowa, opcje kompilatora C++/CX i Opcje konsolidatora obsługują Kompilowanie aplikacji dla środowisko wykonawcze systemu Windows.

## <a name="library-path"></a>Ścieżka biblioteki

Zmienna środowiskowa% LIBPATH% określa domyślną ścieżkę do wyszukiwania plików WinMD.

## <a name="compiler-options"></a>Opcje kompilatora

|Opcja|Opis|
|------------|-----------------|
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW: nostdlib|Włącza rozszerzenia języka środowisko wykonawcze systemu Windows.<br /><br /> `nostdlib`Parametr uniemożliwia kompilatorowi użycie standardowej, wstępnie zdefiniowanej ścieżki wyszukiwania do znajdowania zestawów i plików WinMD.<br /><br /> Opcja kompilatora **/zw** niejawnie określa następujące opcje kompilatora:<br /><br />- **/Fi** vccorlib. h, który wymusza dołączenie pliku nagłówkowego vccorlib. h, który definiuje wiele typów, które są wymagane przez kompilator.<br />- [/Fu](../build/reference/fu-name-forced-hash-using-file.md) Windows. winmd, który wymusza dołączenie pliku metadanych Windows. winmd dostarczonego przez system operacyjny i definiuje wiele typów w środowisko wykonawcze systemu Windows.<br />- **/Fu** Obiekt platform. winmd, który wymusza dołączenie pliku metadanych platformy. winmd, który jest dostarczany przez kompilator, i definiuje większość typów w rodzinie przestrzeni nazw.|
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|Dodaje katalog, który jest określany przez parametr *dir* , do ścieżki wyszukiwania używanej przez kompilator do znajdowania plików Assembly i WinMD.|
|*Plik* /Fu  |Wymusza dołączenie określonego modułu lub pliku winmd. Oznacza to, że nie musisz określać `#using` *pliku* w kodzie źródłowym. Kompilator automatycznie wymusza włączenie własnego pliku metadanych systemu Windows, platform. winmd.|
|/D "WINAPI_FAMILY = 2"|Tworzy definicję, która umożliwia korzystanie z podzestawu Win32 SDK, który jest zgodny z środowisko wykonawcze systemu Windows.|

## <a name="linker-options"></a>Opcje konsolidatora

|Opcja|Opis|
|------------|-----------------|
|/APPCONTAINER [: NO]|Oznacza plik wykonywalny jako możliwy do uruchomienia w kontenerze aplikacji (tylko).|
|/WINMD [: {NO&#124;}]|Emituje plik. winmd i skojarzony plik binarny. Ta opcja musi być przeniesiona do konsolidatora, aby można było wyemitować. winmd.<br /><br /> **Nie**— nie emituje pliku winmd, ale emituje plik binarny.<br /><br /> **Tylko**— emituje plik. winmd, ale nie emituje pliku binarnego.|
|/WINMDFILE:*filename*|Nazwa pliku winmd do emisji, a nie domyślna nazwa pliku winmd. Jeśli w wierszu polecenia określono wiele nazw plików, używana jest ostatnia nazwa.|
|/WINMDDELAYSIGN [: NO]|Częściowo podpisuje plik WinMD i umieszcza klucz publiczny w pliku binarnym.<br /><br /> **Nie**— (domyślnie) nie podpisuje pliku winmd.<br /><br /> /WINMDDELAYSIGN nie działa, chyba że określono również/WINMDKEYFILE lub/WINMDKEYCONTAINER.|
|/WINMDKEYCONTAINER:*Nazwa*|Określa kontener klucza do podpisania zestawu. Parametr *name* odnosi się do kontenera kluczy, który służy do podpisywania pliku metadanych.|
|/WINMDKEYFILE:*filename*|Określa klucz lub parę kluczy, aby podpisać zestaw. Parametr *filename* odpowiada kluczowi użytemu do podpisania pliku metadanych.|

### <a name="remarks"></a>Uwagi

Gdy korzystasz z **/zw**, kompilator automatycznie łączy się z wersją dll środowiska uruchomieniowego języka C (CRT). Łączenie z wersją biblioteki statycznej jest niedozwolone, a wszelkie użycie funkcji CRT, które nie są dozwolone w aplikacji platforma uniwersalna systemu Windows, spowoduje błąd czasu kompilacji.

## <a name="see-also"></a>Zobacz też

[Kompilowanie aplikacji i bibliotek](../cppcx/building-apps-and-libraries-c-cx.md)
