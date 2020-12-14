---
description: 'Dowiedz się więcej o: błąd kompilatora C2599'
title: Błąd kompilatora C2599
ms.date: 11/04/2016
f1_keywords:
- C2599
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
ms.openlocfilehash: e1365ee2570d4af524f7e4dbd36a411916efb9c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312049"
---
# <a name="compiler-error-c2599"></a>Błąd kompilatora C2599

"enum": Deklaracja przekazująca typu enum jest niedozwolona

Kompilator nie obsługuje już deklaracji do przesyłania dalej zarządzanej.

Deklaracja przekazująca typu Enum nie jest dozwolona w obszarze [/za](../../build/reference/za-ze-disable-language-extensions.md).

Poniższy przykład generuje C2599:

```cpp
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```
