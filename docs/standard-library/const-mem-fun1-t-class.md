---
description: Dowiedz się więcej na temat klasy const_mem_fun1_t
title: const_mem_fun1_t — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 998826bbd78745913caf76ad6b152aac490956fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233659"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t — Klasa

Klasa adaptera, która umożliwia **`const`** funkcji składowej, która przyjmuje pojedynczy argument jako obiekt funkcji binarnej, gdy zostanie zainicjowany przy użyciu argumentu wskaźnika. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>Parametry

*member_ptr*\
Wskaźnik do funkcji składowej klasy `Type` , która ma zostać przekonwertowana na obiekt funkcji.

*lewym*\
**`const`** Obiekt, na którym jest wywoływana funkcja członkowska *member_ptr* .

*Kliknij*\
Argument, który jest udzielany *member_ptr*.

## <a name="return-value"></a>Wartość zwracana

Dostosowywalna funkcja binarna.

## <a name="remarks"></a>Uwagi

Szablon klasy przechowuje kopię *member_ptr*, która musi być wskaźnikiem do funkcji składowej klasy `Type` , w prywatnym obiekcie składowej. Definiuje swoją funkcję członkowską `operator()` jako zwracaną `(left->member_ptr)(right) const` .

## <a name="example"></a>Przykład

Konstruktor `const_mem_fun1_t` jest rzadko używany bezpośrednio. `mem_fn` służy do adaptacji funkcji Członkowskich. Zobacz [mem_fn](../standard-library/functional-functions.md#mem_fn) , aby zapoznać się z przykładem użycia adapterów funkcji składowych.
