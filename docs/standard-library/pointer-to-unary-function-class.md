---
description: Dowiedz się więcej na temat klasy pointer_to_unary_function
title: pointer_to_unary_function — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 45a927add90915bcbd8791eeba5561027b7e9217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340700"
---
# <a name="pointer_to_unary_function-class"></a>pointer_to_unary_function — Klasa

Konwertuje wskaźnik jednoargumentowy funkcji na dostosowywalną funkcję jednoargumentową. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Parametry

*pfunc*\
Funkcja binarna do przekonwertowania.

*lewym*\
Obiekt, na którym jest wywoływana *\* pFunc* .

## <a name="return-value"></a>Wartość zwracana

Szablon klasy przechowuje kopię `pfunc` . Definiuje swoją funkcję członkowską `operator()` jako zwracaną ( \* **pFunc**) (_ *Left*).

## <a name="remarks"></a>Uwagi

Jednoargumentowy wskaźnik funkcji jest obiektem funkcji i może być przesłany do dowolnego algorytmu standardowej biblioteki języka C++, który oczekuje jednoargumentowej funkcji jako parametru, ale nie można go dostosować. Aby można było użyć go z adapterem, takim jak powiązanie z nim wartości lub użycie jej z negacją, musi być dostarczana z typami zagnieżdżonymi, co umożliwia `argument_type` `result_type` takie dostosowanie. Konwersja przez `pointer_to_unary_function` umożliwia adapterom funkcji współdziałanie ze wskaźnikami funkcji binarnych.

## <a name="example"></a>Przykład

Konstruktor `pointer_to_unary_function` jest rzadko używany bezpośrednio. Zobacz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) funkcji pomocnika, aby zapoznać się z przykładem sposobu deklarowania i używania `pointer_to_unary_function` predykatu adaptera.
