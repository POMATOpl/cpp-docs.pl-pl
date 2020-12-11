---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4390'
title: Ostrzeżenie kompilatora (poziom 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8067d4beae44e098085122968a227f6ff8bc8b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160444"
---
# <a name="compiler-warning-level-3-c4390"></a>Ostrzeżenie kompilatora (poziom 3) C4390

";": znaleziono pustą instrukcję sterowaną; Czy to jest zamiar?

Znaleziono średnik po instrukcji sterującej, która nie zawiera żadnych instrukcji.

W przypadku uzyskania C4390 z powodu makra należy użyć dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) , aby wyłączyć C4390 w module zawierającym makro.

Poniższy przykład generuje C4390:

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
