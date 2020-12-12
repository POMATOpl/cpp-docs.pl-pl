---
description: 'Dowiedz się więcej na temat: jak tworzyć sprawdzalne projekty języka C++ (C++/CLI)'
title: 'Porady: tworzenie weryfikowalnych projektów C++ (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual Studio C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
ms.openlocfilehash: 5f3a84a4f87db5cf390dcfbad18f167108e0ff08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245996"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Instrukcje: Tworzenie zweryfikowanych projektów języka C++ (C++/CLI)

Kreatory aplikacji Visual C++ nie tworzą możliwego do zweryfikowania projektów.

> [!IMPORTANT]
> Program Visual Studio 2015 jest przestarzały, a program Visual Studio 2017 nie obsługuje opcji **/CLR: Pure** i **/CLR: Safe do bezpiecznego** tworzenia projektów, które są możliwe do zweryfikowania. Jeśli wymagany jest kod do zweryfikowania, zalecamy przetłumaczenie kodu do języka C#.

Jednak jeśli używasz starszej wersji zestawu narzędzi kompilatora języka Microsoft C++, który obsługuje **/CLR: Pure** i **/CLR: Safe**, projekty mogą być konwertowane, aby można było je zweryfikować. W tym temacie opisano, jak ustawić właściwości projektu i zmodyfikować pliki źródłowe projektu w celu przekształcenia projektów programu Visual Studio C++ w celu utworzenia zweryfikowanych aplikacji.

## <a name="compiler-and-linker-settings"></a>Ustawienia kompilatora i konsolidatora

Domyślnie projekty platformy .NET używają flagi kompilatora/CLR i konfigurują konsolidator jako docelowy sprzęt x86. W przypadku kodu możliwego do zweryfikowania należy użyć flagi/clr: Safe i należy nakazać konsolidatorowi generowanie MSIL zamiast natywnych instrukcji maszynowych.

### <a name="to-change-the-compiler-and-linker-settings"></a>Aby zmienić ustawienia kompilatora i konsolidatora

1. Wyświetl stronę właściwości projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie właściwości kompilatora i Build](../build/working-with-project-properties.md).

1. Na stronie **Ogólne** w węźle **Właściwości konfiguracji** ustaw właściwość **Obsługa środowiska uruchomieniowego** CLR na **bezpieczną obsługę środowiska uruchomieniowego CLR (/CLR: safe)**.

1. Na stronie **Zaawansowane** w węźle **konsolidatora** ustaw właściwość **Typ obrazu CLR** , aby **wymusić bezpieczny obraz Il (/CLRIMAGETYPE: safe)**.

## <a name="removing-native-data-types"></a>Usuwanie natywnych typów danych

Ponieważ natywne typy danych nie są możliwe do zweryfikowania, nawet jeśli nie są faktycznie używane, należy usunąć wszystkie pliki nagłówkowe zawierające typy natywne.

> [!NOTE]
> Następująca procedura dotyczy projektów aplikacji Windows Forms (.NET) i aplikacji konsolowych (.NET).

### <a name="to-remove-references-to-native-data-types"></a>Aby usunąć odwołania do natywnych typów danych

1. Dodaj komentarz do wszystkich elementów w pliku stdafx. h.

## <a name="configuring-an-entry-point"></a>Konfigurowanie punktu wejścia

Ze względu na to, że aplikacje podlegające weryfikacji nie mogą używać bibliotek uruchomieniowych C (CRT), nie mogą one zależeć od CRT do wywołania funkcji Main jako standardowego punktu wejścia. Oznacza to, że musisz jawnie podać nazwę funkcji, która ma być wywoływana początkowo do konsolidatora. (W tym przypadku Main () jest używany zamiast Main () lub _tmain (), aby wskazać punkt wejścia inny niż CRT, ale ponieważ punkt wejścia musi być określony jawnie, ta nazwa jest dowolną.)

> [!NOTE]
> Poniższe procedury dotyczą projektów aplikacji konsolowych (.NET).

#### <a name="to-configure-an-entry-point"></a>Aby skonfigurować punkt wejścia

1. Zmień wartość _tmain () na Main () w pliku Main. cpp projektu.

1. Wyświetl stronę właściwości projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie właściwości kompilatora i Build](../build/working-with-project-properties.md).

1. Na stronie **Zaawansowane** w węźle **konsolidatora** wpisz `Main` jako wartość właściwości **punktu wejścia** .

## <a name="see-also"></a>Zobacz też

- [Kod czysty i weryfikowalny (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
