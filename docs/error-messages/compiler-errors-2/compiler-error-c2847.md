---
description: 'Dowiedz się więcej o: błąd kompilatora C2847'
title: Błąd kompilatora C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: fc9b7a75d662778bc532bb35e4520fb5627c9f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260218"
---
# <a name="compiler-error-c2847"></a>Błąd kompilatora C2847

nie można zastosować operatora sizeof do typu zarządzanego lub WinRT "Class"

Operator [sizeof](../../cpp/sizeof-operator.md) Pobiera wartość obiektu w czasie kompilacji. Rozmiar klasy zarządzanej lub WinRT, interfejs lub typ wartości jest dynamiczny i dlatego nie może być znany w czasie kompilacji.

Na przykład poniższy przykład generuje C2847:

```cpp
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
