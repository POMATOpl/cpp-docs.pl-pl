---
description: Dowiedz się więcej na temat klasy is_placeholder
title: is_placeholder — Klasa
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 84d73da6ffe2446a8448b0ff5f30604d259493b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230656"
---
# <a name="is_placeholder-class"></a>is_placeholder — Klasa

Testuje, czy typ jest symbolem zastępczym.

## <a name="syntax"></a>Składnia

Struktura is_placeholder {statyczna stała wartość int;};

## <a name="remarks"></a>Uwagi

Stała wartość `value` jest równa 0, jeśli typ `Ty` nie jest symbolem zastępczym; w przeciwnym razie jego wartość to pozycja argumentu wywołania funkcji, z którym jest powiązany. Służy do określania wartości `N` n-ty symbolu zastępczego `_N` .

## <a name="example"></a>Przykład

```cpp
// std__functional__is_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

using namespace std::placeholders;

template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}
```

```Output
0
3
```
