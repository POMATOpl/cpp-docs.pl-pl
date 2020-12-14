---
description: Dowiedz się więcej na temat klasy type_info
title: type_info — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 6be4d6774842ad015b34e771455026ca27e6539b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295318"
---
# <a name="type_info-class"></a>type_info — Klasa

Klasa **type_info** opisuje informacje o typie wygenerowane w ramach programu przez kompilator. Obiekty tej klasy skutecznie przechowują wskaźnik do nazwy typu. Klasa **type_info** przechowuje również zakodowaną wartość odpowiednią do porównywania dwóch typów dla równości lub kolejności sortowania. Reguły kodowania i sekwencja typów sortowania są nieokreślone i mogą się różnić między programami.

`<typeinfo>`Aby można było użyć klasy **type_info** , należy uwzględnić plik nagłówkowy. Interfejs klasy **type_info** :

```cpp
class type_info {
public:
    type_info(const type_info& rhs) = delete; // cannot be copied
    virtual ~type_info();
    size_t hash_code() const;
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    type_info& operator=(const type_info& rhs) = delete; // cannot be copied
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    size_t hash_code() const noexcept;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

Nie można utworzyć wystąpienia obiektów klasy **type_info** bezpośrednio, ponieważ Klasa ma tylko prywatny Konstruktor kopiujący. Jedynym sposobem konstruowania (tymczasowego) obiektu **type_info** jest użycie operatora [typeid](../cpp/typeid-operator.md) . Ponieważ operator przypisania jest również prywatny, nie można kopiować ani przypisywać obiektów klasy **type_info**.

`type_info::hash_code` definiuje funkcję mieszania **odpowiednią do mapowania wartości typuelement** na rozkład wartości indeksu.

Operatory `==` i `!=` mogą służyć do porównania pod kątem równości i nierówności z innymi obiektami **type_info** , odpowiednio.

Nie ma żadnego połączenia między określoną kolejnością typów i relacjami dziedziczenia. Użyj `type_info::before` funkcji elementu członkowskiego, aby określić kolejność sortowania typów. Nie ma żadnej gwarancji, która będzie zwracać ten `type_info::before` sam wynik w różnych programach lub nawet w różnych uruchomieniach tego samego programu. W ten sposób `type_info::before` jest podobny do operatora address-of `(&)` .

`type_info::name`Funkcja członkowska zwraca `const char*` ciąg zakończony znakiem null reprezentujący czytelną nazwę typu. Wskazywana pamięć jest buforowana i nigdy nie powinna być bezpośrednio dealokowana.

`type_info::raw_name`Funkcja członkowska zwraca `const char*` do ciągu, który jest zakończony znakiem null, reprezentujący nazwę dekoracyjną typu obiektu. Nazwa rzeczywiście jest przechowywana w formie urządzonej, aby zaoszczędzić miejsce. W związku z tym ta funkcja jest szybsza niż, `type_info::name` ponieważ nie musi undecorate nazwy. Ciąg zwracany przez `type_info::raw_name` funkcję jest przydatny w operacjach porównania, ale nie można go odczytać. Jeśli potrzebujesz ciągu do odczytu przez człowieka, `type_info::name` zamiast tego użyj funkcji.

Informacje o typie są generowane dla klas polimorficznych tylko wtedy, gdy określono opcję kompilatora [/gr (Włącz informacje o typie Run-Time)](../build/reference/gr-enable-run-time-type-information.md) .

## <a name="see-also"></a>Zobacz też

[Informacje o typach uzyskiwane w czasie rzeczywistym](../cpp/run-time-type-information.md)
