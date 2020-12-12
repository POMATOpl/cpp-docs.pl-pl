---
description: 'Dowiedz się więcej o: błąd kompilatora C2785'
title: Błąd kompilatora C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: f40b652e30b30f0ef17426b547337352181383e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297905"
---
# <a name="compiler-error-c2785"></a>Błąd kompilatora C2785

"declaration1" i "declaration2" mają różne typy zwracane

Typ zwracany specjalizacji szablonu funkcji różni się od typu zwracanego podstawowego szablonu funkcji.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź wszystkie specjalizacje szablonu funkcji pod kątem spójności.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2785:

```cpp
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```
