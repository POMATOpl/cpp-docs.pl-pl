---
description: 'Dowiedz się więcej o: zasady obsługi zdarzeń'
title: Zasady obsługi zdarzeń (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 29b9542b4e026d320857990a0ef6253f310535e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147982"
---
# <a name="event-handling-principles"></a>Zasady obsługi zdarzeń

Istnieją trzy kroki wspólne dla wszystkich obsługi zdarzeń. Konieczne będzie:

- Zaimplementuj interfejs zdarzenia w obiekcie.

- Należy polecić Źródło zdarzenia, że obiekt chce otrzymywać zdarzenia.

- Jeśli obiekt nie musi już odbierać zdarzeń, należy wykonać niezalecanie źródła zdarzeń.

Sposób implementacji interfejsu zdarzenia będzie zależeć od jego typu. Interfejsem zdarzenia może być tablica tablicowa, Dual lub dispinterface. Do projektanta źródła zdarzeń można zdefiniować interfejs; jest to implementacja tego interfejsu.

> [!NOTE]
> Chociaż nie ma żadnych technicznych powodów, dla których interfejs zdarzenia nie może być podwójny, istnieje wiele dobrych przyczyn projektowania, aby uniknąć używania podwójnych. Jest to jednak decyzja podejmowana przez projektanta/realizatora *źródła* zdarzeń. Ze względu na to, że pracujesz z perspektywy zdarzenia `sink` , musisz zezwolić na możliwość, że nie masz żadnego wyboru, ale wdrożyć interfejs podwójnego zdarzenia. Aby uzyskać więcej informacji na temat podwójnych interfejsów, zobacz [podwójne interfejsy i ATL](../atl/dual-interfaces-and-atl.md).

Zaleca się, aby Źródło zdarzenia zostało podzielone na trzy kroki:

- Zbadaj obiekt źródłowy dla [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Call [IConnectionPointContainer:: FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) PRZEKAZUJĄCY identyfikator IID interfejsu zdarzenia, który Cię interesuje. Jeśli to się powiedzie, spowoduje to zwrócenie interfejsu [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) w obiekcie punktu połączenia.

- Call [IConnectionPoint:: Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) przekazanie `IUnknown` ujścia zdarzeń. Jeśli to się powiedzie, zwróci `DWORD` plik cookie reprezentujący połączenie.

Po pomyślnym zarejestrowaniu zainteresowania w odniesieniu do zdarzeń, metody interfejsu zdarzenia obiektu będą wywoływane w zależności od zdarzeń wyzwalanych przez obiekt źródłowy. Gdy nie musisz już odbierać zdarzeń, możesz przekazać plik cookie z powrotem do punktu połączenia za pośrednictwem [IConnectionPoint:: Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Spowoduje to przerwanie połączenia między źródłem i ujściam.

Należy zachować ostrożność, aby uniknąć cykli referencyjnych podczas obsługi zdarzeń.

## <a name="see-also"></a>Zobacz też

[Obsługa zdarzeń](../atl/event-handling-and-atl.md)
