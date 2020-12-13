---
description: 'Dowiedz się więcej o: błąd kompilatora C3740'
title: Błąd kompilatora C3740
ms.date: 11/04/2016
f1_keywords:
- C3740
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
ms.openlocfilehash: ad2a883de165666127014b58ff32ae57b3c2e7b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340271"
---
# <a name="compiler-error-c3740"></a>Błąd kompilatora C3740

szablony nie mogą być źródłem ani odbierać zdarzeń

Klasa lub struktura z szablonem nie może zawierać [zdarzeń](../../cpp/event-handling.md).

Poniższy przykład generuje C3740:

```cpp
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```
