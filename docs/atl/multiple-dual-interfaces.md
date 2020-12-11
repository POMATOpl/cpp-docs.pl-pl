---
description: 'Dowiedz się więcej na temat: wiele podwójnych interfejsów'
title: Wiele podwójnych interfejsów
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
ms.openlocfilehash: d90c0176b3165cc0e5b976a29ec58b58fd3a7a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159418"
---
# <a name="multiple-dual-interfaces"></a>Wiele podwójnych interfejsów

Warto połączyć zalety podwójnego interfejsu (czyli elastyczność zarówno tablic wirtualnych, jak i późnych powiązań, dzięki czemu Klasa jest dostępna dla języków skryptów oraz języka C++) przy użyciu technik wielokrotnego dziedziczenia.

Chociaż istnieje możliwość uwidocznienia wielu podwójnych interfejsów na pojedynczym obiekcie COM, nie jest to zalecane. Jeśli istnieje wiele podwójnych interfejsów, musi istnieć tylko jeden `IDispatch` interfejs. Dostępne techniki zapewniają, że jest to przypadek, który ma zastosowanie do utraty funkcji lub zwiększonej złożoności kodu. Deweloper rozważający takie podejście powinno starannie zaważyć zalety i wady.

## <a name="exposing-a-single-idispatch-interface"></a>Uwidacznianie pojedynczego interfejsu IDispatch

Możliwe jest uwidocznienie wielu podwójnych interfejsów na pojedynczym obiekcie przez wyprowadzenie z dwóch lub więcej specjalizacji `IDispatchImpl` . Jeśli jednak zezwolisz klientom na wykonywanie zapytań dotyczących `IDispatch` interfejsu, musisz użyć makra [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) (lub [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))), aby określić klasę bazową, która ma być używana w implementacji `IDispatch` .

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

Ponieważ tylko jeden `IDispatch` interfejs jest narażony, klienci, którzy mogą uzyskiwać dostęp do obiektów tylko za pomocą `IDispatch` interfejsu, nie będą mogli uzyskać dostępu do metod lub właściwości w żadnym innym interfejsie.

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Łączenie wielu podwójnych interfejsów w jedną implementację IDispatch

ATL nie zapewnia żadnej obsługi do łączenia wielu podwójnych interfejsów w jedną implementację programu `IDispatch` . Istnieje jednak kilka znanych podejścia do ręcznego łączenia interfejsów, takich jak tworzenie klasy z szablonami, która zawiera związek oddzielnych `IDispatch` interfejsów, tworzenie nowego obiektu do wykonywania `QueryInterface` funkcji lub użycie implementacji obiektów zagnieżdżonych opartych na metodzie tworzenia `IDispatch` interfejsu.

Te podejścia powodują problemy z kolizjami przestrzeni nazw, a także złożoność kodu i łatwość utrzymania. Nie zaleca się tworzenia wielu podwójnych interfejsów.

## <a name="see-also"></a>Zobacz też

[Podwójne interfejsy i ATL](../atl/dual-interfaces-and-atl.md)
