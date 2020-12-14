---
description: 'Dowiedz się więcej o: błąd kompilatora C2844'
title: Błąd kompilatora C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 030d8526e7bfd85e7bcca1c115f1b5ce5d45c3aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260282"
---
# <a name="compiler-error-c2844"></a>Błąd kompilatora C2844

"member": nie może być składową interfejsu "Interface"

[Klasa interfejsu](../../extensions/interface-class-cpp-component-extensions.md) nie może zawierać elementu członkowskiego danych, chyba że jest również właściwością.

Coś innego niż właściwość lub funkcja członkowska jest niedozwolona w interfejsie. Ponadto konstruktory, destruktory i operatory są niedozwolone.

Poniższy przykład generuje C2844:

```cpp
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
