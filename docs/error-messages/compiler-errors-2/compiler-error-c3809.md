---
description: 'Dowiedz się więcej o: błąd kompilatora C3809'
title: Błąd kompilatora C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 62e7ff06e6ed5bf34861fdbae3f823e19ad5aad4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328211"
---
# <a name="compiler-error-c3809"></a>Błąd kompilatora C3809

"Class": typ zarządzany lub WinRT nie może mieć żadnych zaprzyjaźnionych funkcji/klas/interfejsów

Typy zarządzane i typy środowisko wykonawcze systemu Windows nie pozwalają na korzystanie z znajomych. Aby naprawić ten błąd, nie deklaruj znajomych w typach zarządzanych lub środowisko wykonawcze systemu Windows.

Poniższy przykład generuje C3809:

```cpp
// C3809a.cpp
// compile with: /clr
ref class A {};

ref class B
{
public:
   friend ref class A;   // C3809
};

int main()
{
}
```
