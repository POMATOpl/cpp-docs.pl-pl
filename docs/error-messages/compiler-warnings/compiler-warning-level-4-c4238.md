---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4238'
title: Ostrzeżenie kompilatora (poziom 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 8999d9ebeb4583256360f6223d4bf51a842fcb01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334873"
---
# <a name="compiler-warning-level-4-c4238"></a>Ostrzeżenie kompilatora (poziom 4) C4238

użyto niestandardowego rozszerzenia: Klasa rvalue użyta jako lvalue

W celu zapewnienia zgodności z poprzednimi wersjami Visual C++ rozszerzenia Microsoft (**/ze**) umożliwiają użycie typu klasy jako rvalue w kontekście, który niejawnie lub jawnie pobiera swój adres. W niektórych przypadkach, takich jak Poniższy przykład, może to być niebezpieczne.

## <a name="example"></a>Przykład

```cpp
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

To użycie powoduje błąd w obszarze zgodność ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).
