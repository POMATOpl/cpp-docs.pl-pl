---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4265'
title: Ostrzeżenie kompilatora (poziom 3) C4265
ms.date: 11/04/2016
f1_keywords:
- C4265
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
ms.openlocfilehash: f7ad04d59b9896ce91f4a135f205664885af8f68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344175"
---
# <a name="compiler-warning-level-3-c4265"></a>Ostrzeżenie kompilatora (poziom 3) C4265

"Class": Klasa ma funkcje wirtualne, ale destruktor nie jest wirtualny

Gdy Klasa ma funkcje wirtualne, ale destruktor niewirtualny, obiekty typu mogą nie zostać zniszczone prawidłowo, gdy Klasa jest niszczona przez wskaźnik klasy bazowej.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4265:

```cpp
// C4265.cpp
// compile with: /W3 /c
#pragma warning(default : 4265)
class B
{
public:
   virtual void vmf();

   ~B();
   // try the following line instead
   // virtual ~B();
};   // C4265

int main()
{
   B b;
}
```
