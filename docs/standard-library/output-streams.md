---
description: 'Dowiedz się więcej o: strumienie wyjściowe'
title: Strumienie wyjściowe
ms.date: 11/04/2016
helpviewer_keywords:
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
ms.openlocfilehash: ec09a6bee1bcd2f329522b61950f3d051fb57889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340869"
---
# <a name="output-streams"></a>Strumienie wyjściowe

Obiekt strumienia wyjściowego jest miejscem docelowym dla bajtów. Trzy najważniejsze klasy strumienia wyjściowego to `ostream` , `ofstream` , i `ostringstream` .

`ostream`Klasa, za pomocą klasy pochodnej `basic_ostream` , obsługuje wstępnie zdefiniowane obiekty strumienia:

- `cout` Wyjście standardowe

- `cerr` błąd standardowy z ograniczoną buforowaniem

- `clog` Podobnie jak `cerr` w przypadku pełnego buforowania

Obiekty są rzadko skonstruowane `ostream` ; często używane są wstępnie zdefiniowane obiekty. W niektórych przypadkach można ponownie przypisać wstępnie zdefiniowane obiekty po uruchomieniu programu. `ostream`Klasa, którą można skonfigurować dla operacji buforowanej lub niebuforowanej, najlepiej nadaje się do sekwencyjnego wyjścia w trybie tekstowym. Wszystkie funkcje klasy podstawowej, `ios` ,, są zawarte w `ostream` . W przypadku konstruowania obiektu klasy należy `ostream` określić `streambuf` obiekt dla konstruktora.

`ofstream`Klasa obsługuje dane wyjściowe pliku dyskowego. Jeśli potrzebujesz dysku wyjściowego, Utwórz obiekt klasy `ofstream` . Można określić, czy `ofstream` obiekty będą akceptować dane binarne lub w trybie tekstowym podczas konstruowania `ofstream` obiektu, czy podczas wywoływania `open` funkcji składowej obiektu. Wiele opcji formatowania i funkcji elementów członkowskich stosuje się do `ofstream` obiektów, a wszystkie funkcje klas podstawowych `ios` i `ostream` są uwzględniane.

Jeśli określisz nazwę pliku w konstruktorze, ten plik zostanie automatycznie otwarty podczas konstruowania obiektu. W przeciwnym razie można użyć `open` funkcji elementu członkowskiego po wywołaniu domyślnego konstruktora.

Podobnie jak w przypadku funkcji Run-Time `sprintf_s` `ostringstream` Klasa obsługuje dane wyjściowe do ciągów w pamięci. Aby utworzyć ciąg w pamięci przy użyciu formatowania strumienia we/wy, Skonstruuj obiekt klasy `ostringstream` .

## <a name="in-this-section"></a>W tej sekcji

[Konstruowanie obiektów strumienia wyjściowego](../standard-library/constructing-output-stream-objects.md)

[Korzystanie z operatorów wstawiania i formatu kontrolki](../standard-library/using-insertion-operators-and-controlling-format.md)

[Funkcje członkowskie strumienia pliku wyjściowego](../standard-library/output-file-stream-member-functions.md)

[Efekty buforowania](../standard-library/effects-of-buffering.md)

[Binarne pliki wyjściowe](../standard-library/binary-output-files.md)

[Przeciążanie operatora << dla własnych klas](../standard-library/overloading-the-output-operator-for-your-own-classes.md)

[Pisanie własnych operacji manipulowania bez argumentów](../standard-library/writing-your-own-manipulators-without-arguments.md)

## <a name="see-also"></a>Zobacz też

[ofstream](../standard-library/basic-ofstream-class.md)\
[ostringstream —](../standard-library/basic-ostringstream-class.md)\
[Programowanie iostream](../standard-library/iostream-programming.md)
