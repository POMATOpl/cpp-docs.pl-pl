---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4634'
title: Ostrzeżenie kompilatora (poziom 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: 87144f1a3c95f46159b07dc776707da06a56ff21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134130"
---
# <a name="compiler-warning-level-4-c4634"></a>Ostrzeżenie kompilatora (poziom 4) C4634

Komentarz dokumentu XML: nie można zastosować: Przyczyna

Tagi dokumentacji XML nie mogą być stosowane do wszystkich konstrukcji języka C++.  Na przykład nie można dodać komentarza do dokumentacji do przestrzeni nazw lub szablonu.

Aby uzyskać więcej informacji, zobacz [dokumentację XML](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C4634.

```cpp
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

Poniższy przykład generuje C4634.

```cpp
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```
