---
description: Dowiedz się więcej na temat klasy slice_array
title: slice_array — Klasa
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 580a09d99b08bc563c64571247d74a980eb229f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153983"
---
# <a name="slice_array-class"></a>slice_array — Klasa

Wewnętrzny, pomocniczy szablon klasy, który obsługuje obiekty wycinków, dostarczając operacje między tablicami podzestawu zdefiniowanymi przez wycinek elementu valarray.

## <a name="syntax"></a>Składnia

```cpp
template <class Type>
class slice_array : public slice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;
    void operator=(const Type& x) const;
    void operator*=(const valarray<Type>& x) const;
    void operator/=(const valarray<Type>& x) const;
    void operator%=(const valarray<Type>& x) const;
    void operator+=(const valarray<Type>& x) const;
    void operator-=(const valarray<Type>& x) const;
    void operator^=(const valarray<Type>& x) const;
    void operator&=(const valarray<Type>& x) const;
    void operator|=(const valarray<Type>& x) const;
    void operator<<=(const valarray<Type>& x) const;
    void operator>>=(const valarray<Type>& x) const;
    // The rest is private or implementation defined
}
```

## <a name="remarks"></a>Uwagi

Klasa opisuje obiekt, który przechowuje odwołanie do obiektu klasy [valarray](../standard-library/valarray-class.md) **\<Type>** , wraz z obiektem [wycinka](../standard-library/slice-class.md)klasy, który opisuje sekwencję elementów do wybrania z obiektu **valarray \<Type>** .

Szablon klasy jest tworzony pośrednio przez pewne operacje valarray i nie może być używany bezpośrednio w programie. Wewnętrzny, pomocniczy szablon klasy, który jest używany przez Operator indeksu dolnego:

`slice_array`\< **Type**>`valarray` <  **Typ**:: `operator[]` ( `slice` ).

Obiekt można skonstruować `slice_array<Type>` tylko przez napisanie wyrażenia w formie [VA&#91;SL&#93;](../standard-library/valarray-class.md#op_at), dla wycinka `sl` valarray `va` . Funkcje składowe klasy slice_array następnie zachowują się jak odpowiadające im sygnatury funkcji zdefiniowane dla `valarray<Type>` , z tą różnicą, że dotyczy tylko sekwencji wybranych elementów. Sekwencja kontrolowana przez slice_array jest definiowana przez trzy parametry konstruktora wycinka, indeks pierwszego elementu w wycinkze, liczbę elementów i odległość między elementami. Slice_array wyciętych z valarray `va` zadeklarowanych przez **VA**[ `slice` (2, 5, 3)] wybiera elementy z indeksami 2, 5, 8, 11 i 14 z `va` . Indeksy muszą być prawidłowe, aby procedura była prawidłowa.

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [wycinka:: Slice](../standard-library/slice-class.md#slice) , aby zapoznać się z przykładem sposobu deklarowania i używania slice_array.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<valarray>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
