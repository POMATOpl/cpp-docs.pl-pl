---
description: 'Dowiedz się więcej na temat: Kolekcja ATL i klasy modułów wyliczających'
title: Klasy kolekcji i modułów wyliczających ATL
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: b1f30aabb4908b0299a927f92a6d5ee4e9370a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166047"
---
# <a name="atl-collection-and-enumerator-classes"></a>Klasy kolekcji i modułów wyliczających ATL

ATL oferuje następujące klasy, które ułatwiają implementowanie kolekcji i modułów wyliczających.

|Klasa|Opis|
|-----------|-----------------|
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Implementacja interfejsu kolekcji|
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Implementacja interfejsu modułu wyliczającego (zakłada, że dane są przechowywane w kontenerze zgodnym ze standardem C++)|
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Implementacja interfejsu modułu wyliczającego (zakłada, że dane są przechowywane w tablicy)|
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Implementacja obiektu modułu wyliczającego (w użyciu `IEnumOnSTLImpl` )|
|[CComEnum](../atl/reference/ccomenum-class.md)|Implementacja obiektu modułu wyliczającego (w użyciu `CComEnumImpl` )|
|[_Copy](../atl/atl-copy-policy-classes.md)|Kopiuj klasę zasad|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Kopiuj klasę zasad|
|[CAdapt](../atl/reference/cadapt-class.md)|Adapter — Klasa (ukrywa **operator &** zezwalania `CComPtr` , `CComQIPtr` i `CComBSTR` do przechowywania w kontenerach standardowej biblioteki C++)|

## <a name="see-also"></a>Zobacz też

[Kolekcje i moduły wyliczające](../atl/atl-collections-and-enumerators.md)
