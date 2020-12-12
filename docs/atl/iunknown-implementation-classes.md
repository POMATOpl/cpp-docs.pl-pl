---
description: Dowiedz się więcej na temat klas implementacji IUnknown
title: Klasy implementacji IUnknown (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
ms.openlocfilehash: a28bd14be86501fd6566b8038b73a51efcc1c18d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147657"
---
# <a name="iunknown-implementation-classes"></a>Klasy implementacji IUnknown

Następujące klasy implementują `IUnknown` i powiązane metody:

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) Zarządza zliczaniem odwołań dla obiektów zagregowanych i niezagregowanych. Pozwala określić model wątkowości.

- [Klasy CComObjectRoot](../atl/reference/ccomobjectroot-class.md) Zarządza zliczaniem odwołań dla obiektów zagregowanych i niezagregowanych. Używa domyślnego modelu wątkowego serwera.

- [CComAggObject](../atl/reference/ccomaggobject-class.md) Implementuje `IUnknown` dla obiektu agregowanego.

- [CComObject](../atl/reference/ccomobject-class.md) Implementuje `IUnknown` dla niezagregowanego obiektu.

- [CComPolyObject](../atl/reference/ccompolyobject-class.md) Implementuje `IUnknown` dla obiektów zagregowanych i niezagregowanych. Przy użyciu `CComPolyObject` unika się zarówno `CComAggObject` , jak i `CComObject` w module. Pojedynczy `CComPolyObject` obiekt obsługuje zarówno zagregowane, jak i niezagregowane przypadki.

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) Implementuje `IUnknown` dla obiektu niezagregowanego, bez modyfikowania liczby blokad modułu.

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) Implementuje `IUnknown` dla interfejsu odrywanego.

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) Implementuje `IUnknown` dla interfejsu "buforowane" odrywania.

- [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) Implementuje `IUnknown` dla obiektu wewnętrznego agregacji lub interfejsu odnoszącego się do odrywania.

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) Zarządza liczbą odwołań w module, aby upewnić się, że obiekt nie zostanie usunięty.

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md) Tworzy tymczasowy obiekt COM przy użyciu implementacji szkieletowej `IUnknown` .

## <a name="related-articles"></a>Powiązane artykuły

[Podstawowe informacje o obiektach COM ATL](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../atl/atl-class-overview.md)<br/>
[Makra agregacji i fabryki klas](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[Makra mapy modelu COM](../atl/reference/com-map-macros.md)<br/>
[Globalne funkcje mapowania modelu COM](../atl/reference/com-map-global-functions.md)
