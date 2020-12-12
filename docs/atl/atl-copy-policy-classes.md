---
description: 'Dowiedz się więcej na temat: klasy zasad kopiowania ATL'
title: Klasy zasad kopiowania ATL
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 502befadbd9317602c49d9a5815dee6ebc239d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165761"
---
# <a name="atl-copy-policy-classes"></a>Klasy zasad kopiowania ATL

Kopiuj klasy zasad to [klasy narzędzi](../atl/utility-classes.md) używane do inicjowania, kopiowania i usuwania danych. Kopiuj klasy zasad umożliwiają definiowanie semantyki kopiowania dla dowolnego typu danych i Definiowanie konwersji między różnymi typami danych.

ATL używa klas zasad kopiowania w ramach implementacji następujących szablonów:

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

Poprzez hermetyzację informacji potrzebnych do kopiowania lub konwertowania danych w klasie zasad kopiowania, która może być przekazana jako argument szablonu, deweloperzy ATL udostępniają skrajnie nieużyteczność tych klas. Na przykład jeśli musisz zaimplementować kolekcję przy użyciu dowolnego dowolnego typu danych, należy podać wszystkie wymagane zasady kopiowania. nie trzeba dotykać kodu, który implementuje kolekcję.

## <a name="definition"></a>Definicja

Według definicji Klasa, która dostarcza następujące funkcje statyczne, jest klasą zasad kopiowania:

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

Można zamienić typy `DestinationType` i *sourceType* z dowolnymi typami danych dla każdej zasady kopiowania.

> [!NOTE]
> Chociaż można zdefiniować klasy zasad kopiowania dla dowolnego typu danych, użycie klas w kodzie ATL powinno ograniczyć typy, które mają sens. Na przykład w przypadku używania klasy zasad kopiowania z implementacją kolekcji lub modułów wyliczających ATL `DestinationType` musi być typem, który może być używany jako parametr w metodzie interfejsu com.

Użyj **init** , aby zainicjować dane, **Skopiuj** , aby skopiować dane i **zniszczyć** , aby zwolnić dane. Precyzyjne znaczenie inicjalizacji, kopiowania i zniszczenia jest domeną klasy zasad kopiowania i będzie się różnić w zależności od typów danych.

Istnieją dwa wymagania dotyczące użycia i implementacji klasy zasad kopiowania:

- Pierwszy parametr do **skopiowania** musi otrzymać tylko wskaźnik do danych, które zostały wcześniej zainicjowane przy użyciu **init**.

- **niszczenie** musi obejmować tylko wskaźnik do danych, które zostały wcześniej zainicjowane przy użyciu **init** lub skopiowane za pomocą **kopiowania**.

## <a name="standard-implementations"></a>Implementacje standardowe

ATL oferuje dwie klasy zasad kopiowania w postaci `_Copy` `_CopyInterface` klas i klasy szablonu:

- `_Copy`Klasa umożliwia jednorodne kopiowanie (nie konwersja między typami danych), ponieważ oferuje tylko jeden parametr szablonu, aby określić zarówno `DestinationType` , jak i *sourceType*. Ogólna implementacja tego szablonu nie zawiera kodu inicjującego ani zniszczenia oraz służy `memcpy` do kopiowania danych. ATL oferuje również specjalizacje `_Copy` dla typów danych Variant, LPOLESTR, OLEVERB i CONNECTDATA.

- `_CopyInterface`Klasa zawiera implementację do kopiowania wskaźników interfejsu zgodnie ze standardowymi regułami com. Ponownie Ta klasa umożliwia tylko jednorodne kopiowanie, więc używa prostego przypisania i wywołania do `AddRef` wykonania kopii.

## <a name="custom-implementations"></a>Implementacje niestandardowe

Zazwyczaj należy zdefiniować własne klasy zasad kopiowania dla kopiowania heterogenicznego (czyli konwersji między typami danych). Aby zapoznać się z przykładami klas niestandardowych zasad kopiowania, zapoznaj się z plikami VCUE_Copy. h i VCUE_CopyString. h w przykładzie [ATLCollections](../overview/visual-cpp-samples.md) . Te pliki zawierają dwie klasy zasad kopiowania szablonów, `GenericCopy` a `MapCopy` także szereg specjalizacji `GenericCopy` dla różnych typów danych.

### <a name="genericcopy"></a>GenericCopy

`GenericCopy` umożliwia określenie argumentów *sourceType* i `DestinationType` as szablonu. Poniżej przedstawiono najbardziej ogólną formę `GenericCopy` klasy z VCUE_Copy. h:

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy. h zawiera również następujące specjalizacje tej klasy: `GenericCopy<BSTR>` , `GenericCopy<VARIANT, BSTR>` , `GenericCopy<BSTR, VARIANT>` . VCUE_CopyString. h zawiera specjalizacje do kopiowania z wartości **std:: String** s: `GenericCopy<std::string>` , `GenericCopy<VARIANT, std::string>` , i `GenericCopy<BSTR, std::string>` . Możesz wzmocnić `GenericCopy` , dostarczając własne specjalizacje.

### <a name="mapcopy"></a>MapCopy

`MapCopy` przyjęto założenie, że kopiowane dane są przechowywane na mapie standardowej biblioteki języka C++, dzięki czemu można określić typ mapy, w której dane są przechowywane i typ docelowy. Implementacja klasy używa tylko elementów typedef dostarczonych przez klasę *MapType* do określenia typu danych źródłowych i wywołania odpowiedniej `GenericCopy` klasy. Nie są wymagana specjalizacje tej klasy.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>Zobacz też

[Implementowanie kolekcji standardowej Library-Based w języku C++](../atl/implementing-an-stl-based-collection.md)<br/>
[Przykład ATLCollections](../overview/visual-cpp-samples.md)
