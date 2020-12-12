---
description: 'Dowiedz się więcej na temat: CString argumentu przekazującego'
title: Przekazywanie argumentu CString
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: ee47898ffdfc5129b11b0f9480669fa142d12818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167178"
---
# <a name="cstring-argument-passing"></a>Przekazywanie argumentu CString

W tym artykule opisano sposób przekazywania obiektów [CString](../atl-mfc-shared/reference/cstringt-class.md) do funkcji i sposobu zwracania `CString` obiektów z funkcji.

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a> CString konwencje Argument-Passing

Podczas definiowania interfejsu klasy należy określić Konwencję przekazywania argumentów dla funkcji składowych. Istnieją pewne standardowe reguły przekazywania i zwracania `CString` obiektów. Jeśli zastosujesz reguły opisane w [ciągach jako dane wejściowe](#_core_strings_as_function_inputs) i [ciągi jako wyniki](#_core_strings_as_function_outputs)funkcji, będziesz mieć wydajny, poprawny kod.

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a> Ciągi jako dane wejściowe funkcji

Najbardziej wydajnym i bezpiecznym sposobem używania `CString` obiektu w wywołanych funkcjach jest przekazanie `CString` obiektu do funkcji. Pomimo nazwy `CString` obiekt nie przechowuje ciągu wewnętrznie jako ciągu w stylu C, który ma terminator o wartości null. Zamiast tego `CString` obiekt zachowuje uważnie śledzenie liczby znaków, które ma. `CString`Udostępnienie wskaźnika LPCTSTR do ciągu zakończonego wartością null jest małą ilością pracy, która może stać się znacząca, Jeśli Twój kod musi być stale używany. Wynik jest tymczasowy, ponieważ jakakolwiek zmiana `CString` zawartości unieważnia stare kopie wskaźnika LPCTSTR.

Zdarza się to w niektórych przypadkach, aby podać ciąg w stylu C. Na przykład może wystąpić sytuacja, w której wywołana funkcja jest zapisywana w języku C i nie obsługuje obiektów. W takim przypadku należy przekształcić `CString` parametr na LPCTSTR, a funkcja pobierze ciąg w stylu języka C zakończony znakiem null. Możesz również przejść do innego kierunku i utworzyć `CString` Obiekt przy użyciu `CString` konstruktora, który akceptuje parametr ciągu w stylu C.

Jeśli zawartość ciągu ma zostać zmieniona przez funkcję, zadeklaruj parametr jako odwołanie niestałe `CString` ( `CString&` ).

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a> Ciągi jako dane wyjściowe funkcji

Zazwyczaj można zwracać `CString` obiekty z funkcji, ponieważ `CString` obiekty są zgodne z semantyką wartości, takimi jak typy pierwotne. Aby zwrócić ciąg tylko do odczytu, użyj stałej `CString` odwołania ( `const CString&` ). Poniższy przykład ilustruje użycie `CString` parametrów i zwracanych typów:

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>Zobacz też

[Ciągi (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
