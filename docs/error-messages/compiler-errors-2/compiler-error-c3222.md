---
description: 'Dowiedz się więcej o: błąd kompilatora C3222'
title: Błąd kompilatora C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 77883b6bd9be034fff2a0bcf3babdb1489c9a937
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267719"
---
# <a name="compiler-error-c3222"></a>Błąd kompilatora C3222

"parameter": nie można zadeklarować domyślnych argumentów dla funkcji składowych typu zarządzanego lub generycznego lub funkcji ogólnych

Deklarowanie parametru metody z domyślnym argumentem nie jest dozwolone. Przeciążona forma metody to jeden ze sposobów obejścia tego problemu. Oznacza to, że należy zdefiniować metodę o tej samej nazwie bez parametrów, a następnie zainicjować zmienną w treści metody.

Poniższy przykład generuje C3222:

```cpp
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
