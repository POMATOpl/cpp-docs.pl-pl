---
description: Dowiedz się więcej na temat klasy pointer_to_binary_function
title: pointer_to_binary_function — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 5cdecc297ff5c55c9b6c57b5b6ab029636f3958c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340713"
---
# <a name="pointer_to_binary_function-class"></a>pointer_to_binary_function — Klasa

Konwertuje wskaźnik funkcji binarnej na dostosowywalną funkcję binarną. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Parametry

*pfunc*\
Funkcja binarna do przekonwertowania.

*lewym*\
Lewy obiekt, na którym jest wywoływana *\* pFunc* .

*Kliknij*\
Prawidłowy obiekt, w którym jest wywoływana *\* pFunc* .

## <a name="return-value"></a>Wartość zwracana

Szablon klasy przechowuje kopię `pfunc` . Definiuje swoją funkcję członkowską `operator()` jako zwracaną `(* pfunc)(Left, right)` .

## <a name="remarks"></a>Uwagi

Wskaźnik funkcji binarnej jest obiektem funkcji i może być przesłany do dowolnego algorytmu standardowej biblioteki języka C++, który oczekuje funkcji binarnej jako parametru, ale nie można go dostosować. Aby można było użyć go z adapterem, takim jak powiązanie z nim wartości lub użycie jej z negacją, musi być dostarczone z zagnieżdżonymi typami, `first_argument_type` `second_argument_type` i, `result_type` Aby umożliwić takie dostosowanie. Konwersja przez `pointer_to_binary_function` umożliwia adapterom funkcji współdziałanie ze wskaźnikami funkcji binarnych.

## <a name="example"></a>Przykład

Konstruktor `pointer_to_binary_function` jest rzadko używany bezpośrednio. Zobacz [ptr_fun](../standard-library/functional-functions.md#ptr_fun) funkcji pomocnika, aby zapoznać się z przykładem sposobu deklarowania i używania `pointer_to_binary_function` predykatu adaptera.
