---
description: 'Dowiedz się więcej o: błąd kompilatora C3176'
title: Błąd kompilatora C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: 8dda09ccbe6faa80d77f43c38b2c94427956cc3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242044"
---
# <a name="compiler-error-c3176"></a>Błąd kompilatora C3176

"Type": nie można zadeklarować lokalnego typu wartościowego

Klasa może być zadeklarowana jako typ wartości tylko w zakresie globalnym.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3176.

```cpp
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```
