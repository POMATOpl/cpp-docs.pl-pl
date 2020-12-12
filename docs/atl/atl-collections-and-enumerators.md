---
description: 'Dowiedz się więcej na temat: Kolekcje ATL i moduły wyliczające'
title: Kolekcje i wyliczenia ALT
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 92e9ab3df52219812d72ae5cb811f57a3ecf4fad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166008"
---
# <a name="atl-collections-and-enumerators"></a>Kolekcje i wyliczenia ALT

A `collection` jest obiektem com, który udostępnia interfejs, który umożliwia dostęp do grupy elementów danych (nieprzetworzone dane lub inne obiekty). Interfejs, który następuje po standardach zapewniających dostęp do grupy obiektów jest znany jako *interfejs kolekcji*.

Co najmniej interfejsy kolekcji muszą dostarczać `Count` Właściwość zwracającą liczbę elementów w kolekcji, właściwość zwracająca `Item` element z kolekcji na podstawie indeksu i `_NewEnum` Właściwość zwracająca moduł wyliczający dla kolekcji. Opcjonalnie interfejsy kolekcji mogą zapewnić `Add` i `Remove` metody zezwalające na wstawianie elementów do kolekcji lub usuwanie ich z niej oraz `Clear` metodę usuwania wszystkich elementów.

`enumerator`Jest obiektem com, który zapewnia interfejs do iterowania za pomocą elementów w kolekcji. Interfejsy modułu wyliczającego zapewniają dostęp szeregowy do elementów kolekcji za pomocą czterech wymaganych metod: `Next` , `Skip` , `Reset` , i `Clone` .

Więcej informacji na temat interfejsów modułu wyliczającego można uzyskać, odczytując zawartość referencyjną, taką jak interfejs [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) .

## <a name="in-this-section"></a>W tej sekcji

[Klasy kolekcji i modułów wyliczających ATL](../atl/atl-collection-and-enumerator-classes.md)<br/>
Krótko opisuje i oferuje linki do klas ATL, które ułatwią implementowanie kolekcji i modułów wyliczających.

[Zasady projektowania dotyczące interfejsów kolekcji i modułów wyliczających](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
Omawia różne zasady projektowania za każdym typem interfejsu.

[Implementowanie kolekcji standardowej Library-Based w języku C++](../atl/implementing-an-stl-based-collection.md)<br/>
Rozszerzony przykład, który przeprowadzi Cię przez implementację standardowej kolekcji opartej na bibliotece C++.

## <a name="related-sections"></a>Sekcje pokrewne

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Zawiera łącza do tematów koncepcyjnych dotyczących sposobu programowania przy użyciu Active Template Library.

[Przykład ATLCollections](../overview/visual-cpp-samples.md)<br/>
Przykład demonstrujący używanie `ICollectionOnSTLImpl` i `CComEnumOnSTL` i implementacji niestandardowych klas zasad kopiowania.

## <a name="see-also"></a>Zobacz też

[Pojęcia](../atl/active-template-library-atl-concepts.md)
