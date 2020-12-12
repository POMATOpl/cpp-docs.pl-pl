---
description: 'Dowiedz się więcej o: błąd kompilatora C2719'
title: Błąd kompilatora C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 61e01107d5681c4bab39b06b00293ecdbeb9fc9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320725"
---
# <a name="compiler-error-c2719"></a>Błąd kompilatora C2719

"parameter": formalny parametr z __declspec (align ("#")) nie będzie wyrównany

Modyfikator [align](../../cpp/align-cpp.md) **`__declspec`** nie jest dozwolony w przypadku parametrów funkcji. Wyrównanie parametru funkcji jest kontrolowane przez użytą konwencję wywoływania. Aby uzyskać więcej informacji, zobacz [konwencje wywoływania](../../cpp/calling-conventions.md).

Poniższy przykład generuje C2719 i pokazuje, jak to naprawić:

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
