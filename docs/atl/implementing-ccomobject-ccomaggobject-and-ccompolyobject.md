---
description: 'Dowiedz się więcej o: implementowanie CComObject, CComAggObject i CComPolyObject'
title: Implementowanie klas CComObject, CComAggObject i CComPolyObject
ms.date: 11/04/2016
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: e0cc8a6b65ec9d85249cd47e2f43cf1bec2b8ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147774"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>Implementowanie klas CComObject, CComAggObject i CComPolyObject

Klasy szablonów [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md)i [CComPolyObject](../atl/reference/ccompolyobject-class.md) są zawsze najbardziej pochodnymi klasami w łańcuchu dziedziczenia. Jest ona odpowiedzialna za obsługę wszystkich metod w `IUnknown` : `QueryInterface` , `AddRef` i `Release` . Ponadto `CComAggObject` i `CComPolyObject` (gdy są używane w przypadku obiektów agregowanych) podaj specjalne zliczanie odwołań i `QueryInterface` semantykę wymaganą dla nieznanego elementu wewnętrznego.

Określa `CComObject` , czy `CComAggObject` `CComPolyObject` jest używane, zależy od tego, czy zadeklarujesz jeden (lub brak) następujących makr:

|Makro|Efekt|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|Zawsze używa `CComObject` .|
|DECLARE_AGGREGATABLE|Używa `CComAggObject` , jeśli obiekt jest zagregowany i `CComObject` Jeśli nie jest. `CComCoClass` zawiera to makro, więc jeśli żadna z DECLARE_ * _AGGREGATABLE makra nie są zadeklarowane w klasie, będzie to wartość domyślna.|
|DECLARE_ONLY_AGGREGATABLE|Zawsze używa `CComAggObject` . Zwraca błąd, jeśli obiekt nie jest agregowany.|
|DECLARE_POLY_AGGREGATABLE|ATL tworzy wystąpienie elementu **CComPolyObject \<CYourClass>** , gdy `IClassFactory::CreateInstance` jest wywoływana. Podczas tworzenia jest sprawdzana wartość nieznanego elementu zewnętrznego. Jeśli ma wartość NULL, `IUnknown` jest zaimplementowana dla niezagregowanego obiektu. Jeśli nieznana zewnętrzna nie ma wartości NULL, `IUnknown` jest zaimplementowana dla obiektu agregowanego.|

Zaletą korzystania z programu `CComAggObject` i `CComObject` jest `IUnknown` Optymalizacja implementacji dla rodzaju tworzonego obiektu. Na przykład, obiekt niezagregowany wymaga liczby odwołań, natomiast zagregowany obiekt wymaga zarówno liczby odwołań dla nieznanego elementu, jak i wskaźnika do nieznanego elementu zewnętrznego.

Zaletą korzystania z programu `CComPolyObject` jest unikanie, `CComAggObject` aby oba i `CComObject` w module obsługiwały zagregowane i niezagregowane przypadki. Pojedynczy `CComPolyObject` obiekt obsługuje oba przypadki. Oznacza to, że w module istnieją tylko jedną kopię tabeli metod wirtualnych i jedną kopię funkcji. W przypadku dużej liczby tablic wirtualnych może to znacznie zmniejszyć rozmiar modułu. Jeśli jednak tablica tablicowa jest mała, użycie `CComPolyObject` może spowodować nieco większy rozmiar modułu, ponieważ nie jest zoptymalizowany pod kątem zagregowanych lub niezagregowanych obiektów, ponieważ są `CComAggObject` i `CComObject` .

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje o obiektach COM ATL](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Makra agregacji i fabryki klas](../atl/reference/aggregation-and-class-factory-macros.md)
