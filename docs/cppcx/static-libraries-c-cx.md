---
title: Biblioteki statyczne (C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: 756f8d2c1af2c6be414ad39b4a96fa6cc7ccfb02
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924710"
---
# <a name="static-libraries-ccx"></a>Biblioteki statyczne (C++/CX)

Biblioteka statyczna, która jest używana w aplikacji platforma uniwersalna systemu Windows (platformy UWP), może zawierać kod ISO standard C++, w tym typy STL, a także wywołania interfejsów API Win32, które nie są wykluczone z platformy aplikacji środowisko wykonawcze systemu Windows. Biblioteka statyczna wykorzystuje składniki środowisko wykonawcze systemu Windows i może tworzyć składniki środowisko wykonawcze systemu Windows z pewnymi ograniczeniami.

## <a name="creating-static-libraries"></a>Tworzenie bibliotek statycznych

Instrukcje dotyczące tworzenia nowego projektu różnią się w zależności od zainstalowanej wersji programu Visual Studio. Aby wyświetlić dokumentację preferowanej wersji programu Visual Studio, użyj kontrolki selektora **wersji** . Znajduje się w górnej części spisu treści na tej stronie.

::: moniker range="msvc-160"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>Aby utworzyć bibliotekę statyczną platformy UWP w programie Visual Studio 2019

1. Na pasku menu wybierz pozycję **plik** > **Nowy** > **projekt** , aby otworzyć okno dialogowe **Tworzenie nowego projektu** .

1. W górnej części okna dialogowego Ustaw  **Język** na **C++** , ustaw **platformę** na **Windows** , a następnie ustaw **Typ projektu** na **platformy UWP** .

1. Z listy filtrowane typy projektów wybierz pozycję **Biblioteka statyczna (uniwersalna platforma Windows-C++/CX)** , a następnie wybierz przycisk **dalej** . Na następnej stronie Nadaj projektowi nazwę i określ lokalizację projektu w razie potrzeby.

1. Wybierz przycisk **Utwórz** , aby utworzyć projekt.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Aby utworzyć bibliotekę statyczną platformy UWP w programie Visual Studio 2017 lub Visual Studio 2015

1. Na pasku menu wybierz pozycję **plik**  >  **Nowy**  >  **projekt** . W obszarze **Visual C++**  >  **uniwersalna** **Biblioteka statyczna systemu Windows (uniwersalna platforma Windows)** .

1. W **Eksplorator rozwiązań** Otwórz menu skrótów dla projektu, a następnie wybierz polecenie **Właściwości** . W oknie dialogowym **Właściwości** na stronie **Właściwości konfiguracji**  >  **C/C++** ustaw wartość Użyj **środowisko wykonawcze systemu Windows rozszerzenia** na **tak (/zw)** .

::: moniker-end

Podczas kompilowania nowej biblioteki statycznej, jeśli wywołasz Win32 API, który jest wykluczony dla aplikacji platformy UWP, kompilator zgłosi błąd C3861, "nie znaleziono identyfikatora". Aby wyszukać alternatywną metodę obsługiwaną dla środowisko wykonawcze systemu Windows, zobacz [alternatywy dla interfejsów API systemu Windows w aplikacjach platformy UWP](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

W przypadku dodania projektu biblioteki statycznej języka C++ do rozwiązania aplikacji platformy UWP może być konieczne zaktualizowanie ustawień właściwości projektu biblioteki, aby Właściwość obsługa platformy UWP została ustawiona na **wartość tak** . Bez tego ustawienia kod kompiluje i łączy, ale wystąpi błąd podczas próby zweryfikowania aplikacji dla Microsoft Store. Statyczna biblioteka lib powinna być skompilowana przy użyciu tych samych ustawień kompilatora co projekt, który go używa.

W przypadku korzystania z biblioteki statycznej, która tworzy `ref` klasy publiczne, klasy interfejsu publicznego lub publiczne klasy wartości, Konsolidator wywołuje to ostrzeżenie:

> **Ostrzeżenie LNK4264:** archiwizowanie pliku obiektu skompilowanego z/zw w bibliotece statycznej; należy pamiętać, że podczas tworzenia typów środowisko wykonawcze systemu Windows nie zaleca się łączenia z biblioteką statyczną zawierającą środowisko wykonawcze systemu Windows metadanych.

Można bezpiecznie zignorować to ostrzeżenie tylko wtedy, gdy biblioteka statyczna nie produkuje składników środowisko wykonawcze systemu Windows, które są używane poza samą biblioteką. Jeśli biblioteka nie korzysta ze zdefiniowanego przez siebie składnika, konsolidator może zoptymalizować implementację, mimo że metadane publiczne zawierają informacje o typie. Oznacza to, że składniki publiczne w bibliotece statycznej zostaną skompilowane, ale nie zostaną aktywowane w czasie wykonywania. Z tego powodu każdy składnik środowisko wykonawcze systemu Windows, który jest przeznaczony do użycia przez inne składniki lub aplikacje, musi być zaimplementowany w bibliotece dołączanej dynamicznie (DLL).

## <a name="see-also"></a>Zobacz także

[Wątkowość i kierowanie](../cppcx/threading-and-marshaling-c-cx.md)
