---
description: 'Dowiedz się więcej o programie: programowanie z CComBSTR (ATL)'
title: Programowanie przy użyciu CComBSTR (ALT)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 6c348d703aeaeba40f1f47b8f6fd0ee858b7babd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159222"
---
# <a name="programming-with-ccombstr-atl"></a>Programowanie przy użyciu CComBSTR (ALT)

Klasa ATL [CComBSTR](../atl/reference/ccombstr-class.md) udostępnia otokę wokół typu danych BSTR. Chociaż `CComBSTR` jest użytecznym narzędziem, istnieje kilka sytuacji, w których należy zachować ostrożność.

- [Problemy z konwersją](#programmingwithccombstr_conversionissues)

- [Problemy dotyczące zakresu](#programmingwithccombstr_scopeissues)

- [Jawne Zwalnianie obiektu CComBSTR](#programmingwithccombstr_explicitlyfreeing)

- [Używanie obiektów CComBSTR w pętlach](#programmingwithccombstr_usingloops)

- [Problemy przecieków pamięci](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a> Problemy z konwersją

Chociaż kilka `CComBSTR` metod automatycznie przekonwertuje argument ciągu ANSI na Unicode, metody zawsze będą zwracały ciągi w formacie Unicode. Aby przekonwertować ciąg wyjściowy z powrotem do ANSI, użyj klasy konwersji ATL. Aby uzyskać więcej informacji na temat klas konwersji ATL, zobacz [makra konwersji ciągów ATL i MFC](reference/string-conversion-macros.md).

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

Jeśli używasz literału ciągu do modyfikowania `CComBSTR` obiektu, użyj ciągów znaków dwubajtowych. Spowoduje to zmniejszenie niepotrzebnych konwersji.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a> Problemy dotyczące zakresu

Podobnie jak w przypadku każdej dobrze zachowanej klasy, `CComBSTR` program zwolni swoje zasoby, gdy znajdzie się poza zakresem. Jeśli funkcja zwraca wskaźnik do `CComBSTR` ciągu, może to spowodować problemy, ponieważ wskaźnik będzie odwoływać się do pamięci, która została już zwolniona. W takich przypadkach Użyj `Copy` metody, jak pokazano poniżej.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a> Jawne Zwalnianie obiektu CComBSTR

Istnieje możliwość jawnie zwolnienia ciągu zawartego w `CComBSTR` obiekcie przed przekroczeniem zakresu. Jeśli ciąg jest zwolniony, `CComBSTR` obiekt jest nieprawidłowy.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a> Używanie obiektów CComBSTR w pętlach

Ponieważ `CComBSTR` Klasa przydziela bufor do wykonywania pewnych operacji, takich jak `+=` operator lub `Append` Metoda, nie zaleca się przeprowadzania manipulowania ciągami w obrębie ścisłej pętli. W takich sytuacjach `CStringT` zapewnia lepszą wydajność.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a> Problemy przecieków pamięci

Przekazywanie adresu zainicjowane `CComBSTR` do funkcji jako parametr **[out]** powoduje przeciek pamięci.

W poniższym przykładzie ciąg przydzielony do przechowywania ciągu `"Initialized"` jest przeciek, gdy funkcja `MyGoodFunction` zastępuje ciąg.

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

Aby uniknąć wycieku, `Empty` `CComBSTR` przed przekazaniem adresu jako parametru **[out]** Wywołaj metodę dla istniejących obiektów.

Należy zauważyć, że ten sam kod nie powoduje wycieku, jeśli parametr funkcji był **[in, out]**.

## <a name="see-also"></a>Zobacz też

[Pojęcia](../atl/active-template-library-atl-concepts.md)<br/>
[Klasa CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[wstring](../standard-library/basic-string-class.md)<br/>
[Makra konwersji ciągów](../atl/reference/string-conversion-macros.md)
