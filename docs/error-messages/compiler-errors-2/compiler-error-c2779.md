---
title: Błąd kompilatora C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: cf2a59726e87f5cd2cdb82129db2677bf6a69d29
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220239"
---
# <a name="compiler-error-c2779"></a>Błąd kompilatora C2779

"Deklaracja": metody właściwości mogą być skojarzone tylko z niestatycznymi składowymi danych

**`property`** Rozszerzony atrybut jest niepoprawnie stosowany do statycznego elementu członkowskiego danych.

Poniższy przykład generuje C2779:

```cpp
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```
