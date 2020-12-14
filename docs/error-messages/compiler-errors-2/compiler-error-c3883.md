---
description: 'Dowiedz się więcej o: błąd kompilatora C3883'
title: Błąd kompilatora C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 216cfdc6385f12ff565eca581068ac5625a09044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274427"
---
# <a name="compiler-error-c3883"></a>Błąd kompilatora C3883

"var": statyczna składowa danych initonly musi być zainicjowana

Zmienna oznaczona przy użyciu [initonly](../../dotnet/initonly-cpp-cli.md) nie została poprawnie zainicjowana.

Poniższy przykład generuje C3883:

```cpp
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

Poniższy przykład demonstruje możliwe rozwiązanie:

```cpp
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

Poniższy przykład pokazuje, jak zainicjować w konstruktorze statycznym:

```cpp
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```
