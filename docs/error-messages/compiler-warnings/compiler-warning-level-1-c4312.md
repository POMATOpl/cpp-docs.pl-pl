---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4312'
title: Ostrzeżenie kompilatora (poziom 1) C4312
ms.date: 11/04/2016
f1_keywords:
- C4312
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
ms.openlocfilehash: 52e165fd30a9171c1a08aa16f78cc1f298271b17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340076"
---
# <a name="compiler-warning-level-1-c4312"></a>Ostrzeżenie kompilatora (poziom 1) C4312

'operacja' : konwersja z 'typ1' na 'typ2' o większym rozmiarze

To ostrzeżenie wykrywa próbę przypisania wartości 32-bitowej do typu wskaźnika 64-bitowego, na przykład rzutowania 32 bitowego **`int`** lub **`long`** do wskaźnika 64-bitowego.

Może to być niebezpieczna konwersja nawet w przypadku wartości wskaźnika, które mieszczą się w 32 bitach, gdy występuje rozszerzenie podpisywania. Jeśli ujemna 32-bitowa liczba całkowita jest przypisana do typu wskaźnika 64-bitowego, rozszerzenie znaku powoduje, że wartość wskaźnika odwołuje się do adresu pamięci innego niż wartość całkowita.

To ostrzeżenie jest wydawane wyłącznie dla 64-bitowych kompilacji elementów docelowych. Aby uzyskać więcej informacji, zobacz [reguły dotyczące korzystania ze wskaźników](/windows/win32/WinProg64/rules-for-using-pointers).

Poniższy przykład kodu generuje C4312 podczas kompilowania dla elementów docelowych 64-bitowych:

```cpp
// C4312.cpp
// compile by using: cl /W1 /LD C4312.cpp
void* f(int i) {
   return (void*)i;   // C4312 for 64-bit targets
}

void* f2(__int64 i) {
   return (void*)i;   // OK
}
```
