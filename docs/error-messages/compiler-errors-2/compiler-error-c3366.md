---
description: 'Dowiedz się więcej o: błąd kompilatora C3366'
title: Błąd kompilatora C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 922fa882efcaead4df87bbfc104394e12b797955
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150842"
---
# <a name="compiler-error-c3366"></a>Błąd kompilatora C3366

"zmienna": statyczne składowe danych zarządzane lub WinRTtypes muszą być zdefiniowane w ramach definicji klasy

Podjęto próbę odwołania się do statycznego elementu członkowskiego klasy WinRT lub lub interfejsu platformy .NET poza definicją tej klasy lub interfejsu.

Kompilator musi znać pełną definicję klasy (do emisji metadanych po jednym przebiegu) i wymaga zainicjowania statycznych elementów członkowskich danych w klasie.

Na przykład poniższy przykład generuje C3366 i pokazuje, jak go naprawić:

```cpp
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
