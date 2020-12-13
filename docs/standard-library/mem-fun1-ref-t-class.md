---
description: Dowiedz się więcej na temat klasy mem_fun1_ref_t
title: mem_fun1_ref_t — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_ref_t
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
ms.openlocfilehash: 6418812fb4c924c8d67ba4fc09d4595455ad73c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149126"
---
# <a name="mem_fun1_ref_t-class"></a>mem_fun1_ref_t — Klasa

Klasa adaptera, która umożliwia `non_const` funkcji składowej, która przyjmuje pojedynczy argument jako obiekt funkcji binarnej, gdy zostanie zainicjowany przy użyciu argumentu odwołania. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;
};
```

### <a name="parameters"></a>Parametry

*_Pm*\
Wskaźnik do funkcji składowej klasy `Type` , która ma zostać przekonwertowana na obiekt funkcji.

*lewym*\
Obiekt, na którym jest wywoływana funkcja członkowska *_Pm* .

*Kliknij*\
Argument, który jest udzielany *_Pm*.

## <a name="return-value"></a>Wartość zwracana

Dostosowywalna funkcja binarna.

## <a name="remarks"></a>Uwagi

Szablon klasy przechowuje kopię *_Pm*, która musi być wskaźnikiem do funkcji składowej klasy `Type` , w prywatnym obiekcie składowej. Definiuje swoją funkcję członkowską `operator()` jako zwracaną (**Left**. \* `_Pm` ) (**prawo**).

## <a name="example"></a>Przykład

Konstruktor `mem_fun1_ref_t` nie jest zazwyczaj używany bezpośrednio; funkcja pomocnika `mem_fun_ref` służy do adaptacji funkcji Członkowskich. Zobacz [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) , aby zapoznać się z przykładem użycia adapterów funkcji składowych.
