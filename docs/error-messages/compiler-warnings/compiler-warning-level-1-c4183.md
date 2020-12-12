---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4183'
title: Ostrzeżenie kompilatora (poziom 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 1e9753637d0ee52ef40ce875e4e2d66fbdaab9db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266679"
---
# <a name="compiler-warning-level-1-c4183"></a>Ostrzeżenie kompilatora (poziom 1) C4183

"Identyfikator": Brak typu zwracanego; przyjęto, że jest funkcją członkowską zwracającą wartość "int"

Wbudowana definicja funkcji składowej w klasie lub strukturze nie ma zwracanego typu. Przyjęto, że ta funkcja członkowska ma domyślny zwracany typ **`int`** .

Poniższy przykład generuje C4183:

```cpp
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```
