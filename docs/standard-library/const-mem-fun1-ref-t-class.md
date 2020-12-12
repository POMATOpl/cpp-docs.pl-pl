---
description: Dowiedz się więcej na temat klasy const_mem_fun1_ref_t
title: const_mem_fun1_ref_t — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: f2d8b96c3888e3b7b07b5cccef8ce58cdedb6732
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324948"
---
# <a name="const_mem_fun1_ref_t-class"></a>const_mem_fun1_ref_t — Klasa

Klasa adaptera, która umożliwia **`const`** funkcji składowej, która przyjmuje pojedynczy argument jako obiekt funkcji binarnej, gdy zostanie zainicjowany przy użyciu argumentu odwołania. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Result, class Type, class Arg>
    class const_mem_fun1_ref_t
        : public binary_function<Type, Arg, Result>
{
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
};
```

### <a name="parameters"></a>Parametry

*23:59:59*\
Wskaźnik do funkcji składowej klasy `Type` , która ma zostać przekonwertowana na obiekt funkcji.

*lewym*\
**`const`** Obiekt, na którym jest wywoływana funkcja członkowska *PM* .

*Kliknij*\
Argument, który jest przypisywany do *PM*.

## <a name="return-value"></a>Wartość zwracana

Dostosowywalna funkcja binarna.

## <a name="remarks"></a>Uwagi

Szablon klasy przechowuje kopię *PM*, która musi być wskaźnikiem do funkcji składowej klasy `Type` , w prywatnym obiekcie składowej. Definiuje swoją funkcję członkowską `operator()` jako zwracaną ( `left` . \* *PM*) ( `right` ) **`const`** .

## <a name="example"></a>Przykład

Konstruktor `const_mem_fun1_ref_t` nie jest zazwyczaj używany bezpośrednio; funkcja pomocnika `mem_fun_ref` służy do adaptacji funkcji Członkowskich. Zobacz [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) , aby zapoznać się z przykładami korzystania z adapterów funkcji składowych.
