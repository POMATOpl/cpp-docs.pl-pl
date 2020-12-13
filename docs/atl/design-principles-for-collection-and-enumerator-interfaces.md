---
description: 'Dowiedz się więcej o programie: zasady projektowania dotyczące interfejsów kolekcji i modułów wyliczających'
title: Projektowanie kolekcji i interfejsów modułu wyliczającego (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
ms.openlocfilehash: effd2cce775ef926befc89bb6b72a976d85bdf23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148008"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Zasady projektowania dotyczące interfejsów kolekcji i modułów wyliczających

Istnieją różne zasady projektowania za każdym typem interfejsu:

- Interfejs kolekcji zapewnia *losowy* dostęp do *pojedynczego* elementu w kolekcji za pośrednictwem `Item` metody, dzięki czemu klienci mogą wykrywać liczbę elementów w kolekcji za pośrednictwem `Count` właściwości i często umożliwiają klientom Dodawanie i usuwanie elementów.

- Interfejs modułu wyliczającego zapewnia dostęp *szeregowy* do *wielu* elementów w kolekcji, nie pozwala klientowi na odnajdowanie liczby elementów w kolekcji (do momentu, gdy moduł wyliczający przestanie zwracać elementy) i nie zapewnia żadnego sposobu dodawania lub usuwania elementów.

Każdy typ interfejsu odgrywa inną rolę w zapewnianiu dostępu do elementów w kolekcji.

## <a name="see-also"></a>Zobacz też

[Kolekcje i moduły wyliczające](../atl/atl-collections-and-enumerators.md)
