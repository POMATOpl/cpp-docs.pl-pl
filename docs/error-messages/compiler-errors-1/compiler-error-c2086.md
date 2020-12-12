---
description: 'Dowiedz się więcej o: błąd kompilatora C2086'
title: Błąd kompilatora C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: b98b4ed3896b11d8df434935c1b539f76640f24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252080"
---
# <a name="compiler-error-c2086"></a>Błąd kompilatora C2086

"Identyfikator": zmiana definicji

Identyfikator jest zdefiniowany więcej niż raz lub kolejna deklaracja różni się od poprzedniej.

C2086 może być również wynikiem tworzenia przyrostowego dla przywoływanego zestawu języka C#. Skompiluj zestaw C#, aby rozwiązać ten problem.

Poniższy przykład generuje C2086:

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
