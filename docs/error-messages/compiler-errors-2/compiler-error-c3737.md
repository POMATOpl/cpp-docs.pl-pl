---
description: 'Dowiedz się więcej o: błąd kompilatora C3737'
title: Błąd kompilatora C3737
ms.date: 11/04/2016
f1_keywords:
- C3737
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
ms.openlocfilehash: 0b7c604f49c710334eb9ddfafa253df90c72103c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244982"
---
# <a name="compiler-error-c3737"></a>Błąd kompilatora C3737

"delegat": delegat może nie mieć jawnej konwencji wywoływania

Nie można określić [konwencji wywoływania](../../cpp/calling-conventions.md) dla elementu **`delegate`** .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3737:

```cpp
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
