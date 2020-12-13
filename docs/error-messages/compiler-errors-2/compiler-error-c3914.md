---
description: 'Dowiedz się więcej o: błąd kompilatora C3914'
title: Błąd kompilatora C3914
ms.date: 11/04/2016
f1_keywords:
- C3914
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
ms.openlocfilehash: 7f5291e09d7f3f794d7d1bec90f0a753d7dfe38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143965"
---
# <a name="compiler-error-c3914"></a>Błąd kompilatora C3914

domyślna właściwość nie może być statyczna

Właściwość domyślna została zadeklarowana nieprawidłowo.  Aby uzyskać więcej informacji, zobacz [jak: korzystanie z właściwości w języku C++/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3914 i pokazuje, jak rozwiązać ten problem.

```cpp
// C3914.cpp
// compile with: /clr /c
ref struct X {
   static property int default[int] {   // C3914
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```
