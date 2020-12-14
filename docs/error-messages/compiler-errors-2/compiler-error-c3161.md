---
description: 'Dowiedz się więcej o: błąd kompilatora C3161'
title: Błąd kompilatora C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 4e45d64e1c1f318a126122148c2dd8e3ddb9c5af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203968"
---
# <a name="compiler-error-c3161"></a>Błąd kompilatora C3161

"Interface": zagnieżdżanie klasy, struktury, Unii lub interfejsu w interfejsie jest niedozwolone; Zagnieżdżanie interfejsu w klasie, strukturze lub Unii jest niedozwolone

[__Interface](../../cpp/interface.md) może występować tylko w zakresie globalnym lub w przestrzeni nazw. Klasa, struktura lub Unia nie mogą występować w interfejsie.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3161.

```cpp
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```
