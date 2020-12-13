---
description: Dowiedz się więcej na temat atrybutów C++ dla modelu COM i platformy .NET
title: Atrybuty języka C++ dla modelu COM i platformy .NET
ms.custom: index-page
ms.date: 11/19/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI], reference topics
ms.assetid: 613a3611-b3eb-4347-aa38-99b654600e1c
ms.openlocfilehash: 6fc791f81ddc43f9f91c8ab46db6aebf1959d16b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333219"
---
# <a name="c-attributes-for-com-and-net"></a>Atrybuty języka C++ dla modelu COM i platformy .NET

Firma Microsoft definiuje zestaw atrybutów języka C++, które upraszczają programowanie obiektów COM i .NET Framework opracowywanie środowiska uruchomieniowego języka wspólnego. Po dołączeniu atrybutów do plików źródłowych kompilator współpracuje z bibliotekami DLL dostawcy, aby wstawić kod lub zmodyfikować kod w wygenerowanych plikach obiektów. Te atrybuty ułatwiają tworzenie plików. idl, interfejsów, bibliotek typów i innych elementów COM. W zintegrowanym środowisku programistycznym (IDE) atrybuty są obsługiwane przez kreatorów i okno Właściwości.

Chociaż atrybuty eliminują niektóre ze szczegółowych kodowania potrzebnych do pisania obiektów COM, potrzebujesz tła dla [podstawowych elementów com](/windows/win32/com/the-component-object-model) , aby najlepiej z nich korzystać.

> [!NOTE]
> Jeśli szukasz standardowych atrybutów C++, zobacz [atrybuty](../../cpp/attributes.md).

## <a name="purpose-of-attributes"></a>Cel atrybutów

Atrybuty rozszerzone języka C++ w sposób nie jest obecnie możliwy, bez przerywania struktury klasycznej. Atrybuty Zezwalaj dostawcom (oddzielnym Bibliotekom DLL) na dynamiczne zwiększanie funkcjonalności języka. Głównym celem atrybutów jest uproszczenie tworzenia składników modelu COM, a także zwiększenie poziomu produktywności dla deweloperów składnika. Atrybuty mogą być stosowane do niemal każdej konstrukcji języka C++, takiej jak klasy, składowe danych lub funkcje członkowskie. Poniżej przedstawiono wyróżnienie korzyści oferowanych przez tę nową technologię:

- Ujawnia znaną i prostą konwencję wywoływania.

- Używa wstawionego kodu, który, w przeciwieństwie do makr, jest rozpoznawany przez debuger.

- Umożliwia łatwe wyprowadzanie z klas bazowych bez uciążliwości szczegółów implementacji.

- Zastępuje dużą ilość kodu IDL wymaganego przez składnik COM przy użyciu kilku zwięzłych atrybutów.

Na przykład w celu zaimplementowania prostego ujścia zdarzeń dla generycznej klasy ATL można zastosować atrybut [event_receiver](event-receiver.md) do określonej klasy, takiej jak `CMyReceiver` . Ten `event_receiver` atrybut jest następnie kompilowany przez kompilator języka Microsoft C++, który wstawia właściwy kod do pliku obiektu.

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

Następnie można skonfigurować `CMyReceiver` metody `handler1` i `handler2` obsłużyć zdarzenia (przy użyciu funkcji wewnętrznej [__hook](../../cpp/hook.md)) ze źródła zdarzeń, które można utworzyć przy użyciu [event_source](event-source.md).

## <a name="basic-mechanics-of-attributes"></a>Podstawowa mechanika atrybutów

Istnieją trzy sposoby wstawiania atrybutów do projektu. Najpierw można wstawić je ręcznie do kodu źródłowego. Następnie można wstawić je za pomocą siatki właściwości obiektu w projekcie. Na koniec można je wstawić przy użyciu różnych kreatorów. Aby uzyskać więcej informacji na temat korzystania z okna **Właściwości** i różnych kreatorów, zobacz [Visual Studio projects-C++](../../build/creating-and-managing-visual-cpp-projects.md).

Tak jak wcześniej, podczas kompilowania projektu kompilator analizuje każdy plik źródłowy C++, generując plik obiektu. Jeśli jednak kompilator napotka atrybut, jest on analizowany i syntaktycznie zweryfikowany. Następnie kompilator dynamicznie wywołuje dostawcę atrybutów, aby wstawić kod lub wprowadzić inne modyfikacje w czasie kompilacji. Implementacja dostawcy różni się w zależności od typu atrybutu. Na przykład atrybuty związane z ATL są implementowane przez Atlprov.dll.

Na poniższej ilustracji przedstawiono relacje między kompilatorem a dostawcą atrybutów.

![Komunikacja atrybutów składników](../media/vccompattrcomm.gif "Komunikacja atrybutów składników")

> [!NOTE]
> Użycie atrybutów nie powoduje zmiany zawartości pliku źródłowego. Jedyny wygenerowany kod atrybutu jest widoczny podczas debugowania sesji. Ponadto dla każdego pliku źródłowego w projekcie można wygenerować plik tekstowy, który wyświetla wyniki podstawienia atrybutu. Aby uzyskać więcej informacji na temat tej procedury, zobacz [/FX (Scalanie wstrzykniętego kodu)](../../build/reference/fx-merge-injected-code.md) i [debugowanie wstrzykniętego kodu](/visualstudio/debugger/how-to-debug-injected-code).

Podobnie jak większość konstrukcji języka C++, atrybuty mają zestaw cech, który definiuje ich prawidłowe użycie. Jest to nazywane kontekstem atrybutu i jest rozwoływany w tabeli kontekstowej atrybutu dla każdego tematu odwołania do atrybutu. Na przykład atrybut [klasy coclass](coclass.md) może być stosowany tylko do istniejącej klasy lub struktury, w przeciwieństwie do atrybutu [cpp_quote](cpp-quote.md) , który można wstawić w dowolnym miejscu w pliku źródłowym języka C++.

## <a name="building-an-attributed-program"></a>Kompilowanie programu opartego na atrybutach

Po umieszczeniu Visual C++ atrybutów w kodzie źródłowym możesz chcieć, aby kompilator języka Microsoft C++ generował bibliotekę typów i plik. idl. Poniższe opcje konsolidatora ułatwiają tworzenie plików TLB i IDL:

- [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)

- [/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)

- [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)

Niektóre projekty zawierają wiele niezależnych plików. idl. Są one używane do tworzenia dwóch lub więcej plików. tlb i opcjonalnie powiązania ich z blokiem zasobów. Ten scenariusz nie jest obecnie obsługiwany w Visual C++.

Ponadto Visual C++ konsolidator będzie wyprowadzał wszystkie informacje o atrybutach języka IDL do pojedynczego pliku MIDL. Nie będzie można generować dwóch bibliotek typów z pojedynczego projektu.

## <a name="attribute-contexts"></a><a name="contexts"></a> Konteksty atrybutu

Atrybuty języka C++ można opisać przy użyciu czterech podstawowych pól: cel, do którego można zastosować (**dotyczy**), jeśli są powtarzalne lub nie (**powtarzane**), wymagana obecność innych atrybutów (**wymaganych atrybutów**) i niezgodności z innymi atrybutami (**nieprawidłowe atrybuty**). Te pola są wymienione w tabeli towarzyszącej w temacie odwołania do poszczególnych atrybutów. Każde z tych pól zostało opisane poniżej.

### <a name="applies-to"></a>Dotyczy:

To pole opisuje różne elementy języka C++, które są dozwolonymi celami dla określonego atrybutu. Na przykład, jeśli atrybut określa "Klasa" w polu **dotyczy** , oznacza to, że atrybut może być stosowany tylko do dozwolonej klasy języka C++. Jeśli atrybut jest stosowany do funkcji składowej klasy, wynikiem może być błąd składniowy.

Aby uzyskać więcej informacji, zobacz [atrybuty według użycia](attributes-by-usage.md).

### <a name="repeatable"></a>Powtarzalność

To pole określa, czy atrybut może być wielokrotnie stosowany do tego samego obiektu docelowego. Większość atrybutów nie jest powtarzana.

### <a name="required-attributes"></a>Wymagane atrybuty

To pole zawiera listę innych atrybutów, które muszą być obecne (to jest stosowane do tego samego obiektu docelowego), aby określony atrybut działał prawidłowo. Dla atrybutu nie można mieć żadnych wpisów dla tego pola.

### <a name="invalid-attributes"></a>Nieprawidłowe atrybuty

To pole zawiera listę innych atrybutów, które są niezgodne z określonym atrybutem. Dla atrybutu nie można mieć żadnych wpisów dla tego pola.

## <a name="in-this-section"></a>W tej sekcji

[Programowanie atrybutów — często zadawane pytania](attribute-programming-faq.md)<br/>
[Atrybuty według grupy](attributes-by-group.md)<br/>
[Atrybuty według użycia](attributes-by-usage.md)<br/>
[Alfabetyczne odwołanie do atrybutów](attributes-alphabetical-reference.md)
