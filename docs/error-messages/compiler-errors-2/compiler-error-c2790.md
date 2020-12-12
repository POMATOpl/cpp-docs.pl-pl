---
description: 'Dowiedz się więcej o: błąd kompilatora C2790'
title: Błąd kompilatora C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: 0913b87f40e7f4ad2ecccb333e67bb0d76b4afde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297807"
---
# <a name="compiler-error-c2790"></a>Błąd kompilatora C2790

"Super": to słowo kluczowe może być używane tylko w treści funkcji składowej klasy

Ten komunikat o błędzie pojawia się, gdy użytkownik próbuje użyć słowa kluczowego [Super](../../cpp/super.md) poza kontekstem funkcji członkowskiej.

Poniższy przykład generuje C2790:

```cpp
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```
