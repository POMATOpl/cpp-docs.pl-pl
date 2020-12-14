---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4130'
title: Ostrzeżenie kompilatora (poziom 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: e7096f471405b0b22bcb0a825dd9ccd0de4e3510
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261817"
---
# <a name="compiler-warning-level-4-c4130"></a>Ostrzeżenie kompilatora (poziom 4) C4130

"operator": operacja logiczna na adresie ciągu stałej

Użycie operatora z adresem literału ciągu powoduje nieoczekiwany kod.

Poniższy przykład generuje C4130:

```cpp
// C4130.cpp
// compile with: /W4
int main()
{
   char *pc;
   pc = "Hello";
   if (pc == "Hello") // C4130
   {
   }
}
```

**`if`** Instrukcja porównuje wartość przechowywaną w wskaźniku `pc` na adres ciągu "Hello", który jest przypisywany oddzielnie za każdym razem, gdy ciąg występuje w kodzie. **`if`** Instrukcja nie porównuje ciągu wskazywanego przez `pc` ciąg "Hello".

Aby porównać ciągi, użyj `strcmp` funkcji.
