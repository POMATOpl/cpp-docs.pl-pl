---
description: 'Dowiedz się więcej o: błąd kompilatora C2825'
title: Błąd kompilatora C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: fa72f915a77ec26e6da402ae8ff87ee380f1838c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194582"
---
# <a name="compiler-error-c2825"></a>Błąd kompilatora C2825

var: musi być klasą lub przestrzenią nazw, gdy następuje po niej znak "::"

Podjęto nieudaną próbę utworzenia nazwy kwalifikowanej.

Na przykład upewnij się, że kod nie zawiera deklaracji funkcji, której nazwa funkcji rozpoczyna się od::.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2825:

```cpp
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```
