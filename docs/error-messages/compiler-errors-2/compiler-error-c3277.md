---
description: 'Dowiedz się więcej o: błąd kompilatora C3277'
title: Błąd kompilatora C3277
ms.date: 11/04/2016
f1_keywords:
- C3277
helpviewer_keywords:
- C3277
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
ms.openlocfilehash: ca04074dd077c63355f7da9a6a5feabcc0d03fac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228992"
---
# <a name="compiler-error-c3277"></a>Błąd kompilatora C3277

nie można zdefiniować niezarządzanego wyliczenia "enum" wewnątrz zarządzanego typu "

Wyliczenie zostało nieprawidłowo zdefiniowane wewnątrz typu zarządzanego.

Poniższy przykład generuje C3277:

```cpp
// C3277a.cpp
// compile with: /clr
ref class A
{
   enum E {e1,e2};   // C3277
   // try the following line instead
   // enum class E {e1,e2};
};

int main()
{
}
```
