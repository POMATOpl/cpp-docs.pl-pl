---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4232'
title: Ostrzeżenie kompilatora (poziom 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: 272fdcbc856ef5e86a8ff043b5aeab98a36413a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291418"
---
# <a name="compiler-warning-level-4-c4232"></a>Ostrzeżenie kompilatora (poziom 4) C4232

użyto niestandardowego rozszerzenia: "Identyfikator": adres elementu dllimport "dllimport" nie jest statyczny, tożsamość nie jest gwarantowana

W obszarze rozszerzenia Microsoft (/ze) można nadać wartości niestatycznej jako adres funkcji zadeklarowanej za pomocą **`dllimport`** modyfikatora. W obszarze zgodność ze standardem ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)) powoduje to wystąpienie błędu.

Poniższy przykład generuje C4232:

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
