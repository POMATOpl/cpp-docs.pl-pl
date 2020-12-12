---
description: 'Dowiedz się więcej na temat: Dodawanie (+)'
title: Dodawanie (+)
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
ms.openlocfilehash: 33cc1284c9ab36988d9fcba2fcc9e27d052cb4cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280186"
---
# <a name="addition-"></a>Dodawanie (+)

Operator dodawania ( **+** ) powoduje dodanie dwóch operandów. Oba operandy mogą być typu całkowitego lub zmiennoprzecinkowego lub jeden operand może być wskaźnikiem, a drugą liczbą całkowitą.

Gdy liczba całkowita zostanie dodana do wskaźnika, wartość całkowita (*i*) jest konwertowana przez pomnożenie jej przez rozmiar wartości, która jest adresem wskaźnika. Po konwersji wartość *całkowita reprezentuje położenie* pamięci, gdzie każda pozycja ma długość określoną przez typ wskaźnika. Gdy przekonwertowana wartość całkowita zostanie dodana do wartości wskaźnika, wynik jest nową wartością wskaźnika reprezentującą adres *i* pozycje z oryginalnego adresu. Nowa wartość wskaźnika odnosi się do wartości tego samego typu co oryginalna wartość wskaźnika i dlatego jest taka sama jak indeksowanie tablicy (zobacz [tablice jednowymiarowe](../c-language/one-dimensional-arrays.md) i [tablice wielowymiarowe](../c-language/multidimensional-arrays-c.md)). Jeśli wskaźnik sum wskazuje poza tablicę, z wyjątkiem pierwszej lokalizacji poza górną końcówką, wynik jest niezdefiniowany. Aby uzyskać więcej informacji, zobacz [arytmetyka wskaźnika](../c-language/pointer-arithmetic.md).

## <a name="see-also"></a>Zobacz też

[Operatory addytywne języka C](../c-language/c-additive-operators.md)
