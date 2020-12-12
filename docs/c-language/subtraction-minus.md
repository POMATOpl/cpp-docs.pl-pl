---
description: 'Dowiedz się więcej o: odejmowaniu (-)'
title: Odejmowanie (-)
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
ms.openlocfilehash: 8e0daf4e1bfdbb844df99e3f79dc2baf5a30e6e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114562"
---
# <a name="subtraction--"></a>Odejmowanie (-)

Operator odejmowania ( **-** ) Odejmuje drugi operand od pierwszego. Oba operandy mogą być typu całkowitego lub zmiennoprzecinkowego lub jeden operand może być wskaźnikiem, a drugą liczbą całkowitą.

Gdy są odejmowane dwa wskaźniki, różnica jest konwertowana na podpisaną wartość całkowitą przez podzielenie różnicy przez rozmiar wartości typu, którego dotyczy wskaźnik. Rozmiar wartości całkowitej jest definiowany przez typ **ptrdiff_t** w standardowym pliku include STDDEF. H. Wynik przedstawia liczbę pozycji pamięci tego typu między dwoma adresami. Wynik jest gwarantowany tylko dla dwóch elementów tej samej tablicy, zgodnie z opisem w obszarze [arytmetyczny wskaźnik](../c-language/pointer-arithmetic.md).

W przypadku odejmowania wartości całkowitej od wartości wskaźnika operator odejmowania konwertuje wartość całkowitą (*i*) przez pomnożenie jej przez rozmiar wartości, która jest adresem wskaźnika. Po konwersji wartość *całkowita reprezentuje położenie* pamięci, gdzie każda pozycja ma długość określoną przez typ wskaźnika. Gdy przekonwertowana wartość całkowita zostanie odjęta od wartości wskaźnika, wynikiem jest adres pamięci, *po* którym naliczane są adresy przed pierwotnym adresem. Nowy wskaźnik wskazuje wartość typu rozkierowanego przez oryginalną wartość wskaźnika.

## <a name="see-also"></a>Zobacz też

[Operatory addytywne języka C](../c-language/c-additive-operators.md)
