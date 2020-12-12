---
description: Dowiedz się więcej na temat klasy bad_weak_ptr
title: bad_weak_ptr — Klasa
ms.date: 11/04/2016
f1_keywords:
- memory/std::bad_weak_ptr
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
ms.openlocfilehash: db74ed31ff92f7665e8ecde5fc4700bcdf1a7fc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312920"
---
# <a name="bad_weak_ptr-class"></a>bad_weak_ptr — Klasa

Zgłasza zły wyjątek weak_ptr.

## <a name="syntax"></a>Składnia

```cpp
class bad_weak_ptr : public std::exception
{
    bad_weak_ptr();
    const char *what() throw();
};
```

## <a name="remarks"></a>Uwagi

Klasa opisuje wyjątek, który może zostać wygenerowany z konstruktora [klasy shared_ptr](../standard-library/shared-ptr-class.md) , który przyjmuje argument typu [klasy weak_ptr](../standard-library/weak-ptr-class.md). Funkcja członkowska `what` zwraca wartość `"bad_weak_ptr"` .

## <a name="example"></a>Przykład

```cpp
// std__memory__bad_weak_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```

```Output
bad weak pointer
```

## <a name="see-also"></a>Zobacz także

[Klasa weak_ptr](../standard-library/weak-ptr-class.md)
