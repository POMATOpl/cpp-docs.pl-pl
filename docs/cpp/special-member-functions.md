---
description: 'Dowiedz się więcej o: specjalnych funkcji składowych'
title: Specjalne funkcje składowe
ms.date: 12/06/2016
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
ms.openlocfilehash: ab3b5be3c7006729e135cc273e9b7856adbd3252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113834"
---
# <a name="special-member-functions"></a>Specjalne funkcje składowe

*Specjalne funkcje członkowskie* to funkcje członkowskie klasy (lub struktury), które w niektórych przypadkach automatycznie generują kompilator. Te funkcje są [konstruktorem domyślnym](constructors-cpp.md#default_constructors), [destruktorem](destructors-cpp.md), [konstruktorem kopiującym i operatorem przypisania kopiowania](copy-constructors-and-copy-assignment-operators-cpp.md), a [konstruktorem przenoszenia i operatorem przypisania przenoszenia](move-constructors-and-move-assignment-operators-cpp.md). Jeśli Klasa nie definiuje co najmniej jednej specjalnej funkcji składowej, kompilator może niejawnie deklarować i zdefiniować funkcje, które są używane. Implementacje generowane przez kompilator są nazywane *domyślnymi* specjalnymi funkcjami składowymi. Kompilator nie generuje funkcji, jeśli nie są one zbędne.

Można jawnie zadeklarować domyślną specjalną funkcję członkowską za pomocą słowa kluczowego **= default** . Powoduje to, że kompilator definiuje funkcję tylko w razie potrzeby, w taki sam sposób, jak w przypadku, gdy funkcja nie została zadeklarowana w ogóle.

W niektórych przypadkach kompilator może generować *usunięte* specjalne funkcje członkowskie, które nie są zdefiniowane i w związku z tym nie są wywoływane. Może się tak zdarzyć w przypadkach, gdy wywołanie określonej specjalnej funkcji składowej w klasie nie ma sensu, pod kątem innych właściwości klasy. Aby jawnie zapobiec automatycznemu generowaniu specjalnej funkcji składowej, można zadeklarować ją jako usuniętą za pomocą słowa kluczowego **= delete** .

Kompilator generuje *Konstruktor domyślny*, Konstruktor, który nie przyjmuje argumentów, tylko wtedy, gdy nie został zadeklarowany żaden inny Konstruktor. Jeśli zadeklarowano tylko konstruktora, który pobiera parametry, kod, który próbuje wywołać Konstruktor domyślny powoduje, że kompilator tworzy komunikat o błędzie. Konstruktor domyślny wygenerowany przez kompilator wykonuje prostą [domyślną inicjalizację](initializers.md#default_initialization) obiektu. Domyślna Inicjalizacja pozostawia wszystkie zmienne Członkowskie w nieokreślonym stanie.

Domyślny destruktor wykonuje zniszczenie obiektu przez element. Jest ona wirtualna tylko wtedy, gdy destruktor klasy bazowej jest wirtualny.

Domyślne kopiowanie i przenoszenie oraz operacje tworzenia i przypisywania są wykonywane w ramach kopiowania wzorca bitowego lub przenoszenia niestatycznych elementów członkowskich danych. Operacje przenoszenia są generowane tylko wtedy, gdy nie są zadeklarowane żadne operacje wykonywania destruktora lub przenoszenia lub kopiowania. Domyślny konstruktor kopiujący jest generowany tylko wtedy, gdy żaden Konstruktor kopiowania nie jest zadeklarowany. Jest on niejawnie usuwany w przypadku zadeklarowania operacji przenoszenia. Domyślny operator przypisania kopii jest generowany tylko wtedy, gdy żaden operator przypisania kopiowania nie został jawnie zadeklarowany. Jest on niejawnie usuwany w przypadku zadeklarowania operacji przenoszenia.

## <a name="see-also"></a>Zobacz też

[Dokumentacja języka C++](cpp-language-reference.md)
