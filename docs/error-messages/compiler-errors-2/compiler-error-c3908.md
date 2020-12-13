---
description: 'Dowiedz się więcej o: błąd kompilatora C3908'
title: Błąd kompilatora C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 67258f9f5946d180af9a270b931f88f263238856
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144173"
---
# <a name="compiler-error-c3908"></a>Błąd kompilatora C3908

poziom dostępu mniej restrykcyjny niż "konstrukcja"

Metoda dostępu do właściwości (get lub Set) nie może mieć mniej restrykcyjnego dostępu niż określony we właściwości.  Podobnie, w przypadku metod metody dostępu do zdarzeń.

Aby uzyskać więcej informacji, zobacz [Właściwości](../../extensions/property-cpp-component-extensions.md) i [zdarzenia](../../extensions/event-cpp-component-extensions.md).

Poniższy przykład generuje C3908:

```cpp
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```
