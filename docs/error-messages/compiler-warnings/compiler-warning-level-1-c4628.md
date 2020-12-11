---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4628'
title: Ostrzeżenie kompilatora (poziom 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: b5dd017afb5b8bb0d882700cb047643d6d118685
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112378"
---
# <a name="compiler-warning-level-1-c4628"></a>Ostrzeżenie kompilatora (poziom 1) C4628

dwuznaki nieobsługiwane z -Ze. Sekwencja znaków 'dwuznak' nie jest interpretowana jako alternatywny token dla 'char'

Wykresy nie są obsługiwane w obszarze [/ze](../../build/reference/za-ze-disable-language-extensions.md). Po tym ostrzeżeniu zostanie zwrócony błąd.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4628:

```cpp
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```
