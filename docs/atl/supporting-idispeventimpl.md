---
description: 'Dowiedz się więcej na temat: Obsługa IDispEventImpl'
title: Obsługa interfejsu IDispEventImpl
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
ms.openlocfilehash: 6a5c12e011ad0dc0f27594325a22dadddd5b92c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157376"
---
# <a name="supporting-idispeventimpl"></a>Obsługa interfejsu IDispEventImpl

Klasa szablonu [IDispEventImpl](../atl/reference/idispeventimpl-class.md) może służyć do zapewnienia obsługi ujścia punktów połączenia w klasie ATL. Ujścia punktu połączenia umożliwia klasy obsługę zdarzeń wyzwalanych z zewnętrznych obiektów COM. Te ujścia punktów połączenia są mapowane przy użyciu mapy ujścia zdarzeń udostępnianej przez klasę.

Aby poprawnie zaimplementować ujścia punktu połączenia dla klasy, należy wykonać następujące czynności:

- Importuj biblioteki typów dla każdego obiektu zewnętrznego

- Zadeklaruj `IDispEventImpl` interfejsy

- Deklarowanie mapy ujścia zdarzeń

- Doradzanie i dedoradzanie punktów połączenia

Kroki związane z implementacją ujścia punktu połączenia są wykonywane przez zmodyfikowanie tylko pliku nagłówkowego (. h) klasy.

## <a name="importing-the-type-libraries"></a>Importowanie bibliotek typów

Dla każdego obiektu zewnętrznego, którego zdarzenia mają być obsługiwane, należy zaimportować bibliotekę typów. Ten krok określa zdarzenia, które mogą być obsługiwane i zawiera informacje, które są używane podczas deklarowania mapy ujścia zdarzeń. Aby to osiągnąć, można użyć dyrektywy [#import](../preprocessor/hash-import-directive-cpp.md) . Dodaj niezbędne `#import` wiersze dyrektywy dla każdego interfejsu wysyłania, który będzie obsługiwany dla pliku nagłówkowego (. h) klasy.

Poniższy przykład importuje bibliotekę typów zewnętrznego serwera COM ( `MSCAL.Calendar.7` ):

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> Musisz mieć oddzielne `#import` instrukcje dla każdej biblioteki typów zewnętrznych, która będzie obsługiwana.

## <a name="declaring-the-idispeventimpl-interfaces"></a>Deklarowanie interfejsów IDispEventImpl

Po zaimportowaniu bibliotek typów poszczególnych interfejsów wysyłania należy zadeklarować oddzielne `IDispEventImpl` interfejsy dla każdego zewnętrznego interfejsu wysyłania. Zmodyfikuj deklarację klasy, dodając `IDispEventImpl` deklarację interfejsu dla każdego obiektu zewnętrznego. Aby uzyskać więcej informacji na temat parametrów, zobacz [IDispEventImpl](../atl/reference/idispeventimpl-class.md).

Poniższy kod deklaruje dwa ujścia punktów połączenia dla `DCalendarEvents` interfejsu dla obiektu com zaimplementowanego przez klasę `CMyCompositCtrl2` :

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>Deklarowanie mapy ujścia zdarzeń

Aby powiadomienia o zdarzeniach były obsługiwane przez właściwą funkcję, Klasa musi kierować każde zdarzenie do odpowiedniej procedury obsługi. Jest to osiągane przez zadeklarowanie mapy ujścia zdarzeń.

ATL oferuje kilka makr, [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)i [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), które ułatwiają to mapowanie. Format standardowy jest następujący:

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

Poniższy przykład deklaruje mapę ujścia zdarzeń z dwoma obsłudze zdarzeń:

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

Implementacja jest niemal zakończona. Ostatni krok dotyczy doradzania i niedoradzania interfejsów zewnętrznych.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>Doradzanie i niedoradzanie interfejsów IDispEventImpl

Ostatnim krokiem jest zaimplementowanie metody, która będzie doradzać (lub poradzić sobie) wszystkie punkty połączenia w odpowiednim czasie. To zalecenie należy wykonać przed rozpoczęciem komunikacji między klientami zewnętrznymi a obiektem. Zanim obiekt staną się widoczne, każdy zewnętrzny interfejs wysyłania obsługiwany przez obiekt jest wysyłany do zapytania dla interfejsów wychodzących. Połączenie zostało nawiązane, a odwołanie do interfejsu wychodzącego jest używane do obsługi zdarzeń z obiektu. Ta procedura jest nazywana "doradzaniem".

Po zakończeniu obiektu z interfejsami zewnętrznymi interfejsy wychodzące powinny zostać powiadomione o tym, że nie są już używane przez klasę. Ten proces jest określany mianem "Unadvise".

Ze względu na unikatowy charakter obiektów COM ta procedura różni się szczegółowo od implementacji i wykonywanie między nimi. Te szczegóły wykraczają poza zakres tego tematu i nie są rozwiązywane.

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje o obiektach COM ATL](../atl/fundamentals-of-atl-com-objects.md)
