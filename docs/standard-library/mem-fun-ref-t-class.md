---
description: Dowiedz się więcej na temat klasy mem_fun_ref_t
title: mem_fun_ref_t — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: e79d7f3b3271ff699f0dd2ad760753c2162d554a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149178"
---
# <a name="mem_fun_ref_t-class"></a>mem_fun_ref_t — Klasa

Klasa adaptera, która umożliwia `non_const` funkcji składowej, która nie przyjmuje argumentów do wywołania jednoargumentowego obiektu funkcyjnego, gdy jest inicjowany z argumentem odwołania. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;
};
```

### <a name="parameters"></a>Parametry

*_Pm*\
Wskaźnik do funkcji składowej klasy `Type` , która ma zostać przekonwertowana na obiekt funkcji.

*lewym*\
Obiekt, na którym jest wywoływana funkcja członkowska *_Pm* .

## <a name="return-value"></a>Wartość zwracana

Dostosowywalna funkcja Jednoargumentowa.

## <a name="remarks"></a>Uwagi

Szablon klasy przechowuje kopię *_Pm*, która musi być wskaźnikiem do funkcji składowej klasy `Type` , w prywatnym obiekcie składowej. Definiuje swoją funkcję członkowską `operator()` jako zwracaną (**Left**. * `_Pm` ) ().

## <a name="example"></a>Przykład

Konstruktor `mem_fun_ref_t` nie jest zazwyczaj używany bezpośrednio; funkcja pomocnika `mem_fun_ref` służy do adaptacji funkcji Członkowskich. Zobacz [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) , aby zapoznać się z przykładem użycia adapterów funkcji składowych.
