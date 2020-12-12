---
description: 'Dowiedz się więcej o: błąd kompilatora C3156'
title: Błąd kompilatora C3156
ms.date: 11/04/2016
f1_keywords:
- C3156
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
ms.openlocfilehash: 265e887a7d075267e7a46d47d6bae9621bd83656
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174146"
---
# <a name="compiler-error-c3156"></a>Błąd kompilatora C3156

"Class": nie można posiadać lokalnej definicji typu zarządzanego lub WinRT

Funkcja nie może zawierać definicji ani deklaracji z klasy zarządzanej lub WinRT, struktury lub interfejsu.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3156.

```cpp
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
