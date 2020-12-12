---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4365'
title: Ostrzeżenie kompilatora (poziom 4) C4365
ms.date: 11/04/2016
f1_keywords:
- C4365
helpviewer_keywords:
- C4365
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
ms.openlocfilehash: d7316e6b32bd90b95f5f9277a565455733185d72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330611"
---
# <a name="compiler-warning-level-4-c4365"></a>Ostrzeżenie kompilatora (poziom 4) C4365

"Action": konwersja z "type_1" na "type_2", niezgodność ze znakiem/bez znaku

Na przykład próbowano skonwertować wartość bez znaku na wartość ze znakiem.

C4365 jest domyślnie wyłączona.  Aby uzyskać więcej informacji, zobacz [ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4365.

```cpp
// C4365.cpp
// compile with: /W4
#pragma warning(default:4365)

int f(int) { return 0; }
void Test(size_t i) {}

int main() {
   unsigned int n = 10;
   int o = 10;
   n++;
   f(n);   // C4365
   f(o);   // OK

   Test( -19 );   // C4365
}
```
