---
description: 'Dowiedz się więcej o: błąd kompilatora C3909'
title: Błąd kompilatora C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: a85e0201e192caae1e4f170a12544177cbb2d7f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144160"
---
# <a name="compiler-error-c3909"></a>Błąd kompilatora C3909

aWinRT lub Deklaracja zdarzenia zarządzanego musi następować w typie WinRT lub zarządzanym

Zdarzenie środowisko wykonawcze systemu Windows lub zdarzenie zarządzane zostało zadeklarowane w typie natywnym. Aby naprawić ten błąd, zadeklaruj zdarzenia w typach środowisko wykonawcze systemu Windows lub typach zarządzanych.

Aby uzyskać więcej informacji, zobacz [zdarzenie](../../extensions/event-cpp-component-extensions.md).

Poniższy przykład generuje C3909 i pokazuje, jak to naprawić:

```cpp
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
