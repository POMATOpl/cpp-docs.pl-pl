---
description: 'Dowiedz się więcej o: strumienie wejściowe'
title: Strumienie wejściowe
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
ms.openlocfilehash: f7e6d41b904b2d28893637681e3c751d24aef441
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323965"
---
# <a name="input-streams"></a>Strumienie wejściowe

Obiekt strumienia danych wejściowych jest źródłem bajtów. Trzy najważniejsze klasy strumienia wejściowego to [IStream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md)i [istringstream —](../standard-library/basic-istringstream-class.md).

`istream`Klasa jest Najlepsza do użycia w sekwencyjnym wejściu w trybie tekstowym. Można skonfigurować obiekty klasy `istream` dla operacji buforowanej lub niebuforowanej. Wszystkie funkcje klasy podstawowej, `ios` ,, są zawarte w `istream` . Obiekty z klasy są rzadko konstruowane `istream` . Zamiast tego zwykle używany jest wstępnie zdefiniowany `cin` obiekt, który jest obiektem klasy [ostream](../standard-library/basic-ostream-class.md). W niektórych przypadkach można przypisać `cin` do innych obiektów strumienia po uruchomieniu programu.

`ifstream`Klasa obsługuje dane wejściowe pliku dyskowego. Jeśli potrzebujesz pliku dyskowego tylko do wprowadzania danych, Utwórz obiekt klasy `ifstream` . Można określić dane binarne lub w trybie tekstowym. Jeśli określisz nazwę pliku w konstruktorze, plik zostanie automatycznie otwarty podczas konstruowania obiektu. W przeciwnym razie można użyć `open` funkcji po wywołaniu konstruktora domyślnego. Wiele opcji formatowania i funkcji Członkowskich ma zastosowanie do `ifstream` obiektów. Wszystkie funkcje klas podstawowych `ios` i `istream` są zawarte w `ifstream` .

Podobnie jak w przypadku funkcji biblioteki `sscanf_s` , `istringstream` Klasa obsługuje dane wejściowe z ciągów w pamięci. Aby wyodrębnić dane z tablicy znaków, która ma terminator o wartości null, przydzielić i zainicjować ciąg, a następnie utworzyć obiekt klasy `istringstream` .

## <a name="in-this-section"></a>W tej sekcji

[Konstruowanie obiektów strumienia danych wejściowych](../standard-library/constructing-input-stream-objects.md)

[Korzystanie z operatorów wyodrębniania](../standard-library/using-extraction-operators.md)

[Testowanie pod kątem błędów wyodrębniania](../standard-library/testing-for-extraction-errors.md)

[Manipulowanie strumieniami wejściowymi](../standard-library/input-stream-manipulators.md)

[Funkcje członkowskie strumienia wejściowego](../standard-library/input-stream-member-functions.md)

[Przeciążanie operatora >> dla własnych klas](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>Zobacz też

[Programowanie iostream](../standard-library/iostream-programming.md)
