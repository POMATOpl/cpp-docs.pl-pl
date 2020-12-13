---
description: Dowiedz się więcej na temat klasy mem_fun1_t
title: mem_fun1_t — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: a0fd8f060757c7dc5004ad753fd168c9e644e1b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149087"
---
# <a name="mem_fun1_t-class"></a>mem_fun1_t — Klasa

Klasa adaptera, która umożliwia `non_const` funkcji składowej, która przyjmuje pojedynczy argument jako obiekt funkcji binarnej, gdy zostanie zainicjowany przy użyciu argumentu wskaźnika. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;
};
```

### <a name="parameters"></a>Parametry

*_Pm*\
Wskaźnik do funkcji składowej klasy `Type` , która ma zostać przekonwertowana na obiekt funkcji.

*_Pleft*\
Obiekt, na którym jest wywoływana funkcja członkowska *_Pm* .

*Kliknij*\
Argument, który jest udzielany *_Pm*.

## <a name="return-value"></a>Wartość zwracana

Dostosowywalna funkcja binarna.

## <a name="remarks"></a>Uwagi

Szablon klasy przechowuje kopię *_Pm*, która musi być wskaźnikiem do funkcji składowej klasy `Type` , w prywatnym obiekcie składowej. Definiuje jej funkcję członkowską `operator()` jako zwracającą (**_Pleft** -> \* `_Pm` ) (**po prawej**).

## <a name="example"></a>Przykład

Konstruktor `mem_fun1_t` nie jest zazwyczaj używany bezpośrednio; funkcja pomocnika `mem_fun` służy do adaptacji funkcji Członkowskich. Zobacz [mem_fun](../standard-library/functional-functions.md#mem_fun) , aby zapoznać się z przykładem użycia adapterów funkcji składowych.
