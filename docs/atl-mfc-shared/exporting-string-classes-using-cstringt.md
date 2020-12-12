---
description: 'Dowiedz się więcej na temat: eksportowanie klas ciągów przy użyciu CStringT'
title: Eksportowanie klas ciągów przy użyciu CStringT
ms.date: 11/04/2016
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
ms.openlocfilehash: 8876ea04f1252e4f5861a950b04dabcd99d6a804
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166996"
---
# <a name="exporting-string-classes-using-cstringt"></a>Eksportowanie klas ciągów przy użyciu CStringT

W przeszłości deweloperzy MFC otrzymali od `CString` do specjalizacji własnych klas ciągów. W Microsoft Visual C++ .NET (MFC 8,0) Klasa [CString](../atl-mfc-shared/using-cstring.md) została zastąpiona przez klasę szablonu o nazwie [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Zapewnia to kilka korzyści:

- Zezwolono `CString` klasie MFC na użycie w projektach ATL bez konsolidacji w większej bibliotece statycznej MFC lub dll.

- Za pomocą nowej `CStringT` klasy szablonu można dostosować `CString` zachowanie przy użyciu parametrów szablonu, które określają cechy znaków, podobnie jak szablony w standardowej bibliotece języka C++.

- Podczas eksportowania własnej klasy ciągów z biblioteki DLL przy użyciu programu `CStringT` kompilator automatycznie eksportuje `CString` klasę bazową. Ponieważ `CString` sama sama jest klasą szablonu, może być tworzona przez kompilator, gdy jest używana, jeśli kompilator nie wie, że `CString` został zaimportowany z biblioteki DLL. Jeśli przeprowadzono migrację projektów z Visual C++ 6,0 do Visual C++ .NET, być może wystąpiły błędy symboli konsolidatora dla wielokrotnie zdefiniowanych z `CString` powodu kolizji `CString` zaimportowanej z biblioteki DLL i lokalnie uruchomionej wersji. Poniższa metoda jest opisana poniżej.

Następujący scenariusz spowoduje utworzenie przez konsolidatora błędów symboli dla wielokrotnie zdefiniowanych klas. Załóżmy, że eksportowana jest `CString` Klasa pochodna ( `CMyString` ) z biblioteki DLL rozszerzenia MFC:

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

Kod klienta używa kombinacji `CString` i `CMyString` . "Ciąg". h "nie jest uwzględniony w prekompilowanym nagłówku, a niektóre użycie elementu `CString` nie jest `CMyString` widoczne.

Załóżmy, że używasz `CString` klas i `CMyString` w oddzielnych plikach źródłowych, Source1. cpp i Source2. cpp. W Source1. cpp użyjemy `CMyString` i #include ciągu. h. W SOURCE2. cpp należy użyć `CString` , ale nie #include ciągu. h. W takim przypadku konsolidator będzie skargą o wartości, `CStringT` które zostały zdefiniowane. Jest to spowodowane tym, `CString` że są one importowane z biblioteki DLL, która eksportuje `CMyString` i tworzy lokalnie przez kompilator za pośrednictwem `CStringT` szablonu.

Aby rozwiązać ten problem, wykonaj następujące czynności:

Eksportuj `CStringA` i `CStringW` (i wymagane klasy podstawowe) z MFC90.DLL. Projekty, które obejmują MFC, zawsze będą używać biblioteki MFC DLL wyeksportowane `CStringA` i `CStringW` , jak w poprzednich implementacjach MFC.

Następnie Utwórz klasę pochodną do eksportu przy użyciu `CStringT` szablonu, jak `CStringT_Exported` pokazano poniżej, na przykład:

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

W AfxStr. h Zastąp poprzednie `CString` , `CStringA` , i `CStringW` Typedefs w następujący sposób:

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

Istnieją pewne zastrzeżenia:

- Nie należy eksportować `CStringT` samego siebie, ponieważ spowoduje to wyeksportowanie wyspecjalizowanej klasy przez projekty tylko ATL `CStringT` .

- Użycie klasy pochodnej możliwej do eksportu z `CStringT` minimalizuje konieczność ponownego zaimplementowania `CStringT` funkcji. Dodatkowy kod jest ograniczony do przekazywania konstruktorów do `CStringT` klasy bazowej.

- `CString`, `CStringA` i `CStringW` powinny być oznaczone tylko `__declspec(dllexport/dllimport)` podczas kompilowania przy użyciu udostępnionej biblioteki DLL MFC. W przypadku łączenia z biblioteką statyczną MFC nie należy oznaczać tych klas jako wyeksportowanych; w przeciwnym razie wewnętrzne użycie `CString` , `CStringA` , i `CStringW` wewnątrz bibliotek DLL użytkownika będzie oznaczać `CString` również jako wyeksportowane.

## <a name="related-topics"></a>Tematy pokrewne

[Klasa CStringT](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>Zobacz też

[Użycie CStringT](../atl-mfc-shared/using-cstringt.md)<br/>
[Użycie CString](../atl-mfc-shared/using-cstring.md)
