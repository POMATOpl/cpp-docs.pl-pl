---
description: 'Dowiedz się więcej na temat: initonly (C++/CLI)'
title: initonly (C++/CLI)
ms.date: 11/04/2016
f1_keywords:
- initonly_cpp
- initonly
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
ms.openlocfilehash: 186f8f18a3c5ff7ee963b19801a23e9dd82e50a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316651"
---
# <a name="initonly-ccli"></a>initonly (C++/CLI)

**initonly** to kontekstowe słowo kluczowe, które wskazuje, że przypisanie zmiennej może wystąpić tylko jako część deklaracji lub w konstruktorze statycznym w tej samej klasie.

Poniższy przykład przedstawia sposób użycia `initionly` :

```cpp
// mcpp_initonly.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst1;

   initonly
   static int staticConst2 = 0;

   static Y1() {
      staticConst1 = 0;
   }
};
```

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../extensions/classes-and-structs-cpp-component-extensions.md)
