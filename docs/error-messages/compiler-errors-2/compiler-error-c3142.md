---
description: 'Dowiedz się więcej o: błąd kompilatora C3142'
title: Błąd kompilatora C3142
ms.date: 11/04/2016
f1_keywords:
- C3142
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
ms.openlocfilehash: b03f6efbbf473493354742ef7654e5629b5e5fba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204046"
---
# <a name="compiler-error-c3142"></a>Błąd kompilatora C3142

"property_name": nie można przyjąć adresu właściwości

Adres właściwości nie jest dostępny dla dewelopera.

Poniższy przykład generuje C3142:

```cpp
// C3142_2.cpp
// compile with: /clr
using namespace System;
ref class CSize {
private:
   property int Size {
      int get();
   }
};

int main() {
    &CSize::Size; // C3142
}
```
