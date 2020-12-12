---
description: 'Dowiedz się więcej o: błąd kompilatora C3252'
title: Błąd kompilatora C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: 59b5a0073d3dc8147b2e89d637fd98ba7339f6b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194309"
---
# <a name="compiler-error-c3252"></a>Błąd kompilatora C3252

"Metoda": nie można zmniejszyć dostępności metody wirtualnej w typie zarządzanym lub WinRT

Klasa implementująca metodę wirtualną z klasy bazowej lub dowolnej metody z interfejsu nie może zmniejszyć dostępu do tej metody.

Należy pamiętać, że wszystkie metody w interfejsie są publiczne.

Poniższy przykład generuje C3252 i pokazuje, jak to naprawić:

```cpp
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```
